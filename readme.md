##Solution:

#Understanding:
1.Interpolation for Sabertooth: we need to convert the channel data from the RC transmitter into a format that the sabertooth understands.The sabertooth motor driver understands commands in a specific formal by which it controls the motor's speed and direction. 

2.RC Transmitter Data: the rc trnasmitter sends data to the sbus which then communicates wiht the microcontroller. the data is typically in the range of 1000-2000 microseconds.

#Thought process:
1. we need to convert the transmitter data into a range so that the sabertooth motor understands it.
2. the input range typically varies between 1000-2000 microseconds but the sabertooth motor expects values between the ranges of 0 to 255.
3. thus we need to map the rc transmitter's values to the sabertooth's expectd range.

##Implementation:
1. Mapping Process: for the sabertooth to understand the commands we need to match its expected rnage and thus we need to covert the values from one range to another.
2. the above mapping will be done using a process called Linear interpolation.
3.Linear interpolation is a method used to estimate unknown values that fall between known values. It’s a simple technique used to find a value within a range based on a linear relationship between the known values.
4. for linear interpolation we must have two known points (x1,y1) and (x2,y2) where x is the input value and y is the output value.
5. we need to determine Input and Output Ranges:
Input Range: 1000 μs to 2000 μs (from the RC transmitter).
Output Range: 0 to 255 (for the Sabertooth driver).
6. formula:
Mapped Value=((input value - input min)/(input max-input min))*(output max-output min)+output min
7. Variables:
Input Min: 1000 μs (minimum value from RC).
Input Max: 2000 μs (maximum value from RC).
Output Min: 0 (minimum value for Sabertooth).
Output Max: 255 (maximum value for Sabertooth)
8. now we need to implement it using code.

##Problems faced:
1. i was told that basic working knowledge of C programming language is required when people from team rudra had come to our class.
2. i had to search and learn a lot about how a sabertooth motor works and how do i write a code to complete the tasks.
3. i did not have much knowledge about how github works and so i had to figure that out along the way too.
4. i have managed to write some part of the code but i have not entirely completed it.
5. this was a good learning experience.
6. 
