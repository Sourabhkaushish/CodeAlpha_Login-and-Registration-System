#include <iostream>
#include <unordered_map>
#include <string>
#include <functional>
using namespace std;

// In-memory storage for users (username → hashed password)
unordered_map<string, string> userDatabase;

// Simple hash function (not secure but okay for learning)
string hashPassword(const string& password) {
    hash<string> hasher;
    return to_string(hasher(password));
}

// Register a new user
void registerUser() {
    string username, password;
    cout << "Enter username: ";
    cin >> username;
    cout << "Enter password: ";
    cin >> password;

    // Check if username already exists
    if (userDatabase.find(username) != userDatabase.end()) {
        cout << "❌ Username already exists. Please choose another.\n";
        return;
    }

    // Hash password and store it
    userDatabase[username] = hashPassword(password);
    cout << "✅ Registration successful!\n";
}

// Login an existing user
void loginUser() {
    string username, password;
    cout << "Enter username: ";
    cin >> username;
    cout << "Enter password: ";
    cin >> password;

    // Check if user exists
    if (userDatabase.find(username) == userDatabase.end()) {
        cout << "❌ User not found. Please register first.\n";
        return;
    }

    // Verify password
    if (userDatabase[username] == hashPassword(password)) {
        cout << "✅ Login successful. Welcome, " << username << "!\n";
    } else {
        cout << "❌ Incorrect password.\n";
    }
}

// Main Menu
int main() {
    int choice;

    while (true) {
        cout << "\n==== Login & Registration System ====\n";
        cout << "1. Register\n";
        cout << "2. Login\n";
        cout << "3. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1: registerUser(); break;
            case 2: loginUser(); break;
            case 3: cout << "👋 Exiting...\n"; return 0;
            default: cout << "❌ Invalid choice. Try again.\n";
        }
    }

    return 0;
}
