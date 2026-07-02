🚆 Railway Reservation System

A console-based Java application that simulates a Railway Ticket Reservation System with intelligent berth allocation, RAC (Reservation Against Cancellation), and Waiting List management.

Built to demonstrate Core Java concepts including Enum-based Singleton pattern, Collections Framework (HashMap, LinkedList Queue), OOP, and smart booking logic.

🛠️ Tech Stack

| Technology | Usage |
|-----------|-------|
| Java | Core application logic |
| Java Collections | HashMap for passenger data, LinkedList Queue for RAC & Waiting List |
| Enum Singleton | Thread-safe singleton pattern for booking engine |
| OOPS | Encapsulation, getters/setters, modular class design |
| Scanner | Console-based user input handling |

✨ Features

🎫 Smart Ticket Booking
- Book tickets with berth preference (Lower / Middle / Upper)
- Automatic berth allocation based on availability
- RAC (Reservation Against Cancellation) — passengers get side berth when confirmed berths are full
- Waiting List management when RAC is also full
- Auto-generated Passenger ID for each booking

👴 Priority-Based Berth Allocation
- Senior citizens (age > 60) → Automatically assigned Lower Berth
- Mothers with children (age < 5) → Automatically assigned Lower Berth with child details
- Children under 5 → Cannot be allotted a separate berth (travels with parent)

❌ Ticket Cancellation & Auto-Promotion
- Cancel booked tickets by Passenger ID
- RAC passengers automatically promoted to confirmed berth on cancellation
- Waiting List passengers automatically promoted to RAC on cancellation
- Berth availability updated in real-time

📊 View Tickets
- View all available ticket counts (Lower, Middle, Upper, RAC, Waiting List)
- View all **booked passenger details with berth allocation info

📁 Project Structure

RailwayReservationSystem/
│
├── Passenger.java          # Passenger model class (POJO with getters/setters)
├── TicketBook.java         # Booking engine (Enum Singleton with core logic)
├── Reservationtask.java    # Main class with menu-driven interface
└── README.md               # Project documentation

Class Responsibilities

| Class | Role |
|-------|------|
| Passenger | Data model — stores passenger info (name, age, gender, child details, berth preference, auto-ID) |
| TicketBook | Business logic — berth allocation, cancellation, RAC/WL promotion (Enum Singleton) |
| Reservationtask | Entry point — menu-driven UI, user input handling |

🚀 How to Run

 Prerequisites
- Java JDK 8 or higher installed
- Any terminal or IDE (IntelliJ IDEA / Eclipse / VS Code)

Steps:

bash
1. Clone the repository
git clone https://github.com/Nithis-Kumar-1999/RailwayReservationSystem.git

2. Navigate to the project directory
cd RailwayReservationSystem

3. Compile all Java files
javac -d . *.java

4. Run the application
java com.railwayreservationsystem.Reservationtask

🖥️ Application Flow

Main Menu
├── 1. Book Ticket
│   ├── Enter passenger details (name, age, gender)
│   ├── Female? → Option to add child details
│   ├── Enter berth preference (L / M / U)
│   └── Smart allocation:
│       ├── Age > 60 → Auto Lower Berth
│       ├── Mother with child < 5 → Auto Lower Berth
│       ├── Preferred berth available → Allot preferred
│       ├── Any berth available → Allot available
│       ├── No confirmed → Move to RAC
│       └── No RAC → Move to Waiting List
├── 2. Cancel Ticket
│   ├── Enter Passenger ID
│   ├── Cancel and free berth
│   ├── Auto-promote RAC → Confirmed
│   └── Auto-promote Waiting List → RAC
├── 3. Available Tickets
│   └── Shows count: Lower, Middle, Upper, RAC, Waiting List
├── 4. Booked Tickets
│   └── Shows all passenger details with allotted berth
└── 5. Exit

📸 Sample Output

1)Book :
2)Cancel :
3)Available Tickets :
4)Booked Tickets :
5)Exit :

Enter the choice :
1

Enter the Passenger Name
Nithis
Enter the Passenger Age
25
Enter the Passenger Gender (Male-M, Female-F)
M
Enter the Berth Preference (L-Lower, M-Middle, U-Upper)
L

Lower Berth is allotted for you...

Passenger ID : 1
Passenger Name : Nithis
Berth Allotted : Lower Berth


📌 Key Concepts Demonstrated

- Enum Singleton Pattern — TicketBook uses Java Enum for a thread-safe singleton booking engine
- Java Collections Framework — HashMap for passenger data storage, LinkedList as Queue for RAC and Waiting List
- Queue (FIFO) — RAC and Waiting List follow First-In-First-Out for fair promotion
- Encapsulation — Passenger class with private fields and public getters/setters
- Business Logic — Priority-based berth allocation, cascading promotion on cancellation
- Menu-Driven Architecture — Clean switch-case based navigation
🔮 Future Enhancements

- [ ] Connect to **MySQL database** for persistent ticket storage
- [ ] Build a **Spring Boot REST API** for web-based booking
- [ ] Add **train search** with source, destination, and date
- [ ] Implement **seat map visualization** showing berth layout
- [ ] Add **payment gateway integration** simulation
- [ ] Build a **React.js frontend** for a complete web application

👤 Author

S Nithis Kumar
- 💼 Software Engineer at Advento Technologies
- 🔗 [LinkedIn](https://www.linkedin.com/in/nithis-kumar-s/)
- 🐙 [GitHub](https://github.com/Nithis-Kumar-1999)

📝 License

This project is open-source and available for learning and reference purposes.
