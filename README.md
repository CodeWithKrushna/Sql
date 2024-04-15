1.	User
create table users(u_id int auto_increment primary key, 
u_name varchar(255)unique not null,
u_Email varchar(255) not null,
u_mobile varchar(22) not null,
u_dob varchar(22), 
u_add varchar(500),
u_pass varchar(100)not null
);

2.	Admin
create table admin(a_id int auto_increment primary key,
 a_name varchar(50) ,
 a_pass varchar(50)
 );

3.	RTO Officer
create table rtooffi(R_id int auto_increment primary key,
R_name varchar(255),
R_pass varchar(50),
R_idcard_no int
);

4.	Vehicle
create table vehicle (V_id int auto_increment primary key,
V_regi_no varchar(100),
V_user_id int ,
foreign key(V_user_id) references users(u_id),
V_owner_name varchar(255),
v_type int
);

5.	Driving / Learners License
create table DLL(
user_id int auto_increment primary key,
foreign key(user_id) references users(u_id),
us_name varchar(255),
u_age int check(u_age>18),
type_of_lic int 
);
6.	Learning License
create table LL(ll_id int auto_increment primary key,
ll_name varchar(255),
ll_pass varchar(50),
usr_id int ,
foreign key(usr_id) references users(u_id)
 );

7.	Driving License
create table DL(dl_id int auto_increment primary key,
dl_name varchar(255),
dl_add varchar(500),
dl_pass varchar(50),
ll_no int,
ll_id int ,
foreign key(ll_id) references LL(ll_id)
 );

8.	Address change
create table addchange(Ad_id int auto_increment primary key,
 u_name varchar(255),
 u_pass varchar(50),
 dl_no int,
 dl_old_add varchar (500),
 dl_new_add varchar(500)
 );

9.	Challan
create table challan(c_id int auto_increment primary key,
vhe_no varchar(100),
chassis_no int
);

10.	Insurance Policy
create table insurance(ins_id int auto_increment primary key,
ins_typ varchar(100),
vhe_id int,
foreign key(vhe_id) references vehicle(V_id),
vhe_regi_no varbinary(100),
o_name varchar (255),
o_maill varchar (255),
o_pass varchar(100)
);

11.	Feedback
create table feedback(f_id int auto_increment primary key,
c_id int,
u_name varchar(255),
e_mail varchar (255),
message text,
constraint fk_LL foreign key(c_id) references users(u_id)
);
