# Campus Golf Cart Booking System

A Python-based command-line tool built to manage and schedule campus golf carts. It handles booking requests, assigns carts automatically, prevents double-booking, and suggests upcoming time slots if all carts are occupied.

Built to solve transit congestion and scheduling conflicts across common campus transit points—such as hostels, the library, and academic blocks—using clean modular Python and lightweight flat-file persistence.

---

## Features

- **Smart Slot Booking:** Books trips across 15-minute operating windows (`08:00` to `19:45`) and automatically assigns the first available cart.
- **Alternative Slot Suggestions:** Automatically searches ahead and recommends the next 3 available time slots whenever all carts are occupied at a requested time.
- **Persistent Flat-File Storage:** Saves, reads, and updates all bookings in a comma-delimited text file (`bookings.txt`) so records persist across restarts without external database dependencies.
- **Strict Input Validation:** Validates passenger counts (`1–4`), enforces operating hours, normalizes single-digit time entries (e.g., `9:00` → `09:00`), and prevents identical pickup and drop-off locations.
- **Fleet Status & Cancellation:** Lets users check real-time cart availability for any specific time slot, view all active bookings in an aligned console table, or cancel a scheduled trip using its unique Booking ID (`GC1001`, `GC1002`, etc.).

---

## System Configuration

| Parameter | Value |
| :--- | :--- |
| **Fleet Size** | 4 Carts (`Cart 1` to `Cart 4`) |
| **Passenger Capacity** | Up to 4 passengers per cart |
| **Operating Hours** | `08:00` to `19:45` (15-minute intervals) |
| **Campus Stops** | Hostel Area, Main Gate, Academic Block, Library, Sports Complex |
| **Data Storage** | Plain-text CSV (`bookings.txt`) |

---

## Project Structure

```text
├── Cartracker.py     # Main CLI application and booking/allocation logic
├── bookings.txt      # Flat-file CSV database storing active trip records
└── README.md         # Project documentation
