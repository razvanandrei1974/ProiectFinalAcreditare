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

### :large_orange_diamond: **Am sters coloana Oras ** din tabela "Departamente" **
```
ALTER TABLE Departamente
DROP COLUMN Oras;
```

### :large_orange_diamond: **Am inlocuit in tabela "Departamente" denumirea coloanei Oras cu Termen de livrare  ** 
```
alter table Produse 
change Oras TermenLivrare varchar(20);
```
### :large_orange_diamond: Am adaugat in tabela "Produse" coloana "Specificatii"**
```
ALTER TABLE Produse
ADD Specificatii varchar(40);
```

### :large_orange_diamond: Am creat tabela "Facturi"**
```
create table Facturi
(IDFactura int,
SerieFactura varchar(25),
NumarFactura varchar(30),
Cantitate int,
PretUnitar int,
ValoareBruta int,
ValoareNeta int,
primary key (IDFactura));
```
### :large_orange_diamond: Am populat tabela "Facturi" cu trei facturi**
```
insert into Facturi(IDFactura,SerieFactura,NumarFactura,Cantitate,PretUnitar,ValoareBruta,ValoareNeta) values
(12001,'ROCS','025689',12,120,1440,1713),
(12002,'ROCS','025699',8,135,1080,1285),
(12003,'ROCS','025700',2,2560,5120,6093);
```
### :large_orange_diamond: Am sters datele inregistrate in tabela "Facturi"**
```
TRUNCATE TABLE Facturi;
```
### :large_orange_diamond: Am sters in totalitate tabela "Facturi"**
```
DROP TABLE Facturi;
```

# 📌 Instructiuni **DML** :
 ### Insert, Delete, Update 

 ### :large_blue_diamond: **Am populat tabela "Departamente" cu denumirea celor 8 departamente ale firmei :**
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
 ### :large_blue_diamond: **Am populat tabela "Angajati" cu datele celor 25 angajati ai firmei :**
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
```
 ### :large_blue_diamond: **Am populat tabela "Salarizare" cu numele, prenumele, functia, salarul si orasul celor 25 angajati ai firmei :**
 ```
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
```
 ### :large_blue_diamond: **Am modificat numarul de caractere din coloana "Prenume" :**
```
alter table Angajati
modify Prenume varchar(40);
```

 ### :large_blue_diamond: **Am selectata toate coloanele din tabela "Produse":**
 ```
select * from Produse;
```
 ### :large_blue_diamond: **Am sters toate datele din tabela "Produse":**
```
truncate table Produse;
```
 ### :large_blue_diamond: **Am adaugat coloana "Brand" in tabela "Produse":**
```
ALTER TABLE Produse
ADD Brand varchar(40);
```

 ### :large_blue_diamond: **Am populat cu datele si caracteristicile produselor aflate la vanzare  tabela "Produse":**
```
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
```
 ### :large_blue_diamond: **Am schimbat functia si orasul pentru angajatul cu ID 1010":**
```
UPDATE Angajati
SET Functia = 'OperatorVanzari', Oras = 'Cluj Napoca'
WHERE AngajatID = 1010;
```
 ### :large_blue_diamond: **Am verificat daca inlocuirea s-a facut cu succes:**
```
select * from angajati;
```
### :large_blue_diamond: **Am schimbat numarul de produse in stoc si brandul pentru produsul cu ID 1002 :**
```
UPDATE Produse
SET Stoc = 85 , Brand = 'Motorola'
WHERE IDProdus = 1002;
```
### :large_blue_diamond: Am sters din tabela "Produse", produsul cu ID 1020 :**
```
DELETE FROM Produse WHERE IDProdus=1020;
```
### :large_blue_diamond: Am modificat in tabela "Salarizare" prenumele si salarul pentru angajatul cu ID 1011 :**
```
UPDATE Salarizare
SET Prenume = 'Florin-Marius' , Salar = 6000
WHERE ID = 1011;
```
 ### :large_blue_diamond: **Am verificat daca inlocuirea s-a facut cu succes:**
select * from salarizare;

 ### :large_blue_diamond: **Am adaugat inca un produs in tabela produse, produsul cu ID 1021 :**
```
INSERT INTO Produse (IDProdus,Denumire,Categorie,Stoc,Pret,TermenLivrare) VALUES
(1021,'Tableta','Telefoane',100,720,'5 zile');
```
 ### :large_blue_diamond: **Am sters produsul cu ID 1021 prin filtrare cu where :**
```
delete from produse where IDProdus = 1021;
```
 ### :large_blue_diamond: **Am verificat daca inlocuirea s-a facut cu succes:**
SELECT nume, prenume
FROM Salarizare;

# 📌 Instructiuni **DQL** :
 ### select, filtrare cu where, filtrări cu like, filtrări cu AND și OR, funcții agregate, filtrări pe funcții agregate, joinuri - inner join, left join, right join, cross join, limite, order by, chei primare, chei secundare)

 ### :yellow_square: **Am selectat toate coloanele din tabela "Produse" ** :
```
select * from produse;
```
![Tabela Produse](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/Tabela%20produse.jpg) 

### :yellow_square: **Am interogat tabela "Angajati" pentru a vedea din ce orase sunt angajatii firmei" ** :
```
SELECT DISTINCT Oras FROM Angajati;
```
![Tabela Orase](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/tABELA%20ORASE.jpg) 

### :yellow_square: **Am interogat tabela "Angajati" pentru a vedea angajatii firmei care primesc un salariu egal cu 4250 lei" ** :
```
SELECT * FROM Salarizare
WHERE Salar=4250;
```
![Tabela Salar 4250](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/Angajati%20salar%204250.jpg) 

### :yellow_square: **Am interogat tabela "Produse" pentru a vedea toate produsele cu un pret mai mare de 1250 lei" ** :
```
SELECT * FROM Produse
WHERE Pret > 1250;
```
![Tabela Pret 1250](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/Tabela%20produse%20cu%20pret%20mai%20mare%20de%201250%20lei.jpg) 

### :yellow_square: **Am interogat tabela "Produse" pentru a vedea coloanele : denumire si stoc ** :
```
select denumire,stoc from produse;
```
![Coloane denumire si stoc](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/Coloane%20denumire%20si%20stoc.jpg)


### :yellow_square: **Am interogat tabela "SAlarizare" pentru a vedea numele, prenumele si salarul fiecarui angajat din firma ** :
```
select nume, prenume, salar from salarizare;
```
![Coloane nume, prenume si salar](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/Coloane%20nume%20prenume%20salar%20angajati.jpg)




### :yellow_square: **Am interogat tabela "Produse" pentru a vedea unde sunt inregistrate produsele Smartphone si DesktopPC ** :
```
select * from produse where Denumire in ("Smartphone", "DesktopPC");
```
![Produse smarthone si desktopPC](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/tabela%20denumire%20smartphone%20si%20desktopPC.jpg)


### :yellow_square: **Am interogat tabela "Salarizare" pentru a vedea angajatii cu functia de Agent de vanzari si Operator Vanzari** :
```
select * from angajati where Functia in ("AgentVanzari" , "OperatorVanzari");
```
![Agent de vanzari si operator vanzari](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/Agenti%20de%20vanzari%20si%20Operator%20vanzari.jpg)


### :yellow_square: **Am interogat tabela "Angajati" pentru a vedea angajatii a caror nume incepe cu literele "ba" sau cu litera "t" ** :
```
select * from angajati where nume like 'ba%';
```
```
select * from produse where categorie like 't%';
```
### :yellow_square: **Am interogat tabela "Produse" pentru a vedea produsele care incep cu litera "s" si au un termen de livrare care incepe cu cifra "3" ** :
```
select * from produse
where denumire like 's%'
and TermenLivrare like '3%';
```
![Agent de vanzari si operator vanzari](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/Produse%20cu%20s%20si%20termen%20de%20livrare%20cu%203.jpg)

### :yellow_square: **Am interogat tabela "Produse" pentru a vedea produsele care incep cu litera "s" si au un termen de livrare care incepe cu cifra "3" si brandul cu litera "m"** :
```
select * from produse
where denumire like 's%'
or TermenLivrare like '3%'
and Brand like 'm%';
```


### :yellow_square: **Am interogat tabela salarizare pentru a aflas suma tuturor salariilor, salariul mediu si salariul minim :
```
select sum(salar) from salarizare;
select avg(salar) from salarizare;
select min(salar) from salarizare;
```

### :yellow_square: **Am interogat tabela Produse pentru a afla pretul minim, pretul maxim si am calculat cate randuri avem in tabela:**
```
select min(pret) from produse;
select max(pret) from produse;
select count(*) from angajati;
```

### :yellow_square: **Am creat tabelele ComenziDeschise, ComenziDeschise, FirmaVanzari  pentru a face legatura cu tabela "Produse" si "Comenzi"cu ajutorul cheilor secundare "** :
1. Am creat intre coloana prID din tabela ComenziDeschise legatura cu coloana IDProdus din tabela Produse prin intermediul cheii secundare (Foreign-key). 
2. Am creat intre coloana prID din tabela ComenziDeschise legatura cu coloana IDComanda din tabela Comenzi prin intermediul cheii secundare (Foreign_key).
3. Am creat intre coloana anID din tabela Firma_Vanzari legatura cu coloana ID din tabela Salarizare prin intermediul cheii secundare (Foreign_key).
4. Am creat intre coloana fvID din tabela Firma_Vanzari legatura cu coloana AngajatID din tabela Angajati prin intermediul cheii secundare (Foreign_key).
```
create table ComenziDeschise (
cdID int not null auto_increment, 
status_com varchar(50) not null,
data_comenzii  date not null,
prID int not null,
primary key (cdID),
constraint fk_ComenziDeschise_Produse foreign key (prID) references Produse(IDProdus) 
);
```
```
create table ComenziDeschise1 (
cdID int not null auto_increment, 
status_com varchar(50) not null,
data_comenzii  date not null,
prID int not null,
primary key (cdID),
constraint fk_ComenziDeschise_Comenzi foreign key (prID) references Comenzi(IDComanda) 
);
```
```
create table FirmaVanzari (
fvID int not null auto_increment, 
status_firma varchar(50) not null,
data_angajarii  date not null,
anID int not null,
primary key (fvID),
constraint fk_FirmaVanzari_Angajati foreign key (anID) references salarizare(ID) 
);
```
```
create table FirmaVanzari1 (
fvID int not null auto_increment, 
status_firma varchar(50) not null,
data_angajarii  date not null,
anID int not null,
primary key (fvID),
constraint fk_FirmaVanzari_Salarizare foreign key (anID) references angajati(AngajatID) 
);
```
![Engineering Diagram](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/Engineering%20Diagram.jpg)


select * from salarizare cross join angajati;

### :yellow_square: **Am interogat tabelele "Angajati" si " Salarizare" pentru a vedea informatiile comune din ambele tabele dupa ID "** :
```
select * from angajati inner join salarizare on salarizare.ID=angajati.AngajatID ;
```
![InnerJoin angajati si Salarizare](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/InnerJoin%20angajati%20si%20salarizare.jpg)

### :yellow_square: **Am interogat tabelele "Produse" si " Comenzi" pentru a vedea informatiile comune din ambele tabele dupa Denumire produs "** :
```
select * from produse inner join comenzi on produse.Denumire=comenzi.DenumireProdus;
```
![InnerJoin produse si comenzi](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/InnerJoin%20produse%20si%20comenzi.jpg)

### :yellow_square: **Am interogat tabelele "Produse" si " Comenzi" pentru a vedea informatiile comune din ambele tabele in functie de tabela din stanga "** :
```
select * from produse left join comenzi on produse.Denumire=comenzi.DenumireProdus;
```
### :yellow_square: **Am interogat tabelele "Produse" si " Comenzi" pentru a vedea informatiile comune din ambele tabele in functie de tabela din stanga, dar fara sa afiseze randurile fara inregistrari "** :
```
select * from produse left join comenzi on produse.Denumire=comenzi.DenumireProdus where Comenzi.DenumireProdus is not null;
```
### :yellow_square: **Am interogat tabelele "Produse" si " Comenzi" pentru a vedea informatiile comune din ambele tabele in functie de tabela din dreapta "** :
```
select * from produse right join comenzi on produse.Denumire=comenzi.DenumireProdus;
```


# SQL Extras

### :yellow_square: **Am interogat tabelel salarizare si produse pentru a afisa salariile angajatilor din firma, preturile produselor in ordine descrescatoare si aceasi lista cu produse in ordine descrescatoare dar in limita a trei inregistrari**:
```
select * from salarizare order by salar;
select * from produse order by pret desc;
select * from produse order by pret desc limit 3;
```
### :yellow_square: **Am interogat tabela "Produse" si am afisat denumirile si preturile produselor, in acelasi timp creeand si coloana "owner" care afiseaza categoriile produselor :
```
select o.IDProdus, p.Denumire, p.Pret, p.categorie owner, p.pret produs
from produse o inner join produse p on p.IDProdus = o.IDProdus;
```
![InnerJoin produse si owner](https://github.com/razvanandrei1974/ProiectFinalAcreditare/blob/main1/InnerJoin%20produse%20si%20coloana%20categorii.jpg)























