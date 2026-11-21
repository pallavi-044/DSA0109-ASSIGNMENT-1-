

#include <iostream>
using namespace std;

class SmartCard {
private:
    long long balance;
    const long long MIN_BALANCE = 5000;

public:
    SmartCard(long long b) {
        balance = b;
    }

    bool canTravel(long long fare) {
        return balance - fare >= MIN_BALANCE;
    }

    void deduct(long long fare) {
        if (canTravel(fare)) {
            balance -= fare;
            cout << "Travel allowed\n";
        } else {
            cout << "Travel denied\n";
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

    card.deduct(4000);
    card.display();

    return 0;
}
