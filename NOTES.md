I created the database, schemas, loaded into staging schema using the mac terminal. so all of steps 1 and 2 were in the mac terminal. I will begin using the terminal in vscode from now on. 
>> To begin a project after shutting it down:
    (base) bk@Mac Sales_Analysis_Project % source .venv/bin/activate -> activate python venv
    (.venv) (base) bk@Mac Sales_Analysis_Project % psql -U sales_admin -d sales_analytics -> loginto sales_analytics databse
    Password for user sales_admin: 
    psql (17.4)
    Type "help" for help.
    sales_analytics-# SET search_path TO core, staging, public; -> check the right path for tables