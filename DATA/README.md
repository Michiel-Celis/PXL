# SQL Oefeningen
# Table of Contents
1 - [Introductie en installatie SQL Server](#1---Introductie-&-installatie-SQL-Server)

2 - [SQL basisbegrippen](#2---SQL-basisbegrippen)

3 - [Queries (Raadpleging)](#3---Queries-(Raadpleging))

4 - [SubQueries](#4---SubQueries)

5 - [Numerieke- en string functies](#5---numerieke--en-string-functies)

6 - [Algemene functies](#6---Algemene-functies)

7 - [Datum- en conversie functies](#7---Datum--en-conversie-functies)

8 - [Join](#7---Join)

9 - [Groepsfuncties](9---Groepsfuncties)

10 - [Verzamelingsoperatoren](10---Verzamelingsoperatoren)

11 - [Views](11---Views)

12 - [DML](12---DML)

13 - [Proefexamen](13---Proefexamen)

14 - [Examen](14---Examen)


## 1 - Introductie & installatie SQL Server

### SQLCMD
```sql 
sqlcmd -S .\SQLEXPRESS 
```
### Open Database
```sql
USE DataEssentials
```


## 2 - SQL basisbegrippen

### 2.1 Data Defenition Language (DDL)

#### Tabel maken, aanpassen en verwijderen

```sql
CREATE TABLE medewerkers
(
	mnr INT NOT NULL,
	naam VARCHAR(20) NOT NULL,
	voorn VARCHAR(20) NOT NULL,
	afd INT NOT NULL,
	maandsal DECIMAL(8,2) NOT NULL,
	gbdatum DATE NOT NULL,
	chef INT NULL,
	functie VARCHAR(20) NOT NULL,
	comm DECIMAL(8,2) NULL,
	email VARCHAR(50) NULL,
	CONSTRAINT pk_medewerkers PRIMARY KEY (mnr)
)
```
```sql
ALTER TABLE medewerkers
ADD CONSTRAINT fk_medewerkers_afdelingen FOREIGN KEY (afd) REFERENCES afdelingen (anr)
```
```sql
DROP TABLE medewerkers

```

### 2.2 Data Manipulation Language (DML)

#### Rijen(Records) Invoegen, bijwerken en verwijderen
```sql
DELETE ... FROM ...
```
```sql
INSERT ... INTO ...
```
```sql
UPDATE ... SET ...
```

Kan onderdeel zijn van een transactie
> bevestigt wijziging huidige transactie
```sql
COMMIT
```
> annulleert wijziging huidige transactie
```sql
ROLLBACK
```

### 2.3 Data Control Language (DCL)
- Toegang gebruikers
- Wachtwoorden
- Privileges
	- Object
	- System
```sql
CREATE USER
```
```sql
ALTER USER
```
```sql
DROP USER
```
```sql
GRANT
```
```sql
REVOKE
```

### 2.4 Queries
- Raadplegen van database
- werkt op tabelniveau



## 3 - Queries (Raadpleging)
1. Geef het nummer en de naam van de medewerkers.
```sql
SELECT mnr, naam FROM medewerkers
```
2. In welke locaties zijn er afdelingen gevestigd?
```sql
SELECT DISTINCT locatie FROM afdelingen
```
3. Geef de code en de omschrijving van elke cursus.
```sql
SELECT code, omschrijving FROM cursussen
```
4. Geef de naam en functie van alle medewerkers die verkoper zijn.
```sql
SELECT naam, functie FROM medewerkers WHERE functie = 'verkoper'
```
5. Geef de naam en functie van alle medewerkers die geen boekhouders zijn.
```sql
SELECT naam, functie FROM medewerkers WHERE functie != 'boekhouder'
```
6. Geef alle medewerkers die meer dan €5000 verdienen en geen manager zijn.
```sql
SELECT naam from medewerkers WHERE (maandsal > 5000) AND (functie != 'manager')
```
7. Welke medewerkers verdienen minder dan €2500?
```sql
SELECT naam FROM medewerkers WHERE maandsal < 2500
```
8. Geef de naam van de afdeling waarvan medewerker 7698 de baas is.
```sql
SELECT naam FROM afdelingen WHERE hoofd = 7698
```
9. Geef de verschillende functies van de medewerkers in de onderneming.
```sql
SELECT DISTINCT functie FROM medewerkers
```
10. Geef het nummer en de naam van elke medewerker die trainer is.
```sql
SELECT mnr, naam FROM medewerkers WHERE functie = 'trainer'
```
11. Geef de naam, de functie en het salaris van elke medewerker die in afdeling 30 werkt en meer dan €2500 verdient.
```sql
SELECT naam, functie, maandsal FROM medewerkers WHERE afd = 30 AND maandsal > 2500
```
12. Geef de locatie van de afdeling die door medewerker 7566 geleid wordt.
```sql
SELECT locatie FROM afdelingen WHERE hoofd = 7566
```
13. Geef de namen van de medewerkers die in afdeling 10 of 20 werken.
```sql
SELECT naam FROM medewerkers WHERE afd IN (10, 20)
```
14. Geef van elke medewerker de naam en jaarsalaris (incl. commissie).
```sql
SELECT naam, maandsal * 12 + comm FROM medewerkers
```
15. Geef de namen van de medewerkers wiens naam eindigt op 'N'.
```sql
SELECT naam FROM medewerkers WHERE naam LIKE '%N'
```
16. Geef de namen van alle medewerkers waarin een dubbele 'o' voorkomt.
```sql
SELECT naam FROM medewerkers WHERE naam LIKE '%oo%'
```



## 4 - SubQueries
1.	Geef de naam en het salaris van de medewerkers die meer verdienen dan Clerckx.
```sql
SELECT naam FROM medewerkers
WHERE maandsal > (SELECT maandsal FROM medewerkers WHERE naam ='CLERCKX')
```
2.	Geef de namen van de medewerkers die in dezelfde afdeling werken als Allard.
```sql
SELECT naam FROM medewerkers
WHERE maandsal > (SELECT functie FROM medewerkers WHERE naam ='ALLARD')
```
3.	Geef de naam van alle medewerkers die zich voor een cursus hebben ingeschreven (in volgorde van de naam).
```sql
SELECT naam FROM medewerkers
WHERE mnr IS
(
	SELECT cursist FROM inschrijvingen
) 
ORDER BY naam
```
4.	Geef de medewerkers (namen) die jonger zijn dan hun collega E Jacobs.
```sql
SELECT naam FROM medewerkers
WHERE gbdatum > 
(
	SELECT gbdatum FROM medewerkers
	WHERE voorn LIKE 'E%' AND naam = 'JACOBS'
)
```
5.	Geef de cursisten die een cursus in Maaseik gevolgd hebben.
```sql
SELECT naam FROM medewerkers
WHERE mnr IN 
(
	SELECT cursist FROM inschrijvingen 
	WHERE cursus + CONVERT(VARCHAR, begindatum) IN 
	(
		SELECT cursus + CONVERT(VARCHAR, begindatum) FROM uitvoeringen 
		WHERE locatie = 'Maaseik'
	)
)
```
6.	Geef de cursusnamen (en het type) die de medewerkers van de afdeling Verkoop hebben gevolgd.
```sql
SELECT omschrijving, type FROM cursussen 
WHERE code IN 
(
	SELECT cursus FROM uitvoeringen WHERE cursus + CONVERT(VARCHAR, begindatum) IN
	(
		SELECT cursus + CONVERT(VARCHAR, begindatum) FROM inschrijvingen WHERE cursist IN
		(
			SELECT mnr FROM medewerkers WHERE afd IN
			(
				SELECT anr FROM afdelingen WHERE naam = 'verkoop'
			)
		)
	)
)
```
7.	Geef naam en voornaam van iedereen die ooit bij J. Caspers een cursus heeft gevolgd.
```sql
SELECT naam, voorn FROM medewerkers
WHERE mnr IN
(
	SELECT cursist FROM inschrijvingen
	WHERE cursus + CONVERT(VARCHAR, begindatum, 120) IN
	(
		SELECT cursus + CONVERT(VARCHAR, begindatum, 120) FROM uitvoeringen
		WHERE docent =
		(
			SELECT mnr FROM medewerkers
			WHERE voorn LIKE 'J%' AND naam = 'Caspers'
		)
	)
)
```
8.	Geef de namen van de cursussen waarvan de docent niet gekend is.
```sql
SELECT omschrijving FROM cursussen
WHERE code IN
(
	SELECT cursus FROM uitvoeringen
	WHERE docent IS NULL
)
```
9.	Geef de namen van de medewerkers van de afdeling verkoop wiens commissie niet gekend is.
```sql
SELECT naam FROM medewerkers
WHERE comm IS NULL AND afd IN
(
	SELECT anr FROM afdelingen
	WHERE naam = 'verkoop'
)
```
10. Geef de namen van de medewerkers die zich inschreven voor een cursus waarvan de docent niet gekend is.
```sql
SELECT naam FROM medewerkers
WHERE mnr IN
(
	SELECT cursist FROM inschrijvingen
	WHERE cursus + CONVERT(VARCHAR, begindatum, 112) IN
	(
		SELECT cursus + CONVERT(VARCHAR, begindatum, 112) FROM uitvoeringen
		WHERE docent IS NULL
	)
)
```



## 5 - Numerieke- en string functies
⚠ Op een screenshot zal naam, voorn weergegeven worden waar voorn in __lowercase__ staat

⚠ Let op Hoofdletters ! en gebruik UPPER (LEFT(Functie, 1 ))

⚠ Sorteringen worden expliciet gevraagd op het examen, lower-UPPER en kolomtitels NIET
```sql
SELECT naam, LOWER(voorn) "voornaam" FROM medewerkers

```
```sql
naam            voornaam
--------------- ------------
CASPERS         jana
ALLARD          nele
DEFOUR          thomas
JACOBS          emma
MARTENS         raf
BRIERS          andrea
CLERCKX         an
SWINNEN         chris
DE KONING       lieve
DEN RUYTER      joachim
SLECHTEN        tom
JACOBS          simon
DE COOMAN       dorien
WOUTERS         sven
```
1. Maak een lijst met achter elke medewerker het precieze uurloon, het uurloon dat op twee decimalen is afgerond, en het uurloon dat op twee decimalen is afgekapt. Het uurloon wordt berekend op basis van een kwartaal: (maandsalaris x 3) / (38 x 13)
```sql
SELECT 
	voorn "voornaam", 
	naam "naam", 
	(maandsal x 3) / (38 x 13) "precieze uurloon" ,
	ROUND((maandsal x 3) / (38 x 13),2) "afgerond",
	ROUND((maandsal x 3) / (38 x 13),2,1) "afgekapt"
FROM medewerkers
```
2. Maak een lijst waarin de verschillende waarden van FUNCTIE elk op drie manieren wordt weergegeven: met alleen aan het begin een hoofdletter, volledig in hoofdletters en volledig in kleine letters.
```sql
SELECT DISTINCT
	UPPER(Functie) AS "FUNCTIE",
	UPPER (LEFT(Functie, 1 )) + LOWER(SUBSTRING(Functie, 2, LEN(Functie))) AS "Functie",
	LOWER(Functie) AS "functie"
FROM medewerkers
```
3. Geef van elke cursus de naam en de lengte van de naam.
```sql
SELECT omschrijving "Cursusnaam", LEN(Omschrijving) "Lengte cursusnaam"
FROM cursussen
```
4. Doorzoek de namen van de medewerkers op de letter 'e'. Wordt de letter 'e' gevonden dan drukt men in het resultaat het positienummer af. Laat op drie manieren zoeken:
   * zoek vanaf de eerste positie naar de eerste letter 'e'
   * zoek vanaf de vierde positie naar de eerste letter 'e'
   * zoek vanaf de eerste positie naar de tweede letter 'e'.
```sql
SELECT
	naam AS "Naam"
	CHARINDEX('E', naam) AS "Manier 1",
	CHARINDEX('E', naam, 4) AS "Manier 2",
	CHARINDEX('E', naam, CHARINDEX('E', naam) + 1) AS "Manier 3"
FROM medewerkers
```
5. Maak een histogram met als maatstaf de lengte van de namen van de medewerkers.
   * NAAM LENGTE HISTOGRAM
   * BRIERS 6 ******
   * DE KONING 9 *********
```sql
SELECT 
	naam AS "Naam",
	LEN(naam) AS "Lengte",
	REPLICATE('*', LEN(naam)) AS "Histogram"
FROM medewerkers
```
6. Maak een lijst met de namen van de medewerkers, met hun namen zonder vooraan de letters 'DE'. Verwijder ook eventuele spaties vooraan. Tip: kijk eerst of er een 'DE' vooraan staat, indien ja: laat deze weg.
```sql
SELECT
	CASE CHARINDEX('DE', naam)
		WHEN 1 THEN 
			TRIM(LEADING 'DE ' FROM naam)
		ELSE naam
		END
AS naam
FROM medewerkers
```
7. Geef een lijst met de namen van de afdelingen, de nummers en de nummers voorafgegaan door de letters 'AF'.
```sql
SELECT naam "Naam", anr "Nummer", CONCAT('AF', anr) "AF-Nummer"
FROM afdelingen
```
```sql
SELECT naam "Naam", anr "Nummer", 'AF' + CAST(anr AS VARCHAR) "AF-Nummer"
FROM afdelingen
```
8. Geef een lijst met de namen van alle cursussen waarbij de letters 'wc#' vervangen worden door 'zk-'.
```sql
SELECT REPLACE (REPLACE(REPLACE(omschrijving,'w', 'z'), 'c', 'k'), '#', '-') "Gekke naam"
FROM cursussen
```
9. Sorteer de namen van de medewerkers zonder rekening te houden met eventuele blanco's.
```sql
SELECT 
	REPLACE(naam, ' ', '') AS "Naam"
FROM medewerkers
ORDER BY "Naam" ASC
```
10.  Druk enkel de medewerkers af waarvan de naam uit 2 delen bestaat. Het eerste gedeelte wordt in kleine letters en tussen haakjes na het tweede gedeelte (in hoofdletters) van de naam afgedrukt.
    * DE KONING
    * DEKONING
    * Vb. KONING (de)
```sql
SELECT
	SUBSTRING(naam, CHARINDEX(' ', naam), LEN(naam))+
	' (' +
	LOWER(SUBSTRING(naam, 1, CHARINDEX(' ', naam) - 1)) +
	')' "Naam"
FROM medewerkers
WHERE naam LIKE '% %'
```


## 6 - Algemene functies
```sql
SELECT * FROM medewerkers WHERE isnull(email, '') = ''
```
1. Bepaal voor elke medewerker wiens naam een 'e' bevat wat groter is: zijn salaris*2, zijn MNR of het MNR van zijn chef? Naast de naam en het **grootste** element wordt aangegeven welk element de grootste waarde heeft (chef, salaris of mnr).
```sql
SELECT 
	mnr "MNR",
	maandsal*2 "MAANDSAL *2",
	chef "CHEF", GREATEST(maandsal*2, mnr, chef) "GROOTSTE",
	CASE GREATEST(maandsal*2, mnr, chef)
		WHEN maandsal*2 THEN 'MAANDSAL'
		WHEN mnr THEN 'MNR'
		ELSE 'CHEF'
	END "WAT IS HET ?"
FROM medewerkers WHERE naam LIKE '%e%'
```
2.  Bepaal voor elke medewerker wiens naam een 'e' bevat wat kleiner is: zijn salaris*2, zijn MNR of het MNR van zijn chef? Naast de naam en het kleinste element wordt aangegeven welk element de kleinste waarde heeft (chef, salaris of mnr). Gebruik hiervoor de CASE (zonder WHEN).
```sql
SELECT 
	mnr "MNR",
	maandsal*2 "MAANDSAL *2",
	chef "CHEF", LEAST(maandsal*2, mnr, chef) "GROOTSTE",
	CASE LEAST(maandsal*2, mnr, chef)
		WHEN maandsal*2 THEN 'MAANDSAL'
		WHEN mnr THEN 'MNR'
		ELSE 'CHEF'
	END "WAT IS HET ?"
FROM medewerkers WHERE naam LIKE '%e%'
```
3.  Geef een lijst van de medewerkers waarbij de functie 'TRAINER' voorgesteld wordt als 'LERAAR' en 'DIRECTEUR' als 'HOOFD'. Alle overige functies worden als 'MEDEWERKER' voorgesteld. Los op met CASE WHEN.
```sql
SELECT
	naam "NAAM",
	CASE functie
		WHEN 'TRAINER' THEN 'LERAAR'
		WHEN 'DIRECTEUR' THEN 'HOOFD'
		ELSE 'MEDEWERKER'
	END "Functie"
FROM medewerkers
```
4.  Welke waarde is het grootst: het MNR-2000 of de 2de macht van de eerste letterwaarde van de medewerkersnaam? Geef aan welke waarde het grootste is.
```sql
SELECT
	mnr "MNR",
	naam "NAAM",
	CASE GREATEST(mnr-2000,POWER(ASCII(naam),2))
		WHEN mnr-2000 THEN 'MNR-2000'
		ELSE "POWER(ASCII(naam),2"
	END "GROOTSTE"
FROM medewerkers
```
5.  Geef een lijst van de medewerkers waarbij de kolommen NAAM, FUNCTIE en OVERZICHT worden afgedrukt. In de kolom OVERZICHT wordt voor een trainer zijn/haar salaris afgedrukt, voor een verkoper wordt zijn/haar commissie afgedrukt en in alle andere gevallen drukt men 'onbelangrijk' af.
```sql
SELECT
	naam "NAAM",
	functie "FUNCTIE",
	CASE functie
		WHEN 'TRAINER' THEN CAST(maandsal AS VARCHAR)
		WHEN 'VERKOPER' THEN CAST(comm AS VARCHAR)
		ELSE 'ONBELANGRIJK'
	END "OVERZICHT"
FROM medewerkers
```

⚠ Kollommen hebben een __datatype__, daarom is __conversie__ nodig om hier __numerieke__ waarden in een __string kolom__ te zetten




## 7 - Datum- en conversie functies

1. Geef voor alle managers de dag van de week, de dag, de maand en het jaar in vier cijfers waarop ze geboren zijn. Vb. JACOBS donderdag 02 april 1987
```sql
SELECT
	naam "Naam",
	gbdatum "Geboortedatum",
	CASE DATEPART(WEEKDAY, gbdatum)
		WHEN 1 THEN 'Zondag'
		WHEN 2 THEN 'Maandag'
		WHEN 3 THEN 'Dinsdag'
		WHEN 4 THEN 'Woensdag'
		WHEN 5 THEN 'Donderdag'
		WHEN 6 THEN 'Vrijdag'
		WHEN 7 THEN 'Zaterdag'
	END "Weekdag",
	RIGHT('0' + CAST(DATEPART(dd, gbdatum) AS VARCHAR), 2) "Dag",
		CASE datepart(m, gbdatum)
		WHEN 1 THEN 'Januari'
		WHEN 2 THEN 'Februari'
		WHEN 3 THEN 'Maart'
		WHEN 4 THEN 'April'
		WHEN 5 THEN 'Mei'
		WHEN 6 THEN 'Juni'
		WHEN 7 THEN 'Juli'
		WHEN 8 THEN 'Augustus'
		WHEN 9 THEN 'September'
		WHEN 10 THEN 'Oktober'
		WHEN 11 THEN 'November'
		WHEN 12 THEN 'December'
	END "Maand",
	DATEPART(YEAR, gbdatum) "Jaar"
FROM medewerkers
WHERE functie = 'MANAGER'
ORDER BY gbdatum
```
```sql
SELECT
	naam "Naam",
	gbdatum "Geboortedatum",
	FORMAT(gbdatum, 'dddd', 'nl-be') "Weekdag",
	RIGHT('0' + CAST(DATEPART(dd, gbdatum) AS VARCHAR), 2) "Dag",
	FORMAT(gbdatum, 'mmmm', 'nl-be') "Maand",
	DATEPART(YEAR, gbdatum) "Jaar"
FROM medewerkers
WHERE functie = 'MANAGER'
ORDER BY gbdatum
```
2. Hoeveel dagen oud ben je?
```sql
SELECT DATEDIFF(day, '1991-10-21', GETDATE()) AS 'Days Old'
```
3. Geef het weeknummer, het kwartaal en de dag van het jaar van de geboortedata van Wouters en Swinnen?
```sql
SELECT
	naam,
	DATEPART(WEEK, gbdatum) "Weeknummer",
	DATEPART(QUARTER, gbdatum) "Quartaal",
	DATEPART(DY, gbdatum) "Dag van hetjaar"
FROM medewerkers
WHERE naam = 'WOUTERS' OR naam = 'SWINNEN'
```
4. Maak een lijst waarin voor elke medewerker aangegeven staat op welk uur van de dag hij/zij geboren is. De tijd die in het voorbeeld wordt afgedrukt is de tijd die in het attribuut GBDATUM werd opgeslagen. Standaard is deze tijd 12:00 AM omdat deze niet is opgeslaan in de databank.
```sql
SELECT
	voorn "Voornaam",
	naam "Naam",
	DATEPART(hour, CAST(gbdatum AS DATETIME)) "Uur geboorte"
FROM medewerkers
```
5. Geef voor alle medewerkers de geboortedatum en de datum 6 maanden later.
```sql
SELECT 
	naam "Naam",
	gbdatum "Geboortedatum",
	DATEADD(month, 6, gbdatum) "6 maanden later"
FROM medewerkers
```
6. Geef naam, de vierkantswortel van het salaris en het aantal jaren dat de medewerker oud is.
```sql
SELECT
	naam "Naam",
	ROUND(SQRT(maandsal),2) "Vierkantswortel",
	DATEDIFF(year, gbdatum, GETDATE()) "Jaren"
FROM medewerkers
```
7. Druk de leeftijd af in maanden, dagen en jaren voor elke medewerker ouder dan 35 jaar.
```sql
SELECT
	naam "Naam",
	DATEDIFF(month, gbdatum, GETDATE()) "Maanden",
	DATEDIFF(day, gbdatum, GETDATE()) "Dagen",
	DATEDIFF(year, gbdatum, GETDATE()) "Jaren"
FROM medewerkers
WHERE DATEDIFF(year, gbdatum, GETDATE()) > 35
GO
```
8. Druk voor alle medewerkers de laatste dag af van de maand waarop zij geboren zijn.
```sql
SELECT
	voorn "Voornaam",
	naam "Naam",
	gbdatum "Geboortedatum",
	DATEPART(day, EOMONTH(gbdatum)) "Laatste dag vd maand"
FROM medewerkers
```
9. Druk van elke medewerker de datum af van 3000 dagen na de geboortedatum.
```sql
SELECT
	voorn "Voornaam",
	naam "Naam",
	gbdatum "Geboortedatum",
	DATEADD(day, 3000, gbdatum) "3000 dagen na geboortedatum"
FROM medewerkers
GO
```
10. Geef de functie en naam van alle medewerkers die voor 1984 geboren zijn. Vermeld per medewerker de inkomensklasse. Wanneer het maandelijks salaris kleiner is dan 2500 wordt "goedkoop" vermeld anders is het "duur". Sorteer de resultaattabel op basis van de functie. Eerst de directeur, dan de managers, vervolgens de verkopers en tenslotte de trainer en boekhouder.
```sql
SELECT 
	functie,
	naam,
	maandsal,
	CASE
		WHEN maandsal < 2500 THEN 'Goedkoop'
		ELSE 'Duur'
	END "Inkomensklasse"
FROM medewerkers
ORDER BY
	CASE functie
		WHEN 'DIRECTEUR' THEN 1
		WHEN 'MANAGER' THEN 2
		WHEN 'VERKOPER' THEN 3
		WHEN 'TRAINER' THEN 4
		ELSE 5
	END ASC
```




## 8 - Join
⚠ Zie je op het examen resultaten in een kolom die uit verschillende tabellen komen ? Hier MOET zowiso een JOIN gebruikt worden

⚠ Elke Subquery kan als JOIN geschreven worden, niet omgekeerd

⚠ Bij JOIN kunnen extra kolommen uit andere tabellen toegevoegd worden

1. Geef van elke medewerker het nummer en de naam van de afdeling waarvoor hij/zij werkt.
```sql
SELECT
	m.mnr "Medewerkernummer",
	m.naam "Naam",
	a.naam "Afdeling"
FROM medewerkers m
JOIN afdelingen a ON m.afd = a.anr
```
2. Geef de naam en het salaris van elke medewerker die meer verdient dan Clerckx.
```sql
SELECT
	m.naam "Naam",
	m.maandsal "Maandsalaris"
FROM medewerkers m
JOIN medewerkers c ON m.maandsal > c.maandsal
WHERE c.naam = 'CLERCKX'
```

3. Geef de namen van de medewerkers die in dezelfde afdeling werken als Wouters.
```sql
SELECT
	m.naam "Naam"
FROM medewerkers m
JOIN medewerkers w ON m.afd = w.afd
WHERE w.naam = 'WOUTERS'
```
4. Geef het nummer van elke medewerker die in de afdeling verkoop werkt.
```sql
SELECT
	m.mnr "Mnr"
FROM medewerkers m
JOIN afdelingen a ON m.afd = a.anr
WHERE a.naam = 'VERKOOP'
```
5. Geef het nummer van elke medewerker gevolgd door de naam van zijn of haar baas.
```sql
SELECT
	m.mnr,
	c.naam
FROM medewerkers m
JOIN medewerkers b ON m.chef = b.mnr
```
6. Geef van elke medewerker het mnr en de naam van de afdeling waarvoor hij of zij werkt.
```sql
SELECT
	m.mnr,
	a.naam
FROM medewerkers m
JOIN afdelingen a ON a.anr = m.afd
```
7. Welke medewerkers verdienen meer dan hun baas wanneer het salaris van de baas met 1000 EUR verminderd wordt?
```sql
SELECT
	m.naam
FROM medewerkers m
JOIN medewerkers b ON m.chef = b.mnr
WHERE m.maandsal > b.maandsal - 1000
```
8. Geef de namen van de chef (ook van De Koning) en hun ondergeschikten.
```sql
SELECT
	c.naam "Chef",
	o.naam "Ondergeschikte"
FROM medewerkers c
JOIN medewerkers o ON c.mnr = o.chef
ORDER BY c.naam ASC
```
9. Geef de namen van alle afdelingen en de naam van het afdelingshoofd.
```sql
SELECT
	a.naam "Afdeling",
	m.naam "Afdelingshoofd"
FROM afdelingen a
JOIN medewerkers m ON a.hoofd = m.mnr
```
10. Geef de naam en voornaam van de medewerkers die een cursus volgen waar een bedrijfsafdeling gevestigd is.
```sql
SELECT DISTINCT
	m.naam "Naam",
	m.voorn "Voornaam"
FROM medewerkers m
JOIN inschrijvingen i ON m.mnr = i.cursist
JOIN uitvoeringen u ON u.cursus = i.cursus AND i.begindatum = u.begindatum
WHERE u.locatie IN (SELECT DISTINCT locatie FROM afdelingen)
```
11. Geef de naam en voornaam van de medewerkers die een cursus volgen waar hun eigen afdeling gevestigd is.
```sql
SELECT DISTINCT
	m.naam "Naam",
	m.voorn "Voornaam",
	a.locatie "Afdeling Locatie"
FROM medewerkers m
JOIN afdelingen a ON m.afd = a.anr
JOIN inschrijvingen i ON m.mnr = i.cursist
JOIN uitvoeringen u ON i.cursus = u.cursus AND i.begindatum = u.begindatum
WHERE (u.locatie = a.locatie)
```
12. Geef de namen van de medewerkers die een cursus gevolgd hebben die hun chef ook gevolgd heeft.
```sql
SELECT DISTINCT
	m.naam "Naam",
	m.voorn "Voornaam"
FROM medewerkers m
JOIN inschrijvingen i ON m.mnr = i.cursist
JOIN inschrijvingen ii ON ii.cursist = m.chef
JOIN uitvoeringen u ON i.cursus = u.cursus AND i.begindatum = u.begindatum
WHERE i.cursus = ii.cursus
```
13. Geef de namen van docenten die cursussen SQL, ORG of WEB doceren.
```sql
SELECT DISTINCT
	m.naam "Naam",
	c.omschrijving "CursusNaam"
FROM medewerkers m
JOIN uitvoeringen u ON u.docent = m.mnr
JOIN cursussen c ON u.cursus = c.code
WHERE u.cursus IN ('SQL', 'ORG', 'WEB')
```
```sql
SELECT DISTINCT
	m.naam "Naam",
	c.omschrijving "CursusNaam"
FROM medewerkers m
JOIN uitvoeringen u ON u.docent = m.mnr
JOIN cursussen c ON u.cursus = c.code
WHERE 
	c.omschrijving LIKE '%SQL%' OR 
	c.omschrijving LIKE '%ORG%' OR 
    c.omschrijving LIKE '%WEB%'
```
14. Geef van alle inschrijvingen de naam van de docent, de naam van de cursus en de naam van de cursist.
```sql
SELECT
	m.naam "Naam docent",
	i.cursus "Naam Cursus",
	mm.naam "Naam Cursist"
FROM m.medewerkers
JOIN
```
15. Geef de naam en omschrijving van alle cursussen samen met de docent die deze cursussen doceren, evenals de begindata. Bovendien moet je voor een lege waarde bij docent '==onbekend==' weergeven.
```sql
SELECT
	c.code "Naam",
	c.omschrijving "Omschrijving",
	CASE
		WHEN m.naam IS NULL THEN '==onbekend=='
		ELSE m.naam
	END "Docent",
	u.begindatum "Begindatum"
FROM cursussen c
JOIN uitvoeringen u ON u.cursus = c.code
LEFT JOIN medewerkers m ON u.docent = m.mnr
```
16. Geef van alle cursisten hun naam, de naam van hun chef, de naam van de afdeling waar ze werken, de namen van de cursussen waarvoor ze zich eventueel inschreven en de namen van de docenten die deze cursussen geven.
```sql	
SELECT	deelnemer.naam + ',' + deelnemer.voorn	AS "Deelnemer",
		chef.naam								AS "Chef",
		a.naam									AS "Afdeling",
		c.omschrijving							AS "Cursus",
		docent.naam + ',' + docent.voorn		AS "Docent"
FROM inschrijvingen i
JOIN medewerkers deelnemer	ON i.cursist 		= deelnemer.mnr
JOIN medewerkers chef		ON deelnemer.chef 	= chef.mnr
JOIN afdelingen a			ON deelnemer.afd 	= a.anr
JOIN uitvoeringen u			ON i.cursus 		= u.cursus 		AND i.begindatum = u.begindatum
JOIN cursussen c			ON u.cursus 		= c.code
JOIN medewerkers docent		ON u.docent 		= docent.mnr
ORDER BY deelnemer, chef, afdeling, cursus, docent
```




## 9 - Groepsfuncties
⚠ 'Per' of 'Tel' wijzen op een groepsfunctie

⚠ 


1. Geef het aantal medewerkers per afdeling.
```sql
SELECT 
	afd,
	COUNT(mnr) AS "Aantal"
FROM medewerkers
GROUP BY afd
```
2. Geef het gemiddelde salaris per afdeling.
```sql
SELECT 
	afd, 
	AVG(maandsal) AS "Gemiddelde"
FROM medewerkers
GROUP BY afd
```
> Of als je echt de naam van de afdeling wil tonen:
```sql
SELECT 
    a.naam AS "Afdeling",
    AVG(m.maandsal) AS "Gemiddelde salaris"
FROM medewerkers m
JOIN afdelingen a ON m.afd = a.anr
GROUP BY a.naam
```
3. Geef het aantal medewerkers per afdeling, maar enkel voor de afdelingen waar in de afdelingsnaam een "OO" voorkomt.
```sql
SELECT
	afd AS "Afdeling",
	COUNT(mnr) AS "Aantal"
FROM medewerkers
WHERE afd IN
(
	SELECT anr FROM afdelingen WHERE naam LIKE '%OO%'
)
GROUP BY afd
```
4. Geef het aantal medewerkers voor alle afdelingen behalve de afdeling 10.
```sql
SELECT
	afd AS "Afdeling",
	COUNT(mnr) AS "Aantal"
FROM medewerkers
WHERE afd != 10
GROUP BY afd
```
5. Geef het maximum en het minimum salaris en de afdelingsnaam per afdeling.
```sql
SELECT 
    a.naam AS "Afdeling",
    MAX(m.maandsal) AS "Maximum salaris",
	Min(m.maandsal) AS "Minimum salaris"
FROM medewerkers m
JOIN afdelingen a ON m.afd = a.anr
GROUP BY a.naam
```
6. Geef de naam en het salaris van de medewerker die het meest verdient.
```sql
SELECT TOP 1
	naam "Naam",
	maandsal "Maandsal"
FROM medewerkers
ORDER BY maandsal DESC
```
```sql
SELECT
	naam "Naam",
	maandsal "Maandsal"
FROM medewerkers
WHERE maandsal = (SELECT MAX(maandsal) FROM medewerkers)
```
7. Geef per afdeling en per functie het aantal medewerkers en het gemiddelde salaris.
```sql
SELECT
	afd "Afdeling",
	functie "Functie",
	COUNT(mnr) "Aantal medewerkers",
	AVG(maandsal) "Gemmiddelde salaris"
FROM medewerkers
GROUP BY functie, afd
```
⚠ binnen afd splitsen op functie

8.  Geef per afdeling het gemiddelde salaris voor die afdelingen waar meer dan 3 medewerkers werken.
```sql
SELECT 
	afd, 
	AVG(maandsal) AS "Gemiddelde"
FROM medewerkers
GROUP BY afd
HAVING COUNT(mnr) > 3
```
9. Geef per afdeling de naam van de afdeling en de naam van de medewerker(s) die het meest verdient.
```sql
SELECT 
    a.naam AS "Afdeling",
    m.naam AS "Medewerker die het meest verdient"
FROM medewerkers m
JOIN afdelingen a ON m.afd = a.anr
WHERE m.maandsal = (SELECT MAX(maandsal) FROM medewerkers  WHERE afd = a.anr)
```
10. Geef de namen van de medewerkers die een hoger salaris hebben dan het gemiddelde salaris.
```sql
SELECT 
	naam,
	maandsal
FROM medewerkers
WHERE maandsal > (SELECT AVG(maandsal) FROM medewerkers)
```
11. Geef de namen van de medewerkers die een hoger salaris hebben dan het gemiddelde salaris van hun afdeling.
```sql
SELECT 
	naam,
	maandsal
FROM medewerkers m
WHERE m.maandsal > (SELECT AVG(maandsal) FROM medewerkers mm WHERE m.afd = afd GROUP BY afd)
```
12. Geef het aantal cursussen die elke medewerker gevolgd heeft (stijgend gesorteerd).
We doen een LEFT JOIN voor ook de mederwerkers die geen cursussen gevolgd hebben.
```sql
SELECT 
	m.naam,
	COUNT(cursus) "Aantal"
FROM medewerkers m
LEFT JOIN inschrijvingen i ON m.mnr = i.cursist
GROUP BY m.naam
ORDER BY aantal ASC
```
13.  Wat is het gemiddelde salaris van de medewerkers die in dezelfde -- afdeling werken als 'Den Ruyter'?
```sql
SELECT 
	AVG(maandsal)
FROM medewerkers
WHERE afd = (SELECT afd FROM medewerkers WHERE naam = 'DEN RUYTER')
```
14.  Hoeveel medewerkers verdienen minder dan het gemiddelde salaris plus 200?
```sql
SELECT 
	COUNT(mnr)
FROM medewerkers
WHERE maandsal < (SELECT AVG(maandsal) + 200 FROM medewerkers)
```
15.  Hoe heten de drie hoogst betaalde medewerkers?
```sql
SELECT TOP 3
	naam,
	maandsal
FROM medewerkers
ORDER BY maandsal DESC
```
16.  Wat zijn de namen en de salarissen van de vijf laagst betaalde medewerkers?
```sql
SELECT TOP 5
	naam,
	maandsal
FROM medewerkers
ORDER BY maandsal ASC
```
17.  Idem vraag 16, maar sorteer het resultaat dalend op salaris.
```sql
SELECT TOP 3
	naam,
	maandsal
FROM medewerkers
ORDER BY maandsal DESC
```
18.  Hoe heten de 3 meest verdienende verkopers?
```sql
SELECT TOP 3
	naam,
	maandsal
FROM medewerkers
WHERE functie = 'VERKOPER'
ORDER BY maandsal DESC
```
19.  Welke is van alle gemiddelde maandsalarissen per afdeling het hoogste gemiddelde maandsalaris?
```sql
SELECT TOP 1
	afd,
	AVG(maandsal) "Gemiddelde"
FROM medewerkers
GROUP BY afd
ORDER BY AVG(maandsal) DESC
```
```sql
SELECT MAX(gemiddelde) FROM
(
	SELECT
		afd,
		AVG(maandsal) AS "Gemiddelde"
	FROM medewerkers
	GROUP BY afd
) AS gemiddelden
```
20.  Welke afdeling (naam) heeft het hoogste gemiddelde maandsalaris?
```sql
SELECT TOP 1
	a.naam "Afdeling",
	AVG(maandsal) "Gemiddelde"
FROM medewerkers m
JOIN afdelingen a ON m.afd = a.anr
GROUP BY a.naam
ORDER BY AVG(maandsal) DESC
```
21.  Op welke datum is voor het laatst een cursus gepland?
```sql
SELECT TOP 1
	begindatum
FROM uitvoeringen
ORDER BY begindatum DESC
```
22.  Toon per afdelingsnummer en functie: het totaal aantal medewerkers en het gemiddelde maandsalaris.
```sql
SELECT 
	afd,
	functie,
	COUNT(mnr) "Aantal",
	AVG(maandsal) "Gemiddelde"
FROM medewerkers
GROUP BY afd, functie
ORDER BY afd, functie
```
23.  Toon per afdelingsnummer en functie: het totaal aantal medewerkers en het gemiddelde maandsalaris. Toon enkel de afdelingen waar meer dan 3 medewerkers werken.
```sql
SELECT 
	afd,
	functie,
	COUNT(mnr) "Aantal",
	AVG(maandsal) "Gemiddelde"
FROM medewerkers
GROUP BY afd, functie
HAVING COUNT(mnr) > 3
ORDER BY afd, functie
```




## 10 - Verzamelingsoperatoren
⚠ Verzamelingsoperatoren werken enkel op __gelijkaardige__ tabellen

⚠ Een __UNION__ werkt enkel als de tabellen __dezelfde kolommen__ hebben

⚠ 

1. Geef een lijst van de medewerkersnamen en de afdelingsnamen.
```sql
SELECT m.naam
FROM medewerkers m
UNION
SELECT a.naam
FROM afdelingen a
GO
```
2. Geef een lijst met namen van afdelingen en namen van cursussen die respectievelijk in 
Hasselt gevestigd zijn of daar doorgaan.
```sql
SELECT a.naam
FROM afdelingen a
WHERE locatie = 'HASSELT'
UNION
SELECT c.omschrijving
FROM uitvoeringen u
JOIN cursussen c ON u.cursus = c.code
WHERE locatie = 'HASSELT'
```
3. Geef de medewerkers die geen manager zijn.
```sql
SELECT naam
FROM medewerkers
EXCEPT
SELECT functie
FROM MEDEWERKERS
WHERE functie = 'MANAGER'
```
```sql
SELECT naam, functie
FROM medewerkers
WHERE functie != 'MANAGER'
```
4. Geef de locaties waar wel cursussen doorgaan maar waar geen afdelingen gevestigd zijn.
```sql
SELECT locatie
FROM uitvoeringen
EXCEPT
SELECT locatie
FROM afdelingen
```
5. Geef de naam en begindatum van elke cursus die alleen door de medewerker 7844 
gevolgd is.
```sql
SELECT 
	c.omschrijving,
	u.begindatum
FROM inschrijvingen i
JOIN uitvoeringen u ON i.cursus = u.cursus AND i.begindatum = u.begindatum
JOIN cursussen c ON u.cursus = c.code
WHERE i.cursist != 7844
```
6. Geef de cursuscode van de cursussen die E. Jacobs niet gevolg heeft.
```sql
SELECT c.code
FROM cursussen c
EXCEPT
SELECT c.code
FROM inschrijvingen i
JOIN cursussen c ON i.cursus = c.code
JOIN medewerkers m ON i.cursist = m.mnr
WHERE m.naam = 'JACOBS'
```
7. Geef de namen van de medewerkers die geen cursussen gevolgd hebben.
```sql
SELECT naam
FROM medewerkers
EXCEPT
SELECT m.naam
FROM inschrijvingen i
JOIN medewerkers m ON i.cursist = m.mnr
```
8. In welke plaatsen is minstens 1 afdeling gevestigd en wordt minstens 1 cursus gepland?
```sql
SELECT locatie
FROM afdelingen
INTERSECT
SELECT locatie
FROM uitvoeringen
```
9. Geef de nummers van de medewerkers die de cursus 'Windows Server' gevolgd hebben en 
in de afdeling Verkoop werken.
```sql
SELECT mnr
FROM inschrijvingen i
JOIN cursussen c ON i.cursus = c.code
JOIN medewerkers m ON i.cursist = m.mnr
WHERE c.omschrijving = 'Windows Server'
INTERSECT
SELECT mnr
FROM medewerkers
WHERE afd = 20
```




## 11 - Views

1. Maak een view Baas dat het nummer van elke medewerker geeft, gevolgd door de naam van zijn of haar baas.
```sql
CREATE VIEW baas AS
SELECT
	mnr,
	naam,
	chef
FROM medewerkers
```
2. Wijzig de view zodat de gegevens stijgend gesorteerd op de naam van de baas worden weergegeven.
```sql
SELECT * FROM baas ORDER BY chef ASC
```
3. Zoek de view op in de datadictionary en geef de viewdefinitie.
```sql
SELECT * FROM INFORMATION_SCHEMA.VIEWS
```
4. Maak een view Jaarsal dat de voornamen, de namen, afdelingsnaam en het jaarsalaris (incl. commissie) van alle medewerkers berekent.
```sql
CREATE VIEW jaarsal AS
SELECT
	voorn,
	naam,
	a.naam "Afdeling",
	maandsal * 12 + ISNULL(comm, 0) "Jaarsalaris"
FROM medewerkers m
```
5. Gebruik de view om enkel de medewerkers van de afdeling opleidingen te selecteren. Verwijder je laatste view.
```sql
SELECT * FROM jaarsal WHERE afd = 30
DROP VIEW jaarsal
```



## 12 - DML (Data Manipulation Language)

1. Wijzig de naam van medewerker met mnr 7876 in Boonen.
```sql
ALTER TABLE medewerkers
UPDATE naam = 'Boonen'
WHERE mnr = 7876
```
2. Verander de locatie van afdeling 10 in Tongeren.
```sql
ALTER TABLE afdelingen
UPDATE locatie = 'Tongeren'
WHERE anr = 10
```
3. Verwijder cursus LIN.
```sql
DELETE FROM cursussen WHERE code = 'LIN'
```
4. Alle medewerkers van de afdeling Verkoop krijgen 10% opslag.
```sql
ALTER TABLE medewerkers
UPDATE maandsal = maandsal * 1.1
WHERE afd = 20
```
5. Voeg aan de tabel MEDEWERKERS de gegevens toe van een nieuwe medewerker:
	● 7999, Willem Revis, 21/01/1983, boekhouder, salaris €2950, chef 7782.
```sql
INSERT INTO medewerkers (mnr, naam, voorn, gbdatum, functie, maandsal, chef)
VALUES (7999, 'Willem', 'Revis', '1983-01-21', 'BOEKHOUDER', 2950, 7782)
```
1. Voer de gegevens in van nog een medewerker:
	● Polien Dox, 7989, trainer, chef 7902 en geboren op de 350ste dag van 1980. Let op: je moet hier wel een Maandsal meegeven, want dit mag niet NULL zijn!
```sql
INSERT INTO medewerkers (mnr, naam, voorn, gbdatum, functie, maandsal, chef)
VALUES (7989, 'Polien', 'Dox', '1980-12-16', 'TRAINER', 2000, 7902)
```



## 13 - ProefExamen
1. Geef een overzicht volgens onderstaande resultaatquery van alle medewerkers
   
bepaal de nieuwe wedde als volgt:
   * de naam De Koning: 30% verhoging
   * de functie Boekhouder: 15% verhoging
   * de functie Trainer: 5% verhoging
   * de functie Manager: 20% verhoging

Druk het resultaat af in volgorde van de functie:
   * eerst de directeur
   * dan de managers
   * dan de rest in aflopende volgorde van de naam

```sql
SELECT
	CONCAT(UPPER(LEFT(naam, 1)) + LOWER(SUBSTRING(naam, 2, LEN(naam))), ' ', voorn) "MEDEWERKER",
	functie "FUNCTIE",
	CASE functie
		WHEN 'DIRECTEUR' THEN maandsal * 1.3
		WHEN 'MANAGER' THEN maandsal * 1.2
		WHEN 'BOEKHOUDER' THEN maandsal * 1.15
		WHEN 'TRAINER' THEN maandsal * 1.05
		ELSE maandsal
	END "Nieuwe Wedde"
FROM medewerkers
ORDER BY
	CASE functie
		WHEN 'DIRECTEUR' THEN 1
		WHEN 'MANAGER' THEN 2
		ELSE 3
	END ASC,
	naam DESC
```

1. Geef de namen van de medewerkers die in de maanden november of december geboren zijn en die een hoger maandsalaris hebben dan het gemiddelde van hun afdeling.
Toon tevens ook de naam van de afdeling waarvoor zij werken, hun maandsalaris en het gemiddelde van de salarissen van de afdeling waar ze in werken.
```sql
SELECT
	LOWER(a.naam) AS "afdeling",
	m.naam AS "naam",
	m.maandsal AS "maandsal",
	avg.maandsal AS "Afdelingsgemiddelde"
FROM medewerkers m
JOIN afdelingen a ON m.afd = a.anr
JOIN (
	SELECT 
		afd,
		AVG(maandsal) AS maandsal
	FROM medewerkers
	GROUP BY afd
) avg ON avg.afd = m.afd
WHERE
	DATEPART(month, m.gbdatum) IN (11, 12) AND
	m.maandsal > avg.maandsal
GROUP BY a.naam, m.naam, m.maandsal, avg.maandsal
```

1. Wat is de gemiddelde commissie van de verkopers wanneer de verkopers die momenteel geen commissie (= 0) hebben een commissie zouden hebben van 200 EUR?
```sql
SELECT
	AVG(CASE WHEN comm = 0 THEN 200 ELSE comm END) AS "Gemiddelde commissie"
FROM medewerkers
WHERE functie = 'VERKOPER'
```

1. Welke medewerkers zijn ouder dan hun chef?
```sql
SELECT
	m.naam "Naam medewerker",
	m.gbdatum "Geboortedatum medewerker",
	mm.gbdatum "geboortedatum baas"
FROM medewerkers m 
JOIN medewerkers mm ON m.chef = mm.mnr
WHERE m.gbdatum < mm.gbdatum
```

1. Welke medewerkers hebben zowel een cursus WEB als SQL gevolgd?
Sorteer deze volgens omgekeerd maandsalaris (van hoog naar laag).
```sql
SELECT 
	m.mnr "mnr",
	m.naam "naam",
	m.voorn "voorn"
FROM medewerkers m
JOIN inschrijvingen i ON m.mnr = i.cursist
JOIN uitvoeringen u ON i.cursus = u.cursus AND i.begindatum = u.begindatum
JOIN cursussen c ON u.cursus = c.code
WHERE c.code IN ('WEB', 'SQL')
GROUP BY m.mnr, m.naam, m.voorn
HAVING COUNT(DISTINCT c.code) = 2
ORDER BY MAX(m.maandsal) DESC
```

1. Geef de medewerkers die NIET aan de afdeling "opleidingen" zijn verbonden.
Toon alleen de medewerkers wiens naam eindigt met een 'S' en die een even
aantal letters in de voornaam hebben.
```sql
SELECT
	mnr,
	naam,
	voorn
FROM medewerkers
WHERE afd != (SELECT anr FROM afdelingen WHERE naam = 'OPLEIDINGEN')
	AND naam LIKE '%S'
	AND LEN(voorn) % 2 = 0
```

1. Voeg een afdeling 50 met naam 'IT' toe.
Hoofd van deze afdeling wordt 7782, locatie van de afdeling is MAASEIK.
Voeg voor deze afdeling een medewerker met nummer 8003 toe met naam 'BRIERS', voornaam 'PATRICIA', maandsalaris 5000, functie 'TRAINER', geboortedatum 1/1/1970.
```sql
INSERT INTO afdelingen (anr, naam, hoofd, locatie)
VALUES (50, 'IT', 7782, 'MAASEIK');
INSERT INTO medewerkers (mnr, naam, voorn, maandsal, functie, gbdatum, afd)
VALUES (8003, 'BRIERS', 'PATRICIA', 5000, 'TRAINER', '1970-01-01', 50);
```


## 14 - Examen

1. 
```sql

```

2. 
```sql

```

3. 
```sql

```

4. 
```sql

```

5. 
```sql

```

6. 
```sql

```

7. 
```sql

```


