# Travel Planner Simulator 🌍✈️

# 1. Traveler Profile Setup
print("🌐 Welcome to Python Travel Planner!")

name = input("What's your name? ")
home_country = input("Where are you from? ")
trip_goal = input("What do you want to experience (e.g., adventure, relaxation, culture)? ")

print(f"\n✈️ Hello {name} from {home_country}!")
print(f"You're looking for a {trip_goal} vacation. Let's plan your journey!")

# 2. Destination Selector
print("\n🧭 Available destinations:")
destinations = ["Japan", "Italy", "Brazil", "Canada", "Australia"]

for i in range(len(destinations)):
    print(f"{i + 1}. {destinations[i]}")

choice = int(input("Choose a destination by number: ")) - 1

if 0 <= choice < len(destinations):
    selected_destination = destinations[choice]
    print(f"🌍 You've selected {selected_destination} as your travel destination!")
else:
    print("❌ Invalid choice. Defaulting to 'Italy'.")
    selected_destination = "Italy"

# 3. Budget Planner
print("\n💸 Let's plan your travel budget!")

budget = float(input("Enter your total travel budget in USD: "))
flight_cost = float(input("Estimated flight cost: "))
hotel_cost = float(input("Estimated hotel cost: "))
food_cost = float(input("Estimated food cost: "))

total_cost = flight_cost + hotel_cost + food_cost
remaining_budget = budget - total_cost

print(f"\n🧾 Total estimated cost: ${total_cost:.2f}")
if remaining_budget >= 0:
    print(f"✅ You're within budget! You have ${remaining_budget:.2f} left.")
else:
    print(f"⚠️ You're over budget by ${-remaining_budget:.2f}. Consider adjusting your plans.")

# 4. Itinerary Builder
print("\n📅 Let's plan your 3-day itinerary!")

itinerary = []
for day in range(1, 4):
    activity = input(f"Enter an activity for Day {day}: ")
    itinerary.append(activity)

# 5. Trip Summary
print("\n🔚 Trip Summary")
print("-" * 30)
print(f"👤 Traveler: {name}")
print(f"🌍 Destination: {selected_destination}")
print(f"💸 Budget: ${budget:.2f}")
print(f"🧾 Total Estimated Cost: ${total_cost:.2f}")
print(f"💰 Remaining: ${remaining_budget:.2f}")
print("\n🗓️ Itinerary:")
for i in range(3):
    print(f"  Day {i + 1}: {itinerary[i]}")
print("-" * 30)
print("🎉 Trip planning complete! Bon voyage!")
