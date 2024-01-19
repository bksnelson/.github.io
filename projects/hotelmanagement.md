---
layout: project
type: project
image: img/c++/c++.png
title: "Hotel Management"
date: 2023
published: true
labels:
  - Group project
  - C++
summary: "C++ group project that manages rooms and customers in a hotel."
---

This C++ group project is a hotel management system that keeps track of customers and available rooms.
The requirements for this project focused on class inheritance and objects. We created the functionality of adding and removing new rooms into the hotel with a singular array. Whithin those rooms, we added the functionality to check in/out customers and collect the total costs of visits. 

```cpp
byte ADCRead(byte ch)
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
```cpp
byte ADCRead(byte ch)
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
byte ADCRead(byte ch)
class HotelManagement: public Room{
    //Variables
    protected:
        Customer customer; //Customer object of a room
```
```cpp
byte ADCRead(byte ch)
class BookingSystem{
    //Variables
    private:
        HotelManagement rooms[20]; //Array of rooms 
        int roomCount = 0; //Counter for number of rooms 
```
