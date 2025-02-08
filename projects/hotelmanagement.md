---
layout: project
type: project
image: img/c++/c++.png
title: "Hotel Management"
date: 2023
published: false
labels:
  - Group project
  - C++
summary: "C++ group project that manages rooms and customers in a hotel."
---

This C++ group project is a hotel management system that keeps track of customers and available rooms.
The requirements for this project focused on class inheritance and objects. We created the functionality of adding and removing new rooms into the hotel with a singular array. Whithin those rooms, we added the functionality to check in/out customers and collect the total costs of visits. 

#### Customer Class:
The Customer Class encapsulates essential customer details, such as booking ID, name, address, contact, check-in/out dates, and advance payment. It features constructors to handle default instances and check-ins.
```cpp
class Customer{
    //Variables
	private: 
		int bookingID;
		string name;
		string address;
        string phoneNum;
		string inDate;
		string outDate;
		double advance;
```

#### Room Class:
The Room Class represents individual hotel rooms, storing crucial data like room number, AC availability, comfort type, size, and daily rate. The class includes a method to display detailed room information.
```cpp

class Room{
    //Variables
	protected:
		int roomNum; 
        char ac; 
		char comfort;
		char size;
		double dailyRate;
```

```cpp
void displayRoom(){
		cout << "Room Number: " << roomNum << "\n";
		cout << "Room with AC/No AC (A/N): " << ac << "\n";
		cout << "Type of Comfort (S/N): " << comfort<< "\n";
		cout << "Room Size (B/S): " << size << "\n";
		cout << "Daily Rate: " << dailyRate << "\n";
    }
```

#### HotelManagement Class:
The HotelManagement Class, an extension of Room, manages the association between rooms and customers. It facilitates adding customers to rooms and clearing customer data.
```cpp
class HotelManagement: public Room{
    //Variables
    protected:
        Customer customer; //Customer object of a room
```

```cpp
void displayCheckout(int days){ //Param - number of days customer has been renting room
    cout << "Customer Name : " << customer.getName() << "\n";
    cout << "Room Number : " <<  roomNum << "\n";
    cout << "Address : " << customer.getAddress() << "\n";
    cout << "Phone : " << customer.getPhoneNum() << "\n";
    cout << "Total Amount Due : " << days * dailyRate << " /\n";
    cout << "Advance Paid: " << customer.getAdvance() << " /\n";   
    cout << "***Total Payable: " << days * dailyRate - customer.getAdvance() << "/ only\n";
}
```

#### BookingSystem Class:
The BookingSystem Class serves as the core management entity, overseeing an array of HotelManagement objects. Its functionalities include adding and deleting rooms, checking in customers, checking out customers with accurate billing, searching for available rooms, and generating a guest summary report.
```cpp
class BookingSystem{
    //Variables
    private:
        HotelManagement rooms[20]; //Array of rooms 
        int roomCount = 0; //Counter for number of rooms
```

```cpp
void checkOut(){
    int days; //Number of days renting room
    int i = getIndex(); // Get the index of room number 
    if(i >= 0){ 
	cout << "\nEnter Number of Days: "; //If it exists then collect number of days from user 
	cin >> days;
	cout << "\n######## CheckOut Details ########\n\n";
	rooms[i].displayCheckout(days); // Display check out details 
	rooms[i].clearCust(); // Clear customer by calling default customer constructor 
    }
}
```
