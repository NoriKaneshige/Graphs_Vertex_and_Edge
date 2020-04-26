# Graphs_Vertex_and_Edge


> ## Vertex and Edges creation for Graphs: :wink:
``` js
class Graph{
    constructor(){
        this.adjacencyList = {};
    }
    addVertex(vertex){
        if(!this.adjacencyList[vertex]) this.adjacencyList[vertex] = [];
    }

    addEdge(v1,v2){
        this.adjacencyList[v1].push(v2);
        this.adjacencyList[v2].push(v1);
    }

    removeEdge(vertex1,vertex2){
    	// take current adjacencyList, filter it, keep everything where it is not equal to vertex2
        this.adjacencyList[vertex1] = this.adjacencyList[vertex1].filter(
            v => v !== vertex2
        );
        this.adjacencyList[vertex2] = this.adjacencyList[vertex2].filter(
            v => v !== vertex1
        );
    }

    removeVertex(vertex){
        while(this.adjacencyList[vertex].length){
            const adjacentVertex = this.adjacencyList[vertex].pop();
            this.removeEdge(vertex, adjacentVertex);
        }
        delete this.adjacencyList[vertex]
    }

}

var g = new Graph()
g.addVertex("Tokyo")
console.log(g) // Graph { adjacencyList: { Tokyo: [] } }
console.log(g.adjacencyList) // { Tokyo: [] }
console.log(g.adjacencyList["Tokyo"]) // []
g.adjacencyList["Tokyo"].push("something")
console.log(g.adjacencyList["Tokyo"]) // [ 'something' ]
g.addVertex("Dallas")
g.addVertex("Aspen")
g.addEdge("Dallas","Tokyo")
console.log(g.adjacencyList) // { Tokyo: [ 'something', 'Dallas' ], Dallas: [ 'Tokyo' ], Aspen: [] }
g.removeEdge("Dallas","Tokyo")
console.log(g.adjacencyList) // { Tokyo: [ 'something' ], Dallas: [], Aspen: [] }

g.addVertex("Los Angeles");
g.addVertex("Hong Kong")
g.addEdge("Dallas", "Tokyo");
g.addEdge("Dallas", "Aspen");
g.addEdge("Hong Kong", "Tokyo");
g.addEdge("Hong Kong", "Dallas");
g.addEdge("Los Angeles", "Hong Kong");
g.addEdge("Los Angeles", "Aspen");
console.log(g.adjacencyList)
// {
//   Tokyo: [ 'something', 'Dallas', 'Hong Kong' ],
//   Dallas: [ 'Tokyo', 'Aspen', 'Hong Kong' ],
//   Aspen: [ 'Dallas', 'Los Angeles' ],
//   'Los Angeles': [ 'Hong Kong', 'Aspen' ],
//   'Hong Kong': [ 'Tokyo', 'Dallas', 'Los Angeles' ]
// }

g.removeVertex("Hong Kong")
console.log(g.adjacencyList)
// {
//   Tokyo: [ 'something', 'Dallas' ],
//   Dallas: [ 'Tokyo', 'Aspen' ],
//   Aspen: [ 'Dallas', 'Los Angeles' ],
//   'Los Angeles': [ 'Aspen' ]
// }

```
![edge_vertex](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/edge_vertex.png)
![undirected](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/undirected.png)
![directed](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/directed.png)
![weighted_graph](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/weighted_graph.png)
![adjacency_matrix](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/adjacency_matrix.png)
![adjacency_list](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/adjacency_list.png)
![adjacency_list_hash](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/adjacency_list_hash.png)
![ad_list_matrix_bigO_1](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/ad_list_matrix_bigO_1.png)
![ad_list_matrix_bigO_2](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/ad_list_matrix_bigO_2.png)
![adding_edge](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/adding_edge.png)
![removing_edge](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/removing_edge.png)
![removing_vertex_1](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/removing_vertex_1.png)
![removing_vertex_2](https://github.com/NoriKaneshige/Graphs_Vertex_and_Edge/blob/master/removing_vertex_2.png)
