# LabTest2-Automated-Teller-Machine
Automated Teller Machine 
/* Program used to operate an ATM
for a bank. This is used for
managing your Pin.

Author:Markus Baciu
Date:31.10.2018
*/
#include <stdio.h>
#define PIN 1234

int main()
{
    //variable initialisation
    int operation;
    int pin = PIN;
    int pin2;
    int correct = 0;
    int incorrect = 0;
    
    do
    {
        //The menu
        printf("\n\nWelcome to The ATM");
        printf("\nChoose one of the following:");
        printf("\n1.Enter Pin and verify correct");
        printf("\n2.Change Pin");
        printf("\n3.Display the number of times the pin was entered i)correctly ii)incorrectly");
        printf("\n4.Exit program\n");
        scanf("%d",&operation);
        
        
        //entering a pin
        if(operation == 1)
        {
            printf("\nEnter your pin\n");
            scanf("%d",&pin2);
            
            if(pin2 == pin)
            {
                printf("\nYour pin is correct");
                //incrementing correct counter by 1
                correct++;
            }//end if
            
            else
            {
                printf("Your pin is incorrect");
                //incrementing incorrect counter by 1
                incorrect++;
                
            }//end else
            
        }//end if(operation == 1)
        
        //changing pin
        if(operation == 2)
        {
            printf("\nEnter a new pin\n");
            scanf("%d",&pin2);
            
            if(pin2<0000||pin2>9999)
            {
                printf("Must be a number of 4 digits\n");
            }//end if
            
            else
            {
                //verification of new pin
                printf("Verify your pin\n");
                scanf("%d",&pin);
                
                if(pin2 == pin)
                {
                    printf("\nYou have changed your pin successfully");
                }//end if
                
                else //if verification is wrong, pin goes back to original pin
                {
                    pin = PIN;
                    printf("Verification incorrect.Your password has not changed");
                }//end inner else
            }//end outer else
        }//end if(operation == 2)
        
        //chcecking how many times password was entered correctly or incorrectly
        if(operation ==3)
        {
            printf("\n Your pin has been entered %d time(s) correctly",correct);
            printf("\n Your pin has been entered %d time(s) incorrectly",incorrect);
        }//end if(operation == 3)
    }
    //exit program
    while(operation !=4);
    {
        printf("You have exited the program");
    }//end do while loop

    return 0;
}//end main()
