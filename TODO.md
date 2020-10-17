### 1.1. Speed comparision between Numpy and Python Lists
import time
import numpy as np

size_of_vec = 1000000

def pure_python_version():                                                # This function will return the time for python calculation
    time_python = time.time()                                             # Start time before operation
    my_list1 = range(size_of_vec)                                         # Creating a list with 1000000 values
    my_list2 = range(size_of_vec)
    sum_list = [my_list1[i] + my_list2[i] for i in range(len(my_list1))]  # Calculating the sum
    return time.time() - time_python                                      # Return Current time - start time

def numpy_version():                                                      # This function will return the time for numpy calculation
    time_numpy = time.time()                                              # Start time before operation
    my_arr1 = np.arange(size_of_vec)                                      # Creating a numpy array of 1000000 values
    my_arr2 = np.arange(size_of_vec)
    sum_array = my_arr1 + my_arr2                                         # Calculate the sum
    return time.time() - time_numpy                                       # Return current time - start time


python_time = pure_python_version()                                       # Time taken for Python expression
numpy_time = numpy_version()                                              # Time taken for numpy operation
print("Pure Python version {:0.4f}".format(python_time))
print("Numpy version {:0.4f}".format(numpy_time))
print("Numpy is in this example {:0.4f} times faster!".format(python_time/numpy_time))



    

