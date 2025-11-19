#include <stdio.h>
#include <stdlib.h>

#define MAX 50

int arr[MAX];
int top1 = -1;        // Top of Stack 1 (left side)
int top2 = MAX;       // Top of Stack 2 (right side)

// Push into Stack 1
void push1(int value) {
    if (top1 + 1 == top2) {
        printf("Stack Overflow!\n");
    } else {
        top1++;
        arr[top1] = value;
        printf("%d pushed to Stack 1\n", value);
    }
}

// Push into Stack 2
void push2(int value) {
    if (top2 - 1 == top1) {
        printf("Stack Overflow!\n");
    } else {
        top2--;
        arr[top2] = value;
        printf("%d pushed to Stack 2\n", value);
    }
}

// Pop from Stack 1
void pop1() {
    if (top1 == -1) {
        printf("Stack 1 Underflow!\n");
    } else {
        printf("%d popped from Stack 1\n", arr[top1]);
        top1--;
    }
}

// Pop from Stack 2
void pop2() {
    if (top2 == MAX) {
        printf("Stack 2 Underflow!\n");
    } else {
        printf("%d popped from Stack 2\n", arr[top2]);
        top2++;
    }
}

// Display Stack 1
void display1() {
    if (top1 == -1) {
        printf("Stack 1 is empty!\n");
    } else {
        printf("Stack 1 elements:\n");
        for (int i = top1; i >= 0; i--) {
            printf("%d\n", arr[i]);
        }
    }
}

// Display Stack 2
void display2() {
    if (top2 == MAX) {
        printf("Stack 2 is empty!\n");
    } else {
        printf("Stack 2 elements:\n");
        for (int i = top2; i < MAX; i++) {
            printf("%d\n", arr[i]);
        }
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("\n--- Two Stacks Menu ---\n");
        printf("1. Push to Stack 1\n");
        printf("2. Push to Stack 2\n");
        printf("3. Pop from Stack 1\n");
        printf("4. Pop from Stack 2\n");
        printf("5. Display Stack 1\n");
        printf("6. Display Stack 2\n");
        printf("7. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value: ");
                scanf("%d", &value);
                push1(value);
                break;

            case 2:
                printf("Enter value: ");
                scanf("%d", &value);
                push2(value);
                break;

            case 3:
                pop1();
                break;

            case 4:
                pop2();
                break;

            case 5:
                display1();
                break;

            case 6:
                display2();
                break;

            case 7:
                exit(0);

            default:
                printf("Invalid choice!\n");
        }
    }

    return 0;
}
# 1_3-of-program_Shah.c
Two stacks using single array (generalize to n no. of stacks).
