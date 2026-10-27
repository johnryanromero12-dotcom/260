expenses = []

while True:
    print("\n=== EXPENSE TRACKER ===")
    print("1. Add Expense")
    print("2. View Expenses")
    print("3. Exit")

    choice = input("Choose an option: ")

    if choice == "1":
        name = input("Expense name: ").strip()

        if not name:
            print("Error: Name cannot be empty.")
            continue

        try:
            amount = float(input("Expense amount: ₱"))

            if amount <= 0:
                print("Error: Amount must be greater than zero.")
                continue

            expenses.append([name, amount])
            print("Expense added successfully!")

        except ValueError:
            print("Error: Enter a valid number.")

    elif choice == "2":
        total = 0
        print("\n=== YOUR EXPENSES ===")

        for name, amount in expenses:
            print(f"{name}: ₱{amount:.2f}")
            total += amount

        print(f"Total: ₱{total:.2f}")

    elif choice == "3":
        print("Thank you for using Expense Tracker!")
        break

    else:
        print("Invalid choice. Try again.")
