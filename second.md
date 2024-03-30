On a specific day, the exchange rates were as follows: the British pound was valued at $1.487 U.S., the French franc at $0.172, the German deutschemark at $0.584, and the Japanese yen at $0.00955. Write a program that prompts the user to input an amount in U.S. dollars. The program should then display this amount converted into these four other currencies. Test the program by inputting various dollar amounts and ensuring that the conversions to British pounds, French francs, German deutschemarks, and Japanese yen are accurate. Additionally, test the program with negative dollar amounts to verify that it handles invalid input appropriately.
#include <iostream>
#include <iomanip> 
using namespace std;
int main() {
    const double GBP_RATE = 1.487;
    const double FRF_RATE = 0.172;
    const double DEM_RATE = 0.584;
    const double JPY_RATE = 0.00955;
    cout << "Enter an amount in U.S. dollars: ";
    double usd_amount;
    cin >> usd_amount;
    if (usd_amount < 0) {
        cout << "Invalid input. Amount must be non-negative." << endl;
    } else {
        double gbp_amount = usd_amount * GBP_RATE;
        double frf_amount = usd_amount * FRF_RATE;
        double dem_amount = usd_amount * DEM_RATE;
        double jpy_amount = usd_amount * JPY_RATE;
        cout << fixed << setprecision(2);
        cout << "Converted amounts:" << endl;
        cout << "GBP: " << gbp_amount << endl;
        cout << "FRF: " << frf_amount << endl;
        cout << "DEM: " << dem_amount << endl;
        cout << "JPY: " << jpy_amount << endl;
    }
}
