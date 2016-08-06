There are a few simple tips to make code more concise, and beauty. 

##Less Code Maker
cons: ```
      if(i == 0) return j;  
      
      if(j == 0) return i;
      ```
pros: `if(i==0 || j==0) return i + j;`   

##Follow the logic, No turn
cons: `if(isOK != true) doSomething();` 
pros: `if(isOK == false) doSomething();` 

cons: `return v1 < v2 ? v1 : v2;`
pros: `return v1 > v2 ? v2 : v1;` 


