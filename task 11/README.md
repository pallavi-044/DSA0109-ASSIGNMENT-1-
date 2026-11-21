
#include <iostream>
using namespace std;

class SmartCard {
private:
    long long balance;

public:
    SmartCard(long long amount) {
        balance = amount;
    }

    bool canTravel(long long fare) {
        return balance - fare >= 5000;
    }

    void travel(long long fare) {
        if (fare < 0) {
            cout << "Invalid fare\n";
        }
        else if (canTravel(fare)) {
            balance -= fare;
            cout << "Journey successful\n";
        }
        else {
            cout << "Insufficient balance\n";
        }
    }

    void displayBalance() {
        cout << "Balance: Rs " << balance / 100 << '\n';
    }
};

int main() {
    SmartCard card(10000);

    card.travel(2000);
    card.displayBalance();

    card.travel(6000);
    card.displayBalance();

    return 0;
}

