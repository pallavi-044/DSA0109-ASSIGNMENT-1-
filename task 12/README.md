

#include <iostream>
using namespace std;

enum class Zone {
    Inner = 1,
    Middle,
    Outer,
    Airport
};

constexpr long long FARE[] = {
    1000, 2000, 3000, 6000
};

class Pass {
private:
    int zone1, zone2;

public:
    Pass(int z1, int z2) {
        zone1 = z1;
        zone2 = z2;
    }

    bool hasPass(int zone) {
        return zone == zone1 || zone == zone2;
    }
};

class SmartCard {
private:
    long long balance;

public:
    SmartCard(long long b) {
        balance = b;
    }

    void travel(int zone, bool peak,
                bool weekend, Pass &pass) {

        if (zone < 1 || zone > 4) {
            cout << "Invalid zone\n";
            return;
        }

        if (pass.hasPass(zone)) {
            cout << "Free travel using monthly pass\n";
            return;
        }

        long long fare = FARE[zone - 1];

        if (weekend) {
            fare = fare * 90 / 100;
        }
        else if (peak) {
            fare = fare * 120 / 100;
        }

        if (balance - fare >= 5000) {
            balance -= fare;

            cout << "Fare: Rs " << fare / 100 << "."
                 << (fare % 100 < 10 ? "0" : "")
                 << fare % 100 << '\n';
        }
        else {
            cout << "Travel denied\n";
        }

        cout << "Balance: Rs " << balance / 100 << '\n';
    }
};

int main() {
    SmartCard card(20000);

    Pass monthlyPass(1, 2);

    card.travel(1, false, false, monthlyPass);
    card.travel(3, true, false, monthlyPass);
    card.travel(4, false, true, monthlyPass);
    card.travel(2, false, false, monthlyPass);

    return 0;
}
