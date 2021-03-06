Here are a few simple tips to make code more concise, and beauty. (in Java)

##Less Code Maker
1, magic number 0:   
con: 
```   
      if(m == 0) return n;    
      if(n == 0) return m;
```
pro: `if(m==0 || n==0) return m + n;`   

2, magic number 1:   
con: 
```   
      if(m == 1) return n;    
      if(n == 1) return m;
```    
pro: 
```   
      if(m==1 || n==1) return m * n;
```  

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
1) Less code in build up a graph when calling addEdge();  
2) We can easily build up edges with same vertex addEdge(v, x).addEdge(v,y).addEdge(v,z)...  
3) Or we can build up connections like addEdge(a, b).addEdge(b, c).addEdge(c, d)...  
```
      ...
      Graph addEdge(int v, int w) {
            // do something
            return this;
      }
      public static main(String[] args) {
            Graph g = new Graph();
            g.addEdge(3,4).addEdge(3,5);
            g.addEdge(2, 3).addEdge(3, 6).addEdge(6, 9).addEdge(9, 10);
            ...
      }
```

##Decisive Effect  
con:  
```
if(cond == false) 
      return statement;
else
      doSomething();
```  
pro:  
```
if(cond == false)
      return statement;
doSomething();
```  

      
