package codsofttasks;
import java.util.Scanner;

public class StudentGradeCalculator{
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Step 1: Input number of subjects
        System.out.print("Enter number of subjects: ");
        int numSubjects = sc.nextInt();

        int totalMarks = 0;

        // Step 2: Take marks for each subject
        for (int i = 1; i <= numSubjects; i++) {
            System.out.print("Enter marks for subject " + i + " (out of 100): ");
            int marks = sc.nextInt();

            // Validation to ensure correct input
            if (marks < 0 || marks > 100) {
                System.out.println("Invalid marks! Please enter between 0 and 100.");
                i--; // Repeat for the same subject
                continue;
            }

            totalMarks += marks;
        }

        // Step 3: Calculate average percentage
        double averagePercentage = (double) totalMarks / numSubjects;

        // Step 4: Grade calculation
        String grade;
        if (averagePercentage >= 90) {
            grade = "A";
        } else if (averagePercentage >= 80) {
            grade = "B";
        } else if (averagePercentage >= 70) {
            grade = "C";
        } else if (averagePercentage >= 60) {
            grade = "D";
        } else {
            grade = "F";
        }

        // Step 5: Display results
        System.out.println("\n----- Student Grade Report -----");
        System.out.println("Total Marks: " + totalMarks);
        System.out.println("Average Percentage: " + averagePercentage + "%");
        System.out.println("Grade: " + grade);

        sc.close();
    }
}
