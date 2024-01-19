---
layout: project
type: project
image: img/c++/c++.png
title: "Library Management"
date: 2023
published: true
labels:
  - Group project
  - C++
summary: "C++ group project that organizes library books by genre."
---
This C++ group project is a library management system that organizes books by genre and fiction/non-fiction. The requirements for this project focused on class inheritance and objects. We made this program by visualizing what a row of book shelves would like in arrays. To achieve this, we created 3D arrays that represent genres, finction/non-fiction and the books.

```cpp
class Book{
    protected:
        // variables
        int isbn;
        string title;
        string author;
        int edition;
        string publication;
```
```cpp
class Fiction: public Book{ // Check if this count matches genre counts
    public:
        Fiction(){
            fictionCount++;
    }
};
```
```cpp
class Mystery: public Fiction{
    public:
        Mystery(int isbn, string title, string author, int edition, string publication){
            this -> isbn = isbn;
            this -> title = title;
            this -> author = author;
            this -> edition = edition;
            this -> publication = publication;
            mysteryCount++;
        }
};
```
```cpp
int main() {
    Book* library[2][2][20] = {{{nullptr}}}; 
    int choice;
    bool menu = true;
    
    // Menu
    cout << "\n*************************";
    cout << "\nLibrary Management System\n";
    cout << "*************************\n\n";
```
