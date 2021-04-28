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

    - Will change to MIPS at a later date

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
