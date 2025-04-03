# Expense Tracker

## Introduction
The **Expense Tracker** is a Python-based application designed to help users manage their finances efficiently. It provides functionalities to log expenses, set budgets, and generate reports, all within an intuitive **Tkinter** GUI. The project integrates **MySQL** for data storage and **Matplotlib** for data visualization.

---

## Objectives
- Provide an easy-to-use interface for tracking expenses.
- Categorize expenses for better financial management.
- Allow users to set budgets and monitor spending habits.
- Generate reports and visualize financial data.

---

## Technologies Used
- **Programming Language:** Python
- **GUI Framework:** Tkinter
- **Database:** MySQL
- **Visualization Library:** Matplotlib

---

## Features

### User Interface
- A **Tkinter**-based GUI with navigation menus.
- **Home Page** displaying a welcome message.

### Expense Management
- Users can enter expenses and assign them to predefined categories.
- Expenses are stored in a MySQL database for persistence.

### Budgeting
- Users can set category-specific budgets.
- Budgets help users track their spending against limits.

### Reporting & Visualization
- A report page displaying **expenses vs. budgets** in tabular form.
- A **data visualization** option using Matplotlib.

---

## Implementation Details

### Database Connection
The application connects to a **MySQL database** using the `mysql.connector` module. The connection is established with:
```python
cnx = mysql.connector.connect(
    user=username,
    password=password,
    host=host,
    database=database
)
cursor = cnx.cursor()
```

### GUI Structure
The main interface is structured into:
- **Header Frame** (Logo & Title)
- **Navigation Bar** (Buttons for Home, Expenses, Budget, Reports, Logout)
- **Content Frame** (Dynamic content based on user selection)

### Functions for Page Navigation
Each page (Home, Expenses, Budget, Reports) has a dedicated function:
```python
def show_expenses_page():
    for widget in content_frame.winfo_children():
        widget.destroy()
    # Expense entry form setup...
```

### Adding an Expense
The **"Add Expense"** button captures user input and stores it in the database:
```python
def add_expense(amount, category):
    query = "INSERT INTO expenses (amount, category) VALUES (%s, %s)"
    cursor.execute(query, (amount, category))
    cnx.commit()
```

### Reports & Visualization
A table displays **category-wise expenses** along with budgets. Users can click **"Visualize Data"** to generate a graphical representation using Matplotlib.

---

## Conclusion
The **Expense Tracker** is a user-friendly, efficient financial management tool. It integrates **Tkinter, MySQL, and Matplotlib** to provide a seamless experience for users looking to track their spending and stay within budget. 

### Future Enhancements
- Multi-user support
- Cloud storage integration
- AI-driven expense predictions

---

## License
This project is licensed under the **MIT License**.

---

## Contributing
Contributions are welcome! Feel free to fork this repository and submit a pull request.

---

## Contact
For any queries or suggestions, reach out via [your email or GitHub profile link].
