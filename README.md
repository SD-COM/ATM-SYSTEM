# ATM-SYSTEM

pin = 4423
balance = 500000
attempts = 3

print("================================")
print("       WELCOME TO ATM")
print("================================")

while attempts > 0:
    entered_pin = int(input("\nEnter your ATM PIN: "))

    if entered_pin == pin:
        print("\nLogin Successful!")
        break
    else:
        attempts = attempts - 1
        print("Incorrect PIN!")

        if attempts > 0:
            print("You have", attempts, "attempts remaining.")
        else:
            print("Your ATM access is blocked!")

if entered_pin == pin:
    while True:
        print("\n------ ATM MENU ------")
        print("1. Check Balance")
        print("2. Withdraw Money")
        print("3. Deposit Money")
        print("4. Exit")

        choice = int(input("Enter your choice: "))

        if choice == 1:
            print("Your Current Balance is: Rs.", balance)

        elif choice == 2:
            amount = int(input("Enter amount to withdraw: "))

            if amount > 0 and amount <= balance:
                balance = balance - amount
                print("Please collect your cash.")
                print("Remaining Balance: Rs.", balance)
            else:
                print("Insufficient Balance or Invalid Amount!")

        elif choice == 3:
            amount = int(input("Enter amount to deposit: "))

            if amount > 0:
                balance = balance + amount
                print("Amount Deposited Successfully!")
                print("Updated Balance: Rs.", balance)
            else:
                print("Invalid Deposit Amount!")

        elif choice == 4:
            print("Thank you for using our ATM!")
            break

        else:
            print("Invalid Choice! Please try again.")
