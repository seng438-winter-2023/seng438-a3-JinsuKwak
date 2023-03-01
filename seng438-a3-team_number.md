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

Text…

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
