# EXPENCE-TRACKER
For those students who are unable to handle there budgets for there monthly uses and daily basis needs, etc. 

#include <stdio.h>
#include <string.h>

#define MAX_EXPENSES 100

struct Expense {
    char date[11];
    char category[20];
    char description[50];
    float amount;
};

int main() {
    struct Expense expenses[MAX_EXPENSES];
    int count = 0;
    int choice;

    while (1) {
        printf("\nExpense Tracker\n");
        printf("1. Add Expense\n");
        printf("2. View All Expenses\n");
        printf("3. Total Amount\n");
        printf("4. Exit\n");
        printf("Choose an option: ");
        scanf("%d", &choice);

        if (choice == 1) {
            printf("Enter date (YYYY-MM-DD): ");
            scanf("%s", expenses[count].date);

            printf("Enter category: ");
            scanf("%s", expenses[count].category);

            printf("Enter description: ");
            scanf(" %[^\n]s", expenses[count].description);

            printf("Enter amount: ");
            scanf("%f", &expenses[count].amount);

            count++;
            printf("Expense added successfully!\n");
        }
        else if (choice == 2) {
            printf("\nAll Expenses:\n");
            for (int i = 0; i < count; i++) {
                printf("%s | %s | %s | %.2f\n",
                       expenses[i].date,
                       expenses[i].category,
                       expenses[i].description,
                       expenses[i].amount);
            }
        }
        else if (choice == 3) {
            float total = 0;
            for (int i = 0; i < count; i++) {
                total += expenses[i].amount;
            }
            printf("Total expenses: %.2f\n", total);
        }
        else if (choice == 4) {
            break;
        }
        else {
            printf("Invalid choice!\n");
        }
    }

    return 0;
}