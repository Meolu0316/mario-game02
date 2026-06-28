#include <iostream>
using namespace std;

int main() {
    char map[5][11] = {
        "##########",
        "#M       #",
        "#   ##   #",
        "#      F #",
        "##########"
    };

    int x = 1, y = 1;

    while (true) {
        system("cls");   // Trên Linux/OnlineGDB có thể đổi thành system("clear");

        for (int i = 0; i < 5; i++) {
            for (int j = 0; j < 10; j++) {
                if (i == y && j == x)
                    cout << 'M';
                else
                    cout << map[i][j];
            }
            cout << endl;
        }

        cout << "A: Trai  D: Phai  Q: Thoat\n";

        char c;
        cin >> c;

        if (c == 'q') break;

        if (c == 'a' && map[y][x-1] != '#') x--;
        if (c == 'd' && map[y][x+1] != '#') x++;

        if (map[y][x] == 'F') {
            cout << "Ban da chien thang!\n";
            break;
        }
    }

    return 0;
}
