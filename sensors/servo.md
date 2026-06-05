# Servo (angle control)

A **servo motor** rotates to a specific **angle** (typically 0°–180°) and holds it, which makes it
perfect for steering, levers, robot arms, and gauges. It is controlled by a PWM signal; SemiBlock
wraps that in a small `Servo` driver so you just give it an angle.

## How to wire it

A hobby servo has three wires:

| Servo wire | Connect to | Notes |
|------------|-----------|-------|
| Signal (orange/white) | a GPIO (default **GPIO 15**) | the PWM control line |
| Power (red) | `5V` | servos draw real current — use an external 5 V supply for larger ones |
| Ground (brown/black) | `GND` | shared ground with the board |

> **Tip:** for anything bigger than a micro 9 g servo, power it from a separate 5 V supply and
> connect the grounds together. Powering a servo from the board's 3.3 V can brown-out the ESP32.

## The blocks

- **`servo`** — create the servo object on a control pin.
- **`servoAngle`** — move the servo to an angle.

### Create the servo

With the default fields (variable `servo`, pin `15`) the block generates:

```python
servo=Servo(15)
```

The `from servo import Servo` line is added to the top of your program automatically when a servo
block is present.

### Set the angle

`servoAngle` (variable `servo`, angle `15`) generates a call to a helper:

```python
servo_Angle(servo, 15)
```

`servo_Angle(servo_object, angle)` moves the given servo to the requested angle in degrees
(commonly 0–180).

> **Note:** the *create* block uses `Servo(...)`, while the *angle* block calls the
> `servo_Angle(...)` helper — pass the same servo variable to both.

## Complete example — sweep between 0° and 180°

```python
servo=Servo(15)

while True:
    servo_Angle(servo, 0)
    sleep(1)
    servo_Angle(servo, 180)
    sleep(1)
```

The servo snaps to 0°, waits a second, swings to 180°, waits, and repeats — a basic back-and-forth
sweep.

## Next

Return to the [Sensors Overview](index.md), or continue to **Part V — Displays** with the
[Display Overview](../display/index.md).
