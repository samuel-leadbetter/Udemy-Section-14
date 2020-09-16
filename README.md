# Udemy-Section-14
Basic Input and Output including java.util
225. Exceptions
226. Stack Trace and Call Stack
227. Catching and Throwing Exceptions
228. Multi catch exceptions
_______________________________________________________________________________________________
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        int x = 98;
        int y = 0;
        System.out.println(divideLBYL(x, y));
       System.out.println(divideEAFP(x, y));
        System.out.println(divide(x, y));
        int x = getIntEAFP();
        System.out.println("x is " + x);
    }

    private static int getInt() {
        Scanner s = new Scanner(System.in);
        return s.nextInt();
    }

    private static int getIntLBYL() {
        Scanner s = new Scanner(System.in);
        boolean isValid = true;
        System.out.println("Enter integer ");
        String input = s.next();
        for(int i = 0; i < input.length(); i++) {
            if(!Character.isDigit(input.charAt(i))) {
                isValid = false;
                break;
            }
        }
        if(isValid) {
            return Integer.parseInt(input);
        }
        return 0;
    }

    private static int getIntEAFP() {
        Scanner s = new Scanner(System.in);
        System.out.println("Enter integer ");
        try {
            return s.nextInt();
        } catch(InputMismatchException e) {
            return 0;
        }

    }

    private static int divideLBYL(int x, int y) {
        if(y != 0) {
            return x / y;
        } else {
            return 0;
        }
    }

    private static int divideEAFP(int x, int y) {
        try {
            return x / y;
        } catch(ArithmeticException e) {
            return 0;
        }
    }

    private static int divide(int x, int y) {
        return x / y;
    }
}
________________________________________________________________________________________________

import java.util.InputMismatchException;
import java.util.NoSuchElementException;
import java.util.Scanner;

public class Example {

    public static void main(String[] args) {
        try {
            int result = divide();
            System.out.println(result);
        } catch (ArithmeticException | NoSuchElementException e) {
            System.out.println(e.toString());
            System.out.println("Unable to perform division");
        }
    }

    private static int divide() {
        int x, y;
            x = getInt();
            y = getInt();
            System.out.println("x is " + x + ", y is " + y);
            return x / y;
    }

    private static int getInt() {
        Scanner s = new Scanner(System.in);
        System.out.println("Enter integer ");
        while(true) {
            try {
                return s.nextInt();
            } catch(InputMismatchException e) {
                s.nextLine();
                System.out.println("Invalid input. Enter integer ");
            }
        }
    }
}
