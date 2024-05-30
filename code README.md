54257 abubakar awan
53102 muqeet ahmed
code
package bakar;

import java.util.Random;
import java.util.Scanner;

// Abstract class demonstrating abstraction
abstract class Ticket {
    private String movieName;
    private String seatNumber;
    private double price;

    // Constructor
    public Ticket(String movieName, String seatNumber, double price) {
        this.movieName = movieName;
        this.seatNumber = seatNumber;
        this.price = price;
    }

    // Getter and Setter methods demonstrating encapsulation
    public String getMovieName() {
        return movieName;
    }

    public void setMovieName(String movieName) {
        this.movieName = movieName;
    }

    public String getSeatNumber() {
        return seatNumber;
    }

    public void setSeatNumber(String seatNumber) {
        this.seatNumber = seatNumber;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }

    // Abstract method
    public abstract void printTicket();
}

// Child class demonstrating inheritance and polymorphism
class MovieTicket extends Ticket {

    private String userName; // Adding userName attribute

    // Constructor
    public MovieTicket(String movieName, String seatNumber, double price, String userName) {
        super(movieName, seatNumber, price);
        this.userName = userName;
    }

    // Overriding the abstract method demonstrating polymorphism
    @Override
    public void printTicket() {
        System.out.println("---------- Movie Ticket ----------");
        System.out.println("Your name: " + userName); // Printing user's name
        System.out.println("Movie: " + getMovieName());
        System.out.println("Seat: " + getSeatNumber());
        System.out.println("Price: $" + getPrice());
        System.out.println("----------------------------------");
    }
}

// Main class to test the Theater Ticket System
public class Bakar {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        // Asking user input for their name
        System.out.print("Enter your name: ");
        String userName = scanner.nextLine();

        // Asking user input for movie details
        System.out.print("Enter the movie name: ");
        String movieName = scanner.nextLine();

        System.out.print("Enter the seat number: ");
        String seatNumber = scanner.nextLine();

        // Generating a random price for the ticket
        double price = 5.0 + (15.0 - 5.0) * random.nextDouble();

        // Creating an object of MovieTicket
        Ticket ticket = new MovieTicket(movieName, seatNumber, price, userName);

        // Printing the ticket
        ticket.printTicket();

        scanner.close();
    }
}
