
#include <iostream>
using namespace std;

int main() {
    long long journeys[] = {
        20000, 500000, 3000000
    };

    long long fare = 1000;

    for (int i = 0; i < 3; i++) {
        long long total = journeys[i] * fare;

        double doubleTotal = journeys[i] * 10.0;

        cout << "Journeys: " << journeys[i] << '\n';

        cout << "Long long total (paise): "
             << total << '\n';

        cout << "Double total (rupees): "
             << doubleTotal << "\n\n";
    }

    return 0;
}
