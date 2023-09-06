# Loan-management-Project

CREATE TABLE ms_auser(
	auser_id serial PRIMARY KEY, 
    auser_username varchar(20) UNIQUE NOT NULL, 
    auser_password varchar(50) NOT NULL
);

CREATE TABLE ms_customers(
	cust_id serial PRIMARY KEY,
    cust_firstname varchar(50),
    cust_lastname varchar(50),
    cust_dob date, 
    cust_panno varchar(10),
    cust_mobile bigint NOT NULL CHECK (cust_mobile >= 1000000000 AND cust_mobile <= 9999999999),
    cust_address varchar(255),
    cust_gname varchar(50),
    cust_luudate date,
    cust_luser int, 
    FOREIGN KEY (cust_luser) REFERENCES ms_auser(auser_id)
);

CREATE TABLE ms_loantypes(
	lnty_id serial PRIMARY KEY,
    lnty_name varchar(50),
    lnty_desc varchar(255)
);
