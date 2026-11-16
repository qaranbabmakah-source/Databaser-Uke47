# Uke47-Databaser

Mandag – Steg 1: Start med behovet 

Forstå hvorfor FjordTek trenger en database, og hvilken informasjon systemet skal lagre.

Hva gjorde jeg?

Jeg undersøkte behovene til FjordTek, som ønsker å lage et enkelt kundestøttesystem. Systemet skal holde oversikt over kunder, ansatte og supportsaker.

Databasen skal kunne vise:

Hvem kunden er.

Hvilken supportsak kunden har.

Hvilken ansatt som arbeider med saken.

Hva statusen på saken er.

Når supportsaken ble opprettet.

Hvorfor er dette viktig?

Det er viktig å forstå behovene før vi begynner å lage databasetabeller. Da kan vi velge riktig informasjon og unngå å lagre unødvendige opplysninger.

Jeg har forstått at FjordTek trenger en database med informasjon om kunder, ansatte og supportsaker. Dette blir grunnlaget for tabellene og ER-diagrammet som skal lages senere.


Steg 2 – Tabell, rad og felt

<img width="945" height="498" alt="image" src="https://github.com/user-attachments/assets/743ceed4-75cd-4b92-8aba-76af39a10385" />

Hva gjorde jeg?

Jeg åpnet dbdiagram og laget en tabell som heter Kunde.

Jeg la inn tre felter:

KundeID – integer (PK)
Navn – varchar
Epost – varchar

Hva lærte jeg?

Tabell: Lagrer informasjon om kunder.
Rad: Informasjon om én kunde.
Felt: For eksempel KundeID, Navn og Epost.

Resultat

Jeg klarte å lage Kunde-tabellen i dbdiagram. Jeg brukte KundeID som primærnøkkel (PK).

Jeg lærte hvordan en enkel databasetabell fungerer, og forskjellen mellom tabell, rad og felt.

Steg 3 – entitet og tabell

<img width="945" height="426" alt="image" src="https://github.com/user-attachments/assets/9564bd9d-2686-4498-aa64-a9cac3166ac5" />

Jeg brukte  dbdiagram  og laget tre tabeller: Kunde, Ansatt og Sak.

En entitet er noe databasen trenger å lagre informasjon om.

Jeg laget tre separate tabeller fordi FjordTek trenger å holde oversikt over kunder, ansatte og supportsaker.

Resultat: Jeg fikk laget alle tre tabellene i dbdiagram.io.


Steg 4 – velg felter

<img width="945" height="433" alt="image" src="https://github.com/user-attachments/assets/2b4c7385-256b-4957-855c-f5dcffd65d18" />

Jeg brukte dbdiagram og la inn flere felter i de tre tabellene.

Kunde: KundeID, Navn, Epost og Telefon.

Ansatt: AnsattID, Navn, Avdeling og Epost.

Sak: SakID, Tittel, Status og OpprettetDato.

Jeg brukte integer for ID, varchar for tekst og timestamp for dato og tidspunkt.

Resultat: Alle tre tabellene har nå fire felter.

Jeg lærte at det er viktig å plassere informasjonen i riktig tabell før man lager relasjoner.


Steg 5 – Primærnøkkel (PK)

Jeg markerte KundeID, AnsattID og SakID som primærnøkler (PK) i dbdiagram.io.


En primærnøkkel er en unik ID som brukes til å identifisere hver rad i en tabell.

Jeg bruker en egen ID fordi flere personer kan ha samme navn, og navn og e-post kan endres.


Resultat: Alle tre tabellene har en primærnøkkel.

Steg 6 – et første møte med datatyper

Jeg brukte forskjellige datatyper i dbdiagram.io.

integer: Brukes til ID-numre.

varchar: Brukes til tekst, for eksempel navn og e-post.

timestamp: Brukes til dato og tidspunkt.

Jeg brukte integer for KundeID, AnsattID og SakID, varchar for tekstfeltene og timestamp for OpprettetDato.

Resultat: Alle feltene i de tre tabellene har passende datatyper.

Jeg lærte at datatyper bestemmer hvilken type informasjon som kan lagres i hvert felt.


Steg 7 – første relasjon: Kunde og Sak

<img width="947" height="424" alt="image" src="https://github.com/user-attachments/assets/93dc814a-89d2-474e-bd09-cdb4d929fd17" />

Hva gjorde jeg?

Jeg brukte dbdiagram og laget en relasjon mellom Kunde og Sak.

Jeg la til feltet KundeID i Sak-tabellen og koblet det til Kunde-tabellen.

Hva lærte jeg?

Jeg lærte at en relasjon viser hvordan to tabeller henger sammen.

Én kunde kan ha mange supportsaker, men hver supportsak tilhører én kunde. Dette kalles en M-relasjon.

Jeg brukte også [not null] fordi hver supportsak må ha en kunde.

Resultat

Jeg klarte å koble Kunde og Sak sammen. Relasjonen vises som en linje i ER-diagrammet.

Jeg lærte hvordan to tabeller kan kobles sammen ved hjelp av KundeID.

Steg 8 – tegn fra en ny spesifikasjon

<img width="950" height="430" alt="image" src="https://github.com/user-attachments/assets/c6d6433c-5a8e-4b20-a1d8-8a71461b9b52" />

Oppgave A – Avdeling og Ansatt

Hva gjorde jeg?

Jeg opprettet et nytt diagram i dbdiagram og laget to tabeller: Avdeling og Ansatt.

Jeg la inn følgende felter:

Avdeling:

AvdelingID – integer (PK)

Navn – varchar

Ansatt:

AnsattID – integer (PK)

Navn – varchar

Epost – varchar

AvdelingID – integer (FK)

Jeg koblet Avdeling og Ansatt sammen med en 1:M-relasjon.

Hva lærte jeg?

Jeg lærte at én avdeling kan ha mange ansatte, men hver ansatt tilhører én avdeling.

AvdelingID i Ansatt brukes til å koble den ansatte til riktig avdeling.

Resultat:

Jeg klarte å lage begge tabellene og koble dem sammen i dbdiagram.

Oppgave B – Produkt og Kategori

<img width="957" height="425" alt="image" src="https://github.com/user-attachments/assets/22f89c40-c276-4de2-a082-8dfc774d1bed" />


Hva gjorde jeg?

Jeg opprettet et nytt diagram i dbdiagram og laget to tabeller: Kategori og Produkt.

Jeg la inn følgende felter:

Kategori:

KategoriID – integer (PK)
Navn – varchar

Produkt:

ProduktID – integer (PK)

Navn – varchar

Pris – decimal

KategoriID – integer (FK)

Jeg koblet Kategori og Produkt sammen med en 1:M-relasjon.

Hva lærte jeg?

Jeg lærte at én kategori kan inneholde mange produkter, men hvert produkt tilhører én kategori.

KategoriID i Produkt brukes til å koble produktet til riktig kategori.

Jeg brukte også datatypen decimal for pris.

Resultat:

Jeg klarte å lage begge tabellene og koble dem sammen i dbdiagram


I denne oppgaven lærte jeg å lage databasetabeller fra en spesifikasjon.

Jeg brukte primærnøkler (PK) for å identifisere hver rad og fremmednøkler (FK) for å koble tabellene sammen.

Jeg lærte også hvordan en 1:M-relasjon fungerer.


Mandagens grunnoppgave

1.	Hva er forskjellen mellom tabell, rad og felt?

En tabell lagrer informasjon om én type ting. En rad inneholder informasjon om én bestemt ting. Et felt beskriver en egenskap, for eksempel navn eller e-post.

2. Hva er en entitet?

En entitet er noe vi ønsker å lagre informasjon om i en database, for eksempel Kunde, Ansatt eller Sak.

3. Hvorfor trenger vi en primærnøkkel?

Vi trenger en primærnøkkel (PK) for å identifisere hver rad i en tabell. En ID er unik, selv om flere personer har samme navn.

4. Hva betyr 1:M?

1:M betyr en-til-mange. En kunde kan ha mange supportsaker, men hver supportsak tilhører en kunde.

5. Hvorfor ligger KundeID i Sak?

KundeID ligger i Sak for å vise hvilken kunde supportsaken tilhører. Det brukes til å koble Kunde og Sak sammen.

Videre utforskning – 

<img width="945" height="424" alt="image" src="https://github.com/user-attachments/assets/a8246db2-ea43-4d80-af5b-96d6deb4d535" />

Hva gjorde jeg?

Jeg valgte å lage et enkelt biblioteksystem i dbdiagram

Jeg opprettet tre tabeller:

Lantaker: Lagrer informasjon om låntakere.

Bok: Lagrer informasjon om bøker.

Lan: Lagrer informasjon om utlån av bøker.

Jeg la inn felter med passende datatyper og markerte primærnøkler (PK).

Relasjoner

Jeg laget to 1:M-relasjoner:

Én låntaker kan ha mange utlån.

Én bok kan lånes ut mange ganger over tid.

Jeg brukte LantakerID og BokID i Lan-tabellen for å koble tabellene sammen.

Resultat

Jeg klarte å lage tre tabeller og to relasjoner i dbdiagram

Hva lærte jeg?

Jeg lærte hvordan et biblioteksystem kan organiseres med flere tabeller, primærnøkler og relasjoner.


















