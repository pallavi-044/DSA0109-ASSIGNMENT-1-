

#include <iostream>
using namespace std;

long long calculateFare(int zone, int hour) {
    long long fare;

    switch (zone) {
        case 1: fare = 1000; break;
        case 2: fare = 2000; break;
        case 3: fare = 3000; break;
        default: return -1;
    }

    bool peak = (hour >= 8 && hour < 10) ||
                (hour >= 17 && hour < 20);

    if (peak) {
        fare += fare * 20 / 100;
    }

    return fare;
}

int main() {
    int zone, hour;
    long long balance = 10000;

    cout << "Enter zone (1-3): ";
    if (!(cin >> zone)) {
        cout << "Invalid input\n";
        return 0;
    }

    cout << "Enter hour (0-23): ";
    if (!(cin >> hour)) {
        cout << "Invalid input\n";
        return 0;
    }

    if (zone < 1 || zone > 3 || hour < 0 || hour > 23) {
        cout << "Invalid journey\n";
        return 0;
    }

    long long f = calculateFare(zone, hour);

    if (balance - f >= 5000) {
        balance -= f;

        cout << "Fare: Rs " << f / 100 << "."
             << (f % 100 < 10 ? "0" : "") << f % 100 << '\n';

        cout << "Remaining balance: Rs " << balance / 100 << '\n';
    } else {
        cout << "Travel denied\n";
    }

    return 0;
}
