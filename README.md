VennPlot
========

This is a Java program for drawing rotationally symmetric Venn diagrams that are simple and monotone. Any closed curve divides the plane into two regions : the interior of the curve and the exterior of the curve. With a collection of n curves therefore, we can have up to 2^n different regions. An n-Venn diagram is defined as a collection of n closed curves containing exactly 2^n regions where each region is in the interior of a unique subset of the curves.

Labelling the curves of an n-Venn diagram from 1 to n, we associate a binary number r to a region, called the rank of the region, where the i-th bit is 1 if curve number i contains the region, otherwise it is 0. The number of curves containing a region, which is the same as the number of 1's in the rank of the region, is called the weight of the region.

A Venn diagram is simple if no more than two curves intersect at any given point. A monotone Venn digram is the one in which any region of weight k is adjacent to at least one region of weight k + 1 and is also adjacent to at least one region of weight k-1.

A rotationally symmetric Venn diagram consists of n congruent pie slices. A pie slice of a simple symmetric monotone Venn diagram of n curves can be represented by a binary matrix of n-1 rows and (2^n - 2)/n columns such that each column contains exactly one 1 and no two 1's are adjacent in a row. The 1's in the matrix represent the points at which the curves intersect. Similarly, it can be represented by a sequence of length (2^n -2)/n of integers in range [0, n-2] which is called the crossing sequence. The i-th element indicates the row number of the matrix which contains a 1 at column i. 

For example the famous three circle Venn diagram can be represented by the following binary matrix and crossing sequence.

   A pie-slice of symmetric 3-Venn diagram : 
                            ____   ___________
                                \ /
                                 *
                            ____/ \____   ____
                                       \ /
                                        *
                            ___________/ \____
                            
    Binary Matrix :              1      0          
                            
                                 0       1
                                 
                              ---------------
                                 
    Crossing Sequence :          0   ,   1  

Given the crossing sequence of a simple symmetric n-Venn diagram as input, this program creates an SVG file of the Venn diagram.

The program takes 5 arguments as input which are :
n : The number of curves
input-file-name : The name of the file containing the crossing sequences.
This file contains the crossing sequence of the Venn diagrams we want to draw.
Each diagram is given as a sequence of (2^n-2)/n integers numbers between 0 and n-2 and separated by a space.

colors-file-name : The name of the file containing the codes of filling/stroke colours.
This files contains an integer n as the number of colours followed by n colour codes in hexadecimal format, for example, #FF0000 for the red colour. 

filling-mode : Indicates the filling style. 1 : filled, 0 : not-filled.
drawing-mode : Indicates the style of drawing. 0 : Radial, 1 : Cylindrical.