Contributors:

John Adriaans 220038627
Hannah Dunaiski 220086915
Revaldo Gertze 220056676
Uahengisa Katjizuko 220040850
Shaun Kamesiepo 220053685

Documentation

This program will help Shoprite with some of its daily operations.
The program is split into 3 modules: sales, employee management, and stock control.
Each module is further divided into sub-modules: product sales, addition of stock, removal of stock, 
                                                 checking for low stock, retrieval of product information, 
                                                 removal of employees, addition of employees, updating of 
                                                 employee details, and the retrieval of employee information.

These modules each perform a specific task. The descriptions of functions for these modules can be found below.

//------------------------------------
Start of program:

A class called employee is created that will store employee information.
The variable in employee are id(integer), name(string), age(int), position(string), hours_worked(int),
and dollars_per_hour(int). The variables store the data they are named after. All variables are available 
to all functions throughout the program.

A class called product is created that stores product information. The variables id(int), name(string),
price(int), amount(int) store the data they are named after.

An array of type employee is created to store the data of all current employees.
An array of type product is created store the data of all products in stock.

A variable that determines whether or the program is being run is created. This variable will be used to end the while loop in the 
main function

A variable sales_for_month is created to store the total sales for the month.

The main function is called with no arguments

End of program 
//-----------------------------------------

Functions:

main():
pass in: nothing

 variables in use: emp(employee) and prod(product) are used to store objects returned by functions. 
            event stores user actions eg a barcode scan signaling a sale or a request to update 
            employee information, running is a global variable from outside the function that will terminate the loop once false.
 What function does: the function continuosly loops through a while loop waiting for user input.
                     It also calls the check_low_stock function and displays an items that have low stock.
                     Once user input is gained, it checks to see which action the user wants to perform by using 
                     a switch statement. Once a match is found, the appropriate function is called and, if necessary, returned data is 
                     stored in emp or prod and the data is displayed.

pass out: nothing


products_sold():
pass in: nothing
    variables in use: id is used to identify the right product, quantity is the number of items being bought, total is the final cost of everything,
                      more_items is used to terminate the loop when false, ans stores the users response to a question.
    
    What the function does: it continuously asks for the input of an id and quantity of a product in loop. Once inputs are received, a nested loop searches for 
                            the product with the matching id. Once the product is found, its price is multiplies by the quantity entered and this value is added 
                            to total. remove_stock is then called to decrease the amount of the product available and then nested loop is ended. The user is 
                            then asked to answer Y or N to the question: "Are there more items?". If the user answers 
                            N, more_items is set to false which will end the main loop. total is then added to sales_for_month and then total is displayed.
pass out: nothing

 
get_prod_details():
pass in: id
    variables in use: id is used to find the correct product, prod is the array of products that has to be checked

    What the function does: it loops through the prod array and finds the product with the id that matches the id passed 
                            into the function. Once the correct product is found, the variable is passed out (returned) to whatever called the function
                            and the loop is ended. If no match is found then nothing is passed out (returned). 
pass out: nothing                           
                    
get_emp_details():
pass in: id
    variables in use: id is used to find the correct employee, emp is the array that stores employee data

    What the function does: it loops through the emp array and finds the employee that has the same id as the 
                            id passed in. If found, the correct emp variable is passed out (returned). If no match was found then 
                            nothing is passed out (returned)
pass out: nothing                           

remove_stock():
pass in: id, amount
    variables in use: id is used to find correct product, amount is the number of items to be removed, prod is the array that stores different product information

    What the function does: it loops through the prod array and finds the product with the id that matches the id passed in. Once found, 
                            the amount value of the prod object is decreased by the amount passed in.
pass out: nothing                           

add_stock():
pass in: id, amount
    variables in use: id is used to find correct product, amount is the number of items to be removed, prod is the array that stores different product information

    What the function does: it loops through the prod array and finds the product with the id that matches the id passed in. Once found, 
                            the amount value of the prod object is increased by the amount passed in.
pass out: nothing


add_emp():
pass in: name,age,position,employment type, dollars_per_hour
    variables in use: emp_count keeps track of the number of employees. emp is an array of objects of type employee.
                      The variables passed in store the data they are named after.
    
    What the function does: it increases the size of the emp array by 1 to make space for the new employee and increases emp_count 
                            by 1. It then stores all the data that was passed into the function in the corrisponding variables in the 
                            new object at the end of the array. The new object at the end of the array was created when the size of 
                            the array was increased.
pass out: nothing                           

remove_emp():
pass in: id
    variables in use: id is used to find the right employee, emp is the array of objects that stores the data of all employees.
                      emp_count keeps track of the number of employees

    What the function does: it loops through the emp array and finds the employee with the id that matches the id passed in.
                            Once found, the data of the found emp is deleted and the size of the array is decreased by 1. emp_count 
                            is also decreased by 1. The loop is then ended.
pass out: nothing                           

update_emp_details()"
pass in: id,name,age,position,hours_worked,employment_type
    variables in use: id is used to find the right employee. emp is the array of objects that store the data of all employees.
                      All the other variables passed in store the values they are named for and are simply used to update employee data.
    
    What the function does: it loops the emp array and finds the emp with the id that matches the id passed in.
                            It then checks each of the variables passed into the function. If a variable is not empty then 
                            the matching emp value will be updated with the value of the passed in variable e.g. if name is not empty, then 
                            emp[i].name will be updated with whatever is in the name variable. If a variable is empty, no update will be made.
pass out: nothing

calculate wage():
pass in: nothing
    variables in use: emp is an array of objects that stores the data of all employees

    What the function does: it loops through the emp array and calculates the wage of each emp by multiplying 
                            emp.hours_worked with emp.dollars_per_hour and storing it in emp.wage. This is done for 
                            all employees.

pass out: nothing