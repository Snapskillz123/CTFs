```java
import java.io.*;
import java.util.Scanner;

public class FileOperations {

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        while (true) {
            System.out.println("\nMenu:");
            System.out.println("1. Write to a file");
            System.out.println("2. Read from a file");
            System.out.println("3. Copy bytes from one file to another file");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            int choice = scanner.nextInt();
            scanner.nextLine();  // Consume the newline

            switch (choice) {
                case 1:
                    writeFile();
                    break;
                case 2:
                    readFile();
                    break;
                case 3:
                    copyFile();
                    break;
                case 4:
                    System.out.println("Exiting...");
                    return;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    // Method to write to a file
    private static void writeFile() {
        System.out.print("Enter the filename to write to: ");
        String filename = scanner.nextLine();
        System.out.print("Enter the content to write: ");
        String content = scanner.nextLine();

        try (FileOutputStream fos = new FileOutputStream(filename)) {
            fos.write(content.getBytes());
            System.out.println("Content written to file successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred while writing to the file.");
            e.printStackTrace();
        }
    }

    // Method to read from a file
    private static void readFile() {
        System.out.print("Enter the filename to read from: ");
        String filename = scanner.nextLine();

        try (FileInputStream fis = new FileInputStream(filename)) {
            System.out.println("Reading content from file:");
            int byteData;
            while ((byteData = fis.read()) != -1) {
                System.out.print((char) byteData);
            }
            System.out.println();  // Newline after file content
        } catch (IOException e) {
            System.out.println("An error occurred while reading from the file.");
            e.printStackTrace();
        }
    }

    // Method to copy bytes from one file to another file
    private static void copyFile() {
        System.out.print("Enter the source filename: ");
        String sourceFile = scanner.nextLine();
        System.out.print("Enter the destination filename: ");
        String destFile = scanner.nextLine();

        try (FileInputStream fis = new FileInputStream(sourceFile);
             FileOutputStream fos = new FileOutputStream(destFile)) {

            int byteData;
            while ((byteData = fis.read()) != -1) {
                fos.write(byteData);
            }
            System.out.println("File copied successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred while copying the file.");
            e.printStackTrace();
        }
    }
}
```
