CREATE DATABASE BDE;
create TABLE MEMBER_BDE  (ID INT , name varchar(39), prenom varchar(30)  , email varchar(100) , dateDadhsion date , ROLE_ID  INT  , primary key (ID), FOREIGN KEY (ROLE_ID) REFERENCES ROLE(ID));
create table evenment (
    id int unique not null,
    nom varchar(30) not null,
    dateEvent DATETIME,
    lieu varchar(50),
    budget int not null,
    description TEXT,
    primary key (id)
);

create table organiser (
    id int unique not null,
    idMember int,
    idEvent int,
    primary key (idMember, idEvent),
    FOREIGN KEY (idMember) REFERENCES MEMBER_BDE (ID),
    FOREIGN KEY (idEvent) REFERENCES evenment (id)
);

create table Contact (
    id int unique not null,
    name varchar(40),
    email varchar(100),
    phoneNumber int,
    primary key (id)
);

create table participant (
    id int unique not null,
    name varchar(30),
    prenom varchar(50),
    email varchar(100),
    status va rchar (50),
    primary key (id)
);

create table Sponsors (
    id int unique not null,
    name varchar(30),
    montant double,
    listEvenment varchar(100),
    idContact int not null,
    primary key (id),
    foreign key (idContact) references Contact (id)
);

INSERT INTO
    participant (
        id,
        name,
        prenom,
        email,
        status
    )
VALUES (
        1,
        'John',
        'Doe',
        'john.doe@example.com',
        'Active'
    );

insert into
    MEMBER_BDE
values (
        1,
        "brahim",
        "khaldi",
        "brahim@gmail.com",
        '2024-04-11',
        1
    );

insert into
    evenment
values (
        1,
        "hackaton",
        "2013-09-22 16:19:43",
        "barnoci",
        6000,
        "trying to having fun "
    );