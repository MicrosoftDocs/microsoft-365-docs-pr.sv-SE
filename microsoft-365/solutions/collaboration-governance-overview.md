---
title: Översikt över samarbete i Microsoft 365
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Lär dig mer om hur du styr relaterade funktioner i Microsoft 365 Groups, teams, SharePoint och Yammer.
ms.openlocfilehash: 8784f14530ec94a3151ef58589944947b5de9514
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377587"
---
# <a name="overview-of-collaboration-governance-in-microsoft-365"></a>Översikt över samarbete i Microsoft 365

Microsoft 365 har en mängd olika verktyg för att implementera styr funktioner som din organisation kan behöva. I den här artikeln får IT-tekniker instruktioner för att ställa rätt frågor för att fastställa deras krav för styrning och hur de ska mötas baserat på deras organisations profil.

## <a name="what-are-microsoft-365-groups"></a>Vad är Microsoft 365-grupper?

Vi vet att organisationer idag använder olika verktygs uppsättningar. Det finns en grupp med utvecklare som använder gruppchatt, chefer som skickar e-post och hela organisationen som ansluter via företags social. Flera samarbets verktyg används eftersom alla grupper är unika och har sina egna funktioner och arbets format. Vissa kommer bara att använda e-post medan andra bor i chatten. 

Om användarna tycker att de verktyg som tillhandahålls inte passar deras behov kommer de sannolikt att ladda ner sin favorit-Consumer-app som stöder deras scenarier. Även om den här processen gör det möjligt för användare att komma igång snabbt, leder den till en frustrerande användar upplevelse i hela organisationen med flera inloggningar, svårt att dela och ingen plats för att visa innehåll. Det här begreppet kallas "skuggat" och innebär en betydande risk för organisationer. Det reducerar förmågan att enhetligt hantera användar åtkomst, kontrol lera säkerheten och behovet av tjänst.

Tjänster som Microsoft 365 Groups, teams och Yammer gör det möjligt för användarna att minska risken för att skugga den genom att tillhandahålla de verktyg som behövs för att samar beta. Med Microsoft 365-grupper kan du välja en uppsättning personer som du vill samar beta med och enkelt skapa en samling resurser för de personer som ska dela. Om du lägger till medlemmar i gruppen beviljar du automatiskt de behörigheter som krävs för alla till gångar som tillhandahålls av gruppen. Både team och Yammer använder Microsoft 365 Groups för att hantera deras medlemskap.

![Diagram som visar Microsoft 365-grupper och tillhör ande tjänster](../media/microsoft-365-groups-hub-spoke.png)

Microsoft 365-grupper innehåller flera olika styrnings kontroller, inklusive en policy för utgångs datum, namn regler och en blockerad ord policy som hjälper dig att hantera grupper i din organisation. Mer information finns i [Planera organisation och livscykel organisationer för microsoft 365-grupper och Microsoft Teams](plan-organization-lifecycle-governance.md) .

## <a name="technical-architecture"></a>Teknisk arkitektur

Det finns tre huvudsakliga kommunikations metoder i Microsoft 365:

- Outlook: samarbete via e-post med en delad gruppinkorg och kalender
- Microsoft Teams: en beständig chatt-baserad arbets yta där du kan ha informella samtal i real tid med olika ämnen, ordnade efter specifika under grupper
- Yammer: social erfarenhet för företag

> [!NOTE]
> Om du skapar en ny grupp via andra program, till exempel SharePoint, Planner eller Stream, skapas en grupp med en Outlook-inkorg och möjligheten att ansluta till Teams.

Beroende på var en grupp skapas tillhandahålls vissa resurser automatiskt, till exempel:
- [Inkorg](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) – för e-postkonversationer mellan grupp medlemmar. Denna inkorg har en e-postadress och kan anges för att acceptera meddelanden från personer utanför gruppen, till och med utanför organisationen, ungefär som en traditionell distributions lista.
 - [Kalender](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) – för att schemalägga händelser relaterade till gruppen
- [SharePoint-gruppwebbplats](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) – en central lagrings plats för information, länkar och innehåll relaterade till din grupp
- [OneNote-anteckningsbok](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) – för att samla idéer, forskning och information
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – för att tilldela och hantera projektuppgifter bland grupp medlemmarna
- [Yammer-grupp](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) – en gemensam plats för konversationer och informations delning
- Teams – en chatt-baserad arbets yta i Microsoft 365
- Stream-en video strömnings tjänst

> [!NOTE]
> När en ny Office 365-grupp skapas via Yammer eller teams visas den inte i Outlook eller adress boken eftersom den primära kommunikationen mellan dessa användare sker i sina respektive klienter. Yammer-grupper kan inte anslutas till team.

## <a name="collaboration-options"></a>Samarbets alternativ

Det finns flera ställen att samar beta och ha konversationer i Microsoft 365. Om du förstår var du ska starta en konversation kan du skapa en strategi för kommunikation.

![Diagram som visar när du ska använda Teams, Yammer och Outlook](../media/inner-loop-outer-loop.png)

- Teams: chatt-baserad arbets yta (höghastighets samarbete) – inre loop
  - Byggd för samarbete med de personer som du arbetar med varje dag
  - Placerar information lättillgängligt för användarna i en enda upplevelse
  - Lägga till flikar, kopplingar och robotar
  - Live chatt, ljud-och video konferens, registrerade möten

- Yammer: ansluta i organisationsschemat (företags social) – yttre loop
  - Communitys med övning – kors funktionella grupper av personer som delar ett gemensamt intresse eller kunnande, men som inte nödvändigt vis arbetar tillsammans i dag-till-dags basis
  - Ledarskaps förbindelse, utbildnings grupper, rollbaserade samhällen

- Post låda och kalender (e-postbaserad samarbete)
  - Använda för riktad kommunikation med en grupp personer
  - Delad kalender för möten med andra grupp medlemmar
 
Alla grupper har en ansluten SharePoint-gruppwebbplats där användare kan dela innehåll, skapa anpassade sidor och redigera nyheter. Du kan också [ansluta befintliga SharePoint-gruppwebbplatser till nya Microsoft 365-grupper](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview).

## <a name="illustrations"></a>Illustrationer

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams och relaterade produktivitetstjänster i Microsoft 365 för IT-arkitekter
Den logiska arkitekturen för produktivitetstjänster i Microsoft 365, med Microsoft Teams i spetsen.

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|[![Miniatyrbild av affischen för Teams logiska arkitektur](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Uppdaterad i april 2019   |Microsoft erbjuder ett utbud av produktivitetstjänster som samverkar för att tillhandahålla samarbetsupplevelser med funktioner för datastyrning, säkerhet och efterlevnad. <br/> <br/>Den här serien med illustrationer ger en översikt över produktivitetstjänsternas logiska arkitektur för företagsarkitekter, med Microsoft Teams i spetsen.|


### <a name="groups-in-microsoft-365-for-it-architects"></a>Grupper i Microsoft 365 för IT-arkitekter
Det IT-arkitekter behöver veta om grupper i Microsoft 365

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|[![Miniatyrbild av infografiken för grupper](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Uppdaterad i juni 2019|De här illustrationerna beskriver de olika typerna av grupper, hur de skapas och hanteras samt några rekommendationer för styrning.|

## <a name="conference-sessions"></a>Konferens-sessioner

Se dessa konferens samtal för att lära dig mer om styrning för Microsoft 365-grupper och-team.

**Programmering**

Lär dig grunderna och nya innovationer i Microsoft 365-grupper, inklusive ledning och styrelse trafik, metod tips för att driva användning och antagande samt själv service.

- [Ta med Microsoft 365-grupper](https://www.youtube.com/watch?v=dAamBF1gb7M)

**Styrning**

Lär dig hur du konfigurerar gruppernas livs cykel, namngivnings principer, klassificerings etiketter, samarbete med externa gäster och hanterar behörighet för att skapa grupper.

- [Omvandla samarbete och bekämpa skuggat med Office 365-grupper](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**Kund exempel**

Se ett exempel på hur Microsoft 365 Groups, SharePoint, teams och Yammer samarbetar för att tillhandahålla en global samarbets plattform.

- [Hitta ditt samarbete på en plats med Office 365-grupper, SharePoint, teams och Yammer](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
