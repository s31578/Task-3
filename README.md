# Task-3
import java.util.ArrayList;// Press Shift twice to open the Search Everywhere dialog and type `show whitespaces`,
// then press Enter. You can now see whitespace characters in your code.
import java.util.ArrayList;
import java.util.List;

public class Student {
    public String firstName;
    public String lastName;
    public int age;
    public List<Double> grades;
    public Student(String firstName, String lastName, int age) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
        this.grades = new ArrayList<>();
    }public double calculateAverageGrade() {
        if (grades.isEmpty()) {throw new IllegalArgumentException("No grades available for student " + firstName + " " + lastName);}

        double sum = 0;
        for (Double grade : grades) {
            sum += grade;
        }
       double average = sum / grades.size();
        return roundToNearest(average);
    }
    private double roundToNearest(double value) {
        double[] nearestValues = {2,2.5, 3, 3.5, 4, 4.5, 5};
        double minDiff = Double.MAX_VALUE;
        double closestValue = value;

        for (double v : nearestValues) {
            double diff = Math.abs(value - v);
            if (diff < minDiff) {
                minDiff = diff;
                closestValue = v;
            }
    }
}
