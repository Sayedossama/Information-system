# Assignment 2


## Solution java
```java
import java.util.Scanner;
 
public class Myproject {
 
    public static void main(String[] args) {
         
     Scanner input= new Scanner(System.in);
      
           System.out.println("Enter the minute: "); 
          int minute= input.nextInt();
          double resDay =minute /1440;
          System.out.println(resDay); 
          double resYear =resDay/365;
           System.out.println(resYear); 
    }
}

```

