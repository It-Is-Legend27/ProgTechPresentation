# CMPS-4883-101 <br>Topics in Computer Science: Programming Techniques <br> UVa Online Judge Problem #10135: Herding the Frosh
## By: Angel Badillo ([@It-Is-Legend27](https://github.com/It-Is-Legend27/))<br>Date: 11/01/22
<br/>

### Problem summary:
##### [[Full problem statement here](https://onlinejudge.org/external/101/10135.pdf)]
You are given a set of Cartesian points that each represent the location of a "Frosh" (a college freshman) relative to the telephone post in meters. The telephone has the coordinate point of the origin (0,0). The goal is for all the "Frosh" to be round up with "the minimum amount of silk necessary to encircle all the Frosh". <sup>1</sup> The restriction is that there will be no more than 1000 Frosh.

### The Goal:
Essentially, the goal is to find the minimum length of silk need to surround all the "Frosh". The silk will be tied to a telephone pole, will enclose all the "Frosh" in a manner that the minimum length of silk will be used, and will finally return back to the telephone to be tied.

### How To Solve:
The solution here is to take the set of points in the test case to come up with a convex hull. Then, from there we will find the shortest length from the origin to a vertex of the convex hull. Once that is done, we will compute the length of silk,  _`l`_, using the perimeter of the polygon create by the convex hull, _`P`_, and the shortest length from the origin to a vertex, _`s`_. The formula for the shortest length of silk used will be:
```
l = P + 2s
```

### Explanation
Given the information in the problem statement, it is clear that the goal of the problem is to construct some sort of polygon, given the coordinates of the Frosh, where the polygon has the smallest perimeter possible. It can be ruled out that a non-convex polygon, or concave polygon would not be of good use in this situation, as it would not provide that shortest possible perimeter. Furthermore, even the smallest possible circle that will encompass all the freshman would be of no use, as it would still require constructing a polygon, a cylic polgyon to be exact. Taking that into consid

### Simple Psuedocode for the Solution
```python
# Coordinates of telephone pole
origin = (0,0)

# no. of test cases
T = input()

# Find the shortest length of silk for each case
for c = 0 : 1 : T
    
    # get no. of Frosh
    N = input()
    
    # Create viable data structure to hold N no. frosh coords
    F[N]
    
    # Read in all frosh coords
    for i = 0 : 1 : N
        F[i] = input()
    end-for
    
    # Find the set of points that form the convex hull, C, for given set of coords, F
    C = GrahamScan(F)
    
    # Compute the perimeter, P of convex hull
    P = perimeter(C)
    
    # Find shortest length from origin to vertex of convex hull
    S = shortestSide(origin, convexHull)
    
    # Calculate total length
    l = P + 2*s
    
    # Display the perimeter
    print(l)
end-for
```





<br>

## References:
1. [10135 Herding Frosh](https://onlinejudge.org/external/101/10135.pdf). https://onlinejudge.org/external/101/10135.pdf
1. GeeksforGeeks. [Convex Hull | Set 2 (Graham Scan)](https://www.geeksforgeeks.org/convex-hull-set-2-graham-scan/). GeeksforGeeks. Published July 24, 2013. https://www.geeksforgeeks.org/convex-hull-set-2-graham-scan/
1. GeeksforGeeks. [Quickhull Algorithm for Convex Hull](https://www.geeksforgeeks.org/quickhull-algorithm-convex-hull/). GeeksforGeeks. Published April 19, 2017. https://www.geeksforgeeks.org/quickhull-algorithm-convex-hull/