import java.util.*;

class Product {
    private int id;
    private String name;
    private double price;

    public Product(int id, String name, double price) {
        this.id = id;
        this.name = name;
        this.price = price;
    }

    // Getters
    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public double getPrice() {
        return price;
    }
}

class ShoppingCart {
    private List<Product> items;

    public ShoppingCart() {
        this.items = new ArrayList<>();
    }

    // Add product to cart
    public void addItem(Product product) {
        items.add(product);
    }

    // Get total price of items in cart
    public double getTotalPrice() {
        double totalPrice = 0;
        for (Product item : items) {
            totalPrice += item.getPrice();
        }
        return totalPrice;
    }
}

class Customer {
    private String name;
    private String email;
    private ShoppingCart cart;

    public Customer(String name, String email) {
        this.name = name;
        this.email = email;
        this.cart = new ShoppingCart();
    }

    // Getters
    public String getName() {
        return name;
    }

    public String getEmail() {
        return email;
    }

    // Add product to cart
    public void addToCart(Product product) {
        cart.addItem(product);
    }

    // Get total price of items in cart
    public double getCartTotal() {
        return cart.getTotalPrice();
    }
}

public class OnlineShoppingSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Creating instances of products
        System.out.println("Enter product details:");
        System.out.print("Product ID: ");
        int productId1 = scanner.nextInt();
        scanner.nextLine(); // Consume newline character
        System.out.print("Product Name: ");
        String productName1 = scanner.nextLine();
        System.out.print("Product Price: ");
        double productPrice1 = scanner.nextDouble();
        Product product1 = new Product(productId1, productName1, productPrice1);

        // Creating customer
        System.out.println("\nEnter customer details:");
        System.out.print("Name: ");
        scanner.nextLine(); // Consume newline character
        String customerName1 = scanner.nextLine();
        System.out.print("Email: ");
        String customerEmail1 = scanner.nextLine();
        Customer customer1 = new Customer(customerName1, customerEmail1);

        // Adding products to customer's cart
        customer1.addToCart(product1);

        // Displaying cart total
        System.out.println("\nCustomer: " + customer1.getName());
        System.out.println("Total in Cart: $" + customer1.getCartTotal());

        scanner.close();
    }
}
![Screenshot (37)](https://github.com/MachindraChitale/Onlone-Shpping-System/assets/155707916/946e542f-494e-4c96-ad3a-8bcc6a10d9c4)
