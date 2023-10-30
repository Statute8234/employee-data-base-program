import java.util.List;
import java.util.Scanner;

public class Project {
    public static void main(String[] args) {
        while (true) {
            Scanner input = new Scanner(System.in);
            System.out.println("How many employees? ");
            int numberEmployees = input.nextInt();
            String[][] employeeDataBase = new String[numberEmployees][2];
            System.out.println("Would you like to add names to the employeeDataBase? [Y | N]");
            List<String> myList = List.of("Y", "N");
            String userChoice = Continue(myList);
            if (userChoice.equalsIgnoreCase("Y")) {
                addToEmployeeDataBase(numberEmployees, employeeDataBase);
            } else {
                System.out.println(
                        "Would else would you like to do? [check employee data base | edit employee data base | add employee data base]");
                myList = List.of("check employee data base", "edit employee data base", "add employee data base");
                userChoice = Continue(myList);
                if (userChoice.equalsIgnoreCase("check employee data base")) {
                    System.out.println("Enter employee nane");
                    String name = input.nextLine();
                    name = input.nextLine();
                    checkEmployeeDataBase(name, employeeDataBase);
                }
                if (userChoice.equalsIgnoreCase("edit employee data base")) {
                    editToEmployeeDataBase(numberEmployees, employeeDataBase);
                }
                if (userChoice.equalsIgnoreCase("add employee data base")) {
                    addToEmployeeDataBase(numberEmployees, employeeDataBase);
                }
            }
        }
    }

    public static String Continue(List<String> list) {
        Scanner input = new Scanner(System.in);
        String userContinueWith;
        while (true) {
            System.out.println("Enter your choice:");
            String continueString = input.nextLine();

            if (list.contains(continueString)) {
                userContinueWith = continueString.toLowerCase();
                return userContinueWith;
            } else {
                System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    public static boolean checkEmployeeDataBase(String name, String[][] employeeDataBase) {
        for (int x = 0; x < employeeDataBase.length; x++) {
            if (name.equalsIgnoreCase(employeeDataBase[x][0])) {
                System.out.printf("Name: %s  PerHour: $%s\n");
                return true;
            }
        }
        System.out.printf("sorry, '%s' is not there.\n", name);
        return false;
    }

    public static void editToEmployeeDataBase(int numberEmployees, String[][] employeeDataBase) {
        Scanner input = new Scanner(System.in);
        String name, userChoice, newName;
        double revenue;
        boolean check = false;
        for (int x = 0; x < numberEmployees; x++) {
            System.out.println("Name of employee");
            name = input.nextLine();
            check = checkEmployeeDataBase(name,employeeDataBase);
            if (check) {
                System.out.println("New employee name");
                newName = input.nextLine();
                System.out.println("New employee revenue");
                revenue = input.nextDouble();
                employeeDataBase[x][0] = Double.toString(revenue);
            } else {
                System.out.printf("Sorry, can not find '%s\n",name);
            }
        }
    }

    public static void addToEmployeeDataBase(int numberEmployees, String[][] employeeDataBase) {
        Scanner input = new Scanner(System.in);
        String name;
        double perHourRevenue;
        for (int x = 0; x < numberEmployees; x++) {
            System.out.println("What is the name of the new employee?");
            name = input.nextLine();
            System.out.println("How much perHour");
            perHourRevenue = input.nextDouble();
            boolean check = checkEmployeeDataBase(name, employeeDataBase);
            if (check) {
                System.out.println("Sorry, that name already exists");
            } else {
                int lastRowIndex = employeeDataBase.length - 1;
                employeeDataBase[lastRowIndex][0] = name;
                employeeDataBase[lastRowIndex][1] = Double.toString(perHourRevenue);
                System.out.printf("'%s' has been added, they will make $%d per hour \n", name, perHourRevenue);
            }
        }
    }
}
