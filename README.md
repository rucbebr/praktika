# praktika
1 задача

year = int(input("Введите год: "))

def visok(year):
    if year % 4 == 0 and year % 100 != 0 or year % 400 == 0:
        return True
    else:
        return False

print(visok(year))




2 задача

year = int(input("Введите год: "))

def days(year):
    if year % 4 == 0 and year % 100 != 0 or year % 400 == 0:
        return 366
    else:
        return 365

print(f"В этом году {days(year)} дней")


3 задача

def date(day, month, year):
    if day <= 0 or month <= 0 or year < 0:
        return False
    else:
        months = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
        if month > 12:
           return False
        else:
            if visok(year) == True:  months[1] = 29
            if day <= months[month - 1]:
                if month <= 12:
                    return True
            return False
       
       
def visok(year):
    if year % 4 == 0 and year % 100 != 0 or year % 400 == 0:
        return True
    else:
        return False

day = int(input('День: '))
month = int(input('Месяц: '))
year = int(input('Год: '))
print(date(day, month, year))



4 задача

