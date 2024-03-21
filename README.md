
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino

NAME : VISHNU KM

DEPARTMENT : AI/ML

ROLL NOM : 212223240185

### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 

```
int enable=6;
int input1=3;
int input2=4;

void setup()
{
  pinMode(enable, OUTPUT);
    pinMode(input1, OUTPUT);
    pinMode(input2, OUTPUT);
   
}

void loop()
{
  analogWrite(enable,255);
  delay(1000);
  digitalWrite(input1, HIGH);
  digitalWrite(input2, LOW);
  delay(5000);
  digitalWrite(input1, LOW);
  digitalWrite(input2, HIGH);
  delay(5000);
}
```

### OUTPUT

![EXP 6 CIRCUIT](https://github.com/vishnukayyala/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151489368/fe77377c-559f-4338-821d-9ab3f621b4ad)
![EXP 6 CIRCUIT 2](https://github.com/vishnukayyala/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151489368/a1ad8f50-bfbe-4367-ad20-5e43d8f0d78c)

### GRAPH AND TABULATION 

![EXP 6 TABLE](https://github.com/vishnukayyala/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151489368/884d05e0-dd74-4b65-9866-87a5d54da393)
![EXP 6 GRAPH](https://github.com/vishnukayyala/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151489368/026634ff-a3c1-436b-a699-44bcd209ef88)


### RESULTS AND DISCUSSION 
TUS WE HAVE TO CONTROL THE  SPPED AND DIRECTION OF A DC MOTOR USING L293D DRIVER H BRIDGE
