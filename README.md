# CODSOFT2
#TASK5
import java.util.Scanner;

class courseDatabase{
    int coursecode;
    String title;
    String description;
    int capacity;
    int schedule;
}
class studentdatabase{
    int studID;
    String studname;
    String coursename;
}
class courselist{
    int availabale_slot;
    String course_available;
    
}
class Main {
    public static void main(String[] args) {
        courseDatabase mycd1=new courseDatabase();
        mycd1.coursecode=1;
	    mycd1.title="hi";
	    mycd1.description="msg";
	    mycd1.capacity=10;
	    mycd1.schedule=10;
	    String details="coursecode:"+ mycd1.coursecode +"\ntitle:"+ mycd1.title +"\ndescription:" + mycd1.description + 
	                    "\ncapacity:"+ mycd1.capacity +"\nschedule:"+ mycd1.schedule ;
	    System.out.println("the details are\n" +details);
	    
	    
	    studentdatabase mystu=new studentdatabase();
	    mystu.studID=2;
	    mystu.studname="kalai";
	    mystu.coursename="ECE";
	    String studetails="stuID:"+mystu.studID +"\nstudentname:"+mystu.studname+ "\ncoursename:"+mystu.coursename;
	    System.out.println("the students details are\n" + studetails);
	    
	    courselist sc=new courselist();
	    System.out.println("enter available couses:");
	    sc.course_available="Course 1: ECE\nCourse 2: CSE";
	    sc.availabale_slot=9;
	    String coursedetails=sc.course_available+"\nECE: 2 slots available\nCSE: 4 slots available";
	    System.out.println("courssedails are\n" +coursedetails);
	    if (sc.availabale_slot > 0) {
            System.out.println("The students will be able to register:");
            Scanner scanner = new Scanner(System.in);
            System.out.println("Enter your choice (1 for ECE, 2 for CSE): ");
            int choice = scanner.nextInt();
           

            switch (choice) {
                case 1:
                    System.out.println("The student can register for ECE with 2 slots available");
                    break;
                case 2:
                    System.out.println("The student can register for CSE with 4 slots available");
                    break;
                default:
                    System.out.println("There are no slots available");
            }
        } else {
            System.out.println("No slots are available for registration.");
        }
    }
}

#TASK1
import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Random value = new Random();
        int min = 1;
        int max = 100;
        int attempts=3;
        int score=0;
        boolean playagain=true;
        boolean correctguess=false;
        Scanner sc = new Scanner(System.in);
        while(playagain){
            
        
        int randomNumber = value.nextInt((max - min + 1)) + min;
        System.out.println(randomNumber);
        System.out.println("enter the guess between(1-100): ");
    
        
        for(int count =1; count<=attempts;count++){
            int guess= sc.nextInt();
            System.out.println("attempts" + count + " ");
        
        if (guess == randomNumber){
            System.out.println("Your guess is right:");
            correctguess=true;
            score++;
            break;
            
        }
    
        else if(guess < randomNumber){
            System.out.println("Your guess is less than the generated random number:");
        }
        
        else {
            System.out.println("your guess is wrong:");
        }
        if (!correctguess){
            System.out.println("Sorry, you've used all your attempts. The correct number was " + randomNumber + ".");
        }
        }
        
        
        System.out.print("Do you want to play again? (yes/no): ");
            sc.nextLine(); // Consume the newline
            String response = sc.nextLine();

            if (!response.equals("yes")) {
                playagain = false;
            }
        }

        System.out.println("Your total score based upon number of win is: " + score);
        sc.close();
        
      
    }
}

#TASK2

import java.util.Scanner;
public class Main{
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        System.out.println("enter the number of subjects:");
        int n=sc.nextInt();
        int marks[]=new int[n];
        System.out.println("Enter the marks of each student (1-100):");
        //getting the marks of n number of students
        for(int i=0;i<n;i++){
            int mark=0;
            do{
                System.out.println("enter the marks for each subject"+(i+1)+"-");
                mark=sc.nextInt();
                if(mark>100){
                    System.out.println("invalid mark.please enter the mark again between 1-100");
                }
                else{
                    marks[i]=mark;
                }
                
            }while(mark>100);
        }
        System.out.println("Marks entered:");
        for (int i = 0; i < n; i++) {
            System.out.println("Subject " + (i + 1) + ": " + marks[i]);   //displaying the marks
        }
        int total=0;
        for(int i=0;i <=marks.length;i++){                                //toyal marks
            total += marks[i];
            System.out.println("the total marks of students is" + total);
            float avgpercentage=((float) total/ (n*100)) * 100;           //avgpercentage
            System.out.println("the avgpercentage is" + avgpercentage+"%");
        }
    }
}
