# Longest-Common-String
In this algorimn homework, I use two different algorimn method to find LCS.

## Overviews
1. The original ones is using nested iteration to find common characters, whose time complex is **O(n^2)**

2. The improved one is converting LCS to LIS problem, whose time complex is **O(nlogn)**


For example:
 s1[] = “abcabc”, s2[] = “abbcad”
 
1. Saving each char's index in s1
 a: 0,3
 b: 1,4 
 c: 2,5
 
 2.  converting s2 into a list of number.
    Note that if there are two different index of one char, it should be sorted from big to small, in case of repetive counting.
--> {3,0,4,1,4,1,5,2,3,0} 

 Doing LIS: {0,1,2,3}，length=4  ，and we can know the correspond string is ”abca”.


## Time Complex Analysis - improved LCS
a.	Fetching corresponding index of each char in s1 :O(n)
b.	Fetching the converting number of s2 by the rule of process a. : O(nlogn)  
**The searching time of red-black tree is O(logn)**
c.	Doing LIS : O(nlogn). **By BinarySearch O(logn)**
d.	Matching the result of LIS to string(LCS):O(n)

To sum up , the time complex can be shrink to O(nlogn)

## The comparison
Original :
<img width="258" alt="image" src="https://user-images.githubusercontent.com/57362375/136911072-5eb09a8a-a06c-43a0-ab55-ed61951e5790.png">
Imporved:
<img width="258" alt="image" src="https://user-images.githubusercontent.com/57362375/136911085-4f422cd4-ff5f-4ba3-9e29-00fe5177c129.png">

By creating 100 date set, each length is 10,40,70....2980, we can draw the picture following:
<img width="468" alt="image" src="https://user-images.githubusercontent.com/57362375/136911442-ebe8c921-361b-4618-88a6-86d1bc3e8eab.png">

