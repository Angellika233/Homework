# Homework
import java.util.HashMap;
import java.util.Map;

public class Homework {

    public static void main(String[] args) {

        Map<String, Integer> semestZimowy = new HashMap<>();
        semestZimowy.put("Analiza matematyczna", 4);
        semestZimowy.put("Mikroekonomia", 3);
        semestZimowy.put("Statystyka", 4);
        semestZimowy.put("Układy cyfrowe", 5);
        semestZimowy.put("Ekonometria przestrzenna", 4);

        // sprawdzenie czy element należy do kolekcji
        System.out.println("Przedmiot istnieje w kolekcji: " + semestZimowy.containsKey("Ekonometria przestrzenna"));
        System.out.println("Ocena z Ekonometria przestrzenna: " + (semestZimowy.get("Ekonometria przestrzenna")));
        if(semestZimowy.get("Ekonometria przestrzenna") == null)
            System.out.println(" Przedmiot nie istnieje w kolekcji!");

        int i=0;
        for( String key : semestZimowy.keySet()) {
            i++;
        }
        int j=0;
        for (Integer value : semestZimowy.values()) {
            j++;
        }

        System.out.println("Liczba przedmiotów: " + i + ",liczba ocen: " + j);
        if (i==j)
            System.out.println("Liczba ocen jest równa liczbie przedmiotów");
        else
            System.out.println("Liczba nie jest równa");

        Map<String, Integer> obaSemestry = new HashMap<>();
        obaSemestry.putAll(semestZimowy);
        obaSemestry.put("Mikroekonomia", 3);
        obaSemestry.put("Finanse publiczne", 5);

        for( String key : obaSemestry.keySet())
        {
            System.out.println(key);
        }
        System.out.println("Ilość przedmiotów uniklanych: " + obaSemestry.size());
    }
}
