# Calorie-Calculator
This application count the calorie . How much calorie you have eaten in this week. and tell you how much calorie you should eat. Body mass index 
def getCalories(question): 
    calories = input(question)
    if calories.isdigit(): 
        calories = int(calories)
        if calories > -1 and calories < 50000: 
            return calories
        else:
            print("Invalid amount")
            return getCalories(question)
    else:
        print("Numbers only please")
        return getCalories(question)

print("Welcome to the calorie counter\n")
print("Please enter your calories for the last 7 days")

week = []
for i in range(7):
    day = getCalories(question = "Day " + str(i+1) + ":")
    week.append(day)

total = sum(week)
average = int(total / 7)

print("Your total calorie intake for the week:", total)
print("\nYour average calorie intake for the week:", average)

if total > 21000:
    print("\nYou are eating too many calories. You will get fat!")
elif total < 9000:
    print("\nYou are eating far too few calories. You will become anorexic.")
    
height = int(input("enter your height in cm:"))
weight = int(input("enter your weight in kg:"))

def BMI(height, weight):
    bmi = weight/(height**2)
    return bmi
 

bmi = BMI(height, weight)
print("The BMI is", format(bmi), "so ", end='')
 

if (bmi < 18.5):
    print("underweight")
 
elif ( bmi >= 18.5 and bmi < 24.9):
    print("Healthy")
 
elif ( bmi >= 24.9 and bmi < 30):
    print("overweight")
 
elif ( bmi >=30):
    print("Suffering from Obesity")    
