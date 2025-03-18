# Restaurant-Ordering-System03

#include <iostream>
using namespace std;

class Restaurant {
private:
    string menu[5] = {"Burger", "Pizza", "Pasta", "Sandwich", "Coffee"};
    double price[5] = {99.99, 199.50, 149.00, 79.99, 49.99};

public:
    void displayMenu() {
        cout << "Menu:\n";
        for (int i = 0; i < 5; i++) {
            cout << i + 1 << ". " << menu[i] << " - ₹" << price[i] << endl;
        }
    }

    double calculateBill(int orders[], int n) {
        double total = 0;
        for (int i = 0; i < n; i++) {
            if (orders[i] >= 1 && orders[i] <= 5) {
                total += price[orders[i] - 1];
            }
        }
        return total;
    }
};

int main() {
    Restaurant r;
    int n;

    r.displayMenu();
    
    cout << "Enter the number of items you want to order: ";
    cin >> n;

    int orders[n];
    cout << "Enter item numbers: ";
    for (int i = 0; i < n; i++) {
        cin >> orders[i];
    }

    cout << "Total Bill: ₹" << r.calculateBill(orders, n) << endl;

    return 0;
}
