# JAVA-QUS-3
//######################################QUS 1#########################################

import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class FileReaderDemo {
    public static void main(String[] args) {
        Scanner inputScanner = new Scanner(System.in);
        System.out.print("Enter the file name: ");
        String fileName = inputScanner.nextLine();

        File file = new File(fileName);

        try (Scanner fileScanner = new Scanner(file)) {
            System.out.println("Content of " + fileName + ":");
            while (fileScanner.hasNextLine()) {
                String line = fileScanner.nextLine();
                System.out.println(line);
            }
        } catch (FileNotFoundException e) {
            System.out.println("Error: File not found. Please make sure the file exists.");
        } catch (Exception e) {
            System.out.println("An unexpected error occurred: " + e.getMessage());
        }

        inputScanner.close();
    }
}

//###########################################QUS2####################################################

import java.util.Scanner;

public class DivisionExceptionDemo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            // Get user input
            System.out.print("Enter numerator: ");
            int numerator = scanner.nextInt();

            System.out.print("Enter denominator: ");
            int denominator = scanner.nextInt();

            // Try to perform the division
            int result = numerator / denominator;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Division by zero is not possible.");
        } catch (Exception e) {
            System.out.println("An unexpected error occurred: " + e.getMessage());
        } finally {
            scanner.close(); // Ensure the Scanner is closed
        }
    }
}

//####################################QUS 3###############################################

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class BufferedReaderDemo {
    public static void main(String[] args) {
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));

        try {
            // Prompt for name
            System.out.print("Enter your name: ");
            String name = reader.readLine();

            // Prompt for age
            System.out.print("Enter your age: ");
            int age = Integer.parseInt(reader.readLine());

            // Display formatted message
            System.out.println("Hello, " + name + "! You are " + age + " years old.");

        } catch (IOException e) {
            System.out.println("An error occurred while reading input.");
        } catch (NumberFormatException e) {
            System.out.println("Invalid input. Please enter a valid number for age.");
        }
    }
}

//########################################QUS 4##########################################

import java.util.ArrayList;
import java.util.LinkedList;
import java.util.HashSet;

public class CollectionsDemo {
    public static void main(String[] args) {
        // 1. ArrayList
        ArrayList<String> arrayList = new ArrayList<>();
        arrayList.add("Apple");
        arrayList.add("Banana");
        arrayList.add("Cherry");
        System.out.println("ArrayList elements: " + arrayList);

        // 2. LinkedList
        LinkedList<String> linkedList = new LinkedList<>();
        linkedList.add("Dog");
        linkedList.add("Elephant");
        linkedList.add("Fox");
        System.out.println("LinkedList elements: " + linkedList);

        // 3. HashSet
        HashSet<String> hashSet = new HashSet<>();
        hashSet.add("Guitar");
        hashSet.add("Harp");
        hashSet.add("Guitar"); // Duplicate to show uniqueness
        hashSet.add("Violin");
        System.out.println("HashSet elements: " + hashSet);
    }
}
