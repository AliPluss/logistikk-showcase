<div align="center">

# LOGISTIKK
### Fra lageroversikt til plukkliste

Et skoleprosjekt med fokus på backend, datalagring og en tydelig arbeidsflyt.

![ASP.NET Core](https://img.shields.io/badge/ASP.NET_Core-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-111827?style=for-the-badge&logo=nextdotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

[Se skjermbilder](#skjermbilder) · [Last ned demo](assets/Logistikk-demo.mp4) · [Om utvikleren](https://github.com/AliPluss)

</div>

![Logistikk – oversikt med oppgaver, ordrer og lagervarsler](assets/01-oversikt.png)

> **Om demonstrasjonen:** Bildene viser prosjektets faktiske Next.js-grensesnitt med syntetiske data fra et simulert API. Videoen er en 30 sekunders presentasjon av skjermbildene, uten lyd. Materialet dokumenterer grensesnittet, ikke en full ende-til-ende-test av backend.

## Hva er Logistikk?

Logistikk er et skoleprosjekt på Vg2 IT-utvikling ved Åssiden videregående skole. Prosjektet tar utgangspunkt i behovet for å holde oversikt over varer, ordrer og plukking på lager.

Målet er en forståelig arbeidsflyt: finne en vare, se lagerstatus, følge en ordre og registrere plukkede varer.

## Mitt bidrag

Jeg har hovedansvar for backend og har også arbeidet med webgrensesnittet og det tekniske miljøet rundt løsningen.

- **Backend:** API med ASP.NET Core, innlogging med JWT og rollebasert tilgang.
- **Database:** Arbeid med PostgreSQL, datamodeller og migreringer.
- **Web:** Next.js-grensesnitt for produkter, ordrer og plukklister.
- **Samarbeid:** Dokumentasjon og tilkoblingsveiledning for andre i prosjektgruppen.
- **Drift og læring:** Arbeid med Linux, serveroppsett og tilkobling mellom tjenester.

Prosjektet er et gruppearbeid. Denne presentasjonen beskriver mitt bidrag og utvalgte deler av løsningen.

## Funksjoner i grensesnittet

| Område | Hva visningen viser |
| --- | --- |
| Oversikt | Oppgaver, nyeste ordrer og varer med lav beholdning |
| Produkter | Søk, kategorier, pris, hylleplass og tilgjengelig antall |
| Ordrer | Filtrering etter status og oversikt over betaling |
| Plukklister | Varelinjer, registrering av antall og fremdrift |
| Tilpasning | Bokmål, nynorsk og engelsk; lyst, mørkt og blått tema |

## Skjermbilder

### Produkter og lager

![Produktoversikt med kategorier og lagerbeholdning](assets/02-produkter.png)

### Ordreoversikt

![Ordrer med status og betalingsinformasjon](assets/03-ordrer.png)

### Plukking og fremdrift

![Plukkliste med varelinjer og fremdrift](assets/04-plukkliste.png)

<details>
<summary><strong>Se grensesnittet i mørkt tema</strong></summary>

![Oversikt i mørkt tema](assets/05-morkt-tema.png)

</details>

## Teknisk oppbygning

| Del | Teknologi og ansvar |
| --- | --- |
| Webgrensesnitt | Next.js, React og TypeScript |
| API | C# og ASP.NET Core |
| Tilgang | JWT og roller for lærer, elev og kunde |
| Datalagring | PostgreSQL |

Webgrensesnittet kommuniserer med API-et, som håndterer tilgang, forretningsregler og lagring. Kildekoden ligger i separate, private repositorier.

## Hva jeg lærer

Å knytte sammen innlogging, data og arbeidsflyt har gitt meg praktisk erfaring med både utvikling og feilsøking. Jeg arbeider videre med testing, tydelige feilmeldinger og dokumentasjon, og er særlig interessert i forbindelsen mellom backend og drift.

## Om dette repositoriet

Dette er et **presentasjonsrepo**. Det inneholder utvalgte skjermbilder og en kort video, men ingen privat kildekode, virkelige kundedata eller serverhemmeligheter. Det er ikke en installerbar versjon av applikasjonen.

**Status:** Under utvikling · Skoleprosjekt · Demonstrasjon med syntetiske data

---

**Ali Badr Almrabhi** · Vg2 IT-utvikling · [GitHub-profil](https://github.com/AliPluss)
