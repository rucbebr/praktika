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

def raznica(date1, date2):
    day1, month1, year1 = date1.split(".")
    day2, month2, year2 = date2.split(".")
    if len(day1) > 2 and len(day2) > 2:
        return False
    elif len(month1) > 2 and len(month2) > 2:
        return False
    elif len(year1) > 4 and len(year2) > 4:
        return False
    else:
        day1, month1, year1 = int(day1), int(month1), int(year1)
        day2, month2, year2 = int(day2), int(month2), int(year2)
        
        month1_raz = month1 * month_day(day1,month1,year1)
        month2_raz = month2 * month_day(day2,month2,year2)
        month_razni = month1_raz - month2_raz

        raz_year = (year1 - year2)*365
        raz_year = abs(raz_year)
        
        raz_month = abs(month_razni)
        
        raz_day = day1 - day2
        raz_day = abs(raz_day)

        all_raz = raz_day + raz_month + raz_year
        return all_raz


# фунция из задачи 1
def visok(year):
    if year % 4 == 0 and year % 100 != 0 or year % 400 == 0:
        return True 
    else: 
        return False

#функция для определения сколько дней в месяце
def month_day(day, month, year):
    if day <= 0 or month <= 0 or year < 0:
        return False
    else:
        months = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
        if month > 12:
           return False
        else:
            if visok(year) == True:  months[1] = 29
            month = months[month - 1]
            return month


date = str(input("Введите дату в формате dd.mm.yyyy: "))
date_1 = str(input("Введите дату в формате dd.mm.yyyy: "))
print(f"Разница в днях равна {raznica(date, date_1)}")



задача 4 моя
def raznica_v_days(date1, date2):
    text = "ERROR"
    day1, month1, year1 = date1.split(".")
    day2, month2, year2 = date2.split(".")
    if len(day1) > 2 and len(day2) > 2:
        return False
    elif len(month1) > 2 and len(month2) > 2:
        return False
    elif len(year1) > 4 and len(year2) > 4:
        return False
    else:
        day1, month1, year1 = int(day1), int(month1), int(year1)
        day2, month2, year2 = int(day2), int(month2), int(year2)
        
        if month_day(day1,month1,year1) == False:
            return text
        elif month_day(day2,month2, year2) == False:
            return text
        else:
            






cdjt
def raznica_v_days(date1, date2):
    text = "ERROR"
    day1, month1, year1 = date1.split(".")
    day2, month2, year2 = date2.split(".")
    if len(day1) > 2 and len(day2) > 2:
        return False
    elif len(month1) > 2 and len(month2) > 2:
        return False
    elif len(year1) > 4 and len(year2) > 4:
        return False
    else:
        day1, month1, year1 = int(day1), int(month1), int(year1)
        day2, month2, year2 = int(day2), int(month2), int(year2)
        
        if month_day(day1,month1,year1) == False:
            return text
        elif month_day(day2,month2, year2) == False:
            return text
        else:
            days = 0 
            if year2 > year1:
                days += month_day(day1,month1,year1) - day1
                current_month = month1 + 1
                
                while current_month <= 12:
                    days += month_day(day1,current_month, year1)
                    current_month += 1
                
                current_year = year1 + 1
                while current_year <= year2:
                    days += days_in_year(year1)
                    current_year += 1
                
                current_month = 1
                
                while current_month < month2:
                    days += month_day(day2, current_month, year2)
                    current_month += 1
                days += day1
                return days


# фунция из задачи 1
def visok(year):
    if year % 4 == 0 and year % 100 != 0 or year % 400 == 0:
        return True 
    else: 
        return False

# функция из 2 задачи
def days_in_year(year):
    if year % 4 == 0 and year % 100 != 0 or year % 400 == 0:
        return 366
    else:
        return 365


#функция для определения сколько дней в месяце
def month_day(day, month, year):
    if day <= 0 or day > 31 or month <= 0 or year < 0 :
        return False
    else:
        months = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
        if month > 12:
           return False
        else:
            if visok(year) == True:  months[1] = 29
            month = months[month - 1]
            return month


date = str(input("Введите дату в формате dd.mm.yyyy: "))
date_1 = str(input("Введите дату в формате dd.mm.yyyy: "))
print(raznica_v_days(date, date_1))
