# CS2-Lunch-Price-Calculator
# Lunch Price Calculator System
# Members:
# Rhiane Caye N. Salubre
# Venice Richzyl Mae T. Alquizar
# Jude Christian A. Carcasona

    def print_title():
        print("====================================")
        print("      LUNCH PRICE CALCULATOR         ")
        print("====================================")
        print("Follow the instructions to place your order.\n")

    while True:
        print_title()

        # Input Stage
        name = input("Customer Name (optional): ")

        quantity_input = input("Enter Quantity of Meals: ")
        if not quantity_input.isdigit() or int(quantity_input) <= 0:
            print("Error: Quantity must be a number greater than 0.\n")
            continue
        quantity = int(quantity_input)

        # Meal Type Selection
        print("\nSelect Meal Type:")
        print("1 - Regular (50)")
        print("2 - Special (75)")
        print("3 - Premium (100)")
        meal_choice = input("Enter choice (1-3): ")

        if meal_choice == "1":
            meal_name = "Regular"
            meal_price = 50
        elif meal_choice == "2":
            meal_name = "Special"
            meal_price = 75
        elif meal_choice == "3":
            meal_name = "Premium"
            meal_price = 100
        else:
            print("Error: Invalid meal type.\n")
            continue

        # Optional Add-ons
        addons_cost = 0
        addons_list = []

        add_drink = input("Add drink? (y/n): ").lower()
        if add_drink == "y":
            addons_cost += 20
            addons_list.append("Drink")

        add_rice = input("Add extra rice? (y/n): ").lower()
        if add_rice == "y":
            addons_cost += 10
            addons_list.append("Extra Rice")

        add_dessert = input("Add dessert? (y/n): ").lower()
        if add_dessert == "y":
            addons_cost += 30
            addons_list.append("Dessert")

        # Computation Stage
        base_price = meal_price * quantity
        total_price = base_price + addons_cost

        # Output Section
        print("\n========== ORDER SUMMARY ==========")
        print(f"Customer Name: {name if name else 'N/A'}")
        print(f"Meal Type: {meal_name}")
        print(f"Quantity: {quantity}")
        print(f"Base Price: {base_price}")
        print(f"Add-ons: {', '.join(addons_list) if addons_list else 'None'}")
        print(f"Add-ons Cost: {addons_cost}")
        print(f"Total Price: {total_price}")
        print("Thank you for using the Lunch Price Calculator!")
        print("====================================\n")

        # Reset or Exit Stage
        print("1 - Calculate Again")
        print("2 - Exit Program")
        next_step = input("Enter choice (1-2): ")
        if next_step == "2":
            print("Program closed. Goodbye!")
            break
        print("\n")  # space before next calculation
