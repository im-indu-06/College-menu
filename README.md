---

# 📌 In-Depth Explanation – College Canteen Billing System

## 🔹 1️⃣ Program Purpose

This program is a **menu-driven billing system** for a college canteen.
It allows the user to:

* Select a food category
* Choose food items
* Enter quantity
* Order multiple items
* Generate a detailed bill receipt

It simulates a real-world billing system.

---

# 🔹 2️⃣ Import Statement

```java
import java.util.*;
```

This imports:

* `Scanner` → for user input
* `ArrayList` → to store ordered items dynamically

---

# 🔹 3️⃣ Main Method

```java
public static void main(String[] args)
```

Execution of the program starts here.

---

# 🔹 4️⃣ Variable Declaration

```java
Scanner sc = new Scanner(System.in);
double totalBill = 0;
boolean continueOrder = true;
```

* `sc` → Reads user input
* `totalBill` → Stores total amount of all items
* `continueOrder` → Controls loop for multiple orders

---

# 🔹 5️⃣ ArrayLists for Storing Orders

```java
ArrayList<String> orderedItems = new ArrayList<>();
ArrayList<Integer> orderedQty = new ArrayList<>();
ArrayList<Double> orderedPrice = new ArrayList<>();
```

These store:

* Food names
* Quantities
* Total price per item

Why ArrayList?
Because the number of ordered items is not fixed. It can grow dynamically.

---

# 🔹 6️⃣ While Loop (Main Ordering Loop)

```java
while (continueOrder)
```

This loop runs until the user chooses to stop ordering.

---

# 🔹 7️⃣ Display Main Menu

The program shows 5 categories:

1. Tiffins
2. Lunch
3. Snacks
4. Beverages
5. Bakery Items
6. Exit

User selects category using `mainChoice`.

---

# 🔹 8️⃣ Arrays for Items and Prices

```java
String[] items = {};
double[] prices = {};
```

Inside each `switch case`, the program assigns:

* Item names
* Corresponding prices

Example:

```java
items = new String[]{"Idly","Dosa","Vada"...};
prices = new double[]{30,40,25...};
```

Index positions match:

* `items[0]` → price `prices[0]`

---

# 🔹 9️⃣ Display Items in Selected Category

```java
for (int i = 0; i < items.length; i++)
```

Loop prints all items with price.

---

# 🔹 1️⃣0️⃣ Item Selection & Quantity

```java
int itemChoice = sc.nextInt();
int quantity = sc.nextInt();
```

User selects:

* Item number
* Quantity

---

# 🔹 1️⃣1️⃣ Bill Calculation

```java
String selectedItem = items[itemChoice - 1];
double itemPrice = prices[itemChoice - 1];
double itemTotal = itemPrice * quantity;
```

* `itemChoice - 1` → because arrays start at index 0
* Total price = price × quantity

Then:

```java
totalBill += itemTotal;
```

Adds to grand total.

---

# 🔹 1️⃣2️⃣ Store Order Details

```java
orderedItems.add(selectedItem);
orderedQty.add(quantity);
orderedPrice.add(itemTotal);
```

This ensures:

* All ordered items are saved
* Receipt can be printed later

---

# 🔹 1️⃣3️⃣ Continue Ordering

```java
continueOrder = sc.nextBoolean();
```

If user enters:

* `true` → continue
* `false` → stop ordering

---

# 🔹 1️⃣4️⃣ Bill Receipt Section

After loop ends:

```java
System.out.printf("%-20s %-10s %-10s\n", "Item", "Qty", "Amount");
```

Formatted output:

* Left-aligned columns
* Professional bill format

Then loop prints:

* Item name
* Quantity
* Total price per item

Finally prints:

```java
System.out.println("Total Amount: ₹" + totalBill);
```

---

# 🔹 1️⃣5️⃣ Closing Scanner

```java
sc.close();
```

Closes input stream (good practice).

---

# 🎯 Concepts Used in This Program

✔ Arrays
✔ ArrayList
✔ Switch-case
✔ While loop
✔ For loop
✔ Conditional statements
✔ Arithmetic operations
✔ Formatted printing (`printf`)
✔ User input handling

---

# 💡 Strength of This Program

* Dynamic ordering
* Clean billing structure
* Real-world application
* Easy to upgrade (GST, discount, invoice number)

---
