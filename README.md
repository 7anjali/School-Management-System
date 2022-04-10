# School-Management-System
// School management can save lot's of paper and space of files and also it is easy to use you don't had to have high knowledge of computers with the help of this application.
package fIRSTPROJECT;
import java.util.ArrayList;
import java.util.List;

public class Main {
	

	public static void main(String[] args) {
		Teacher Snape = new Teacher(1,"Severes Snape",500);
        Teacher  Dumbledore= new Teacher(2,"Albus Dumbledore",700);
        Teacher vanderhorn = new Teacher(3,"Vanderhorn",600);

        List<Teacher> teacherList = new ArrayList<>();
        teacherList.add(Snape);
        teacherList.add(Dumbledore);
        teacherList.add(vanderhorn);


        Student Harry = new Student(1,"Harry Potter",4);
        Student Ron = new Student(2,"Ron weasely",12);
        Student Hermonie = new Student(3,"Hermonie Granger",5);
        List<Student> studentList = new ArrayList<>();

        studentList.add(Harry);
        studentList.add(Hermonie);
        studentList.add(Ron);

        School ghs = new School(teacherList,studentList);

        Teacher megan = new Teacher(6,"Megan", 900);

        ghs.addTeacher(megan);


        Harry.payFees(5000);
        Ron.payFees(6000);
        System.out.println("GHS has earned $"+ ghs.getTotalMoneyEarned());

        System.out.println("------Making SCHOOL PAY SALARY----");
        Snape.receiveSalary(Snape.getSalary());
        System.out.println("GHS has spent for salary to " + Snape.getName()
        +" and now has $" + ghs.getTotalMoneyEarned());

        vanderhorn.receiveSalary(vanderhorn.getSalary());
        System.out.println("GHS has spent for salary to " + vanderhorn.getName()
                +" and now has $" + ghs.getTotalMoneyEarned());


        System.out.println(Ron);

        Dumbledore.receiveSalary(Dumbledore.getSalary());

        System.out.println( Dumbledore);


    }
		
	}



