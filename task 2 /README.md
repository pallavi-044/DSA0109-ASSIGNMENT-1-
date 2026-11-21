
#include <iostream>
using namespace std;

enum class Zone {
    Inner, Middle, Outer
};

constexpr int INNER_FARE = 1000;
constexpr int MIDDLE_FARE = 2000;
constexpr int OUTER_FARE = 3000;

constexpr int MIN_BALANCE = 5000;

int main() {
    cout << "Inner Fare: " << INNER_FARE / 100 << '\n';
    cout << "Middle Fare: " << MIDDLE_FARE / 100 << '\n';
    cout << "Outer Fare: " << OUTER_FARE / 100 << '\n';
    cout << "Minimum Balance: " << MIN_BALANCE / 100 << '\n';

    return 0;
}


    if (passengerZone == INNER) {
        cout << "Inner" << endl;
    } else if (passengerZone == MIDDLE) {
        cout << "Middle" << endl;
    } else {
        cout << "Outer" << endl;
    }

    return 0;
}
