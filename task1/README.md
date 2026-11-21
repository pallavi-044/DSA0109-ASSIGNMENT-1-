
#include <iostream>
using namespace std;

class SmartCard {
private:
    int balance;

public:
    SmartCard(int b) {
        balance = b;
    }

    void deduct(int fare) {
        if (balance - fare >= 5000) {
            balance -= fare;
            cout << "Journey successful\n";
        } else {
            cout << "Insufficient balance\n";
        }
    }

    void display() {
        cout << "Balance: Rs " << balance / 100 << '\n';
    }
};

int main() {
    SmartCard card(10000);

    card.deduct(2000);
    card.display();

    return 0;
}

