# ChinookDatabase1.4_CompleteVersion
non_usa_customers.sql: Provide a query showing Customers (just their full names, customer ID and country) who are not in the US.

brazil_customers.sql: Provide a query only showing the Customers from Brazil.

brazil_customers_invoices.sql: Provide a query showing the Invoices of customers who are from Brazil. The resultant table should show the customer's full name, Invoice ID, Date of the invoice and billing country.

sales_agents.sql: Provide a query showing only the Employees who are Sales Agents.

unique_invoice_countries.sql: Provide a query showing a unique/distinct list of billing countries from the Invoice table.

sales_agent_invoices.sql: Provide a query that shows the invoices associated with each sales agent. The resultant table should include the Sales Agent's full name.

invoice_totals.sql: Provide a query that shows the Invoice Total, Customer name, Country and Sale Agent name for all invoices and customers.

total_invoices_{year}.sql: How many Invoices were there in 2009 and 2011?

total_sales_{year}.sql: What are the respective total sales for each of those years?

invoice_37_line_item_count.sql: Looking at the InvoiceLine table, provide a query that COUNTs the number of line items for Invoice ID 37.

line_items_per_invoice.sql: Looking at the InvoiceLine table, provide a query that COUNTs the number of line items for each Invoice. HINT: GROUP BY

line_item_track.sql: Provide a query that includes the purchased track name with each invoice line item.

line_item_track_artist.sql: Provide a query that includes the purchased track name AND artist name with each invoice line item.

country_invoices.sql: Provide a query that shows the # of invoices per country. HINT: GROUP BY

playlists_track_count.sql: Provide a query that shows the total number of tracks in each playlist. The Playlist name should be include on the resulant table.

tracks_no_id.sql: Provide a query that shows all the Tracks, but displays no IDs. The result should include the Album name, Media type and Genre.

invoices_line_item_count.sql: Provide a query that shows all Invoices but includes the # of invoice line items.

sales_agent_total_sales.sql: Provide a query that shows total sales made by each sales agent.

top_2009_agent.sql: Which sales agent made the most in sales in 2009?

Hint: Use the MAX function on a subquery.
top_agent.sql: Which sales agent made the most in sales over all?

sales_agent_customer_count.sql: Provide a query that shows the count of customers assigned to each sales agent.

sales_per_country.sql: Provide a query that shows the total sales per country.

top_country.sql: Which country's customers spent the most?

top_2013_track.sql: Provide a query that shows the most purchased track of 2013.

top_5_tracks.sql: Provide a query that shows the top 5 most purchased tracks over all.

top_3_artists.sql: Provide a query that shows the top 3 best selling artists.

top_media_type.sql: Provide a query that shows the most purchased Media Type.


Using Oracle SQL Developer to run SQL Commands


CODE FOR ORACLE SQL Live

create table course (
course_id number(5), 
Name char(38), 
DepartmentID number(5), 
PRIMARY KEY (course_id) );



create table department (
department_id number(5), 
Name char(28), 
PRIMARY KEY ( department_ID) );


INSERT INTO department(department_id, Name) VALUES (3, 'Biological Science' );
INSERT INTO department(department_id, Name) VALUES (5, 'Technology' );
INSERT INTO department(department_id, Name) VALUES (6, 'Humanities & Social Sciences' );
INSERT INTO department(department_id, Name) VALUES (2, 'Clinical Medicine' );
INSERT INTO department(department_id, Name) VALUES (4, 'Arts and Humanities' );
INSERT INTO department(department_id, Name) VALUES (1, 'Physical Sciences' );





CREATE TABLE professor ( 
    professor_id number NOT NULL, 
    name char(28), 
    department_id   number,
	salary number, 
    PRIMARY KEY (professor_id), 
    CONSTRAINT FK_department_id FOREIGN KEY (department_id) 
    REFERENCES department(department_id) 
);


INSERT INTO Professor (professor_id, Name, department_id, salary) VALUES (1, 'Nancy Daniels', 4, 7169 );
INSERT INTO Professor (professor_id, Name, department_id, salary)  VALUES (2, 'Billy Knight', 1,9793 );
INSERT INTO Professor (professor_id, Name, department_id, salary)  VALUES (3, 'Harry Myers', 4, 25194 );
INSERT INTO Professor (professor_id, Name, department_id, salary) VALUES (4, 'Antonio Rodriquez',3, 9686);
INSERT INTO Professor (professor_id, Name, department_id, salary) VALUES (5, 'Nicole Gome', 2, 30860);

INSERT INTO Professor (professor_id, Name, department_id, salary)  VALUES (6, 'Eugene George', 5, 10487);
INSERT INTO Professor (professor_id, Name, department_id, salary) VALUES (7, 'Gloria Vasquez', 4, 6353);
INSERT INTO Professor (professor_id, Name, department_id, salary) VALUES (8, 'Joyce Flores', 1, 25796);

INSERT INTO Professor (professor_id, Name, department_id, salary) VALUES (9, 'Daniel Gilbert', 5, 35678);
INSERT INTO Professor (professor_id, Name, department_id, salary)  VALUES (10, 'Matthew Stevens', 2, 26648);







create table semester ( 
semester_id number, 
professor_id number, 
course_id number(5), 
semester varchar2(28), 
yearcourse_id number(5), 
PRIMARY KEY (semester_id), 
CONSTRAINT FK_professor_id FOREIGN KEY (professor_id) 
REFERENCES professor(professor_id), 
CONSTRAINT FK_course_id FOREIGN KEY (course_id) 
REFERENCES course(course_id));




ALL OF THESE TABLES ABOVE WORKED.






Inner Joins That Work

select * from professor
INNER join department
ON professor.department_id = department.department_id
WHERE department.name = 'Technology';











