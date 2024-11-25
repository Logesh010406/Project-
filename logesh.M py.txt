#include <stdio.h>
void displaySeatingArrangement() {
    int exam_id;
    printf("Enter exam ID to display seating arrangement: ");
    scanf("%d", &exam_id);

    printf("Seating Arrangement for Exam ID %d:\n", exam_id);
    for (int i = 0; i < student_count; i++) {
        if (students[i].exam_id == exam_id) {
            printf("Seat %d: %s (ID: %d)\n", students[i].seat_number, students[i].name, students[i].student_id);
        }
    }
}

int main() {
    int choice;
    while (1) {
        printf("\n=== Examprocto System ===\n");
        printf("1. Add Student\n");
        printf("2. Add Exam\n");
        printf("3. Arrange Seating\n");
        printf("4. Distribute Exam Papers\n");
        printf("5. Display Seating Arrangement\n");
        printf("6. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                addStudent();
                break;
            case 2:
                addExam();
                break;
            case 3:
                arrangeSeating();
                break;
            case 4:
                distributeExamPapers();
                break;
            case 5:
                displaySeatingArrangement();
                break;
            case 6:
                exit(0);
            default:
                printf("Invalid choice.\n");
        }
    }
    return 0;
}