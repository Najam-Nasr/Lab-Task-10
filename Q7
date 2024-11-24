#include <stdio.h>

typedef struct {
    int day;
    int month;
    int year;
} Date;

int leap_year(int year) {
    return ((year%4==0) && (year%100!=0)) || (year%400==0);
}

int date_validator(Date date) {
    int days_in_month[] = {0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};

    if (leap_year(date.year)) {
        days_in_month[2] = 29;
    }

    return (date.year>0 && date.month>=1 && date.month<=12 && date.day>=1 && date.day<=days_in_month[date.month]);
}

int days_calculator(Date d1, Date d2){
    int i;
    int daysInMonth[] = {0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};

    if (leap_year(d1.year)) 
    daysInMonth[2] = 29;
    
    if (leap_year(d2.year)) 
    daysInMonth[2] = 29;

    int days1 = d1.year * 365 + d1.day;
    int days2 = d2.year * 365 + d2.day;

    for (i=1;i<d1.month;i++) {
        days1 += daysInMonth[i];
    }

    for (i=1;i<d2.month;i++){
        days2 += daysInMonth[i];
    }

    for (i=1;i<d1.year;i++) {
        if (leap_year(i)) 
        days1++;
    }

    for (i=1;i<d2.year;i++) {
        if (leap_year(i)) 
        days2++;
    }

    return days2 - days1;
}

const char* dayOfWeek(Date date) {
    const char* days[] = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};
    int y = date.year;
    int m = date.month;
    int d = date.day;

    if (m<3) {
        m += 12;
        y -= 1;
    }

    int k = y % 100;
    int j = y / 100;

    int dayIndex = (d + (13 * (m + 1)) / 5 + k + (k / 4) + (j / 4) - 2 * j) % 7;

    return days[(dayIndex + 7) % 7];
}

int main() {
    Date date1, date2;

    printf("Enter the first date (dd mm yyyy): ");
    scanf("%d %d %d", &date1.day, &date1.month, &date1.year);

    if (!date_validator(date1)) {
        printf("Invalid first date. Please try again.\n");
        return 1;
    }

    printf("Enter the second date (dd mm yyyy): ");
    scanf("%d %d %d", &date2.day, &date2.month, &date2.year);

    if (!date_validator(date2)) {
        printf("Invalid second date. Please try again.\n");
        return 1;
    }

    printf("Number of days between %02d/%02d/%d and %02d/%02d/%d: %d\n", date1.day, date1.month, date1.year, date2.day, date2.month, date2.year,
    days_calculator(date1, date2));

    printf("Day of the week for %02d/%02d/%d: %s\n", date1.day, date1.month, date1.year, dayOfWeek(date1));

    printf("Day of the week for %02d/%02d/%d: %s\n", date2.day, date2.month, date2.year, dayOfWeek(date2));

}
