# OnTimeForExam

import java.util.Scanner;

public class P39_OnTimeForExam {

    public static void main(String[] args) {
        Scanner var_scan = new Scanner(System.in);
        int examHour = Integer.parseInt(var_scan.nextLine());
        int examMinutes = Integer.parseInt(var_scan.nextLine());
        int arrivalHour = Integer.parseInt(var_scan.nextLine());
        int arrivalMinutes = Integer.parseInt(var_scan.nextLine());

        int examTimeMinutes = examHour * 60 + examMinutes;
        int arrivalTimeMinutes = arrivalHour * 60 + arrivalMinutes;
        int diff = Math.abs(examTimeMinutes - arrivalTimeMinutes);
        int diffHours = 0;
        int diffMinutes = 0;

        if (examTimeMinutes < arrivalTimeMinutes) {
            System.out.println("Late");
            if (diff < 60) {
                System.out.printf("%d minutes after the start", diff);
            } else {
                diffHours = diff / 60;
                diffMinutes = diff % 60;
                if (diffMinutes < 10) {
                    System.out.printf("%d:0%d hours after the start", diffHours, diffMinutes);
                } else {
                    System.out.printf("%d:%d hours after the start", diffHours, diffMinutes);
                }
            }

        } else if (examTimeMinutes > arrivalTimeMinutes) {
            if (diff <= 30) {
                System.out.println("On time");
                System.out.printf("%d minutes before the start", diff);
            } else if (diff < 60) {
                System.out.println("Early");
                System.out.printf("%d minutes before the start", diff);
            } else {
                System.out.println("Early");
                diffHours = diff / 60;
                diffMinutes = diff % 60;
                if (diffMinutes < 10) {
                    System.out.printf("%d:0%d hours before the start", diffHours, diffMinutes);
                } else {
                    System.out.printf("%d:%d hours before the start", diffHours, diffMinutes);
                }
            }
        } else {
            System.out.print("On time");
        }

    }

}
