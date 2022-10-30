# Assignment 3


## Solution java
```java
import java.util.Scanner;
 
public class Myproject {
 
    public static void main(String[] args) {
         
     Scanner input= new Scanner(System.in);
      
           System.out.println("Enter an three edges  : "); 
          int num1=input.nextInt();
           int num2=input.nextInt();
           int num3=input.nextInt();
          if((num1 +num2) >num3 &&(num1 +num3) >num2&& (num3 +num2) >num1  )
          {
             System.out.println("The input is valid");
             int perimeterTriangle=num1+num2+num3;
           System.out.println("The perimeter of Triangle is : "+perimeterTriangle);  
          }
          else
          {
              System.out.println("The input is  not valid");
          }
    }
}





```

