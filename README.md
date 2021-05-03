# banking-system
class User:
    def __init__(self, name, age, gender):
        self.name= name
        self.age=age
        self.gender=gender
    def show_details(self):
        print(f'''
        Name:{self.name}
        Age: {self.age}
        Gender: {self.gender}''')
        

class Bank(User):
        def __init__(self, name, age, gender):
            super().__init__(name, age, gender)
            self.balance=0
            
        def Deposit(self, amount):
            self.amount=amount
            self.balance+=self.amount
            print(f'account balance has been updated={self.balance} AZN')
            
        def withdraw(self, amount):
            self.amount=amount 
            if self.amount>self.balance:
                print(f'insufficient funds! your balance: {self.balance}AZN')
            else:
                self.balance-=self.amount
            print(f'account balance has been updated:{self.balance} AZN')
            
        def view_balance(self):
            self.show_details()
            print(f'your balance: {self.balance} AZN')
            
personal = Bank('mahesh', 20, 'male')
personal.show_details()
personal.Deposit(200)
personal.withdraw(50)
personal.view_balance()
personal.withdraw(180)
