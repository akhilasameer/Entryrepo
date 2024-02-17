# Banking System 
Entry Projects

Here is the video link which explaining the working of the code

https://drive.google.com/file/d/1NJDTJykXv5qjD3eTcWidbtyxWYBYUN8y/view?usp=drivesdk


# creation Bank_Account class
class Bank_Account:
    def __init__(self):
        self.balance = 0
        self.name = ""
        self.password = ""
# welcome function
    def login(self):
       self.name = input("Hello!!! welcome to your Bank Account\nplease enter your name: ")
       self.password = input("please enter your password")
       print(input("You are successfully logged in"))
# balance function
    def current_balance(self):
        print("your current balance is: ",self.balance)
# deposit function
    def deposit(self):
        amount = float(input("Hello {},Please enter amount to be deposited: ".format(self.name)))
        self.balance += amount
        self.current_balance()
# withdraw function
    def withdraw(self):
        amount_withdraw = float(input("Enter amount to be withdraw: "))
        if amount_withdraw > self.balance:
            print("Insufficient balance")
        else:
            self.balance -= amount_withdraw
            print("Amount withdrawn: ",amount_withdraw)
        self.current_balance()

bank = Bank_Account()
bank.login()
while True:
    menu = int(input("Choose your menu\n1. Balance\n2. Deposit\n3. Withdrawal\n4. Exit"))
    if menu == 1:
        bank.current_balance()
    elif menu == 2:
        bank.deposit()
    elif menu == 3:
        bank.withdraw()
    elif menu == 4:
        print("Thank you for banking with us")
        break
    else:
        print("Please enter valid input")
