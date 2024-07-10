import java.util.ArrayList;
import java.util.Scanner;

public class ContactManager {

    private static Scanner scanner = new Scanner(System.in);
    private static ArrayList<Contact> contacts = new ArrayList<>();

    public static void main(String[] args) {
        int choice;

        do {
            System.out.println("\nContact Manager");
            System.out.println("1. Add Contact");
            System.out.println("2. View Contacts");
            System.out.println("3. Delete Contact");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    addContact();
                    break;
                case 2:
                    viewContacts();
                    break;
                case 3:
                    deleteContact();
                    break;
                case 4:
                    System.out.println("Exiting Contact Manager...");
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        } while (choice != 4);
    }

    private static void addContact() {
        System.out.print("Enter name: ");
        String name = scanner.nextLine();
        scanner.nextLine(); // Consume extra newline character

        System.out.print("Enter phone number (optional): ");
        String phone = scanner.nextLine();

        System.out.print("Enter email address (optional): ");
        String email = scanner.nextLine();

        contacts.add(new Contact(name, phone, email));
        System.out.println("Contact added successfully!");
    }

    private static void viewContacts() {
        if (contacts.isEmpty()) {
            System.out.println("There are no contacts to display.");
            return;
        }

        System.out.println("\nContact List:");
        for (int i = 0; i < contacts.size(); i++) {
            System.out.println(i + 1 + ". " + contacts.get(i));
        }
    }

    private static void deleteContact() {
        if (contacts.isEmpty()) {
            System.out.println("There are no contacts to delete.");
            return;
        }

        viewContacts();

        System.out.print("Enter the number of the contact to delete (or 0 to cancel): ");
        int choice = scanner.nextInt() - 1;

        if (choice >= 0 && choice < contacts.size()) {
            contacts.remove(choice);
            System.out.println("Contact deleted successfully!");
        } else {
            System.out.println("Invalid choice.");
        }
    }
}

class Contact {
    private String name;
    private String phone;
    private String email;

    public Contact(String name, String phone, String email) {
        this.name = name;
        this.phone = phone;
        this.email = email;
    }

    @Override
    public String toString() {
        return "Name: " + name +
                (phone.isEmpty() ? "" : ", Phone: " + phone) +
                (email.isEmpty() ? "" : ", Email: " + email);
    }
}
