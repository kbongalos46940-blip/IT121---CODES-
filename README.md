def withdrawal_system():
    balance = 5000

    while True:
        print("\n--- Simple Money Withdrawal System ---")
        print("1. Withdraw Money")
        print("2. Check Balance")
        print("3. Exit")

        choice = input("Choose an option (1/2/3): ")

        if choice == "1":
            try:
                amount = float(input("Enter amount to withdraw: "))

                if amount <= 0:
                    print("Invalid amount. Please enter a positive number.")
                    continue

                if amount > balance:
                    print("Insufficient funds!")
                    print("\nOptions:")
                    print("1. Exit")
                    print("2. Check Balance")
                    print("3. Try Again")

                    option = input("Choose an option (1/2/3): ")

                    if option == "1":
                        print("Exiting...")
                        break
                    elif option == "2":
                        print(f"Your current balance is: {balance}")
                    elif option == "3":
                        continue
                    else:
                        print("Invalid choice.")

                else:
                    balance -= amount
                    print(f"Withdrawal successful! Remaining balance: {balance}")

            except ValueError:
                print("Error: Invalid input. Please enter a number.")

        elif choice == "2":
            print(f"Your current balance is: {balance}")

        elif choice == "3":
            print("Thank you for using the system!")
            break

        else:
            print("Invalid choice. Please select 1, 2, or 3.")


withdrawal_system()
