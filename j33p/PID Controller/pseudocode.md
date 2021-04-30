# Notes for PID Controller

## Links/Sources

[Wiki-Where these notes come from](https://en.wikipedia.org/wiki/PID_controller)

[Medium Article - High Level/No Math/Easy read](https://medium.com/codezillas/pid-controllers-explained-without-maths-551faf251d4f)

## Variables

### KP = Tuning Parameter

    - Difference between Desired and Present Output

### KI = Integral Tuning Parameter

    - How long has there been a difference between setpoint and present system output?

### KD = Deriviative -OR- Final Tuning Parameter

    - Rate of change between setpoint and present system output

### SP = Setpoint -> Desired position

### PV = Process variable -> Sensed position

---

## Psuedocode

    - Non MIPS example

```

prev_error := 0
integral := 0

loop:
    error := setpoint - measured_value
    proprtional := error
    integral := integral + error * dt
    derivative := (error - prev_error) / dt
    output := kp * proportional + ki * integral + kd * derivative
    prev_error := error
    wait(dt)
    goto loop

```

    - MIPS first pass....have not checked

```mips

define prev_error 0
define integral 0

Main:
sub error setpoint measured_value
move proportional error
add integral integral error
mul integral * delta_time
sub error error prev_error
div derivative error delta_time
mul output kp proportional
add output output ki
mul output output integral
add output output kd
mul output output derivative
move prev_error error
wait delta_time
j Main

```
