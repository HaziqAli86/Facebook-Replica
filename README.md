# Facebook Replica - C++ Social Network System

A comprehensive social networking application built in C++ that replicates core Facebook functionalities using advanced Object-Oriented Programming (OOP) concepts.

## 🎯 Project Overview

This project implements a simplified version of Facebook's social networking features, demonstrating key OOP principles including inheritance, polymorphism, encapsulation, and composition. The system manages users, pages, posts, comments, and social interactions through a console-based interface.

## ✨ Key Features

### 🧑‍🤝‍🧑 User Management
- User profiles with friends and liked pages
- Friend lists with limit management (max 10 friends)
- Liked pages tracking (max 10 pages)
- User authentication and session management

### 📄 Page System
- Business/Organization pages
- Page posts and interactions
- User-page relationships (likes)

### 📝 Post & Content Management
- Regular text posts
- Activity posts (feeling/celebrating/making)
- Post timeline with date filtering
- Polymorphic post display system

### 💬 Social Interactions
- Like system for posts (users and pages can like)
- Comment system with nested threading
- Home feed with friend and page content
- Personal timeline view

### 🔍 Search Functionality
- Search across users, pages, and posts
- Content-based text searching
- Comprehensive result display

## 🏗️ System Architecture

### Core Classes

```cpp
├── object (Base Class)
│   ├── user
│   └── Pages
├── post (Base Class)
│   └── Activity (Derived Class)
├── comments
├── date
└── app (Main Application Controller)
```

### Design Patterns Implemented

- **Inheritance**: `object` base class for `user` and `Pages`
- **Polymorphism**: Virtual functions in `post` class for different display behaviors
- **Composition**: Classes contain other objects (users have friends, posts have comments)
- **Operator Overloading**: Custom operators for date operations and object comparisons

## 🛠️ Technical Features

### Object-Oriented Concepts Demonstrated

1. **Encapsulation**
   - Private data members with public accessor methods
   - Protected inheritance in post classes

2. **Inheritance**
   - `user` and `Pages` inherit from `object`
   - `Activity` inherits from `post`

3. **Polymorphism**
   - Virtual `display()` and `disp()` functions
   - Runtime method resolution for different post types

4. **Operator Overloading**
   - Stream insertion operators (`<<`) for object output
   - Assignment operators for deep copying
   - Date arithmetic operations

5. **Dynamic Memory Management**
   - Dynamic arrays for friends, liked pages, and posts
   - Proper destructors for memory cleanup
   - Copy constructors and assignment operators

## 📁 Data Files Required

The application reads from the following text files:

- `SocialNetworkUsers.txt` - User profiles and relationships
- `SocialNetworkPages.txt` - Page information
- `SocialNetworkPosts.txt` - Post content and metadata
- `SocialNetworkComments.txt` - Comment data

### File Format Examples

**SocialNetworkUsers.txt**
```
[Number of users]
[UserID] [FirstName] [LastName] [FriendIDs...] -1 [PageIDs...] -1
```

**SocialNetworkPosts.txt**
```
[Number of posts]
[PostID] [Day] [Month] [Year] [PostText] [ActivityType] [ActivityValue] [SharedByID] [LikedByIDs...] -1
```

## 🚀 Getting Started

### Prerequisites
- C++ compiler (GCC/Visual Studio)
- Standard C++ libraries
- Text data files in project directory

### Compilation
```bash
g++ -o facebook_replica Source.cpp
```

### Running the Application
```bash
./facebook_replica
```

## 💻 Usage Examples

### Setting Current User
```cpp
app.InputUser("u7");           // Set user with ID "u7" as current user
```

### Social Interactions
```cpp
app.likeapost("post5");        // Like a specific post
app.addComment("post8", "Thanks for the wishes");  // Add comment
app.viewapost("post4");        // View specific post with comments
```

### Navigation
```cpp
app.viewHome();                // View home feed
app.viewTimeline();            // View personal timeline
app.showfriends();             // Show friend list
app.viewPage("p1");            // View specific page
```

### Search Functionality
```cpp
app.search("Ali");             // Search for "Ali" across platform
app.search("Birthday");        // Search for birthday-related content
```

## 🔧 Class Relationships

### Inheritance Hierarchy
- `object` → `user`, `Pages`
- `post` → `Activity`

### Composition Relationships
- `user` contains arrays of `user*` (friends) and `Pages*` (liked pages)
- `post` contains arrays of `object*` (liked by) and `comments` (comments)
- `app` contains arrays of `user`, `Pages`, and `post*`

## 📊 Memory Management

The application implements proper memory management with:
- Dynamic memory allocation for expandable arrays
- Custom destructors for cleanup
- Copy constructors for deep copying
- Assignment operator overloading

## 🎮 Demo Functionality

The main function demonstrates:
1. Loading data from files
2. User authentication
3. Social interactions (likes, comments)
4. Content viewing (timeline, pages, posts)
5. Search functionality

## 🔍 Advanced Features

### Date System
- Custom date class with arithmetic operations
- Timeline filtering based on current date
- Date comparison operators

### Activity Posts
- Specialized post type for activities
- Different display formats for various activity types
- Polymorphic behavior demonstration

### Search Algorithm
- String searching across multiple data types
- Comprehensive result categorization
- Case-sensitive pattern matching

## 🎓 Educational Value

This project serves as an excellent demonstration of:
- **OOP Design Principles**: Proper class hierarchy and relationships
- **C++ Advanced Features**: Operator overloading, virtual functions, dynamic memory
- **Software Architecture**: Modular design and separation of concerns
- **Data Management**: File I/O and data structure manipulation

## 🚧 Limitations & Considerations

- Console-based interface (no GUI)
- Fixed limits on friends and liked pages
- Basic search functionality (no fuzzy matching)
- No persistent data storage (reads from files only)

## 📝 Code Quality Features

- Consistent naming conventions
- Proper error handling
- Memory leak prevention
- Modular design pattern
- Comprehensive operator overloading

## 🎯 Learning Outcomes

Upon studying this project, developers will understand:
- Advanced C++ OOP concepts
- Virtual function implementation
- Dynamic memory management
- Operator overloading best practices
- Complex data structure relationships
- File I/O operations in C++

---

**Note**: This project is designed for educational purposes to demonstrate Object-Oriented Programming concepts in C++. It provides a solid foundation for understanding how social networking applications can be architected using OOP principles.
