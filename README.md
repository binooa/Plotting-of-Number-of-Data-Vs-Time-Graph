# Plot a Graph to show the performance of an Algorithm
Plotting a Graph to show the perfromance of an algorithm Python matplotlib and Google colab.

## How to use Google Colab

To start working with Colab you first need to log in to your google account, then go to this link https://colab.research.google.com

```python
import numpy as np
import numpy as np
from scipy.interpolate import make_interp_spline
import matplotlib.pyplot as plt
 
# Dataset
x = np.array([1, 2, 3, 4, 5, 6, 7, 8])
y = np.array([1, 4, 9, 16, 25, 36, 49, 64])
 
X_Y_Spline = make_interp_spline(x, y)
 
# Returns evenly spaced numbers
# over a specified interval.
X_ = np.linspace(x.min(), x.max(), 500)
Y_ = X_Y_Spline(X_)

# Plotting the Graph
plt.plot(X_, Y_,label="Bubble Sort")
plt.grid()
plt.title("Number of Elements Vs Time Taken - Graph")
plt.xlabel("Number of Data (n)")
plt.ylabel("Time Taken to Complete the Execution (t msec)")
plt.legend()
plt.show()

```

## Estimating the Time Taken to Complete execution of a program block

```C
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

float timedifference_msec(struct timeval t0, struct timeval t1)
{
    return (t1.tv_sec - t0.tv_sec) * 1000.0f + (t1.tv_usec - t0.tv_usec) / 1000.0f;
}

int main(void)
{
   struct timeval t0;
   struct timeval t1;
   float elapsed;
   
   long *data;
   long num=100000000, j;
   data = (long *)malloc(sizeof(long)*num);

   gettimeofday(&t0, NULL);
   if(data != NULL)
    {
        for(j = 0; j < num; j++)
        {
            data[j] = rand()%100;
        }
    }
   gettimeofday(&t1, NULL);

   elapsed = timedifference_msec(t0, t1);

   printf("Code executed in %f milliseconds.\n", elapsed);

   return 0;
}
```
## Find out the Execution Time of following two programs 

> Use different num values (num =100, num =10000, num =1000000, num =100000000)
-   [Bubble Sort](https://github.com/binooa/Performance-Evaluation/blob/main/BubbleSort.c)
-   [Selection Sort](https://github.com/binooa/Performance-Evaluation/blob/main/SelectionSort.c)
