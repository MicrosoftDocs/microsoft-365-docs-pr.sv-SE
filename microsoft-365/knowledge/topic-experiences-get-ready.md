---
title: Förbereda din miljö för Microsoft Viva-ämnen
description: Gör miljön klar så att du kan ge användarna så mycket innehåll som möjligt med Microsoft Viva Topics.
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 5a13af3e78848471b436d44ab051eca945176c74
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107702"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>Förbereda din miljö för Microsoft Viva-ämnen

För att få ut mesta möjliga av Viva-ämnen vill du ha så mycket innehåll som möjligt för att kunna identifiera ämnen, så att du kan ha en omfattande uppsättning ämnen för användarna. Men vilket innehåll ska användas för identifiering av ämnen? Hur maximerar du innehållet som indexeras samtidigt som du håller kontrollen? Ju mer innehåll som omfattas, desto bättre blir insikterna som artificiell intelligens kan upptäcka. I den här artikeln får du hjälp med att planera för att se till att du tar med rätt innehåll och att du har rätt personer och resurser för att göra en bra upplevelse för användarna.

För att planera för Viva Topics behöver du:

![Migrera, ansluta, modernisera, skydda och identifiera steg för onboarding till kunskapshantering](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrera innehåll till SharePoint](#1-migrate-content-to-microsoft-365)
    - Ämnesindexeringen omfattar endast innehåll på SharePoint-webbplatser.
      - Om möjligt bör du migrera värdefullt innehåll till SharePoint Online från externa källor.
      - Prioritera innehållskällor med hög potential för tacit-kunskap.
      - Framhäv fördelarna med hantering av kunskap för att uppmuntra användarna att flytta innehåll från OneDrive till SharePoint-webbplatser.

2. [Koppla information till Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - I framtiden kan externt innehåll läggas till i knowledge graph och bli tillgängligt.
    - För innehåll som inte kan flyttas kan du använda Graph Connectors för att förbättra sökningen och förbereda för framtida integrering.

3. [Modernisera SharePoint-sidor](#3-modernize-sharepoint-pages)
    - Ämneskort kan endast visas på moderna sidor.
    - Identifiera klassiska sidor med hög profil som går att modernisera.

4. [Skydda innehåll på rätt sätt](#4-secure-content-appropriately)
    - Ämnesresurser säkerhets trimas baserat på en användares behörigheter.
    - Identifiera innehåll som kan ha felaktigt omfattande eller restriktiva behörigheter:
      - Uppmuntra webbplatsägare att använda delningsrapporterna för att granska behörigheter
      - Se till att administratörer granskar brett delat innehåll med hjälp av sökning
      - Uppmuntra innehållsägare att dela innehåll som inte är känsligt och som kan ha bredare fördelar för organisationen.
    - Granska Microsoft Graph-konfigurationen för användare och innehåll:
      - Topic indexing honors configuration excluding content from Search or Delve (for example, NOINDEX). Kontrollera om de här konfigurationerna fortfarande är relevanta.

5. [Identifiera kunskapshanterare och ämnen](#5-identify-knowledge-managers-and-topics)
    - Använd befintliga taxonomier för att manuellt skapa ämnen, eller hjälp med att bekräfta AI-föreslagna ämnen.
    - Identifiera ämnesexperter (SS) för förväntade eller idelade ämnen.
    - Identifiera webbplatser som täcker en stor mängd värdefulla data som kan användas för att pilottesta ämnesnäring.
    - Engagera kunskapshanterare och communitys.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Migrera innehåll till Microsoft 365

Det finns flera verktyg och tjänster som hjälper dig med migreringen – du kan få en översikt och information om hur du migrerar på Migrera innehåll till [Microsoft 365.](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) Migreringsverktygen omfattar:

- [Migreringshanteraren](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [Migreringsverktyget för SharePoint (SPMT)](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Verktyg och tjänster för partnermigrering](https://www.microsoft.com/solution-providers)

Få ut det mesta av migreringen:

- Migrera till en modern webbplats – som innehåller Microsoft Teams. Indexeringen kan ske på alla SharePoint-webbplatser (klassisk eller modern), men ämnen som bara visas på moderna sidor visas för användare med fokuspunkter och kort.
- Behåll användarnamn – de flesta migreringsverktyg låter dig mappa användaridentiteter under migreringen, så att egenskaper som Skapat av eller Ändrad av bibehålls efter migreringen. Det här är viktigt för ämnen eftersom redigering av filer används för att identifiera de experter som läggs till på en ämnessida eller ett kort. 
- Ange beskrivande namn på tjänstkontot – Det kommer att finnas vissa fall där det inte går att underhålla användarnamn. Till exempel om du migrerar innehåll som har skapats av någon som inte längre är anställd i organisationen. I det här fallet flyttar de flesta migreringsverktyg en fil som om den skapades med ett administratörskonto eller ett tjänstkonto. Om detta inträffar ofta kan det tjänstkontot sedan visas i en lista med ämnen som en expert. Det är här namnet på kontot blir mycket viktigt. Om du ger den en beskrivande beskrivning blir närvaro av dessa icke-mänskliga konton lättförståeliga genom användarnas användning av ämnen.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Koppla information till Microsoft Graph

Om du inte kan migrera visst innehåll ansluter du det till Microsoft Graph:

- Överväg att [implementera Graph Content Connectors.](https://docs.microsoft.com/microsoftsearch/connectors-overview) Med kopplingar kan externt innehåll indexeras i Microsoft Graph, där användarna sedan kan hitta det via Microsoft Search.
- Framtida utvecklingar kommer att föra med sig externa data till Viva Topics.

## <a name="3-modernize-sharepoint-pages"></a>3. Modernisera SharePoint-sidor

Eftersom ämneskort och höjdpunkter bara kan visas på moderna sidor uppdaterar du alla sidor som du vill ska ingå i Viva-ämnen från klassisk till modern. Se [Hur du moderniserar dina klassiska SharePoint-webbplatser.](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites) Du kan använda [SharePoint-moderniseringsskannern](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) för att förbereda klassiska webbplatser för modernisering.

Om du har många klassiska webbplatser bör du prioritera sidor med hög profil att konvertera till moderna.

## <a name="4-secure-content-appropriately"></a>4. Skydda innehåll på rätt sätt

När användare interagerar med ett ämneskort eller en ämnessida kan de se olika resurser. Det beror på att de har åtkomst till olika filer som är kopplade till ämnet. Om dina underliggande behörigheter är för strikta kan de serendiöriska aspekter av informationsidentifiering genom ämnen minska. Å andra sidan, om de är för breda kan ett ämne ytinnehåll för en användare som du inte vill att de ska se.
Här är det viktigt att hantera bra behörigheter. Och god behörighetshantering baseras på ett pågående samarbete mellan administratörer och innehållsägare. Även om det kan vara en pågående aktivitet finns det några praktiska steg som du kan vidta när du förbereder dig för ämnen:

- Uppmuntra webbplatsägare att granska delning och behörigheter.

  SharePoint-webbplatsägare kan granska en delningsrapport för sin webbplats med fullständig information om alla behörigheter och delningslänkar konfigurerade på webbplatsen, se [Delningsrapporter.](https://docs.microsoft.com/sharepoint/sharing-reports) Här listas interna och externa (gäst)användare.

  Webbplatsägare kan också se vem som har behörighet för webbplatsen genom att gå till sidorna **Webbplatsbehörigheter** och **Avancerade behörighetsinställningar.**

  1. Välj Webbplatsbehörigheter **för Inställningar** på din  >  **webbplats.** Kontrollera vem som visas under Webbplatsägare, Webbplatsmedlemmar och Webbplatsbesökare. Kontrollera om det finns gästanvändare.
  2. Välj Avancerade **behörighetsinställningar** på **sidan Behörigheter.** Du kan söka efter unika behörigheter och se vem som har begränsad åtkomst till objekt på webbplatsen.

- Granska Microsoft 365-grupper och -team för att se till att de är korrekt inställda som offentliga eller privata grupper eller team. Nya Grupper och Microsoft 365-grupper är inställda på privata som standard, men när de först släpptes var offentliga som standard. Om du redan använder dessa tekniker kanske du vill granska. Dessutom utvecklas en grupps funktion ofta under hela livscykeln, och inställningen kan behöva uppdateras för att återspegla den aktuella användningen av gruppen.
- Granska användningen av "alla", "alla utom externa användare" eller breda säkerhetsgrupper. Innehållet kan delas felaktigt med dessa värden. Om du vill granska hur dessa grupper används kan du:
  - Skapa ett konto som inte har några gruppmedlemskap
  - Använd sökfunktionen med det här kontot om du vill hitta innehåll som delas allmänt.
  - Om olämpligt innehåll visas för det här kontot via sökning kan du arbeta med webbplatsägarna för att korrigera behörighetskonfigurationen.

Förutom behörigheter kan du även styra omfattningen av vad som kan upptäckas via ämnen. Du har alltid kontroll över vad som indexeras.

Administratörer kan konfigurera indexering i Administrationscenter för Microsoft 365. När du [konfigurerar Knowledge Management](set-up-topic-experiences.md)kan du:

- Tillåt identifiering på alla SharePoint-webbplatser eller ange webbplatser som ska ingå eller uteslutas som ämneskällor.
- Där du har känsliga termer kan du även utesluta ämnen med namn. Om du till exempel har namnet på ett känsligt projekt, där du inte vill att en markering eller ett kort ska visas, oavsett användarens behörighet, kan du utesluta det projektnamnet.

På innehållsnivå kan du även styra vad som kan upptäckas. Alla konfigurationer som du har gjort för att utesluta innehåll från sökning används också för identifiering av innehåll. Om du till exempel har uteslutit att ett visst dokumentbibliotek visas i sökresultaten används inte det här dokumentbiblioteket för identifiering av ämnen.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Identifiera knowledge managers och ämnen

Hantering av ämnen omfattar tre viktiga roller, inklusive två nya Azure Active Directory-roller (AAD): Kunskapsadministratör och Knowledge Manager:

- Knowledge-administratören (KA) är en teknisk roll, vanligtvis inom IT. Med den här rollen kan du konfigurera Viva-ämnen i administrationscentret för M365, samt konfigurationen av ämnesidentifiering och synlighet.
- Knowledge Manager (KM) arbetar med ämnena själva och övervakar deras kvalitet och fullständighet.
- Ämnesdeltagare (TCs) är inte baserade på en AAD-roll, men behörigheter i administrationscentret. De är ämnesexperter som kan ta hand om innehåll om ämnen och lägga till resurser och personer.

Beroende på din organisation kanske det är få eller många personer som arbetar med de här rollerna. I vissa organisationer kan det vara samma personer.

| Kunskapsadministratör | Knowledge Manager | Ämnesdeltagare |
|:-------|:-------|:-------|:-------|
| AAD-roll | AAD-roll | KANT |
| Har åtkomst till administrationscentret | Har åtkomst till administrationscentret | Ingen åtkomst till administrationscentret |
| Uppsättningar av Viva-ämnen | Egen hantering och kvalitet för ämnen | Bidrar till ämnen baserat på deras expertis. |
| Säkerställer att säkerhet och efterlevnadsstandarder upprätthålls och förstår licensavtal.| Utför ämneshanteringsuppgifter, till exempel skapa, redigera, ta bort och avvisa avsnitt. Stöder ämnesdeltagare med sina uppgifter. | Visar information och innehåll på ämnessidor, inklusive vilka personer och resurser som är fästa vid det ämnet. |

Höjdpunkter och kort visas för användare inom ramen för sitt arbete, till exempel när de bläddrar på moderna sidor i SharePoint. Du kan styra användarupplevelsen för ämnen.

- Vem kan se ämnen? Synlighet för ämnen har konfigurerats i administrationscentret för Microsoft 365. Välj vilka grupper du vill tillåta för att visa ämnen:
  - Alla i min organisation. "Alla" inkluderar inte gäster, det är alla interna användare i katalogen
  - Endast valda personer eller säkerhetsgrupper (det här alternativet är bra medan du håller på att distribuera Viva Topics så att du kan testa med en delmängd användare). Om du vill att gäster ska visa ämnen måste du använda alternativet "valda personer eller säkerhetsgrupper" och ge dem en licens.
  - Ingen.

    Alla användare, även gästanvändare, måste ha en licens tillämpad för att kunna visa ämnesupplevelsen. Kom ihåg att behörigheter alltid styr vad som visas.

- Vilka ämnen visas? Du kan välja att:
  - Visa alla kandidatämnen.
  - Visa endast bekräftade ämnen.

Nu när vi har chefer, experter och användare kan vi prata om själva ämnena.

- Det är en bra idé att lägga till ämnen i ämneslistan. Kvaliteten och antalet ämnen baseras på ditt innehåll. Det skapas bara som ett ämne om det ingår i det innehåll som omfattas. Om det finns tillräcklig information och bevis för ämnet skapas det av AI. Med hjälp av ämnen kan Knowledge Manager och ämnesexperter vara till hjälp. Att kombinera kunskap från människor med AI är den bästa vägen för ämnen av hög kvalitet. Så om det finns ämnen som du tror att du manuellt kan skapa i ämnescentret. På så sätt får AI en stark signal om ämnets relevans och identifierar resurser och personer att associera med det ämnet.
- Använd befintliga taxonomier för att planera ditt ämne, antingen från SharePoint eller någon annanstans. Befintliga taxonomier omfattar ofta organisationstermer, produkter, ämnesområden och så vidare. Källor till ämnen kan också komma från listor med projekt, befintliga sökbokmärken och så vidare.
