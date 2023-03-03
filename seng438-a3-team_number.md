**SENG 438 - Software Testing, Reliability, and Quality**

**Lab. Report #3 – Code Coverage, Adequacy Criteria and Test Case Correlation**

| Group     6    |     |
| -------------- | --- |
| Maarya Ahmed   |     |
| Jinsu Kwak     |     |
| Jack Li        |     |
| Hannah Son     |     |

(Note that some labs require individual reports while others require one report
for each group. Please see each lab document for details.)

# 1 Introduction

Text…

# 2 Manual data-flow coverage calculations for X and Y methods

Text…

# 3 A detailed description of the testing strategy for the new unit test

    Range:
        -constrain(double): double
		Sample Range(-1,1)
		TC1: value = 3.0, expected: closer to 1, so 1
		TC2: value = 1, expected output: 1
		TC3: value = -1, expected output: -1
		TC4: value = 0, expected output: 0 
		TC5: value = -5, expected output: closer -1, so -1
		TC6: value = NaN, expected output: NaN

        -equals(Object): boolean
		TC1: range object = [-1,1], expected output: true, same object
		TC2: range object = double, expected output: false since double is not range object
		TC3: range object = [-5, 1], expected output: false cuz lower bound not same
		TC4: range object = [NaN, NaN], expected output: true since it is same
		TC5: range object = [-1, 5], expected output: false cuz upper bound not same
		TC6: range object = [-10, 10], expected output: false cuz not same

        -toString(): String
		TC1: sample range = exampleRange = (-1, 1); expected output: “Range[-1,1]”
		TC2: sample range = exampleRange = (NaN, NaN); expected output: “Range[NaN,NaN]”

        -max(double d1, double d2): double
	To test this function, we need to test another function that uses max
		TC1: Range1=(-5,4), Range2=(-5,2): 
			expected output: Range = (-5, 4)
		TC2: Range1=(-5, 4), Range2=(NaN,2)
			expected output: Range = (-5, 4)
		TC3: Range1=(-5,4), Range2=(NaN,NaN)
			expected output: Range = (-5, 4)

        -getUpperBound(): double
            TC1: Input: range’s lower bound is greater than range’s upper bound
            TC2: Input: range’s lower bound is lower than range’s upper bound
	    
        -scale(Range base, double factor): Range
            TC1: Input: base = null, factor = 1.0
	        TC2: Input: base = Range(-10,10), factor = -3.0
	        TC3: Input: base = Range(-10,10), factor = 2.0
		
        -shiftWithNoZeroCrossing(double, double): double
        -hashCode(): int
        -combineIgnoringNaN(Range range1, Range range2): Range
        -min(double d1, double d2): double
        -isNaNRange(): boolean
        -expand(Range, double, double): Range
        -expandToInclude(Range, double): Range
        -shift(Range, double): Range
        -shift(Range, double, boolean): Range
        -intersects(Range, range): boolean
        
        
    DataUtilities:
        -calculateRowTotal(Values2D data, int row, int[] validCols): double
		TC1: row = 0, validCols = {0, 1, 2},
		TC2: row = 0,  column = 0, validCols = {0}
		TC3: row = 0;data = {{3.0}, {null}, {-1.0}, {-2.0}}, validCols = {0, 1, 2}
		TC4: row = 0; column = 4, data = {{4.0}, {null}, {-6.0}, {2.0}}, validCols = {5}

        -equal(double[][] a, double[][] b): boolean
	        TC1: Input: a = null, b = null
	        TC2: Input: a = not null, b = null
	        TC3: Input: a = {{1.0, 2.1, 3.4}, {-1.2, 0.0, 10.0}, {-1.3, 1.0, 10.0}}, b = {{1.0, 2.1, 3.4},{-1.2, 0.0, 10.0}}  (different rows/length of 2d array)
	        TC4: Input: a = {{1.0, 7.0, 3.0}, {-1.0, 0.0, 20.0}}, b = {{1.0, 2.0, 3.0}, {-1.0, 0.0, 10.0}}
	        TC5: Input: a = {{1.0, 2.1, 3.4}, {-1.2, 0.0, 10.0}}, b = {{1.0, 2.1, 3.4}, {-1.2, 0.0, 10.0}}
		
        -clone(double[][] source): double[][]
            TC1: Input: source = null
	        TC2: Input: source = {{3.0, 5.0, null}, {8.0, 19.0, 4.0}}
	        TC3: Input: source = {{8.0, 14.0, 17.0}, {25.0, 89.0, 103.0}}
		
        -calculateColumnTotal(Values2D data, int column, int[] validRows): double
            TC1: Input:  data = null, column = 0, validRows = {0}
            TC2: Input:  data = {{3.0}, {null}, {1.0}, {10.0}, {2.0}}, column = 0, validRows = {0, 1, 2}
            TC3: Input:  data = {{3.0}, {8.0}, {1.0}, {10.0}, {2.0}}, column = 0, validRows = {0, 2, 3}


# 4 A high level description of five selected test cases you have designed using coverage information, and how they have increased code coverage

Text…

# 5 A detailed report of the coverage achieved of each class and method (a screen shot from the code cover results in green and red color would suffice)

Text…

# 6 Pros and Cons of coverage tools used and Metrics you report

Text…

# 7 A comparison on the advantages and disadvantages of requirements-based test generation and coverage-based test generation.

Advantages of Requirements-Based Test Generation

    -Ensures that requirements have been covered and tested


Disadvantages of Requirements-Based Test Generation

    -Does not ensure that the code has been tested


Advantages of Coverage-Based Test Generation

    -Ensures that the code has been tested

    -Gives a measurement of how much unit testing has been done 


Disadvantages of Coverage-Based Test Generation

    -Does not test if the code has been developed according to the requirements (just that the code works properly)

    -100% coverage does not guarantee the effectiveness of a test suite


# 8 A discussion on how the team work/effort was divided and managed

Section 3.1: Measure Control Flow Coverage

    -This section was completed as a group
    
    
Section 3.2: Measure Data Flow Coverage Manually

    -Method DataUtilities.calculateColumnTotal() was done by Jinsu and Jack
    
    -Method Range.getLength() was done by Maarya and Hannah


Section 3.3: Test Suite Development

    -Each group member was given 5 methods from Range and DataUtilities
    
        -Maarya
            Range:
                -constrain(double): double
                -equals(Object): boolean
                -toString(): String
                -max(double d1, double d2): double
            DataUtilities:
                -calculateRowTotal(Values2D data, int row, int[] validCols): double
        
        -Hannah
            Range:
                -getUpperBound(): double
                -scale(Range base, double factor): Range
            DataUtilities:
                -equal(double[][] a, double[][] b): boolean
                -clone(double[][] source): double[][]
                -calculateColumnTotal(Values2D data, int column, int[] validRows): double
        
        -Jinsu
            Range:
                -shiftWithNoZeroCrossing(double, double): double
                -hashCode(): int
                -combineIgnoringNaN(Range range1, Range range2): Range
                -min(double d1, double d2): double
                -isNaNRange(): boolean
                
        
        -Jack
            Range:
                -expand(Range, double, double): Range
                -expandToInclude(Range, double): Range
                -shift(Range, double): Range
                -shift(Range, double, boolean): Range
                -intersects(Range, range): boolean


# 9 Any difficulties encountered, challenges overcome, and lessons learned from performing the lab

Text…

# 10 Comments/feedback on the lab itself

Text…
