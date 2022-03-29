


create table parents(
    parent_id int unsigned auto_increment primary key,
    first_name varchar(200) not null,
    last_name varchar(200) not null
) engine = innodb;
-- `engine = innodb` is for FK to work


insert into parents (first_name, last_name) values 
    ("Chua Kang", "Phua"),
    ("Ah Teck", "Tan"),
    ("See Mei", "Liang");

--create the students table
create table students(
    student_id int unsigned auto_increment primary key,
    name varchar(45) not null,
    swimming_level varchar(45),
    date_of_birth date
)engine = innodb;

---show all tables
show tables

--insert into <table name> (<column1>, <column2>, ...) values (value1, value2)

insert into parents (first_name, last_name) values ("AH Kow", "Tan");

---show all rows from a table 

select * from parents

--The command to add in a foreign key, FK
--step 1: create the column for the foreign key
alter table students add column parent_id int unsigned;

---step 2: setup the foreign key
alter table students add constraint fk_students_parents
    foreign key (parent_id) references parents(parent_id);


insert into students (name, swimming_level, date_of_birth, parent_id)
values ('Xiao Kow', 'beginner', '2010-09-10', 4);

insert into students (name, swimming_level, date_of_birth, parent_id)
values ('Alien', 'beginner', '2010-09-10', 404);


update students set swimming_level='intermediate' where student_id = 1;

delete from students where student_id = 1;