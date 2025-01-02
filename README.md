#JAVA-PROGRAM-TO-READ-WRITE-AND-MODIFY-TEXT-FILES 

**Company**:codtech it solutions

**Name**:Devaraj P

**Intern ID**:CT6WTDS626

**Domain**:java programming

**Batch Duration**:NOVEMBER 25th,2024 to JANUARY 10th,2025

**Mentor Name**:Neela Santhosh

Key Features:

1. File Writing (writeToFile):

Creates or overwrites a file with specified content.

Writes two predefined lines of text to the file.

2. File Reading (readFromFile):

Reads the content of the file line by line and prints it to the console.

Ensures file content is accessible for verification.

3. File Modification (modifyFile):

Appends additional content to an existing file without overwriting it.

Adds a predefined line of text to the file.

4. Error Handling:

Catches and reports exceptions related to file I/O operations.

Prints stack traces for debugging in case of errors.

5. User Interaction:

Provides clear console messages to inform the user of operations being performed and their success.

6. Resource Management:

Uses try-with-resources to automatically close file streams, ensuring efficient resource handling.

Objectives:

1. Demonstrate Basic File I/O in Java:

Show how to read, write, and append to text files using BufferedWriter and BufferedReader.

2. Handle Common File Operations:

Perform essential file manipulations (write, read, modify) in a structured way.

3. Provide a Modular Design:

Use separate methods for distinct operations to improve readability, maintainability, and reusability.

4. Ensure Data Persistence:

Save data to a file so it can be accessed and modified later.

5. Illustrate Exception Handling:

Safeguard against I/O errors, ensuring the program doesn’t crash unexpectedly.

6. Educate on Best Practices:

Show efficient resource management using try-with-resources.

Provide clean separation of concerns between methods.

program:
import java.io.*;
import java.nio.file.*;
import java.util.Scanner;

public class FileOperations {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // File path to read/write
        String filePath = "example.txt";

        // Write to file
        writeToFile(filePath);

        // Read from file
        readFromFile(filePath);

        // Modify file (append text to the file)
        modifyFile(filePath);

        // Read the file again after modification
        readFromFile(filePath);
    }

    // Method to write data to the file
    public static void writeToFile(String filePath) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filePath))) {
            writer.write("This is the first line in the file.\n");
            writer.write("This is the second line in the file.\n");
            System.out.println("Data written to the file successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred while writing to the file.");
            e.printStackTrace();
        }
    }

    // Method to read data from the file
    public static void readFromFile(String filePath) {
        try (BufferedReader reader = new BufferedReader(new FileReader(filePath))) {
            String line;
            System.out.println("Reading from file:");
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("An error occurred while reading from the file.");
            e.printStackTrace();
        }
    }

    // Method to modify (append) data to the file
    public static void modifyFile(String filePath) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filePath, true))) {
            writer.write("This is an additional line appended to the file.\n");
            System.out.println("Data appended to the file successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred while modifying the file.");
            e.printStackTrace();
        }
    }
}
