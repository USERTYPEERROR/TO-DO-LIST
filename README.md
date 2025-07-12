# TO-DO-LIST
# This is a simple console-based To-Do List Manager developed in C++ that allows users to manage their daily tasks through a text-based interface. 
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main() {
    vector<string> tasks;
    int choice;

    do {
        cout << "TO DO LIST" << endl;
        cout << "1- Add Task" << endl;
        cout << "2- View Task" << endl;
        cout << "3- Delete Task" << endl;
        cout << "4- Exit" << endl;
        cout << "Enter your choice: ";
        cin >> choice;
        cin.ignore();

        if (choice == 1) {
            string task;
            cout << "Name the task: ";
            getline(cin, task);
            tasks.push_back(task);
            cout << "Task added\n";
        } else if (choice == 2) {
            if (tasks.empty()) {
                cout << "There is no task added.\n";
            } else {
                cout << "View Tasks:\n";
                for (int i = 0; i < tasks.size(); i++) {
                    cout << i + 1 << ". " << tasks[i] << endl;
                }
            }
        } else if (choice == 3) {
            if (tasks.empty()) {
                cout << "There is no tasks to delete.\n";
            } else {
                int index;
                cout << "Enter task number to delete: ";
                cin >> index;
                cin.ignore();
                if (index >= 1 && index <= tasks.size()) {
                    tasks.erase(tasks.begin() + index - 1);
                    cout << "Task deleted.\n";
                } else {
                    cout << "Error: task number not found.\n";
                }
            }
        } else if (choice == 4) {
            cout << "Exit: \n";
        } else {
            cout << "Invalid: ";
        }

    } while (choice != 4);

    return 0;
}
