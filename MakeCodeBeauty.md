There are a few simple tips to make code more concise, and beauty. (in Java)

##Less Code Maker
con: 
```   
      if(i == 0) return j;    
      if(j == 0) return i;
```
pro: `if(i==0 || j==0) return i + j;`   

##Follow the logic, No turn
con: `if(isOK != true) doSomething();`   
pro: `if(isOK == false) doSomething();` 

con: `return v1 < v2 ? v1 : v2;`  
pro: `return v1 > v2 ? v2 : v1;` 

##Builder Effect
con:
```
public class Graph{  
      ...
      void addEdge(int v, int w) {
            // do something 
      }
      ...
      public static main(String[] args) {
            Graph g = new Graph();
            g.addEdge(3,4);
            g.addEdge(3,5);
            ...
      }
}
```
pro:
1) less code in build up a graph when calling addEdge();
2) You can easily build up edges with same vertex addEdge(v, x).addEdge(v,y).addEdge(v,z)... 
```
      ...
      Graph addEdge(int v, int w) {
            // do something
            return this;
      }
      public static main(String[] args) {
            Graph g = new Graph();
            g.addEdge(3,4).addEdge(3,5);
            ...
      }
```

