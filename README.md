
package homework2.classes;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.println("Podaj pierwsza liczbę: ");

        int aInt = 0;
        boolean zlawarosc= true;
        while(zlawarosc==true) {
            String a = scanner.nextLine();

            if (a == null || a.length() == 0) {
                System.out.println("Musisz podać liczbę jeszcze raz: ! ");
                zlawarosc=true;
            } else {
                try {
                    aInt = Integer.parseInt(a);
                    zlawarosc= false;
                } catch (NumberFormatException e) {
                    System.out.println("Podana wartość jest nieprawidłowa! Podaj wartosc jeszcze raz:  ");
                }
            }
        }
        System.out.println("Podaj druga liczbę: ");
        int bInt =0;
        boolean zlawarosc2= true;
        while(zlawarosc2==true) {
            String b = scanner.nextLine();

            if (b == null || b.length() == 0) {
                System.out.println("Musisz podać liczbę jeszcze raz: ! ");
                zlawarosc2=true;
            } else {
                try {
                    bInt = Integer.parseInt(b);
                    zlawarosc2= false;
                } catch (NumberFormatException e) {
                    System.out.println("Podana wartość jest nieprawidłowa! Podaj wartosc jeszcze raz:  ");
                }
            }
        }

        dzielenie(aInt, bInt);
        mnozenie(aInt, bInt);
    }
    static double dzielenie(int a, int b) {
        double wynik=0;
        if (b < 5){
            wynik = a / b;
            System.out.println("Iloraz liczb: " + wynik);
        }
        return wynik;
    }
    static double mnozenie(int c, int d) {
        int wynik = 0;
        if (d >= 5) {
            wynik = c * d;
            System.out.println("Iloczyn liczb: " + wynik);
        }
        return wynik;
    }
}





package homework2.classes;

import homework2.classes.Main;
import static org.junit.jupiter.api.Assertions.*;

import org.junit.jupiter.api.Test;
import org.testng.annotations.ITestAnnotation;

class MainTest {

    Main t= new Main();


    @Test
    void testmnozenie(){
        int x=56;
        int y=7;
        assertEquals(392, t.mnozenie(x,y) );
    }

    @Test
    void testdzielenie(){
        int x=15;
        int y=3;
        assertEquals(5, t.dzielenie(x,y));
    }
    @Test
    void testmain() throws NumberFormatException{
    }
    @Test
    void testmain2() throws ArithmeticException{
        int x=56;
        int y=0;
        assertEquals(392, t.dzielenie(x,y) );
    }
}
