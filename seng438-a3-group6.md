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


##  __DataUtilities:__

__Data Flow Graph:__

#### __Def-Use Sets per Statement:__
 Def-Path Set
        
            du(1,data) = {[1,2],[1,2,3,4],[1,2,3,4,5,6,7],[1,2,3,4,5,6,12,13,14]}
            du(1,column) = {[1,2,3,4,5,6,7],[1,2,3,4,5,6,12,13,14]}
            du(3,total) = {[3,4,5,6,7,8,9],[3,4,5,6,12,13,14,15,16]}
            du(4,rowCount) = {[4,5,6],[4,5,6,12,13]}
            du(5,r) = {[5,6],[5,6,7],[5,6,7,8,9,10,11]}
            du(12,r2) = {[12,13],[12,13,14],[12,13,14,15,16,17,18]}
            du(7,n) = {[7,8],[7,8,9]}
            du(14,n) = {[14,15],[14,15,16]}

 Use-Path Set
         
            du(1,2,data) = {[1,2]}
            du(1,4,data) = {[1,2,3,4]}
            
            du(1,7,data) = {
                [1,2,3,4,5,6,7],
                [1,2,3,4,5,6,7,8,9,10,11,6,7],
                [1,2,3,4,5,6,7,8,10,11,6,7]
            }
            
            du(1,14,data) = {
                [1,2,3,4,5,6,12,13,14],
                [1,2,3,4,5,6,12,13,14,15,16,17,18,13,14],
                [1,2,3,4,5,6,12,13,14,15,17,18,13,14],
                [1,2,3,4,5,6,7,8,9,10,11,6,12,13,14,15,16,17,18,13,14],
                [1,2,3,4,5,6,7,8,9,10,11,6,12,13,14,15,17,18,13,14],
                [1,2,3,4,5,6,7,8,10,11,6,12,13,14,15,16,17,18,13,14], 
                [1,2,3,4,5,6,7,8,10,11,6,12,13,14,15,17,18,13,14]
            }
            
            du(1,7,column) = {
                [1,2,3,4,5,6,7],
                [1,2,3,4,5,6,7,8,9,10,11,6,7],
                [1,2,3,4,5,6,7,8,10,11,6,7]
            }
            
            du(1,14,column)  = {
                [1,2,3,4,5,6,12,13,14],
                [1,2,3,4,5,6,12,13,14,15,16,17,18,13,14],
                [1,2,3,4,5,6,12,13,14,15,17,18,13,14],
                [1,2,3,4,5,6,7,8,9,10,11,6,12,13,14,15,16,17,18,13,14], 
                [1,2,3,4,5,6,7,8,9,10,11,6,12,13,14,15,17,18,13,14],
                [1,2,3,4,5,6,7,8,10,11,6,12,13,14,15,16,17,18,13,14], 
                [1,2,3,4,5,6,7,8,10,11,6,12,13,14,15,17,18,13,14]
            }

            du(3,9,total) = {
                [3,4,5,6,7,8,9],
                [3,4,5,6,7,8,9,10,11,6,7,8,9]
            }

            du(3,16,total) = {
                [3,4,5,6,12,13,14,15,16],
                [3,4,5,6,7,8,9,10,11,6,12,13,14,15,16]
            }

            du(3,19,total) = {
                [3,4,5,6,12,13,19]
            }

            du(4,6,rowCount) = {
                [4,5,6],
                [4,5,6,7,8,9,10,11,6],
                [4,5,6,7,8,10,11,6]
            }

            du(4,13,rowCount) = {
                [4,5,6,12,13],
                [4,5,6,12,13,14,15,16,17,18,13]
                [4,5,6,12,13,14,15,17,18,13],
                [4,5,6,7,8,9,10,11,6,12,13],
                [4,5,6,7,8,9,10,11,6,12,13,14,15,16,17,18,13],
                [4,5,6,7,8,9,10,11,6,7,8,9,10,11,6,12,13],
                [4,5,6,7,8,10,11,6,12,13],
                [4,5,6,7,8,10,11,6,12,13,14,15,16,17,18,13],
                [4,5,6,7,8,10,11,6,7,8,9,10,11,6,12,13]
            }

            du(5,6,r) = {
                [5,6],
                [5,6,7,8,9,10,11,6],
                [5,6,7,8,10,11,6]
            }

            du(5,7,r) = {[5,6,7]}
            du(5,11,r) = {[5,6,7,8,9,10,11]}

            du(12,13,r2) = {
                [12,13],
                [12,13,14,15,16,17,18,13],
                [12,13,14,15,17,18,13]
            }

            du(12,14,r2) = {[12,13,14]}
            du(12,18,r2) = {[12,13,14,15,16,17,18]}
            du(7,8,n) = {[7,8]}
            du(7,9,n) = {[7,8,9]}
            du(14,15,n) = {[14,15]}
            du(14,16,n) = {[14,15,16]}


#### __DU pairs per Variable:__

| Variables  |  DU-Pairs  |
| -------------- | --- |
| data   |  (1,2), (1,4), (1,7), (1,14)  |
| column  |  (1,7), (1,14)   |
| total     |  (3,9), (3,16), (3,19)   |
| rowCount     |   (4,6), (4,13)  |
| r     |   (5,6), (5,7), (5,11)  |
| r2     |  (12,13), (12,14), (12,18) |
| n   |  (7,8), (7,9), (14,15), (14,16)|

#### __Pairs Covered per Test Case:__

    -testCaluclateColumnTotalFiveValues()
        Input Values: [7.5, 2.5, 4, -4, 5], ColumnNumber [1]
        Pairs Covered: 
            data(1,2), data(1,4), data(1,7), data(1,14)
            column(1,7), column(1,14)
            total(3,9), total(3,16), total(3,19)
            rowCount(4,6), rowCount(4,13)
            r(5,6), r(5,7), r(5,11)
            r2(12,13), r2(12,14), r2(12,18)
            n(7,8), n(7,9), n(14,15), n(14,16)

    -testCalculateColumnTotalNegative()
        Input Values: [-7.5, -2.5, -6, -4]-, ColumnNumber [1]
        Pairs Covered: 
            data(1,2), data(1,4), data(1,7), data(1,14)
            column(1,7), column(1,14)
            total(3,9), total(3,16), total(3,19)
            rowCount(4,6), rowCount(4,13)
            r(5,6), r(5,7), r(5,11)
            r2(12,13), r2(12,14), r2(12,18)
            n(7,8), n(7,9), n(14,15), n(14,16)

    -testCalculateColumnTotalEmpty()
        Input Values: [], ColumnNumber [0]
        Pairs Covered: 
            data(1,2), data(1,4)
            total(3,9), total(3,16), total(3,19)
            r(5,6), r(5,7), r(5,11)
            r2(12,13), r2(12,14), r2(12,18)

    -testCalculateColumnTotalNegativeColumnIndex()
        Input Values: [3, 7.5, 2.5, 4], ColumnNumber [-1]
        Pairs Covered: 
            data(1,2), data(1,4), data(1,7), data(1,14)
            column(1,7), column(1,14)
            rowCount(4,6), rowCount(4,13)
            r(5,6), r(5,7), r(5,11)
            r2(12,13), r2(12,14), r2(12,18)
            n(7,8), n(14,15)

    -testCalculateColumnNullValue()
        Input Values: [null], ColumnNumber [0]
        Pairs Covered: data(1,2)

#### __DU pair Coverage:__

    Coverage = (number of exercised DU pairs) / (mumber of DU pairs) = 21 / 21 
             = 100%


## __Range:__



# 3 A detailed description of the testing strategy for the new unit test

### __Range:__

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
            TC1: Input: range’s lower bound is lower than range’s upper bound
        
        -scale(Range base, double factor): Range
            TC1: Input: base = null, factor = 1.0
            TC2: Input: base = Range(-10,10), factor = -3.0
            TC3: Input: base = Range(-10,10), factor = 2.0

        -shiftWithNoZeroCrossing(double, double): double
            TC1 & TC2: This test will simulate when input Range of (lower bound + delta < 0) where lower bound > 0
                Input Values: testRange = new Range(5, 10); Range.shift(testRange, -6);
                Expected Output: Expected result: Range(0, UpperBound + delta)
            TC3 & TC4: This test will simulate when input Range of upper bound + delta > 0 when upper bound < 0
                Input Values: testRange = new Range(-10, -5); Range.shift(testRange, 6);    
                Expected result: Range(LowerBound + delta, 0)
            TC5 & TC6: This test will simulate when input Range at (0,0)
                Input Values: testRange = new Range(0, 0); Range.shift(testRange, 6);
                Expected result: Range(LowerBound + delta, UpperBound + delta)
        

        -hashCode(): int
            TC1: This test will simulate this method returns int type (not null value)
                Input Values: testRange = new Range(-1, 1); testRange.hashCode()
                Expected Output: an int type number

        -combineIgnoringNaN(Range range1, Range range2): Range
            TC1: This test will simulate when input Range 1 is Null, Range 2 is not Null but NaN
                Input Values: Range r1 = null; Range r2 = new Range (NaN, NaN); 
                Expected result: null
            TC2: This test will simulate when input Range 1 is Null, Range 2 is Null
                Input Values: Range r1 = null; Range r2 = null; 
                Expected result: null  
            TC3: This test will simulate when input Range 1 is Null, Range 2 is Normal
                Input Values: Range r1 = null;  Range r2 = new Range (-1,1);
                Expected result: Range 2
            TC4: This test will simulate when input Range 1 is notNull but NaN, Range 2 is null
                Input Values: Range r1 = new Range (NaN, NaN); Range r2 = null;
                Expected result: null
            TC5: This test will simulate when input Range 1 is Normal, Range 2 is Null
                Input Values: Range r1 = new Range (-1,1);  Range r2 = null;    
                Expected result: Range 1
            TC6: This test will simulate when input Range 1 is Null, Range 2 is Null
                Input Values: Range r1 = new Range (NaN, NaN);  Range r2 = new Range (NaN, NaN); 
                Expected result: null   
            TC7: This test will simulate when input Range 1 is Normal, Range 2 is Normal
                Input Values: Range r1 = new Range(-2 , 1); Range r2 = new Range(-1 , 2); 
                Expected Values: Combined Range (Range r1 + Range r2)   

        -min(double d1, double d2): double
            To test this function, we need to test another function that uses min
            TC1: This test will simulate when input d1 is Normal, Range d2 is Normal
                Input Values: double d1 = -20; double d2 = 10; Range.combineIgnoringNaN(r1, new Range(d1,d2));  
                Expected result: min value should be set as new range
            TC2: This test will simulate when input d1 is Normal, Range d2 is NaN
                Input Values: double NaN = zero/zero;  double d2 = 10; 
                              Range actualRange = Range.combineIgnoringNaN(r1, new Range(NaN,d2));  
                Expected result: min value should be set as new range
            TC3: This test will simulate when input d1 is NaN, Range d2 is Normal
                Input Values: double NaN = zero/zero;  Range r1 = new Range(-10,10);
                             Range.combineIgnoringNaN(r1, new Range(NaN,NaN));  
                Expected result: Range 1

        -isNaNRange(): boolean
            TC1: This test will simulate when input ranges lower bound is normal, upper bound is Normal
                Input Values: testRange = new Range(-1,1); testRange.isNaNRange();
                Expected result: False
            TC2: This test will simulate when input ranges lower bound is NaN, upper bound is Normal
                Input Values: testRange = new Range(NaN,1); testRange.isNaNRange();
                Expected result: False
            TC3: This test will simulate when input ranges lower bound is Normal, upper bound is NaN
                Input Values: testRange = new Range(-1,NaN); testRange.isNaNRange();
                Expected result: False
            TC5: This test will simulate when input ranges lower bound is NaN, upper bound is NaN
                Input Values: testRange = new Range(NaN,NaN); testRange.isNaNRange();
                Expected result: True 

        -expand(Range, double, double): Range
        -expandToInclude(Range, double): Range
        -shift(Range, double): Range
        -shift(Range, double, boolean): Range
        -intersects(Range, range): boolean
        
        
### __DataUtilities:__

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
            TC3: Input:  data


# 4 A high level description of five selected test cases you have designed using coverage information, and how they have increased code coverage

Text…

# 5 A detailed report of the coverage achieved of each class and method (a screen shot from the code cover results in green and red color would suffice)

       For class Range:
       
       Branch Coverage:
       
<img width="500" alt="Screen Shot 2023-03-03 at 6 55 06 AM" src="https://user-images.githubusercontent.com/56771715/222753967-2fb16534-86ed-474d-ae18-213589768bb6.png">
        
        Statement Coverage:
        
<img width="500" alt="Screen Shot 2023-03-03 at 6 57 08 AM" src="https://user-images.githubusercontent.com/56771715/222754082-8163a54e-d98a-44a8-948b-00501a98af06.png">

       Conditional Coverage:
       
<img width="500" alt="Screen Shot 2023-03-03 at 6 57 21 AM" src="https://user-images.githubusercontent.com/56771715/222754153-ad6f12eb-2c9b-4cff-92ab-7ec6bed2600a.png">


       For class DataUtilities:
       
       Branch Coverage:
       
<img width="500" alt="Screen Shot 2023-03-03 at 6 56 50 AM" src="https://user-images.githubusercontent.com/56771715/222754534-1ca4b98a-c33a-46aa-a266-a4e6183876c1.png">

       
       Statement Coverage:
       
<img width="500" alt="Screen Shot 2023-03-03 at 6 54 15 AM" src="https://user-images.githubusercontent.com/56771715/222754443-8ec54e8b-0d99-4ddb-b903-b3e4dc35b3aa.png">

       
       
       Conditional Coverage:
       
<img width="500" alt="Screen Shot 2023-03-03 at 6 54 54 AM" src="https://user-images.githubusercontent.com/56771715/222754610-8f3c13f1-0a90-48d2-b008-f0559ae32071.png">




       

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
