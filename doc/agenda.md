# Arena Skjema – Kurs for Helse Vest 22.april 2021

Tema

- Legge inn hjelpetekst i skjema
- Skjema med historikk
- Bruk av malvariabler
- Oppdatere skjema med ny OPT
- Pene tabeller
- Gjenbruk av openEHR data
- Bilder som logo i skjema
  -Bilder som støtte for kodeverkslister

## Legge inn hjelpetekster i skjema

De har svært mye tekst og får brytning av ord.

## Skjema med historikk

Se vedlagte skjema _esas_score_ for eksempel på hvordan dette kan løses.
Vi tar en diskusjon om denne type applikasjonsutvikling med tanke på hva som skal ligge til skjema og hva som skal ligge i øvrige komponenter i Arena.

## Malvariabler

Hvordan bruke de - som f.eks. fødselsdato

Eksempel på malvariabler:

- OmsE.STARTTID, f.eks. `2021.03.18`
- Pas.Fodselsdato, f.eks. `1985.08.10`
- Pas.alder, f.eks. `39`

Legg til annotasjon `templateVariable` og definer hvilken malvariabel som skal brukes i klammeparentes som f.eks. `[Pas.alder]`

## Oppdatere skjema med ny OPT

Hvordan oppdatere skjema med nye arketyper gjennom ny versjon av OPT.

I Form Designer kan man "flytte" et skjema til en helt annen template (OPT). **MERK** at dette gjøres på eget ansvar. Når operasjonen gjøres markeres det med gult og rødt. Gult betyr at elementet har endringer. Rødt betyr at det er ikke-kompatible endringer og feltet må fjernes og legges til på nytt.

## Pene tabeller

Hvordan lage pene tabeller?
Følgende muligheter:

- Annotasjon `ShowAsTable` som vist i skjema **TempShowAsTable**
- Annotasjon `MasterDetail` som vist i skjema **TempMasterDetail**
- Custom grid i Form Designer

## Gjenbruk av openEHR data

Først en advarsel: Annotasjonen `aql` er en tidlig utgave av gjenbruk og **skal** ikke brukes lenger. I FormDesigner står det at den støttes av alle versjoner av Arena. Det betyr rett og slett at den har vært siden de første versjoner av FormRenderer. DIPS har sett på dette og vil markere den som _deprecated_ i nyere versjoner av Form Designer.

Gjenbruk av openEHR data gjøres ved følgende rutine:

1. Legg inn spørringer (AQL) etter data som custom annotasjon.
2. Definer på elementet hvilken navngitt AQL som skal brukes med hhv. annotasjon `select` , `selectreadonly` eller `format`.

For å definere AQL er det to måter å gjøre det på:

- Legge inn arketype id
- Legge inn AQL

I tilegg kan det legges inn scope for spørringer. Følgende scope støttes:

- PeriodOfCare
- EpisodeOfCare
- Folder

## Bilder som logo

Hvordan sette inn bilder som en overodnet logo på et bilde?

Dette støttes ikke.

## Bilder for kodeverksverdier

Bilder forskyver seg. Dvs. områdene legges ikke inn der som de ligger.

Det er noen svakheter i Form Designer med tanke på å definere området for kodeverdier. I noen tilfeller hvor området kommer utenfor bildet kan feltet få en vilkårlig plassering.

I repo er det laget et skjema, `Temp_Med_Bilder`, som viser hvordan det kan fungere.
