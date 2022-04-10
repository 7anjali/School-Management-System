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




public class School {
	 private List<Teacher> teachers;
	 private List<Student> students;
	 private static int  totalMoneyEarned;
	 private static int totalMoneySpent;
	

	public School(List<Teacher> teachers, List<Student> students) {
		this.teachers = teachers;
        this.students = students;
        totalMoneyEarned=0;
        totalMoneySpent=0;
		
	}
	public List<Teacher> getTeachers() {
        return teachers;
    }
	public void addTeacher(Teacher teacher) {
        teachers.add(teacher);
    }
	public List<Student> getStudents() {
        return students;
    }
	 public void addStudent(Student student) {
	        students.add(student);
	    }
	 public int getTotalMoneyEarned() {
	        return totalMoneyEarned;
	    }
	 public static void updateTotalMoneyEarned(int MoneyEarned) {
	        totalMoneyEarned += MoneyEarned;
	    }

	 public int getTotalMoneySpent() {
	        return totalMoneySpent;
	    }
	 public static void updateTotalMoneySpent(int moneySpent) {
	        totalMoneyEarned-=moneySpent;
	     }
}
 public class Teacher {

    private int id;
    private String name;
    private int salary;
    private int salaryEarned;

	public Teacher() {
		 this.id=id;
	     this.name=name;
	     this.salary=salary;
	     this.salaryEarned=0;
	}
	 public Teacher(int id, String name, int salary){
	        this.id=id;
	        this.name=name;
	        this.salary=salary;
	        this.salaryEarned=0;
	    }
	public int getId(){
        return id;
    }
	public String getName(){
        return name;
    }
	  public int getSalary(){
	        return  salary;
	    }
	  public void setSalary(int salary){
	        this.salary=salary;
	    }
	  public void receiveSalary(int salary){
	        salaryEarned+=salary;
	        School.updateTotalMoneySpent(salary);
	    }
	  @Override
	    public String toString() {
	        return "Name of the Teacher: " + name
	                +" Total salary earned so far $"
	                + salaryEarned;
	    }
}
public class Student {
private int id;
private String name;
private int grade;
private int feesPaid;
private int feesTotal;

 public Student(int id, String name, int grade){
	 this.feesPaid=0;
     this.feesTotal=30000;
     this.id=id;
     this.name=name;
     this.grade=grade;
     
    
     }
 public void setGrade(int grade){
     this.grade=grade;
 }
 public void payFees(int fees){
     feesPaid+=fees;
     School.updateTotalMoneyEarned(feesPaid);
 }
 public int getId() {
     return id;
 }
 public String getName() {
     return name;
 }
 public int getGrade() {
     return grade;
 }
 public int getFeesPaid() {
     return feesPaid;
 }
 public int getFeesTotal() {
     return feesTotal;
 }
 public int getRemainingFees(){
     return feesTotal-feesPaid;
 }
 @Override
 public String toString() {
     return "Student's name :"+name+
             " Total fees paid so far $"+ feesPaid;
 }
 }



