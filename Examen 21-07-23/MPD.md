![[MLD.png]]

Voici le modèle physique de données en SQL générique :

```sql
CREATE TABLE Stock
(
    idArticle INT PRIMARY KEY NOT NULL,
    Restant INT,
    Prix INT
    
);
CREATE TABLE Réservation (  
	idRéservation int NOT NULL PRIMARY KEY,  
	Durée int NOT NULL,
	StartDate Date,  
	IsConfirmed bool,
	idClient int FOREIGN KEY REFERENCES Client(idClient)  
);

CREATE TABLE Client (
	idClient int NOT NULL PRIMARY KEY,
	Nom VARCHAR(30),
	Prénom VARCHAR(30)
);
CREATE TABLE Chambre (
	idChambre INT NOT NULL PRIMARY KEY,
	Places INT,
	Etat INT,
	Tarifs FLOAT,
	idRéservation INT FOREIGN KEY REFERENCES Réservation(idRéservation)
);
CREATE TABLE Nécessite (
	idChambre INT,
	idService,
	PRIMARY KEY (idChambre, idService)
);
CREATE TABLE Service (
	idService INT NOT NULL PRIMARY KEY,
	Type varchar(60),
	Prix FLOAT,
	idCLient INT FOREIGN KEY REFERENCES Client(idClient),
	idPersonnel INT FOREIGN KEY REFERENCES Personnel(idPersonnel)
);

CREATE TABLE Personnel (
	idPersonnel INT NOT NULL PRIMARY KEY,
	Salaire FLOAT,
	KPIperf FLOAT
);

CREATE TABLE Congé(
	idCongé INT NOT NULL PRIMARY KEY,
	Début DATE,
	Durée INT,
	idPersonnel INT FOREIGN KEY REFERENCES Personnel(idPersonnel)
)

```