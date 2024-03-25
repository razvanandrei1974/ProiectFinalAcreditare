# :orange_square: Proiect Final Acreditare

### 📌 Proiect creat in MySQL Workbench
![MySql](https://github.com/razvanandrei1974/Proiect-MySQL-Testare-Manuala/blob/main/MySQL1.jpg) 

### 📌 **Am creat baza de date cu numele** : _" Vanzari Online "_ 
```
create database VanzariOnline;
```
# 📌 Instructiuni **DDL** :
 ### Create, Alter, Drop, Truncate 
 
### :large_orange_diamond: **Am creat tabela cu numele** : _" Angajati "_ 
```
create table Angajati
(
AngajatID int,
Nume varchar(20),
Prenume varchar(20),
Functia varchar(20),
Departament varchar(25),
Oras varchar(25),
primary key(AngajatID)
);
```
### :large_orange_diamond: **Am creat tabela cu numele** : _" Departamente "_ 

```
create table Departamente
(
DepartamentID int,
Denumire_Departament varchar(30),
NumarAngajati int,
Oras varchar(30),
primary key(DepartamentID)
);
```
### :large_orange_diamond: **Am creat tabela cu numele** : _" Salarizare "_
```
create table Salarizare
(
ID int,
Nume varchar(25),
Prenume varchar(25),
Oras varchar(25),
Salar int,
Functie varchar(25),
primary key(ID)
);
```
### :large_orange_diamond: **Am creat tabela cu numele** : _" Produse "_ 
```
create table Produse
(
IDProdus int,
Denumire varchar(25),
Categorie varchar(25),
Stoc int,
Pret int,
Oras varchar(25),
primary key (IDProdus)
);
```
### :large_orange_diamond: **Am creat tabela cu numele** : _" Comenzi "_ 
```
create table Comenzi
(
IDComanda int,
DenumireProdus varchar(25),
Cantitate int,
Departament varchar(25),
NumeVanzator varchar(25),
Pret int,
Oras varchar(25),
primary key (IDComanda)
);
```
select * from Departamente;

### :large_orange_diamond: **Am sters coloana Oras ** din tabela "Departamente" 
```
ALTER TABLE Departamente
DROP COLUMN Oras;
```

### :large_orange_diamond: **Am inlocuit in tabela "Departamente" denumirea coloanei Oras cu Termen de livrare  ** 
```
alter table Produse 
change Oras TermenLivrare varchar(20);
```
### :large_orange_diamond: Am adaugat in tabela "Produse" coloana "Specificatii"
```
ALTER TABLE Produse
ADD Specificatii varchar(40);
```

insert into Produse(IDProdus,Denumire,Categorie,Stoc,Pret,TermenLivrare,Specificatii) values
(1001,'Notebook Lenovo','Notebook',26,2750,'2 zile','Intel I3'),
(1002,'Smartphone Motorola','Telefoane',145,1835,'3 zile','30 Edge');


create table Facturi
(IDFactura int,
SerieFactura varchar(25),
NumarFactura varchar(30),
Cantitate int,
PretUnitar int,
ValoareBruta int,
ValoareNeta int,
primary key (IDFactura));

insert into Facturi(IDFactura,SerieFactura,NumarFactura,Cantitate,PretUnitar,ValoareBruta,ValoareNeta) values
(12001,'ROCS','025689',12,120,1440,1713),
(12002,'ROCS','025699',8,135,1080,1285),
(12003,'ROCS','025700',2,2560,5120,6093);

TRUNCATE TABLE Facturi;

DROP TABLE Facturi;

alter table Angajati
modify Prenume varchar(40);


# 📌 Instructiuni **DML** :
 ### Insert, Delete, Update 

 ### :large_blue_diamond: **Am populat tabela "Departamente" cu denumirea celor 8 departamente ale firmei :
```
insert into Departamente(DepartamentID,Denumire_Departament,NumarAngajati) values
(1001,'Administratie',12),
(1002,'Vanzari',8),
(1003,'Caserie',6),
(1004,'ComenziOnline',25),
(1005,'Garantii',4),
(1006,'Contabilitate',4),
(1007,'Distributie',40),
(1008,'ReturProduse',10);
```

Insert into Angajati(AngajatID,Nume,Prenume,Functia,Departament,Oras) values
(1001,'ACSINTE','AURELIAN','AgentVanzari','Vanzari','Brasov'),
(1002,'ANGELESCU','ANISOARA','Manager','Administratie','Brasov'),
(1003,'BACILA','DANILA','HR','Administratie','Brasov'),
(1004,'BACIU','ELENA','AgentVanzari','Vanzari','Sibiu'),
(1005,'BADEA','ION','Casier','Caserie','Brasov'),
(1006,'BAICEANU','LILIANA','OperatorVanzari','ComenziOnline','Sibiu'),
(1007,'BANCIU','GIANINA','OperatorVanzari','ComenziOnline','Bucuresti'),
(1008,'BANDRABURU','AUREL','DirectorTehnic','Administratie','Brasov'),
(1009,'BANICA','MARIAN','Sofer','Distributie','Sibiu'),
(1010,'BARBULESCU','MIREL','AgentVanzari','Vanzari','Cluj Napoca'),
(1011,'BELOIU','FLORIN','OperatorVanzari','ComenziOnline','Cluj Napoca'),
(1012,'BIZIRU','CRISTIAN','ResponsabilGarantii','Garantii','Bucuresti'),
(1013,'BOICU','COSTEL','Sofer','Distributie','Cluj Napoca'),
(1014,'BOJNIGEANU','MIRELA','AgentVanzari','Vanzari','Timisoara'),
(1015,'BORDEA','STEFAN','DirectorAdjunct','Administratie','Brasov'),
(1016,'BORDEI','MIHAI','AgentVanzari','Vanzari','Bucuresti'),
(1017,'BORDEI','NICULAE','ResponsabilGarantii','Garantii','Brasov'),
(1018,'BUZATU','OCTAVIAN','Sofer','Distributie','Timisoara'),
(1019,'CALIN','LOREL','OperatorVanzari','ComenziOnline','Timisoara'),
(1020,'CARDON','MIHAITA','OperatorVanzari','ComenziOnline','Alba Iulia'),
(1021,'CAZACU','GHEORGHE','Sofer','Distributie','Alba Iulia'),
(1022,'CAZAN','MARIUS','AgentVanzari','Vanzari','Alba Iulia'),
(1023,'CHIRAN','MARCEL','Sofer','Distributie','Alba Iulia'),
(1024,'CICMEREAN','MIRCEA','AgentVanzari','Vanzari','Iasi'),
(1025,'CIUMAC-ICHIM','GHEORGHE','Contabil','Contabilitate','Brasov'),
(1026,'CIUREA','ANDRA','Contabil Sef','Contabilitate','Brasov');


alter table Angajati
modify Prenume varchar(40);



Insert into Salarizare(ID,Nume,Prenume,Oras,Salar,Functie) values
(1001,'ACSINTE','AURELIAN','Brasov',4250,'AgentVanzari'),
(1002,'ANGELESCU','ANISOARA','Brasov',12600,'Manager'),
(1003,'BACILA','DANILA','Brasov',8900,'HR'),
(1004,'BACIU','ELENA','Sibiu',4250,'AgentVanzari'),
(1005,'BADEA','ION','Brasov',4000,'Caserie'),
(1006,'BAICEANU','LILIANA','Sibiu',5200,'OperatorVanzari'),
(1007,'BANCIU','GIANINA','Bucuresti',5200,'OperatorVanzari'),
(1008,'BANDRABURU','AUREL','Brasov',8500,'DirectorTehnic'),
(1009,'BANICA','MARIAN','Sibiu',3750,'Sofer'),
(1010,'BARBULESCU','MIREL','Cluj Napoca',4250,'AgentVanzari'),
(1011,'BELOIU','FLORIN','Cluj Napoca',5200,'OperatorVanzari'),
(1012,'BIZIRU','CRISTIAN','Bucuresti',5200,'ResponsabilGarantii'),
(1013,'BOICU','COSTEL','Cluj Napoca',3750,'Sofer'),
(1014,'BOJNIGEANU','MIRELA','Timisoara',4250,'AgentVanzari'),
(1015,'BORDEA','STEFAN','Brasov',10300,'DirectorAdjunct'),
(1016,'BORDEI','MIHAI','Bucuresti',4250,'AgentVanzari'),
(1017,'BORDEI','NICULAE','Brasov',5200,'ResponsabilGarantii'),
(1018,'BUZATU','OCTAVIAN','Timisoara',3750,'Sofer'),
(1019,'CALIN','LOREL','Timisoara',5200,'OperatorVanzari'),
(1020,'CARDON','MIHAITA','Alba Iulia',5200,'OperatorVanzari'),
(1021,'CAZACU','GHEORGHE','Alba Iulia',3750,'Sofer'),
(1022,'CAZAN','MARIUS','Alba Iulia',4250,'AgentVanzari'),
(1023,'CHIRAN','MARCEL','Alba Iulia',3750,'Sofer'),
(1024,'CICMEREAN','MIRCEA','Iasi',4250,'AgentVanzari'),
(1025,'CIUMAC-ICHIM','GHEORGHE','Brasov',7325,'Contabil'),
(1026,'CIUREA','ANDRA','Brasov',9600,'Contabil Sef');

select * from Produse;

truncate table Produse;

ALTER TABLE Produse
ADD Brand varchar(40);

insert into Produse(IDProdus,Denumire,Categorie,Stoc,Pret,TermenLivrare,Specificatii,Brand) values
(1001,'Notebook','Laptop',26,2750,'2 zile','Intel I3','Lenovo'),
(1002,'Smartphone','Telefoane',145,1835,'3 zile','30 Edge','Motorola'),
(1003,'Smartphone','Telefoane',98,4650,'3 zile','S22','Samsung'),
(1004,'Smartphone','Telefoane',12,7650,'3 zile','Iphone15','Apple'),
(1005,'Notebook','Laptop',14,12900,'6 zile','MacBook13','Apple'),
(1006,'Notebook','Laptop',22,14350,'12 zile','Intel-I9','Asus'),
(1007,'DesktopPC','PC-Periferice',98,7250,'8 zile','Intel-I7','Lenovo'),
(1008,'DesktopPC','PC-Periferice',2,3980,'4 zile','Intel-I5','Samsung'),
(1010,'DesktopPC','PC-Periferice',8,4150,'2 zile','AMDRyzen5','NoName'),
(1011,'Monitor','PC-Periferice',34,1259,'2 zile','LED28','Samsung'),
(1012,'MonitorCurbat','PC-Periferice',12,1710,'3 zile','Qled24','Asus'),
(1013,'Monitor','PC-Periferice',9,1100,'5 zile','LED17','Philips'),
(1014,'Monitor','PC-Periferice',3,1275,'4 zile','LED19','Samsung'),
(1015,'ImprimantaLaser','PC-Periferice',4,2750,'7 zile','Color','Brother'),
(1016,'ImprimantaLaser','PC-Periferice',2,4150,'3 zile','Color','HP'),
(1017,'ImprimantaJet','PC-Periferice',14,1380,'5 zile','Color','Epson'),
(1018,'ImprimantaJet','PC-Periferice',11,850,'2 zile','Color','Cannon'),
(1019,'MultifunctionalLaser','PC-Periferice',2,18900,'15 zile','Color','Minolta'),
(1020,'MultifunctionalJet','PC-Periferice',6,4850,'5 zile','Color','Epson');



UPDATE Angajati
SET Functia = 'OperatorVanzari', Oras = 'Cluj Napoca'
WHERE AngajatID = 1010;

select * from angajati;


UPDATE Produse
SET Stoc = 85 , Brand = 'Motorola'
WHERE IDProdus = 1002;



DELETE FROM Produse WHERE IDProdus=1020;

UPDATE Salarizare
SET Prenume = 'Florin-Marius' , Salar = 6000
WHERE ID = 1011;

select * from salarizare;

INSERT INTO Produse (IDProdus,Denumire,Categorie,Stoc,Pret,TermenLivrare) VALUES
(1021,'Tableta','Telefoane',100,720,'5 zile');



delete from produse where IDProdus = 1021;



SELECT nume, prenume
FROM Salarizare;


select * from produse;

SELECT DISTINCT Oras FROM Angajati;


SELECT * FROM Salarizare
WHERE Salar=4250;


SELECT * FROM Produse
WHERE Pret > 1250;

select denumire,stoc from produse;

select nume, prenume, salar from salarizare;

select * from salarizare where salar = 5200;

select * from produse where Denumire in ("Smartphone", "DesktopPC");
select * from angajati where Functia in ("AgentVanzari" , "OperatorVanzari");


select * from salarizare where salar between 7500 and 13000;

select * from angajati where nume like 'ba%';

select * from produse where categorie like 't%';

select * from produse
where denumire like 's%'
and TermenLivrare like '3%';

select * from produse
where denumire like 's%'
or TermenLivrare like '3%'
and Brand like 'm%';

select * from produse
where (denumire like 's%'
or TermenLivrare like '3%')
and Brand like 'm%';


select sum(salar) from salarizare;
select avg(salar) from salarizare;
select min(salar) from salarizare;
select min(pret) from produse;
select max(pret) from produse;
select count(*) from angajati;



create table ComenziDeschise (
cdID int not null auto_increment, 
status_com varchar(50) not null,
data_comenzii  date not null,
prID int not null,
primary key (cdID),
constraint fk_ComenziDeschise_Produse foreign key (prID) references Produse(IDProdus) 
);

create table ComenziDeschise1 (
cdID int not null auto_increment, 
status_com varchar(50) not null,
data_comenzii  date not null,
prID int not null,
primary key (cdID),
constraint fk_ComenziDeschise_Comenzi foreign key (prID) references Comenzi(IDComanda) 
);

create table FirmaVanzari (
fvID int not null auto_increment, 
status_firma varchar(50) not null,
data_angajarii  date not null,
anID int not null,
primary key (fvID),
constraint fk_FirmaVanzari_Angajati foreign key (anID) references salarizare(ID) 
);

create table FirmaVanzari1 (
fvID int not null auto_increment, 
status_firma varchar(50) not null,
data_angajarii  date not null,
anID int not null,
primary key (fvID),
constraint fk_FirmaVanzari_Salarizare foreign key (anID) references angajati(AngajatID) 
);


create table ComenziIndividuale (
IDcomandaInd int not null,
cdID int not null,
IDProdus int not null,
Cantitate int not null,
ciID int not null,
primary key (IDcomandaInd),
constraint fk_FirmaVanzari_ComenziDeschise foreign key ( ciID) references FirmaVanzari(fvID)
);

select * from ComenziIndividuale;

insert into ComenziDeschise(cdID,status_com,data_comenzii,prID) values
(10001,'deschisa','2024-03-15',9999);



select * from salarizare cross join angajati;


# Extragem informatiile comune intre cele doua tabele
select * from angajati inner join salarizare on salarizare.ID=angajati.AngajatID ;

select * from produse inner join comenzi on produse.Denumire=comenzi.DenumireProdus;

insert into comenzi(IDComanda,DenumireProdus,Cantitate,Departament,NumeVanzator,Pret,Oras) values
(2001,'Smartphone',2,'vanzarionline','Acsinte Aurelian',7200,'Cluj Napoca');


# Extragem datele comune din tabela Comenzi si tabela Produse
select * from produse left join comenzi on produse.Denumire=comenzi.DenumireProdus;

# Extragem datele comune din tabela Comenzi si tabela Produse, dar nu se afiseaza randurile care nu au inregistrari
select * from produse left join comenzi on produse.Denumire=comenzi.DenumireProdus where Comenzi.DenumireProdus is not null;

# Extragem datele comune din tabela Produse si tabela Comenzi
select * from produse right join comenzi on produse.Denumire=comenzi.DenumireProdus;


# SQL Extras

select * from salarizare order by salar;
select * from produse order by pret desc;
select * from produse order by pret desc limit 3;

select o.IDProdus, p.Denumire, p.Pret, p.categorie owner, p.pret produs
from produse o inner join produse p on p.IDProdus = o.IDProdus;

```





















