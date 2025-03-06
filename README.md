# TicketBooking
class MetroTicketBooking:
    def __init__(self):
        self.stations = ["Station A", "Station B", "Station C", "Station D", "Station E"]
        self.fare_per_station = 5 
        
    def display_stations(self):
        print("Available stations:")
        for i, station in enumerate(self.stations, 1):
            print(f"{i}. {station}")

    def calculate_fare(self, start, end, tickets):
        distance = abs(end - start)
        fare = distance * self.fare_per_station * tickets
        return fare

    def book_ticket(self):
        print("Welcome to Metro Ticket Booking System")
        self.display_stations()

        start_station = int(input("Enter the number of your starting station: ")) - 1
        end_station = int(input("Enter the number of your destination station: ")) - 1
        
        if start_station < 0 or end_station < 0 or start_station >= len(self.stations) or end_station >= len(self.stations):
            print("Invalid station selection. Please try again.")
            return

        tickets = int(input("Enter the number of tickets: "))
        if tickets <= 0:
            print("Invalid number of tickets. Please try again.")
            return

        fare = self.calculate_fare(start_station, end_station, tickets)    

        print("\n--- Ticket Booking Details ---")
        print(f"Starting Station: {self.stations[start_station]}")
        print(f"Destination Station: {self.stations[end_station]}")
        print(f"Number of Tickets: {tickets}")
        print(f"Total Fare: ${fare}")
        print("Thank you for booking with us!")


if __name__ == "__main__":
    metro_booking = MetroTicketBooking()
    metro_booking.book_ticket()
