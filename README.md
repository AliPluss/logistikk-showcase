<div align="center">

# LOGISTIKK
### Fra lageroversikt til plukkliste

Lager- og logistikksystem for en ekte oppdragsgiver, med backend, database og egen server satt opp fra bunnen av.

![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logoColor=white)
![ASP.NET Core](https://img.shields.io/badge/ASP.NET_Core-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-111827?style=for-the-badge&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

![Proxmox](https://img.shields.io/badge/Proxmox-E57000?style=for-the-badge&logo=proxmox&logoColor=white)
![Rocky Linux](https://img.shields.io/badge/Rocky_Linux-10B981?style=for-the-badge&logo=rockylinux&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Tailscale](https://img.shields.io/badge/Tailscale-242424?style=for-the-badge&logo=tailscale&logoColor=white)

[Skjermbilder](#skjermbilder) · [Serveroppsett](#serveroppsett-og-drift) · [Last ned demo](assets/Logistikk-demo.mp4) · [LinkedIn](https://www.linkedin.com/in/ali-badr-a-a-almrabhi-5676b9448/)

</div>

![Logistikk – oversikt med oppgaver, ordrer og lagervarsler](assets/01-oversikt.png)

> [!NOTE]
> Bildene viser prosjektets faktiske Next.js-grensesnitt med syntetiske data fra et simulert API. Videoen er en 30 sekunders presentasjon av skjermbildene, uten lyd. Materialet dokumenterer grensesnittet, ikke en full ende-til-ende-test av backend.

## Hva er Logistikk?

Logistikk er et skoleprosjekt på Vg2 IT-utvikling ved Åssiden videregående skole, utviklet for en **ekte oppdragsgiver**: en butikk der elever jobber, som i dag holder oversikt over varer i Excel og ønsker en bedre løsning.

Målet er en forståelig arbeidsflyt: finne en vare, se lagerstatus, følge en ordre og registrere plukkede varer.

## Mitt bidrag

Jeg har hovedansvar for **backend og server**, og har også arbeidet med webgrensesnittet.

| Område | Hva jeg har gjort |
| --- | --- |
| 🖥️ **Server og drift** | Satte opp serveren fra bunnen av: Proxmox, Rocky Linux, Docker, Nginx, Seq og Tailscale |
| ⚙️ **Backend** | API i C# og ASP.NET Core (.NET 10), innlogging med JWT og rollebasert tilgang |
| 🗄️ **Database** | PostgreSQL, datamodeller og migreringer |
| 🌐 **Web** | Next.js-grensesnitt for produkter, ordrer og plukklister |
| 📄 **Samarbeid** | Dokumentasjon og tilkoblingsveiledning for resten av prosjektgruppen |

Prosjektet er et gruppearbeid. Denne presentasjonen beskriver mitt bidrag og utvalgte deler av løsningen.

## Serveroppsett og drift

Hele miljøet kjører på en server jeg har installert og konfigurert selv.

```mermaid
flowchart TB
    user["👤 Brukere<br/>lærer · elev · kunde"] -->|HTTPS| nginx
    admin["🔐 Utviklere og drift"] -.->|Tailscale| host

    subgraph host["Proxmox VE"]
        subgraph vm["Rocky Linux"]
            nginx["Nginx<br/>reverse proxy"]
            subgraph docker["Docker"]
                web["Next.js<br/>webgrensesnitt"]
                api["ASP.NET Core<br/>API · JWT"]
                seq["Seq<br/>logging"]
            end
            db[("PostgreSQL")]
        end
    end

    nginx --> web
    nginx --> api
    web -->|REST| api
    api --> db
    api -.->|logger| seq
```

| Komponent | Rolle |
| --- | --- |
| **Proxmox VE** | Virtualisering, kjører serveren som virtuell maskin |
| **Rocky Linux** | Operativsystem for serveren |
| **Docker** | Kjører tjenestene i containere |
| **Nginx** | Reverse proxy foran webgrensesnitt og API |
| **Seq** | Strukturert logging fra API-et, brukt til feilsøking |
| **Tailscale** | Sikker tilgang til serveren uten åpne porter |

## Funksjoner i grensesnittet

| Område | Hva visningen viser |
| --- | --- |
| 📊 Oversikt | Oppgaver, nyeste ordrer og varer med lav beholdning |
| 📦 Produkter | Søk, kategorier, pris, hylleplass og tilgjengelig antall |
| 🧾 Ordrer | Filtrering etter status og oversikt over betaling |
| ✅ Plukklister | Varelinjer, registrering av antall og fremdrift |
| 🎨 Tilpasning | Bokmål, nynorsk og engelsk; lyst, mørkt og blått tema |

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
| API | C# og ASP.NET Core (.NET 10) |
| Tilgang | JWT og roller for lærer, elev og kunde |
| Datalagring | PostgreSQL |
| Drift | Proxmox, Rocky Linux, Docker, Nginx, Seq og Tailscale |

Webgrensesnittet kommuniserer med API-et, som håndterer tilgang, forretningsregler og lagring. Kildekoden ligger i separate, private repositorier.

## Hva jeg lærer

Å sette opp både applikasjonen og serveren den kjører på har gitt meg praktisk erfaring med hele kjeden, fra database og API til nettverk, logging og feilsøking i drift. Jeg arbeider videre med testing, tydelige feilmeldinger og dokumentasjon, og er særlig interessert i forbindelsen mellom backend og drift.

## Om dette repositoriet

Dette er et **presentasjonsrepo**. Det inneholder utvalgte skjermbilder og en kort video, men ingen privat kildekode, virkelige kundedata eller serverhemmeligheter. Det er ikke en installerbar versjon av applikasjonen.

**Status:** 🚧 Under utvikling · Skoleprosjekt · Demonstrasjon med syntetiske data

---

<div align="center">

**Ali Badr Almrabhi** · Vg2 IT-utvikling · Åssiden videregående skole

Søker læreplass innen IT-utvikling eller IT-drift

[GitHub](https://github.com/AliPluss) · [LinkedIn](https://www.linkedin.com/in/ali-badr-a-a-almrabhi-5676b9448/)

</div>
