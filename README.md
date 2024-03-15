# demo
This is my first Git repository
Author- Suraj Nishad

My Project- class Product:
    def __init__(self, name, price):
        self.name = name
        self.price = price

class ShoppingCart:
    def __init__(self):
        self.items = []

    def add_item(self, product):
        self.items.append(product)

    def total_price(self):
        return sum(item.price for item in self.items)

def main():
    products = [
        Product("Laptop", 1000),
        Product("Phone", 500),
        Product("Headphones", 100),
        Product("Mouse", 50)
    ]

    cart = ShoppingCart()

    print("Welcome to the Simple Shopping App!")
    print("Available Products:")
    for i, product in enumerate(products, start=1):
        print(f"{i}. {product.name} - ${product.price}")

    while True:
        choice = input("Enter the product number to add to cart (or 'checkout' to finish): ")
        if choice.lower() == 'checkout':
            break
        try:
            choice = int(choice)
            if 1 <= choice <= len(products):
                selected_product = products[choice - 1]
                cart.add_item(selected_product)
                print(f"{selected_product.name} added to cart.")
            else:
                print("Invalid product number.")
        except ValueError:
            print("Invalid input. Please enter a product number or 'checkout'.")

    print("\nYour Shopping Cart:")
    for item in cart.items:
        print(f"- {item.name}: ${item.price}")
    print(f"Total: ${cart.total_price()}")

if __name__ == "__main__":
    main()


