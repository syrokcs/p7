#include <stdio.h>
#include <math.h>

int count_intersection_points(int x1, int y1, int r1, int x2, int y2, int r2) {
    double distance = sqrt(pow(x2 - x1, 2) + pow(y2 - y1, 2));

    if (distance == 0 && r1 == r2) {
        // Кола збігаються
        return -1;
    } else if (distance > r1 + r2 || distance < abs(r1 - r2)) {
        // Кола не перетинаються
        return 0;
    } else if (distance == r1 + r2 || distance == abs(r1 - r2)) {
        // Одна точка перетину
        return 1;
    } else {
        // Дві точки перетину
        return 2;
    }
}

int main() {
    int x1, y1, r1, x2, y2, r2;

    printf("Введіть координату x1: ");
    scanf("%d", &x1);
    printf("Введіть координату y1: ");
    scanf("%d", &y1);
    printf("Введіть радіус r1: ");
    scanf("%d", &r1);
    printf("Введіть координату x2: ");
    scanf("%d", &x2);
    printf("Введіть координату y2: ");
    scanf("%d", &y2);
    printf("Введіть радіус r2: ");
    scanf("%d", &r2);

    int intersection_points = count_intersection_points(x1, y1, r1, x2, y2, r2);

    printf("Кількість точок перетину: %d\n", intersection_points);

    return 0;
}
