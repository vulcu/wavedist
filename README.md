# `wavedist` #
Waveshape Audio Distortion JSFX Plug-in for Reaper DAW

 `tags:` waveshaping, non-linear distortion

 `author:` Winry R. Litwa-Vulcu

 (C) 2017-2020, Winry R. Litwa-Vulcu

## `References:` ##
1)  Aarts, R.M., Larsen, E., and Schobben, D., 2002, 'Improving Perceived Bass and Reconstruction of High Frequencies for Band Limited Signals' Proc. 1st IEEE Benelux Workshop MPCA-2002, pp. 59-71
 2) Arora et al., 2006, 'Low Complexity Virtual Bass Enhancement Algorithm for Portable Multimedia Device' AES 29th International Conferance, Seoul, Korea, 2006 September 2-4
 3) Gerstle, B., 2009, 'Tunable Virtual Bass Enhancement', [ONLINE] <http:rabbit.eng.miami.edu/students/ddickey/pics/Gerstle_Final_Project.pdf>
 4) Yates, R. and Lyons, R., 2008, 'DC Blocker Algorithms' IEEE Signal Processing Magazine, March 2008, pp. 132-134

 ---
## `Algorithms:` ##
```
 1) soft clip alg:        y[n] = (1.5*x[n]) - (0.5*x[n]^3);
 2) leaky integrator alg: y[n] = ((1 - A) * x[n]) + (A * y[n - 1]);
 3) soft knee clip alg:   y[n] = x[n] / (K * abs(x[n]) + 1);
 4) cubic soft clip alg:  y[n] = (1.5 * threshold * HardClip(x[n])) -
                                ((0.5 * HardClip(x[n])^3) / threshold);
 5) warp alg: y[n] = (((x[n] * 1.5) - (0.5 * x[n]^3)) * (((2 * K) / (1 - K))
                    + 1)) / ((abs((x[n] * 1.5) - (0.5 * x[n]^3)) 
                    * ((2 * K) / (1 - K))) + 1);
 6) rectify alg: y[n] = ((1 - R) * softclip(x[n])) + (|softclip(x[n])| * R);
```
---
