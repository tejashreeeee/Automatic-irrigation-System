 int water; //random variable 
void setup() {
  pinMode(3,OUTPUT); //output pin for relay board, this will sent signal to the relay
  pinMode(6,INPUT); //input pin coming from soil sensor
}

void loop() { 
  water = digitalRead(6);  // reading the coming signal from the soil sensor
  if(water == HIGH) // if water level is full then cut the relay 
  {
  digitalWrite(3,LOW); // low is to cut the relay
  }
  else
  {
  digitalWrite(3,HIGH); //high to continue proving signal and water supply
  }
  delay(400); 
}
[07/03, 10:28 am] tejashree: void loop()
{
  int sensor_data = analogRead(sensor_pin);
  Serial.print("Sensor_data:");
  Serial.print(sensor_data);
  Serial.print("\t | ");
  
  if(sensor_data > 950)
  {
    Serial.println("No moisture, Soil is dry");
  }
  else if(sensor_data >= 400 && sensor_data <= 950)
  {
    Serial.println("There is some moisture, Soil is medium");
  }
  else if(sensor_data < 400)
  {
    Serial.println("Soil is wet");
  }

  delay(100);
