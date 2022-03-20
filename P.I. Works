# Author @Mehmet Gokberk Arslan
# This program takes the input file path as an argument.
import sys

# A simple function that determines whether an integer is a prime number or not.
def isPrime(number):
    if number == 1 or number == 0:
        return False
    if number == 2:
        return True
    sqrtOfNumber = number**(0.5)
    for i in range(2,int(sqrtOfNumber)+1):
        if number % i == 0:
            return False
    return True

# This recursive function finds the maximum valued path.
# The function finds the maximum valued path by
# dividing the triangle into smaller triangles from top to bottom.
def sumFinder(rowIndex, columnIndex, selfValue):

    # Assuming that the final number in a path can be a prime
    # since the question states that you cannot walk OVER a prime number.
    if isPrime(selfValue):
        return selfValue

    sum1 = 0
    sum2 = 0

    value1 = int(triangle[rowIndex+1][columnIndex])
    value2 = int(triangle[rowIndex+1][columnIndex+1])

    # No need to call the function again for the values in the bottom.
    if rowIndex == checker-2:
        return selfValue + max(value1, value2)

    # Recursive calls
    sum1 = sumFinder(rowIndex+1, columnIndex, value1)
    sum2 = sumFinder(rowIndex+1, columnIndex+1, value2)
     
    return selfValue + max(sum1, sum2)

# Assuming that the input is received from a file that's path is given as an argument.
with open(sys.argv[1]) as f:
    lines = f.read()

numbersStrip = lines.replace('\n'," ")
numbersSplit = numbersStrip.split()
numberCount = len(numbersSplit)

# Checking if the number count of the input is valid (triangular number),
# and determining the number of rows in the input.
checker = 1
while checker*(checker+1)/2 < numberCount:
    checker += 1
if checker*(checker+1)/2 != numberCount:
    print("Invalid input")
    exit()

rowcount = 0
columncount = 0
triangle = [[-1 for i in range(checker)] for j in range(checker)]

# Inserting the values into a 2-D array in triangular form.
for i in numbersSplit:
    triangle[rowcount][columncount] = i
    columncount += 1
    if columncount > rowcount or rowcount == 0:
        rowcount += 1
        columncount = 0
        
maxValue = sumFinder(0,0,int(triangle[0][0]))
print(maxValue)
