#include <iostream>
#include <vector>
#include <string>
#include <locale>

using namespace std;

struct Apartment {
    string owner;
    int number;
    int residents;
};

int main() {
    setlocale(LC_ALL, "");
    system("chcp 65001 > nul");

    int n;
    cout << "Введіть кількість квартир: ";
    cin >> n;

    vector<Apartment> apartments(n);

    for (int i = 0; i < n; i++) {
        cout << "Введіть прізвище власника квартири " << i + 1 << ": ";
        cin >> apartments[i].owner;
        cout << "Введіть номер квартири: ";
        cin >> apartments[i].number;
        cout << "Введіть кількість мешканців: ";
        cin >> apartments[i].residents;
    }

    cout << "\nСписок власників квартир:" << endl;
    for (const auto& apt : apartments) {
        cout << "Квартира " << apt.number << ": " << apt.owner << endl;
    }

    cout << "\nКвартири, в яких проживає більше 4 осіб:" << endl;
    for (const auto& apt : apartments) {
        if (apt.residents > 4) {
            cout << "Квартира " << apt.number << " з " << apt.residents << " мешканцями" << endl;
        }
    }

    return 0;
}
