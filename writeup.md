@@ -1,33 +0,0 @@
# CarND-Controls-PID
---
## Parameter tuning method

To tune the P, I, D component coefficient was used manual playing method as fastest and simpliest.

All steps are present in `main.cpp`.
```cpp
  //Initial
  //pid.Init(0.3, .1, 0.004);
  //Improvement to stay on road after fails
  //pid.Init(0.15, .01, 0.01);
  //Increasing derivative coefficient to return after big error
  //and decreasing integral coefficient
  //pid.Init(0.15, .001, 1.0);
  //Increasing derivative coefficient again and making integral coefficient equals to 0,
  //because we don't need "historical" errors
  pid.Init(0.15, .0, 1.9);
  //Result - car stays on track after several loops
```

## Final parameters

Finally the parameters are equals to
- Proportional = 0.15
- Integral = 0
- Derivative = 1.9

## Captured video

Here's a [link to video result](./video/FinalParametersSimu.mp4)

One remark: on video there are some situations with significant deviations of cars from trajectory (but still on track). That was observed only during capturing video by some special application, which took approx. 60-70% of processor time. Without capturing a video, the results are much more better, I think - the reason is in delays of socket transmittion between PID application and simulator.

UPD:
Can not submit a video due to huge size (~150MB).
