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
This C++ group project is a library management system that organizes books by genre and fiction/non-fiction. The requirements for this project focused on class inheritance and objects. We made this program by visualizing what a row of book shelves would like in arrays. To achieve this, we created 3D arrays that represent genres, finction/non-fiction and the books. The main function of the program provides a menu-driven interface for users. It allows adding books to the library based on genre and category, searching for books using ISBN, deleting books with appropriate counters adjustment, editing book information, and viewing all books in the library.

*Book Class:*
The Book Class serves as the base class, encapsulating common attributes such as ISBN, title, author, edition, and publication. It includes setters and getters for these attributes, as well as static counters to keep track of the overall book count and counts for specific genres (science, history, horror, mystery). The class also provides methods for subtracting counters when books are deleted.
```cpp
class Book{
    protected:
        // variables
        int isbn;
        string title;
        string author;
        int edition;
        string publication;

        // book counters
        static int bookCount;
        static int fictionCount;
        static int nonFictionCount;
        static int scienceCount;
        static int horrorCount;
        static int mysteryCount;
        static int historyCount;

```

```cpp
public:
    Book(){
        bookCount++;
    }

    // setters & getters
    void setIsbn(int isbn){
        this -> isbn = isbn;
        bookCount++;
    }
```

*Fiction and Nonfiction Classes:*
These classes extend the Book Class and represent the two main categories of books. Each class includes a static counter for the respective category (fiction or non-fiction).
```cpp
class Fiction: public Book{ // Check if this count matches genre counts
    public:
        Fiction(){
            fictionCount++;
    }
};

class Nonfiction: public Book{ // Check if this count matches genre counts
    public:
        Nonfiction(){
            nonFictionCount++;
        }
};
```

*Science, History, Horror, and Mystery Classes:*
These classes further extend the Nonfiction and Fiction classes and represent specific genres within fiction and non-fiction. They include constructors to initialize book information based on user input.
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

*Functionality:*
The main function of the program provides a menu-driven interface for users. It allows adding books to the library based on genre and category, searching for books using ISBN, deleting books with appropriate counters adjustment, editing book information, and viewing all books in the library.
```cpp
int* searchBook(Book* library[2][2][20]){ // triple loop search
    int isbn;
    static int index[3];
    cout << "\nEnter ISBN: ";
    cin >> isbn;
    int i, j, k;

    for(i = 0; i < 2; i++){
        for(j = 0; j < 2; j++){
            for(k = 0; k < 20; k++){
                if(library[i][j][k] != nullptr){ 
                    if(isbn == library[i][j][k]->getIsbn()){
                        index[0] = i;
                        index[1] = j;
                        index[2] = k;
                        break;
                    }  
                }
            }
        }
    }
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
