#include<stdio.h>
#define max_temp 30
int temp_checker(int temp[], int num);
int main(){
    printf("Please enter how many temperatures you have: ");
    int i,result,num;
    scanf("%d",&num);
    int temp[100];
    for(i=0;i<num;i++){
        printf("Please enter temperature %d:",i+1);
        scanf("%d",&temp[i]);
    }
    result = temp_checker(temp,num);
    printf("The temperature exceeded the maximum temperature %d times",result);

}
int temp_checker(int temp[], int num) {
    static int count = 0; 
    if (num>0) {
        if (temp[num-1]>max_temp) { 
            count++;
        }
        temp_checker(temp,num-1);
    }
    return count;
}
