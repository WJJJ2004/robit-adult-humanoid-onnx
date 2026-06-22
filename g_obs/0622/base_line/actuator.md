# ROA 12DOF Baseline PD Gains

## PD Gains

| Joint       |    Kp |    Kd |
| ----------- | ----: | ----: |
| Hip Pitch   | 100.0 | 8.241 |
| Hip Roll    | 133.3 | 8.796 |
| Hip Yaw     | 100.0 | 3.419 |
| Knee Pitch  | 150.0 | 8.654 |
| Ankle Pitch |  20.0 |   5.0 |
| Ankle Roll  |  27.4 |  6.85 |

*Left and right legs use the same gains.*

---

## Torque Limits

The simulator reduces all torque limits to **75%** of the nominal value.

| Joint Type   | Nominal | Sim Limit |
| ------------ | ------: | --------: |
| Hip Pitch    | 84.0 Nm |   63.0 Nm |
| Hip Roll/Yaw | 42.0 Nm |   31.5 Nm |
| Knee Pitch   | 84.0 Nm |   63.0 Nm |
| Ankle        | 11.9 Nm |   8.93 Nm |

---

## Velocity Limits

| Joint Type | Velocity Limit |
| ---------- | -------------- |
| Hips       | 8 rad/s        |
| Knees      | 8 rad/s        |
| Ankles     | 5 rad/s        |

---

## RSU Scaling

RSU ratio:

```text
K = 1.37
```

Applied only to ankle roll:

```text
Ankle Pitch : Kp=20.0, Kd=5.0
Ankle Roll  : Kp=27.4, Kd=6.85
```

---

## Delay Model

```text
min_delay = 7 steps
max_delay = 12 steps
```

Assuming:

```text
dt = 0.005 s (200 Hz)
```

Delay range:

```text
7 steps  = 35 ms
12 steps = 60 ms
```

Effective actuator delay:

```text
35–60 ms
```

---

## Armature

| Joint Type | Armature |
| ---------- | -------: |
| Hips       |   0.0004 |
| Knees      |   0.0004 |
| Ankles     |     0.02 |

---

## Gain Ranking (Highest → Lowest)

```text
Knee Pitch     : Kp = 150
Hip Roll       : Kp = 133.3
Hip Pitch/Yaw  : Kp = 100
Ankle Roll     : Kp = 27.4
Ankle Pitch    : Kp = 20
```

## Summary

* Knee-dominant PD controller.
* Medium stiffness at hips.
* Soft/compliant ankles.
* Torque derated to 75% for stability.
* Simulated control delay of 35–60 ms.
* Same gains for left and right legs.
