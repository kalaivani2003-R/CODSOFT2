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
