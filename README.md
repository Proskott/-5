#include <stdio.h>

#define MOD 12345

int countSequences(int n) {

if (n == 1) return 2;


if (n == 2) return 3;


int a = 2; // Кількість послідовностей довжиною 1 (0 або 1)


int b = 3; // Кількість послідовностей довжиною 2 (00, 01, або 10)


for (int i = 3; i <= n; i++) {
        int temp = (a + b) % MOD;
        a = b;
        b = temp;
    }

    return b;
}

int main() {

int n;

printf("Введіть довжину послідовності n: ");


scanf("%d", &n);

int result = countSequences(n);


printf("Кількість шуканих послідовностей: %d\n", result);

    return 0;
}
