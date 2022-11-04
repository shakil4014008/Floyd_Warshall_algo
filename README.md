# Floyd_Warshall_algo [Dynamic Programming algo]

```` Python
The problem is to find the shortest distances between every pair of vertices in a given edge-weighted directed graph. 
The graph is represented as an adjacency matrix of size n*n. Matrix[i][j] denotes the weight of the edge from i to j. 
If Matrix[i][j]=-1, it means there is no edge from i to j. Do it in-place.

Example 1:

Input: matrix = {{0,25},{-1,0}}
Output: {{0,25},{-1,0}}
Explanation: The shortest distance between every pair is already given(if it exists).

Example 2:
Input: matrix = {{0,1,43},{1,0,6},{-1,-1,0}}
Output: {{0,1,7},{1,0,6},{-1,-1,0}}
Explanation: We can reach 3 from 1 as 1->2->3 and the cost will be 1+6=7 which is less than 43.


	def floyd_shortest_distance(self, matrix):
		#we need this if input comes -1 instead of INF
		for i in range(len(matrix)):
		    for j in range(len(matrix)):
		        if matrix[i][j] == -1:
		            matrix[i][j] = float('inf')
        for k in range(len(matrix)):
            for i in range(len(matrix)):
                for j in range(len(matrix)):
                    matrix[i][j] = min(matrix[i][j], matrix[i][k] + matrix[k][j])   
    
		for i in range(len(matrix)):
		    for j in range(len(matrix)):
		        if matrix[i][j] == float('inf'):
		            matrix[i][j] = -1
````
