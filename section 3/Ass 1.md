# Assignment 1


## Solution java
```java
import java.util.Scanner;
 
public class Myproject {
 
    public static void main(String[] args) {
         
     Scanner input= new Scanner(System.in);
      
           System.out.println("Enter 3 - digit  "); 
          int num1=input.nextInt();
          int num2=input.nextInt();
          int num3=input.nextInt();
          if(num1 == num3)
          {
             System.out.println("the number is palindrome");
          }
          else
          {
              System.out.println("the number is not palindrome");
          }
    }
}




```

