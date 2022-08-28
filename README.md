class Car:
  def __init__(self, list0fcar = {'Hatchback' : 30,
                                  'Sedan' : 50,
                                  'SUV' : 100}):
    self.available = list0fcar

  def display_car(self):
    for car, price in self.available.items():
      print(car, 'for', price, '$')

  


  def rented_car(self, requested_car):
    if requested_car in self.available:
      r = dict(self.available)
      del r[requested_car]
      print('How many days you want to rent the car?')
      day_rent = int(input())
      cost = self.available[requested_car] * day_rent
      print(f'The cost is the following: {cost}')
    else:
      print('Sorry we do not have the car you asked')

  def added_car(self, returned_car):
    self.available[returned_car]
    print('Thank you so much')
    



class Customer:

  def car_request(self):
    print('Which type of car you want: ')
    self.car = input()
    return self.car

  def car_return(self):
    print('Which type of car you return: ')
    self.car = input()
    return self.car

  
car = Car()
customer = Customer()

print('Enter 1 to display the available cars')
print('Enter 2 to rent the available cars')
print('Enter 3 to return the available cars')
print('Enter 4 to quit')


while True:
  choice_car = int(input())
  if choice_car == 1:
    car.display_car()
  elif choice_car == 2:
    requested_car = customer.car_request()
    car.rented_car(requested_car)
  elif choice_car == 3:
    returned_car = customer.car_return()
    car.added_car(returned_car)
  else:
    quit()
