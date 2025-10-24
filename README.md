Accounting Ledger App (Java CLI)

Welcome to the Accounting Ledger App, a  Java-based Command Line Interface (CLI)  that helps users track financial transactions — deposits, payments, and custom reports — stored in a persistent `transactions.csv` file.

t demonstrates clean OOP design, real-world logic, and user-focused CLI interaction.



Project Goals (per Capstone Spec )

-  Add Deposits & Payments  
-  Display Ledger (All / Deposits / Payments)  
-  Run Reports:  
  - Month-to-Date  
  - Previous Month  
  - Year-to-Date  
  - Previous Year  
  - Search by Vendor  
  - Custom Search by date, description, vendor, amount  
- Input validation (no crashing on bad input)  
- Stores data in `transactions.csv`  
- Uses `Scanner`, `BufferedReader/Writer`, `ArrayList`, `LocalDate/Time`



Features & Highlights

CLI Menu with emojis and ANSI-colored text  
Add deposits &  make payments — cleanly saved  
View ledger, sorted newest first  
Built-in Reports with live filters  
Custom Search (mix & match fields)  
Summary Stats: Income, Expenses, Net Balance  
Smart Error Handling — app doesn't crash on bad input


Screenshots 


- 🏠 Main Menu
- ![image](https://github.com/user-attachments/assets/50e1ada7-0810-4e06-810e-6af444351d98)

- 💰 Deposit Form
- ![image](https://github.com/user-attachments/assets/b6cb1675-db66-4f93-8b64-e85e08bb061e)

- 📉 Reports Screen
- ![image](https://github.com/user-attachments/assets/5c8b7473-72d6-4cee-8cae-05c46315067f)
 
- 🔍 Custom Search Prompt
- ![image](https://github.com/user-attachments/assets/70784b23-fa33-4af0-bf46-4bbc44ef90d4)

- 📊 Ledger Output + Net Balance Summary

![image](https://github.com/user-attachments/assets/1c0d073b-40ae-4162-bce4-b2170690de7d)


##  Interesting Code Snippet

Safe numeric input handling with retry prompt:

```java
public static double getValidAmount(Scanner sc) {
    while (true) {
        String input = sc.nextLine();
        try {
            return Double.parseDouble(input);
        } catch (NumberFormatException e) {
            System.out.print("\u001B[31m❌ Invalid number. Try something like 125.50 💡\u001B[0m\n💵 Enter amount again: ");
        }
    }
}
