# Bank-Account_Python

```python
class Person:

    def __init__(self, name, lastname):
        self.name = name
        self.lastname = lastname


class Client(Person):

    def __init__(self, name, lastname, nr_account, balance=0):
        super().__init__(name, lastname)
        self.nr_account = nr_account
        self.balance = balance

    def __str__(self):
        return f"Client Nº {self.name} {self.lastname}. Balance :${self.balance} in {self.nr_account} account."

    def deposit(self, money):
        self.balance += money
        print("Deposit accepted")

    def withdraw(self, money):
        if self.balance >= money:
            self.balance -= money
            print("Withdraw realized")
        else:
            print("Insufficient funds")


def create_client():
    name_cl = input("Please enter your name: ")
    lastname_cl = input("Please enter your lastname: ")
    nr_account_cl = input("Please enter your account number: ")
    client = Client(name_cl, lastname_cl, nr_account_cl)
    return client


def init():
    my_client = create_client()
    print(my_client)
    option = 0

    while option != 'F':
        print("Choose: Deposit (D), Withdraw (W) or Finish (F)")
        option = input()

        if option == "D":
            to_deposit = int(input("Money to deposit: "))
            my_client.deposit(to_deposit)

        elif option == "W":
            to_withdraw = int(input("Money to withdraw: "))
            my_client.withdraw(to_withdraw)

        print(my_client)

    print("Thank you for using Python Bank")


init()
```
