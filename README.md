# Travel Planner

# 1. Traveler Profile Setup
print("Welcome to the Travel Planner!")

name = input("What's your name? ")
home_country = input("Where are you from? ")
trip_goal = input("What do you want to experience (e.g., adventure, relaxation)? ")

print("Hello " + name + " from " + home_country + "!")
print("You want a " + trip_goal + " vacation. Let's plan it!")

# 2. Destination Selector
print("\nHere are some places you can go:")
destinations = ["Japan", "Italy", "Brazil", "Canada", "Australia"]

# Show the list of destinations with numbers
for i in range(5):
    print(str(i + 1) + ". " + destinations[i])

# Ask the user to choose a destination by number
while True:
    try:
        choice = int(input("Pick a destination by number (1-5): ")) - 1
        if choice >= 0 and choice < len(destinations):
            selected_destination = destinations[choice]
            print("You chose " + selected_destination + "!")
            break
        else:
            print("Invalid choice. Please pick a number between 1 and 5.")
    except ValueError:
        print("Please enter a valid number.")

# 3. Budget Planner
print("\nNow, let's plan your budget.")

# Input validation for budget and costs
while True:
    try:
        budget = float(input("How much money do you have for your trip? (GBP): "))
        flight_cost = float(input("What is the estimated flight cost? (GBP): "))
        hotel_cost = float(input("What is the estimated hotel cost? (GBP): "))
        food_cost = float(input("How much will you spend on food? (GBP): "))
        break
    except ValueError:
        print("Please enter a valid number for costs.")

# Calculate the total cost
total_cost = flight_cost + hotel_cost + food_cost
remaining_budget = budget - total_cost

# Show the results
print("\nTotal cost of your trip: £" + str(total_cost))
if remaining_budget >= 0:
    print("You are within your budget! You have £" + str(remaining_budget) + " left.")
else:
    print("You are over your budget by £" + str(-remaining_budget) + ". You may need to adjust your plans.")

# 4. Itinerary Builder
print("\nLet's plan your 3-day trip!")

itinerary = []

# Ask for activities for each day
for day in range(1, 4):
    activity = input("What will you do on Day " + str(day) + "? ")
    itinerary.append(activity)

# 5. Trip Summary
print("\nHere is your trip summary:")
print("------------------------------")
print("Traveler: " + name)
print("Destination: " + selected_destination)
print("Total budget: £" + str(budget))
print("Total cost: £" + str(total_cost))
print("Remaining money: £" + str(remaining_budget))

print("\nYour 3-day itinerary:")
for i in range(3):
    print("  Day " + str(i + 1) + ": " + itinerary[i])

print("------------------------------")
print("Trip planning complete! Have a great time!")

