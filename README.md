# Ukeplan – databaser: struktur, ER-diagram, relasjoner og GDPR

## Mandag – Steg 1: Start med behovet 

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


## Steg 2 – Tabell, rad og felt

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

## Steg 3 – entitet og tabell

<img width="945" height="426" alt="image" src="https://github.com/user-attachments/assets/9564bd9d-2686-4498-aa64-a9cac3166ac5" />

Jeg brukte  dbdiagram  og laget tre tabeller: Kunde, Ansatt og Sak.

En entitet er noe databasen trenger å lagre informasjon om.

Jeg laget tre separate tabeller fordi FjordTek trenger å holde oversikt over kunder, ansatte og supportsaker.

Resultat: Jeg fikk laget alle tre tabellene i dbdiagram.io.


## Steg 4 – velg felter

<img width="945" height="433" alt="image" src="https://github.com/user-attachments/assets/2b4c7385-256b-4957-855c-f5dcffd65d18" />

Jeg brukte dbdiagram og la inn flere felter i de tre tabellene.

Kunde: KundeID, Navn, Epost og Telefon.

Ansatt: AnsattID, Navn, Avdeling og Epost.

Sak: SakID, Tittel, Status og OpprettetDato.

Jeg brukte integer for ID, varchar for tekst og timestamp for dato og tidspunkt.

Resultat: Alle tre tabellene har nå fire felter.

Jeg lærte at det er viktig å plassere informasjonen i riktig tabell før man lager relasjoner.


## Steg 5 – Primærnøkkel (PK)

Jeg markerte KundeID, AnsattID og SakID som primærnøkler (PK) i dbdiagram.io.


En primærnøkkel er en unik ID som brukes til å identifisere hver rad i en tabell.

Jeg bruker en egen ID fordi flere personer kan ha samme navn, og navn og e-post kan endres.


Resultat: Alle tre tabellene har en primærnøkkel.

## Steg 6 – et første møte med datatyper

Jeg brukte forskjellige datatyper i dbdiagram.io.

integer: Brukes til ID-numre.

varchar: Brukes til tekst, for eksempel navn og e-post.

timestamp: Brukes til dato og tidspunkt.

Jeg brukte integer for KundeID, AnsattID og SakID, varchar for tekstfeltene og timestamp for OpprettetDato.

Resultat: Alle feltene i de tre tabellene har passende datatyper.

Jeg lærte at datatyper bestemmer hvilken type informasjon som kan lagres i hvert felt.


## Steg 7 – første relasjon: Kunde og Sak

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

## Steg 8 – tegn fra en ny spesifikasjon

<img width="950" height="430" alt="image" src="https://github.com/user-attachments/assets/c6d6433c-5a8e-4b20-a1d8-8a71461b9b52" />

## Oppgave A – Avdeling og Ansatt

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

## Oppgave B – Produkt og Kategori

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


## Mandagens grunnoppgave

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

<img width="950" height="429" alt="image" src="https://github.com/user-attachments/assets/598ef9d4-eee8-4179-9655-de1b4c853294" />


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


## Tirsdag – les spesifikasjoner og tegn enkle relasjoner

Stage 1 Oppgave – bruker og innlegg

<img width="950" height="442" alt="image" src="https://github.com/user-attachments/assets/8a4867ce-4ce7-4033-84c9-408b0dd76db2" />


Målet var å lage et enkelt ER-diagram med to tabeller og en 1:M-relasjon.

Hva gjorde jeg?

Jeg åpnet dbdiagram.io og opprettet to tabeller: Bruker og Innlegg.

Bruker:

BrukerID – integer (PK)

Brukernavn – varchar

Rolle – varchar

Innlegg:

InnleggID – integer (PK)

Tittel – varchar

Tekst – text

BrukerID – integer (FK)

Jeg koblet tabellene sammen ved hjelp av BrukerID.

Hva lærte jeg?

Jeg lærte hvordan to tabeller kan kobles sammen med en 1:M-relasjon.

Én bruker kan skrive mange innlegg, men hvert innlegg tilhører én bruker.

BrukerID i Innlegg viser hvilken bruker som har skrevet innlegget.

Resultat

Jeg klarte å lage begge tabellene, markere primærnøkler og lage en 1:M-relasjon i dbdiagram 


Jeg lærte hvordan primærnøkler (PK) og fremmednøkler (FK) brukes for å koble sammen tabeller.

## Steg 2 – kontroller modellen

Har begge tabellene en tydelig primærnøkkel?

Ja, Bruker har BrukerID som PK, og Innlegg har InnleggID som PK.

Ligger BrukerID i Innlegg som feltet som kobler tabellene sammen?
 
Ja, BrukerID ligger i Innlegg og brukes som fremmednøkkel (FK) for å koble innlegget til riktig bruker.

Viser relasjonen at én bruker kan ha mange innlegg?

Ja, diagrammet viser en 1:M-relasjon. Én bruker kan skrive mange innlegg, men hvert innlegg tilhører én bruker.

Hvorfor bør ikke Brukernavn kopieres inn i hvert innlegg?

Fordi BrukerID allerede viser hvem som har skrevet innlegget. Da unngår vi å lagre samme informasjon flere ganger.


## Steg 3 – oppgave B: kunde og bestilling

<img width="956" height="436" alt="image" src="https://github.com/user-attachments/assets/7b387c2c-c806-4677-86d2-61798dc83798" />

Hva gjorde jeg?

Jeg brukte dbdiagram.io og laget et ER-diagram med to tabeller: Kunde og Bestilling.

Kunde:

KundeID – integer (PK)

Navn – varchar

Epost – varchar

Bestilling:

BestillingID – integer (PK)

Dato – date

Status – varchar

KundeID – integer (FK)

Jeg koblet tabellene sammen ved hjelp av KundeID.

Hva lærte jeg?

Jeg lærte hvordan to tabeller kan kobles sammen med en 1:M-relasjon.

Én kunde kan ha mange bestillinger, men hver bestilling tilhører én kunde.

KundeID i Bestilling viser hvilken kunde bestillingen tilhører.

Resultat

Jeg klarte å lage begge tabellene, markere primærnøkler (PK) og lage en 1:M-relasjon i dbdiagram.io.

Jeg lærte hvordan primærnøkler og fremmednøkler brukes for å koble sammen tabeller og organisere informasjon i en database.

## Steg 4 – sammenlign de to modellene

Hva er likt mellom de to relasjonene?

Begge modellene har en 1:M-relasjon (én-til-mange).
I den første modellen kan én bruker skrive mange innlegg.

I den andre modellen kan én kunde ha mange bestillinger.

Begge modellene bruker primærnøkler (PK) og fremmednøkler (FK) for å koble sammen tabellene.

Hva lærte jeg?

Jeg lærte at ulike databaser kan ha samme type relasjon, selv om de lagrer forskjellig informasjon.

Begge modellene viser at én rad i den første tabellen kan være koblet til mange rader i den andre tabellen.

## Tirsdagens grunnoppgave

Jeg laget to ER-diagrammer i dbdiagram.io: Bruker og Innlegg, og Kunde og Bestilling.

Jeg markerte primærnøkler (PK) og brukte fremmednøkler (FK) for å koble tabellene sammen.

Jeg lærte at én bruker kan skrive mange innlegg, og at én kunde kan ha mange bestillinger. Begge modellene har en 1:M-relasjon.

Jeg har fullført tirsdagens grunnoppgave.


## Onsdag – fremmednøkler og flere relasjoner

## bSteg 1 – fremmednøkkel

<img width="949" height="425" alt="image" src="https://github.com/user-attachments/assets/0a36f46f-f3e5-47ab-a1b3-d222ff51320e" />

Steg 1: Fremmednøkkel (FK)

En fremmednøkkel (FK) er et felt som kobler sammen to tabeller.

I FjordTek-modellen har jeg koblet tabellene Kunde og Sak sammen.

KundeID er primærnøkkel (PK) i Kunde.

KundeID er fremmednøkkel (FK) i Sak.


Relasjonen mellom Kunde og Sak er 1:M.

Det betyr at én kunde kan ha mange saker, men hver sak tilhører én kunde.

Vi bruker KundeID for å koble tabellene sammen. Derfor trenger vi ikke å kopiere Navn og Epost inn i hver sak.

## Steg 2 – Koble Ansatt til Sak

Jeg har koblet Ansatt og Sak sammen i FjordTek-modellen.

AnsattID er primærnøkkel (PK) i Ansatt og fremmednøkkel (FK) i Sak.

Relasjonen er 1:M. Det betyr at én ansatt kan arbeide med mange supportsaker, men hver supportsak er tildelt én ansatt.

## Steg 3 – Samlet modell

Jeg har laget en samlet ER-modell for FjordTek i dbdiagram.io.

Modellen består av tre hovedtabeller: Kunde, Ansatt og Sak.

Alle tre tabellene har en primærnøkkel (PK).

Sak har to fremmednøkler (FK): KundeID og AnsattID.

Det er to 1:M-relasjoner i modellen:

Én kunde kan ha mange saker.

Én ansatt kan arbeide med mange saker.

Hver sak tilhører én kunde og er tildelt én ansatt.


## Steg 4: Test modellen med eksempeldata

FjordTek – ER-modell

Jeg har testet FjordTek-modellen med eksempeldata for å kontrollere at relasjonene fungerer riktig.

Kan én kunde ha flere saker?

Ja, én kunde kan ha flere saker. For eksempel har Kunde 17 både Sak 103 og Sak 108.

Kan én ansatt ha flere saker?

Ja, én ansatt kan arbeide med flere saker. For eksempel arbeider Ansatt 4 med Sak 103 og Sak 112.

Kan du finne hvilken kunde sak 103 tilhører?

Ja, Sak 103 tilhører Kunde 17, fordi KundeID er 17.

Kan du finne hvilken ansatt som arbeider med sak 103?

Ja, Ansatt 4 arbeider med Sak 103, fordi AnsattID er 4.

Hvorfor gjør vi dette?

Jeg bruker eksempeldata for å kontrollere at relasjonene fungerer riktig før vi bygger databasen. Dette hjelper oss å finne feil og unngå å 

lagre samme informasjon flere ganger.

Konklusjon

FjordTek-modellen har to 1:M-relasjoner.

Én kunde kan ha mange saker, og én ansatt kan arbeide med mange saker.

KundeID og AnsattID er fremmednøkler (FK) i Sak. Disse brukes til å koble tabellene sammen.


## Steg 5: Les relasjonene som setninger

I denne oppgaven har jeg jobbet med ER-modellen for FjordTek. Målet er å forstå hvordan tabellene Kunde, Sak og Ansatt er koblet sammen.

Jeg har laget relasjonene i dbdiagram.io. Nå skal jeg forklare hva relasjonene betyr med vanlige setninger.

Relasjonen mellom Kunde og Sak

Én kunde kan ha mange saker, men hver sak tilhører bare én kunde.

Dette er en 1:M-relasjon (én-til-mange).

I tabellen Kunde er KundeID en primærnøkkel (PK). I tabellen Sak er KundeID en fremmednøkkel (FK).

Fremmednøkkelen gjør at vi kan finne ut hvilken kunde en bestemt sak tilhører.

For eksempel kan Kunde 17 ha både Sak 103 og Sak 108.

Relasjonen mellom Ansatt og Sak

Én ansatt kan arbeide med mange saker, men hver sak er tildelt én ansatt.

Dette er også en 1:M-relasjon.

I tabellen Ansatt er AnsattID en primærnøkkel (PK). I tabellen Sak er AnsattID en fremmednøkkel (FK).

Denne fremmednøkkelen brukes for å finne ut hvilken ansatt som har ansvar for en sak.

For eksempel kan Ansatt 4 arbeide med både Sak 103 og Sak 112.

Hvorfor bruker vi fremmednøkler?

Vi bruker fremmednøkler for å koble tabeller sammen uten å lagre den samme informasjonen flere ganger.

For eksempel trenger vi ikke å skrive kundens navn og e-post i hver sak. Vi bruker KundeID for å finne informasjonen i tabellen Kunde.

Dette gjør databasen enklere å organisere og oppdatere.

Kontroll av ER-modellen

Jeg har kontrollert at modellen har to riktige relasjoner:

Kunde (1) → Sak (M)

Ansatt (1) → Sak (M)

Jeg har også kontrollert at Sak inneholder fremmednøklene KundeID og AnsattID.

Begge relasjonene viser at én rad i en tabell kan være koblet til mange rader i en annen tabell.

Konklusjon

Jeg har lært hvordan jeg kan lese og forklare relasjoner i en ER-modell.

Jeg forstår at én kunde kan ha mange saker, og at én ansatt kan arbeide med mange saker.

Jeg har også lært at fremmednøkler brukes for å koble tabellene sammen.

FjordTek-modellen viser to 1:M-relasjoner mellom Kunde, Ansatt og Sak.


## Stage 6. Finn riktig sted for fremmednøkkelen


<img width="949" height="436" alt="image" src="https://github.com/user-attachments/assets/11b678b4-938d-44b1-8fb6-a1d74cebd523" />



Jeg har laget en ER-modell med tabellene Kategori og Produkt i dbdiagram.io, ved siden av FjordTek-modellen.

Én kategori kan ha mange produkter, men hvert produkt tilhører én kategori. Dette er en 1:M-relasjon.

KategoriID er primærnøkkel (PK) i Kategori og fremmednøkkel (FK) i Produkt.

Fremmednøkkelen ligger i Produkt fordi hvert produkt må være koblet til riktig kategori.

Jeg har lært at fremmednøkkelen skal plasseres på mange-siden (M) i en 1:M-relasjon.

## Onsdagens grunnoppgave – FjordTek

1. Hva er forskjellen mellom PK og FK?

En primærnøkkel (PK) identifiserer hver rad i en tabell. En fremmednøkkel (FK) brukes til å koble en tabell til en annen tabell.

2. Hvorfor ligger KundeID i Sak?

KundeID ligger i Sak fordi hver sak tilhører én kunde. KundeID brukes som fremmednøkkel (FK) for å koble saken til riktig kunde.

3. Hvorfor ligger AnsattID i Sak?

AnsattID ligger i Sak fordi hver sak er tildelt én ansatt. AnsattID brukes som fremmednøkkel (FK) for å vise hvilken ansatt som har ansvar for saken.

4. Hvilke to tabeller peker Sak til?

Sak peker til tabellene Kunde og Ansatt gjennom fremmednøklene KundeID og AnsattID.

Konklusjon

Jeg har laget en ER-modell for FjordTek med to 1:M-relasjoner.

Én kunde kan ha mange saker, og én ansatt kan arbeide med mange saker.

Jeg har også testet modellen med eksempeldata og laget en egen ER-modell for Kategori og Produkt.

Jeg har lært forskjellen mellom primærnøkkel (PK) og fremmednøkkel (FK), og hvordan fremmednøkler kobler tabeller sammen.


## Torsdag – GDPR og ansvarlig databasedesign

##  Steg 1 – Personopplysninger

I denne oppgaven har jeg sett på hvilke personopplysninger som finnes i FjordTek-modellen.

Personopplysninger er informasjon som kan brukes til å finne ut hvem en person er.

Personopplysninger i FjordTek

I tabellen Kunde har jeg disse feltene:

KundeID: Et nummer som viser hvilken kunde det er.

Navn: Navnet til kunden.

Epost: E-postadressen til kunden.

Telefon: Telefonnummeret til kunden.

Disse opplysningene kan brukes til å finne eller kontakte en bestemt person.

KundeID kan også være en personopplysning fordi nummeret kan kobles til en kunde.

Hva er GDPR?

GDPR er regler som beskytter personopplysninger.

Reglene sier hvordan vi skal samle inn, bruke, beskytte og slette informasjon om personer.

Hvorfor er GDPR viktig?

GDPR er viktig fordi vi må ta vare på private opplysninger.

Vi skal bare samle inn informasjon vi trenger, og vi må passe på at uvedkommende ikke får tilgang til den.

Konklusjon

Jeg har lært hva personopplysninger er, og hvorfor GDPR er viktig.

Jeg har også lært at informasjon som Navn, Epost, Telefon og KundeID må behandles på en trygg måte.

## Steg 2 – Dataminimering
Hva er dataminimering?

Dataminimering betyr at vi bare samler inn personopplysninger som vi trenger.

I FjordTek bruker vi et system for å hjelpe kunder med supportsaker.

Hvilke opplysninger trenger vi?

Vi kan trenge:

Navn: For å vite hvem kunden er.

Epost: For å kontakte kunden.

KundeID: For å koble kunden til riktig sak.

Hvilke opplysninger trenger vi ikke?

Vi trenger normalt ikke:

Fødselsdato: Kundens fødselsdato.

Personnummer: Kundens personnummer.

Privat adresse: Kundens hjemmeadresse.

Vi skal ikke samle inn disse opplysningene hvis de ikke er nødvendige.

Hvorfor er dataminimering viktig?

Dataminimering er viktig fordi vi skal beskytte kundenes personopplysninger.

Jo mindre unødvendig informasjon vi lagrer, desto mindre informasjon kan komme på avveie.

Konklusjon

Jeg har lært at vi bare skal samle inn personopplysninger som vi trenger.

I FjordTek skal vi unngå å lagre unødvendige opplysninger om kundene.


## Steg 3 – Relasjoner og personvern

Hva betyr relasjoner og personvern?

I FjordTek-modellen har jeg tabellene Kunde og Sak.

Disse tabellene er koblet sammen med KundeID.

Hvordan fungerer koblingen?

I tabellen Sak finnes KundeID som fremmednøkkel (FK).

KundeID peker til tabellen Kunde, der KundeID er primærnøkkel (PK).

Gjennom denne koblingen kan vi finne kundens navn og e-postadresse.

For eksempel kan vi bruke KundeID i en sak for å finne ut hvilken kunde saken tilhører.

Hvorfor er dette viktig for personvern?

En tabell kan se ut som om den ikke inneholder personopplysninger.

Men når vi kobler den til en annen tabell, kan vi finne informasjon om en bestemt person.

Derfor må vi beskytte personopplysninger i hele databasen.

Konklusjon

Jeg har lært at relasjoner kan gjøre informasjon personidentifiserbar.

Vi må derfor kontrollere hele ER-modellen, ikke bare én tabell.



## Steg 4 – Formål og tilgang

Hva betyr formål?

Formål betyr hvorfor vi samler inn personopplysninger.

I FjordTek skal vi bare samle inn informasjon som vi trenger for å hjelpe kundene.

Hvilke opplysninger trenger vi?

Navn: Vi trenger navn for å vite hvilken kunde saken gjelder.

Epost: Vi kan trenge e-post for å kontakte kunden.

Telefon: Vi må vurdere om vi trenger telefonnummer, eller om e-post er nok.

Fødselsdato: Vi trenger vanligvis ikke fødselsdato for å løse en supportsak.

Personnummer: Vi trenger normalt ikke personnummer i et vanlig kundestøttesystem.

Hva er tilgangsstyring?

Tilgangsstyring betyr at vi bestemmer hvem som kan lese eller endre informasjon i databasen.

Ansatte skal bare ha tilgang til opplysninger de trenger for å gjøre jobben sin.

Dette kalles minste privilegium.

Hvorfor er dette viktig?

Det er viktig for å beskytte kundenes personopplysninger og hindre at uvedkommende får tilgang til privat informasjon.

Konklusjon

Jeg har lært at vi må ha en god grunn til å samle inn personopplysninger.

Jeg har også lært at ansatte bare skal ha tilgang til informasjon de trenger for arbeidsoppgavene sine.




## Steg 5 – Personvernkontroll

<img width="741" height="238" alt="image" src="https://github.com/user-attachments/assets/ef7c12a8-1a68-4622-921b-e93653998297" />

I denne oppgaven har jeg kontrollert personopplysninger i FjordTek-modellen.

Jeg har markert tre personopplysninger i ER-diagrammet i dbdiagram.io:

Navn

Epost

Telefon

Jeg skal forklare hvorfor vi trenger disse opplysningene, hvem som kan se dem, om de kan fjernes, og hva som kan skje hvis informasjonen kommer på avveie.

1. Navn

Hvorfor trenger systemet opplysningen?

Systemet trenger navn for å vite hvilken kunde saken gjelder.

Hvem bør kunne se den?

Ansatte som jobber med kundestøtte og trenger kundens navn.

Kan feltet fjernes?

Ja, hvis KundeID er nok til å finne riktig kunde. Men navn kan være nyttig når vi hjelper kunden.

Hva kan skje dersom opplysningen kommer på avveie?

Andre personer kan få vite hvem kunden er. Dette kan være et problem for personvernet.

2. Epost

Hvorfor trenger systemet opplysningen?

Vi trenger e-post for å kunne kontakte kunden og svare på supportsaker.

Hvem bør kunne se den?

Ansatte som trenger å kontakte kunden.

Kan feltet fjernes?

Ja, hvis vi har en annen trygg måte å kontakte kunden på. Men e-post er nyttig i kundestøtte.

Hva kan skje dersom opplysningen kommer på avveie?

Kunden kan få spam eller falske e-poster. Andre kan også prøve å lure kunden.

3. Telefon
Hvorfor trenger systemet opplysningen?

Telefonnummer kan brukes hvis vi må ringe kunden om en supportsak.

Hvem bør kunne se den?

Bare ansatte som trenger å ringe kunden.

Kan feltet fjernes?

Ja, hvis e-post er nok til å hjelpe kunden, trenger vi kanskje ikke telefonnummer.

Hva kan skje dersom opplysningen kommer på avveie?

Kunden kan få uønskede telefoner eller falske meldinger.

4. Hvorfor er personvernkontroll viktig?

Personvernkontroll er viktig fordi vi må beskytte kundenes private informasjon.

Vi skal bare samle inn opplysninger vi trenger. Ansatte skal bare ha tilgang til informasjon som er nødvendig for jobben deres.

Dette følger prinsippene om dataminimering og minste privilegium.

Konklusjon

Jeg har markert Navn, Epost og Telefon som personopplysninger i FjordTek-diagrammet.

Jeg har lært hvorfor vi trenger opplysningene, hvem som bør kunne se dem, og hvilke problemer som kan oppstå hvis informasjonen kommer på avveie.

Jeg har også lært at vi ikke skal lagre mer informasjon enn nødvendig, og at vi må beskytte kundenes personopplysninger.

Database Diagram Tool - Free ER Diagram Design

Draw database relationship diagrams in seconds by writing simple DBML code. Free, fast, and built for developers and data analysts.


 

## Steg 6: Hvor lenge skal data beholdes?

I denne oppgaven har jeg lært hvor lenge vi bør lagre personopplysninger i FjordTek.

Vi skal ikke lagre personopplysninger lenger enn nødvendig.

1. Bør en avsluttet supportsak ligge i databasen for alltid?

Nei, en avsluttet supportsak bør normalt ikke lagres for alltid.

Vi kan beholde saken en stund hvis vi trenger informasjonen senere.

Når vi ikke trenger informasjonen lenger, bør vi slette den eller fjerne personopplysninger.

2. Bør en kunde som ikke lenger bruker tjenesten fortsatt ha alle personopplysninger lagret uten noen vurdering?

Nei, vi bør kontrollere hvilke opplysninger vi fortsatt trenger.

Hvis kunden ikke bruker tjenesten lenger, bør vi vurdere å slette unødvendige personopplysninger.

Noen opplysninger må kanskje beholdes en periode på grunn av regler eller andre nødvendige formål.

3. Hvorfor er dette viktig?

Dette er viktig fordi vi må beskytte kundenes personopplysninger.

Vi bør ha gode rutiner for å kontrollere og slette informasjon vi ikke trenger.

Databasen bør også være laget slik at det er mulig å rydde opp i gamle data.

Konklusjon

Jeg har lært at personopplysninger ikke skal lagres lenger enn nødvendig.

I FjordTek bør vi ha rutiner for sletting og opprydding av gamle supportsaker og kundeopplysninger.



## Torsdagens grunnoppgave – GDPR og ansvarlig databasedesign

Prosjekt: FjordTek

I denne oppgaven har jeg jobbet med personvern i FjordTek-modellen.


<img width="741" height="238" alt="image" src="https://github.com/user-attachments/assets/e7dac586-4536-4cd1-a8d0-bb864926c961" />


Jeg har brukt ER-diagrammet fra onsdag og markert tre personopplysninger i tabellen Kunde:

Navn

Epost

Telefon

Jeg har også vurdert hvilke opplysninger vi trenger, og hvem som bør ha tilgang til dem.

2. Personvernvurdering

Et felt som bør beholdes:

KundeID bør beholdes fordi det brukes til å koble kunden til riktig supportsak.

Et felt som kan være unødvendig:

Telefon kan være unødvendig hvis vi kan kontakte kunden med e-post.

Hvem bør ha tilgang?

Bare ansatte som trenger opplysningene for å gjøre jobben sin, bør ha tilgang. Andre skal ikke kunne se eller endre informasjonen.

3. Spørsmål og svar

1. Hva betyr dataminimering?

Dataminimering betyr at vi bare samler inn personopplysninger som vi trenger.

2. Hvorfor kan KundeID være en personopplysning?

KundeID kan være en personopplysning fordi det kan kobles til en bestemt kunde.

3. Hvorfor må vi se på relasjonene når vi vurderer personvern?

Fordi relasjonene kobler tabellene sammen. Vi kan for eksempel bruke KundeID i Sak for å finne kundens navn og e-post.

4. Hvorfor bør tilgang til databasen begrenses?

For å beskytte personopplysninger. Bare ansatte som trenger informasjonen for jobben sin, bør ha tilgang.

5. Hva betyr det at personopplysninger ikke bør lagres lenger enn nødvendig?

Det betyr at vi skal slette eller rydde opp i personopplysninger når vi ikke trenger dem lenger, så lenge ingen regler krever at de beholdes.

6. Hvorfor bør vi vurdere formålet før vi legger til et nytt felt i databasen?

Fordi vi må vite hvorfor vi trenger informasjonen. Vi bør ikke samle inn unødvendige personopplysninger.

4. Konklusjon

Jeg har lært at GDPR handler om å beskytte personopplysninger.

Jeg har også lært at vi bare skal samle inn informasjon vi trenger, begrense hvem som har tilgang, og ikke lagre personopplysninger lenger enn 
nødvendig.

ER-modellen må være laget slik at vi kan beskytte og slette personopplysninger på en trygg måte.


## Videre utforskning – Torsdag

Forskjellen mellom vanlige personopplysninger og særlige kategorier

Vanlige personopplysninger er informasjon som kan brukes til å kjenne igjen en person.

Eksempler er navn, e-postadresse og telefonnummer.

Særlige kategorier av personopplysninger er informasjon som trenger ekstra beskyttelse.

Eksempler er helseopplysninger, religion og politiske meninger.

Et eksempel på informasjon jeg ville vært ekstra forsiktig med å lagre

Jeg ville vært ekstra forsiktig med å lagre helseopplysninger.

Dette er privat informasjon som kan være skadelig for personen hvis andre får tilgang til den.

I FjordTek trenger vi vanligvis ikke helseopplysninger for å hjelpe kunder med supportsaker.

Konklusjon

Jeg har lært forskjellen mellom vanlige personopplysninger og særlige kategorier av personopplysninger.

Vi bør bare lagre informasjon som er nødvendig, og beskytte sensitive opplysninger ekstra godt.

## Fredag – oppsummering, Jobbklar

# Fredag – Oppsummeringsoppgave

## ER-modell: Avdeling og Ansatt

<img width="957" height="416" alt="image" src="https://github.com/user-attachments/assets/4e3df5b1-4e4d-4056-bba1-98cfe1c423f0" />


I denne oppgaven har jeg jobbet med en ER-modell i dbdiagram.io.

Jeg har brukt to tabeller: Avdeling og Ansatt.

Målet er å vise hvordan tabellene er koblet sammen med en 1:M-relasjon.

### 2. Tabellen Avdeling

Tabellen Avdeling inneholder:

- **AvdelingID:** integer (PK)
- **Navn:** varchar

AvdelingID er primærnøkkel (PK). Den brukes til å identifisere hver avdeling.

### 3. Tabellen Ansatt

Tabellen Ansatt inneholder:

- **AnsattID:** integer (PK)
- **Navn:** varchar
- **Epost:** varchar
- **AvdelingID:** integer (FK)

AnsattID er primærnøkkel (PK).

AvdelingID er fremmednøkkel (FK) og kobler Ansatt til Avdeling.

### 4. Relasjonen mellom Avdeling og Ansatt

Én avdeling kan ha mange ansatte, men hver ansatt tilhører én avdeling.

Dette er en **1:M-relasjon (én-til-mange)**.

AvdelingID ligger i Ansatt fordi vi må vite hvilken avdeling den ansatte tilhører.

### 5. Arbeid i dbdiagram.io

Jeg har laget og kontrollert ER-diagrammet i dbdiagram.io.

Jeg har markert primærnøklene og fremmednøkkelen.

Diagrammet viser en linje mellom Avdeling og Ansatt med 1 på Avdeling-siden og M på Ansatt-siden.

### 6. Konklusjon

Jeg har lært hvordan jeg kan lage en ER-modell med to tabeller.

Jeg forstår forskjellen mellom PK og FK.

Jeg har også lært at én avdeling kan ha mange ansatte, men hver ansatt tilhører én avdeling.


# Fredag – Oppsummering og Jobbklar

## 1. Forklar kjeden

**Behov → Tabell → PK → Relasjon → FK → ER-modell → Personvern**

### Behov
Først må vi forstå hva systemet skal brukes til, og hvilken informasjon vi trenger.

### Tabell

Vi lager tabeller for å lagre informasjon. For eksempel Avdeling og Ansatt.

### PK – Primærnøkkel

En primærnøkkel gir hver rad i en tabell en unik ID.

For eksempel er AnsattID primærnøkkel i Ansatt.

### Relasjon

En relasjon viser hvordan to tabeller henger sammen.

For eksempel kan én avdeling ha mange ansatte.

### FK – Fremmednøkkel
En fremmednøkkel brukes til å koble sammen tabeller.

AvdelingID er fremmednøkkel i Ansatt.

### ER-modell
En ER-modell viser tabeller, felter og relasjoner.

Jeg har brukt dbdiagram.io for å lage ER-modeller.

### Personvern

Personvern betyr at vi må beskytte personopplysninger.

Vi skal bare samle inn informasjon vi trenger, og passe på hvem som får tilgang til den.

## 2. Jobbklar – Mine ferdigheter

Dette er fem ferdigheter jeg har lært, og som jeg kan beskrive til en arbeidsgiver.

1. Jeg kan gjøre en enkel kravbeskrivelse om til tabeller og felter.

2. Jeg kan markere primærnøkler (PK) og fremmednøkler (FK).

3. Jeg kan tegne og forklare en 1:M-relasjon.

4. Jeg kan lese et enkelt ER-diagram og forklare hvordan tabellene henger sammen.

5. Jeg kan vurdere hvilke personopplysninger en datamodell inneholder.

## 3. Konklusjon

Denne uken har jeg lært å lage enkle ER-modeller i dbdiagram.io.

Jeg har lært hvordan tabeller kobles sammen med primærnøkler og fremmednøkler.

Jeg har også lært hvorfor personvern og GDPR er viktig når vi lager databaser.

Jeg kan bruke denne kunnskapen i videre arbeid med databaser og utviklingsprosjekter.








