

#include <iostream>
#include <iomanip>
#include <limits>
using namespace std;

int main() {
    double fare;

    cout << "Enter fare: ";

    if (!(cin >> fare)) {
        cout << "Invalid input\n";

        cin.clear();

        cin.ignore(numeric_limits<streamsize>::max(), '\n');

        return 0;
    }

    if (fare < 0) {
        cout << "Invalid fare\n";
        return 0;
    }

    cout << fixed << setprecision(2);

    cout << "Fare: Rs " << fare << '\n';

    return 0;
}
