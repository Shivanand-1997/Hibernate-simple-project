# Hibernate-simple-projects
Its just simple basic project on Employee table to perform CRUD operation on table

package orggg.jsp;

import java.util.List;
import java.util.Scanner;

import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.EntityTransaction;
import javax.persistence.Persistence;
import javax.persistence.Query;

public class CRUD {

	public static void create(Employee e){

		EntityManagerFactory f = Persistence.createEntityManagerFactory("shivanand");
		EntityManager m = f.createEntityManager();
		EntityTransaction t = m.getTransaction();
		e.getAge();
		e.getDesignation();
		e.getId();
		e.getName();
		t.begin();
		m.persist(e);
		t.commit();
		System.out.println("Data Saved ");
		System.out.println("----------------");

	}
	public static void update(Employee e){

		EntityManagerFactory e2 = Persistence.createEntityManagerFactory("shivanand");
		EntityManager m2 = e2.createEntityManager();
		EntityTransaction t2 = m2.getTransaction();
		e.getAge();
		e.getDesignation();
		e.getId();
		e.getName();
		t2.begin();
		m2.merge(e);
		t2.commit();
		System.out.println("Data updaed ");
		System.out.println("-------------------------------------------");
	}
	public static void display(Employee e){
		EntityManagerFactory e3 = Persistence.createEntityManagerFactory("shivanand");
		EntityManager m3 = e3.createEntityManager();
		Employee x = m3.find(Employee.class, e.getId());
		if(x!=null){
			System.out.println(x.getAge());
			System.out.println(x.getDesignation());
			System.out.println(x.getName());
			System.out.println(x.getId());
			System.out.println("-------------------------------------------");
		}
		else{
			System.out.println("Employee Id doesnt exist");
			System.out.println("-------------------------------------------");
		}
	}
	public static void displayAll(Employee e){
		EntityManagerFactory e5 = Persistence.createEntityManagerFactory("shivanand");
		EntityManager m5 = e5.createEntityManager();
		Query q=m5.createQuery("select e from Employee e");
		List<Employee> ems=q.getResultList();
		for(Employee e2:ems)
		{
			System.out.print(e2.getId()+" "+e2.getName()+" "+e2.getAge()+" "+e2.getDesignation());
			System.out.println();
		}

	}
	public static void delete(Employee e){
		EntityManagerFactory e5 = Persistence.createEntityManagerFactory("shivanand");
		EntityManager m5 = e5.createEntityManager();
		EntityTransaction t5 = m5.getTransaction();
		Employee x = m5.find(Employee.class, e.getId());
		if(x!=null){
			t5.begin();
			m5.remove(x);
			t5.commit();
			System.out.println("-------------------------------------------");
		}
		else{
			System.out.println("Employee Id doesnt exist");
			System.out.println("-------------------------------------------");
		}


	}
	public static void main(String[] args) {

		Scanner s = new Scanner(System.in);

		while(true){
			System.out.println("-------------------------------------------");
			System.out.println("1: Enter new Employee details");
			System.out.println("2: Update existing Employee details");
			System.out.println("3: Display one  Employee details");
			System.out.println("4: Display All Employee details");
			System.out.println("5: Delete an  Employee details");
			System.out.println("6: Exit");
			System.out.println("-------------------------------------------");
			Employee e = new Employee();
			int choice = s.nextInt();
			switch(choice){
			case 1:
				System.out.println("1:id,/n 2:name, /n 3:age,/n4: designation");
				e.setId(s.nextInt());
				e.setName(s.next());
				e.setAge(s.nextInt());
				e.setDesignation(s.next());
				create(e);
				break;
			case 2:
				System.out.println("Enter the id of Employee you would like to update");
				e.setId(s.nextInt());
				System.out.println("1:name /n 2:age,/n3: designation");
				e.setName(s.next());
				e.setAge(s.nextInt());
				e.setDesignation(s.next());
				update(e);
				break;
			case 3:
				System.out.println("Enter the id of Employee you would like to display");
				e.setId(s.nextInt());
				display(e);
				break;
			case 4:
				displayAll(e);
				break;
			case 5:
				System.out.println("Enter the id of Employee you would like to delete");
				e.setId(s.nextInt());
				delete(e);
				break;
			case 6:
				System.out.println("Thank you");
				System.exit(0);
				s.close();
			}
		}
	}
}
