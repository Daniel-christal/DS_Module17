# Ex24 Topological Sort
## AIM:
To compose the code to determine whether the topological ordering for the following graph is possible or not.

![image](https://github.com/user-attachments/assets/c74a7111-9b59-475c-aad4-9baf23d50ec0)


## Algorithm
1.Initialize variables:

Declare i, v, count, topo_order[MAX], and indeg[MAX].
2.Create the graph:

Call create_graph() to initialize the graph structure.
Calculate indegree for each vertex:

3.For each vertex i from 0 to n-1:
Calculate indeg[i] using indegree(i).
If indeg[i] is 0, insert vertex i into the queue using insert_queue(i).
4.Perform topological sorting:

Initialize count to 0.
5.While the queue is not empty and count is less than n:
Remove vertex v from the queue using delete_queue().
Add vertex v to topo_order at index ++count.
6.For each vertex i from 0 to n-1:
If there is an edge from v to i (i.e., adj[v][i] == 1):
Remove the edge by setting adj[v][i] to 0.
Decrease indeg[i] by 1.
If indeg[i] becomes 0, insert vertex i into the queue.
Check for cycles:

If count is less than n, print "No topological ordering possible, graph contains cycle" and exit the program.
7.Print the topological order:

Print "Vertices in topological order are:".
For each index i from 1 to count, print topo_order[i].
8.End the program:

Return 0 to indicate successful completion.
## Program:
```
/*
Program to determine whether the topological ordering for the following graph is possible or not
Developed by: Daniel C
RegisterNumber: 212223240023
int main()
{
        int i,v,count,topo_order[MAX],indeg[MAX];

        create_graph();

        /*Find the indegree of each vertex*/
        for(i=0;i<n;i++)
        {
                indeg[i] = indegree(i);
                if( indeg[i] == 0 )
                        insert_queue(i);
        }

        count = 0;

        while(  !isEmpty_queue( ) && count < n )
        {
                v = delete_queue();
        topo_order[++count] = v; /*Add vertex v to topo_order array*/
                /*Delete all edges going from vertex v */
                for(i=0; i<n; i++)
                {
                        if(adj[v][i] == 1)
                        {
                                adj[v][i] = 0;
                                indeg[i] = indeg[i]-1;
                                if(indeg[i] == 0)
                                        insert_queue(i);
                        }
                }
        }

        if( count < n )
        {
                printf("No topological ordering possible, graph contains cycle\n");
                exit(1);
        }
        printf("Vertices in topological order are :\n");
        for(i=1; i<=count; i++)
                printf( "%d ",topo_order[i] );
        printf("\n");

        return 0;
}/*End of main()*/

*/
```

## Output:
![image](https://github.com/user-attachments/assets/92892dbb-46b0-4a3f-b79d-e7aac16e4056)



## Result:
Thus, the C program for determining whether the topological ordering for the following graph is possible or not, is implemented successfully.
