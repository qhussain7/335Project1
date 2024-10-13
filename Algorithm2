#Algorithm2

def find_preferred_starting_city(city_distances, fuel, mpg):
    n = len(city_distances)
    total_fuel_needed = 0
    total_fuel_available = 0
    current_fuel = 0
    start_city = 0

    for i in range(n):
        # Calculate the miles the car can travel from the fuel at city i
        fuel_from_city_i = fuel[i] * mpg
        # Calculate the distance to the next city
        fuel_needed_to_next_city = city_distances[i]

        # Update current fuel after moving to the next city
        current_fuel += fuel_from_city_i - fuel_needed_to_next_city

        # If current fuel is negative, we cannot start from this city
        if current_fuel < 0:
            start_city = i + 1
            current_fuel = 0

        # Track total fuel availability and total fuel needed
        total_fuel_needed += fuel_needed_to_next_city
        total_fuel_available += fuel_from_city_i

    # If the total available fuel is less than the total needed, return -1 (no valid starting point)
    if total_fuel_available < total_fuel_needed:
        return -1

    # Return the preferred starting city
    return start_city

# Sample Input
city_distances = [5, 25, 15, 10, 15]
fuel = [1, 2, 1, 0, 3]
mpg = 10

# Call the function
preferred_starting_city = find_preferred_starting_city(city_distances, fuel, mpg)
print(f"The preferred starting city is city {preferred_starting_city}")
