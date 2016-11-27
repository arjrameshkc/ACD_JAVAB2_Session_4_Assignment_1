# ACD_JAVAB2_Session_4_Assignment_1

Employee:
package session4_assignment;     //one package

public class Employee {
	int id;
	String name;
	double basicSalary;
	double hra;
	double da;
	double lta;
	double pf;
	public Employee(int id, String name, double basicSalary, double hra, double da, double lta, double pf) {
		super();
		this.id = id;
		this.name = name;
		this.basicSalary = basicSalary;
		this.hra = hra;
		this.da = da;
		this.lta = lta;
		this.pf = pf;
	}
protected double calculateSalary(){
	
	double sal = basicSalary + hra + da + lta - pf ;
	return sal;
}

}

Manager:
  package session4_different.pack;     // different package
import session4_assignment.Employee;

public class Manager extends Employee {
    double projectAllowance;
    boolean profitDone;
   	public Manager(int id, String name, double basicSalary, double hra, double da, double lta, double pf,
			double projectAllowance,boolean profitDone) {
		super(id, name, basicSalary, hra, da, lta, pf);
		this.projectAllowance = projectAllowance;
		this.profitDone = profitDone;
		
	}

	@Override
	public double calculateSalary() {
		// TODO Auto-generated method stub
		if (profitDone) {
			  return super.calculateSalary() + projectAllowance ;
		}
		else
		{
			return super.calculateSalary() ;
		}
	}	

}
Mainclass:
package session4_assignment;

import session4_different.pack.Manager;

public class MainEmployee {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
     
	Employee empOne = new Employee(12,"ramesh",7000.00,1200.00,500.00,200.00,3000.00);
	System.out.println("the employee Salary is:" +empOne.calculateSalary());
	
    Manager empTwo = new Manager(12,"ramesh",7000.00,1200.00,500.00,200.00,3000.00,2000.00,true);
	System.out.println("the manager Salary is:" + empTwo.calculateSalary());
	
	}
	
}
