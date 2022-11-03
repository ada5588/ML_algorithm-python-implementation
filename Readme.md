### LM_Algorithm Python Implementation

This project is a practice of the Levenberg–Marquardt algorithm using python. The primary purpose is to implement Algorithm 4.3 in Wilhelm Burger's "Zhang's Camera Calibration Algorithm: In-Depth Tutorial and Implementation." The function `curve_fit()` used in Maxwell Goldberg's project [CameraCalibration](https://github.com/goldbema/CameraCalibration) is the Python API for performing the LM algorithm.
With the value function, Jacobian matrix, the initial guess of parameters, and the independent and dependent data given, the parameters best suit the model will be found using the `curve_fit()` function in `scipy.optimize` module.

For more information about the function `curve_fit()` in SciPy library, please visit [here](https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.curve_fit.html).

#### Dependencies
* Python 3.9.7
* Numpy 1.20.3
* Scipy 1.7.1
* Matplotlib 3.4.3

#### About the notebook
There are two sections in the ML_Algorithm.ipynb. Section 1 is the implementation of Algorithm 4.3 in Wilhelm Burger's "Zhang's Camera Calibration Algorithm: In-Depth Tutorial and Implementation" for finding the homography matrix, and section 2 is the implementation for finding parameters of an exponential function.
The dependent data used for model fitting are generated from the ground truth parameter with noise added.

#### Results
The standard deviation error for the parameters found is computed from each section's second return value of `curve_fit()`.
In the last cell of each section, we plot the ground truth data(data generated from the ground truth parameters), and the data generated from the parameter found using Levenberg–Marquardt algorithm.
##### Section1
| |Found|Ground truth|Standard Deviation Error|
|h0 |-6.05|-7.05       |4.78                    |
|h1 |0.87 |1.13        |0.02                    |
|h2 |-0.19|0.82        |0.73                    |
|h3 |1.38 |1.49        |1.07                    |
|h4 |-2.47|-3.29       |1.89                    |
|h5 |-4.82|-5.6        |3.55                    |
|h6 |2.61 |2.93        |1.9                     |
|h7 |4.22 |4.74        |3.08                    |
|h8 |-4.47|-5.02       |3.26                    |

![Result plot1](/Results/section1.png)
The result varies significantly as the initial guess is far from the ground truth and the range of the noise added grows.

##### Secion2
| |Found|Ground truth|Standard Deviation Error|
|-----|-----|------------|------------------------|
|a    |2.03 |2.1         |0.04                    |
|b    |1.11 |1           |0.07                    |
|c    |3.46 |3.5         |0.02                    |

![Result plot2](/Results/section2.png)
The red dotted curve with parameters found from data points perfectly covers the ground truth(black curve).
