# servi-core-
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

void displayWelcomeMessage()
{

    printf("\n");
    printf("*\n");
    printf("*                                  *\n");
    printf("*      WELCOME TO SERVI            *\n");
    printf("*             CORE                 *\n");
    printf("*                                  *\n");
    printf("*\n");
    printf("\n");
}

int main()
{
    int service;
    char experience[100];
    char serviceName[50];
    int rating;
    FILE *file;
    displayWelcomeMessage();

    printf("1 FOR PLUMBER\n");
    printf("2 FOR ELECTRICIAN\n");
    printf("3 FIR CAR MECHANIC\n");
    printf("4 FOR MOBILE PHONE REPAIR\n");
    printf("5 FOR FURNITURE REPAIRING\n");
    printf("6 FOR LAPTOP REPAIRING\n");
    printf("ENTER A NUMBER FOR THE SERVICE :");
    scanf("%d", &service);

    switch (service)
    {
    case 1:
        strcpy(serviceName, "PLUMBER ");
        printf("NAME : PAKISTAN PLUMBER \n");
        printf("EXPERIENCE : 10 YEARS \n");
        printf("RATING : 4.5/5 \n");
        printf("Phone : +91 1234567890 \n");
        break;
    case 2:
        strcpy(serviceName, "ELECTRICIAN ");
        printf("NAME : ROHAN ELECTRICIAN \n");
        printf("EXPERIENCE : 5 YEARS \n");
        printf("RATING : 4.0/5 \n");
        printf("Phone : +91 9876543210 \n");
        break;
    case 3:
        strcpy(serviceName, "CAR MECHANIC ");
        printf("NAME : ALI CAR MECHANIC \n");
        printf("EXPERIENCE : 8 YEARS \n");
        printf("RATING : 4.2/5 \n");
        
        printf("Phone : +91 8765432109 \n");
        break;
    case 4:
        strcpy(serviceName, "MOBILE PHONE REPAIR ");
        printf("NAME : SARAH MOBILE REPAIR \n");
        printf("EXPERIENCE : 3 YEARS \n");
        printf("RATING : 4.8/5 \n");
        printf("Phone : +91 7654321098 \n");
        break;
    case 5:
        strcpy(serviceName, "FURNITURE REPAIRING ");
        printf("NAME : AHMED FURNITURE REPAIR \n");
        printf("EXPERIENCE : 6 YEARS \n");
        printf("RATING : 4.3/5 \n");
        printf("Phone : +91 1357911234 \n");
        break;
    case 6:
        strcpy(serviceName, "LAPTOP REPAIRING ");

        printf("NAME : FATIMA LAPTOP REPAIR \n");
        printf("EXPERIENCE : 4 YEARS \n");
        printf("RATING : 4.6/5 \n");
        printf("Phone : +91 1122334455 \n");
        break;
    default:
        printf("INVALID SERVICE NUMBER. PLEASE TRY AGAIN.\n");
        return 1;
    }
    printf("PLEASE RATE THE SERVICE (1-5): ");
    getchar();
    fgets(experience, sizeof(experience), stdin);
    rating = atoi(experience);
    if (rating >= 1 && rating <= 5)
    {
        printf("THANK YOU FOR RATING %s WITH %d STARS!\n", serviceName, rating);
        file = fopen("service_ratings.txt", "a");
        if (file != NULL)
        {
            fprintf(file, "Service: %s, Rating: %d\n", serviceName, rating);
            fclose(file); 
        }
        else
        {
            printf("ERROR OPENING FILE TO SAVE RATING.\n");
        }
    }
    else
    {
        printf("INVALID RATING. PLEASE ENTER A NUMBER BETWEEN 1 AND 5.\n");
    }
    printf("THANK YOU FOR USING SERVI CORE! HAVE A GREAT DAY!\n");
    return 0;
}
