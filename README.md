// Expense tracker / CS350 project 
// Week 6 – Classes and Objects, applied to the Expense Tracker
//
// Shows:
//   1. Instantiating objects using new
//   2. Using dot notation to access fields and call methods
//   3. Multiple objects keeping independent state

public class ExpenseClassesDemo {

    public static void main(String[] args) {

        // ---------- 1. Create objects using new ----------
        ExpenseCategory food = new ExpenseCategory();
        ExpenseCategory transport = new ExpenseCategory();

        // ---------- 2. Dot notation: set the fields of each object ----------
        food.name = "Food";
        food.budgetLimit = 500.0;
        food.totalSpent = 0.0;

        transport.name = "Transport";
        transport.budgetLimit = 300.0;
        transport.totalSpent = 0.0;

        // Objects from the existing Expense class in ExpenseTracker.java
        ExpenseTracker.Expense lunch = new ExpenseTracker.Expense("Lunch", 45.0);
        ExpenseTracker.Expense groceries = new ExpenseTracker.Expense("Groceries", 180.0);
        ExpenseTracker.Expense busFare = new ExpenseTracker.Expense("Bus fare", 60.0);

        // Dot notation: call methods on the objects
        System.out.println("Expense object: " + lunch.getName() + " - K" + lunch.getPrice());

        food.addExpense(lunch);
        food.addExpense(groceries);
        transport.addExpense(busFare);
        transport.addSpending(25.0);

        // ---------- 3. Each object keeps its own state ----------
        System.out.println("\n----- Category Details -----");
        food.displayCategory();
        System.out.println();
        transport.displayCategory();

        // Changing one object does not affect the other
        food.name = "Food & Drinks";
        food.addSpending(100.0);

        System.out.println("\n----- After changing the food object only -----");
        System.out.println("food.name = " + food.name);
        System.out.println("transport.name = " + transport.name);
        System.out.println("food.totalSpent = K" + food.totalSpent);
        System.out.println("transport.totalSpent = K" + transport.totalSpent);
        System.out.println("food remaining = K" + food.remainingBudget());
        System.out.println("transport remaining = K" + transport.remainingBudget());
    }
}
 
