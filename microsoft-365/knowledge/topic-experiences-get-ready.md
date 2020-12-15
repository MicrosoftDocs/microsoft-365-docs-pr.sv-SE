---
title: Förbered din miljö för ämne (för hands version)
description: Förbered din miljö så att du kan ange så mycket innehåll som möjligt för användarna med ämnen (för hands version).
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX
ms.openlocfilehash: 19112b222be328eb75b7eea807bea94e524fd56d
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683468"
---
# <a name="get-your-environment-ready-for-topic-experiences-preview"></a>Förbered din miljö för ämne (för hands version)

> [!Note]
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

För att få ut det mesta av avsnitts upplevelser vill du ha så mycket innehåll som möjligt med avsnitts identifiering, så att du kan ha många olika ämnen för dina användare. Vilket innehåll ska användas för avsnitts identifiering? Hur gör du för att maximera innehållet som är indexerat, och samtidigt behålla kontrollen? Mer innehåll är i omfattning, desto bättre blir den artificiella intelligensen. I den här artikeln får du stegvisa instruktioner för att se till att du inkluderar lämpligt innehåll och att du har rätt personer och resurser för att få en bra upplevelse för dina användare.

För att kunna planera för avsnitts upplevelser (för hands version) måste du:

![Migrera, ansluta, modernisera, skydda och identifiera steg för att hantera kunskaps hantering](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrera innehåll till SharePoint](#1-migrate-content-to-microsoft-365)
    - Avsnitts utvinning inkluderar bara innehåll på SharePoint-webbplatser.
      - Om möjligt migrerar du värdefullt innehåll till SharePoint Online från externa källor.
      - Prioritera innehålls källor med stor potential för tyst kunskap.
      - Markera fördelarna med kunskaps hantering för att uppmuntra användare att flytta innehåll från OneDrive till SharePoint-webbplatser.

2. [Koppla information till Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - I framtiden kan du gå in i kunskaps diagrammet och bli tillgänglig.
    - För innehåll som inte kan flyttas bör du överväga att använda Graph-kopplingar för att förbättra sökningar och förbereda för framtida inkludering.

3. [Modernisera SharePoint-sidor](#3-modernize-sharepoint-pages)
    - Ämnes kort kan bara placeras på moderna sidor.
    - Identifiera klassiska sidor med hög profil som är Modernization kandidater.

4. [Skydda innehållet på lämpligt sätt](#4-secure-content-appropriately)
    - Ämnes resurser är säkerhetstrimmade baserat på en användares behörigheter.
    - Identifiera innehåll som kan ha fel generella eller begränsade behörigheter:
      - Uppmuntra webbplats ägarna att använda delnings rapporterna för att granska behörigheter
      - Låt administratörer granska allt delat innehåll med Sök funktionen
      - Uppmuntra innehålls ägarna att dela innehåll som inte är känsligt och kan ha en bredare fördel för organisationen.
    - Granska Microsoft Graph-konfigurationen för användare och innehåll:
      - Avsnitts utvinning följer konfiguration exklusive innehåll från sökning eller Delve. Kontrol lera om dessa konfigurationer fortfarande är relevanta.

5. [Identifiera kunskaps chefer och ämnen](#5-identify-knowledge-managers-and-topics)
    - Använd befintliga taxonomier för att manuellt skapa avsnitt.
    - Identifiera ämnes experter (SMF) för förväntade eller dirigerade ämnen.
    - Identifiera webbplatser som täcker en stor del av värdefulla data som kan användas för pilot ämnen.
    - Delta i kunskaps chefer och i övnings grupper.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Migrera innehåll till Microsoft 365

Det finns flera verktyg och tjänster som hjälper dig med migreringen – du kan få en översikt över och information om hur du migrerar genom att [migrera innehållet till Microsoft 365](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online). Migreringsverktyg inkluderar:

- [Migreringshanteraren](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [Migreringsverktyg för SharePoint (SPMT)](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Migreringsverktyg och tjänster för partner](https://www.microsoft.com/solution-providers)

Få ut mesta möjliga av migreringen:

- Migrera till en modern webbplats-med Microsoft Teams. När indexeringen kan ske på alla SharePoint-webbplatser (klassiska eller moderna) visas bara ämnen för användare via högdagrar och kort på moderna sidor.
- Underhåll användar namn-de flesta Migreringsverktyg gör att du kan mappa användar identiteter i migreringen, så att egenskaper som skapas av eller ändras av hanteras efter migreringen. Det här är viktigt för ämnen eftersom fil författare används för att identifiera de experter som läggs till på en ämnes sida eller ett kort. 
- Skapa namn på tjänst konton – det finns vissa fall där det inte går att bevara användar namn. Om du till exempel migrerar innehåll som skapats av någon som inte längre är anställd i organisationen. I den här instansen flyttar de flesta migreringsverktyget en fil som om den skapades av ett administratörs konto eller ett tjänst konto. Om det här inträffar ofta kan det här tjänst kontot listas mot ämnen som en expert. Det är där namnet på kontot blir mycket viktigt. Om du gör det beskrivande är närvaron av dessa icke-mänskliga konton lättare att förstå för användare som använder ämnen.

## <a name="2-connect-information-to-microsoft-graph"></a>2. koppla informationen till Microsoft Graph

Om du inte kan migrera lite innehåll kan du ansluta det med Microsoft Graph:

- Överväg att implementera [Graph-innehåll](https://docs.microsoft.com/microsoftsearch/connectors-overview). Genom att använda kopplingar kan externa innehåll indexeras i Microsoft Graph, där användarna kan hitta dem via Microsoft Search.
- Den framtida utvecklingen kommer att överföra externa data till ämnen.

## <a name="3-modernize-sharepoint-pages"></a>3. modernisera SharePoint-sidor

Eftersom det bara går att Visa ämnes kort och högdagrar på moderna sidor kan du uppdatera de sidor som du vill ska ingå i ämnes erfarenheterna från klassisk till modern. Se [modernisera dina klassiska SharePoint-webbplatser](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites). Du kan använda [SharePoint Modernization-skannern](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) för att förbereda de klassiska webbplatserna för Modernization.

Om du har många klassiska webbplatser kan du prioritera de många profil sidor som du vill konvertera till moderna.

## <a name="4-secure-content-appropriately"></a>4. skydda innehållet på lämpligt sätt

När användarna interagerar med ett ämnes kort eller en ämnes sida kan de se olika resurser. Det beror på att de har åtkomst till olika filer som är kopplade till avsnittet. Om dina underliggande behörigheter är för strikta kan de serendipitous aspekterna av information som upptäcks genom ämnen minskas. Å andra sidan, om de är för breda kan ett avsnitt ha Surface-innehåll för en användare som du inte vill att de ska se.
Det är viktigt att hantera god behörighet. Och hantering av god behörighet är baserat på ett pågående partnerskap mellan administratörer och innehålls ägare. Det här kan vara en pågående aktivitet som du kan vidta för att förbereda olika ämnen:

- Uppmuntra webbplats ägarna att granska delning och behörigheter.

  Du kan granska en delnings rapport för webbplatsen som visar fullständiga uppgifter om alla behörigheter och delnings länkar som har kon figurer ATS på webbplatsen i [dela rapporter](https://docs.microsoft.com/sharepoint/sharing-reports). Här listas intern och extern (gäst) användare.

  Webbplats ägare kan också se vem som har behörighet för webbplatsen genom att gå till sidorna **webbplats behörigheter** och **avancerade behörigheter** .

  1. Välj   >  **webbplats behörigheter** för inställningar på webbplatsen. Kontrol lera vilka som är listade under webbplats ägare, webbplats medlemmar och besökare. Sök efter gäst användare.
  2. Välj **avancerade behörigheter** på sidan **behörigheter** . Du kan söka efter unika behörigheter och se vilka som har begränsad åtkomst till objekt på webbplatsen.

- Granska Microsoft 365-grupper och Teams för att se till att de är korrekt inställda som offentliga eller privata grupper eller team. Nya team och Microsoft 365 Groups är privata som standard, men när första utgivningen är offentlig som standard. Om du var tidigare inför dessa tekniker kanske du vill granska. Dessutom utvecklas en grupps funktion ofta över hela livs cykeln och det kan hända att inställningen måste uppdateras för att det ska gå att använda teamet.
- Granska användning av "alla", "alla utom externa användare" eller breda säkerhets grupper. Innehållet kan delas felaktigt med dessa värden. Om du vill granska hur de här grupperna används kan du:
  - Skapa ett konto som inte har några grupp medlemskap
  - Använd Sök funktionen med det här kontot för att hitta innehåll som delas.
  - Om olämpligt innehåll visas för det här kontot via sökning kan du arbeta med webbplats ägarna för att korrigera behörighets konfigurationen.

Utöver behörigheter kan du också styra omfattningen av vad som kan upptäckas genom olika ämnen. Du har alltid kontroll över vad som är indexerat.

Administratörer kan konfigurera indexering i administrations centret för Microsoft 365. När du konfigurerar [kunskaps hantering](set-up-topic-experiences.md)kan du göra följande:

- Tillåt identifiering på alla SharePoint-webbplatser eller ange webbplatser att inkludera eller exkludera som avsnitts källor.
- Om du har känsliga villkor kan du även utesluta ämnen efter namn. Om du till exempel har namnet på ett känsligt projekt och du inte vill att en högdager eller ett kort ska visas, oavsett användarens behörigheter, kan du utesluta projekt namnet.

På innehålls nivå kan du också kontrol lera vad som kan upptäckas. Alla konfigurationer som du har gjort för att undanta innehåll från sökning används också för innehålls identifiering. Om du till exempel har uteslutit ett visst dokument bibliotek från en sökning i Sök resultaten används inte det här dokument biblioteket för avsnitts ökning.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. identifiera kunskaps chefer och ämnen

Hantering av ämnen handlar om tre viktiga roller, inklusive två nya Azure Active Directory-roller (AAD): kunskaps administratör och kunskaps chef:

- Kunskaps administratören (KA) är en teknisk roll, vanligt vis i den. Med den här rollen kan du konfigurera avsnitts funktionerna i administrations centret för M365, samt konfiguration av identifiering och synlighet för avsnitt.
- Kunskaps ledaren (KM) fungerar tillsammans med ämnena och ser till att deras kvalitet och fullständighet visas.
- Ämnes deltagare är inte baserade på en AAD-roll, men behörigheter i administrations centret. De är föremål för experter som kan granska innehållet i avsnitt, lägga till resurser och personer.

Beroende på din organisation kan du ha få eller många personer som agerar i dessa roller. För vissa organisationer kan de vara samma personer.

| Kunskaps administratör | Kunskaps chef | Ämnes deltagare |
|:-------|:-------|:-------|:-------|
| AAD-roll | AAD-roll | STORT |
| Har åtkomst till administrations centret | Har åtkomst till administrations centret | Ingen åtkomst till administrations centret |
| Konfigurerar ämnen | Äger hantering och kvalitet av ämnen | Bidrar till ämnen baserat på deras expertis. |
| Säkerställer att säkerhets-och efterföljandekrav efterlevs och förstår licens avtal.| Utför hanterings uppgifter som att skapa, redigera, ta bort och avvisa ämnen. Stöd för ämne deltagare med deras uppgifter. | Granska informationen och innehållet på ämnes sidorna, inklusive vilka personer och resurser som har fästs i det avsnittet. |

Högdagrar och kort visas för användare i deras arbete, till exempel när de bläddrar bland moderna sidor i SharePoint. Du styr användar upplevelsen för slutanvändare.

- Vilka kan se ämnena? Ämnet är synligt i administrations centret för Microsoft 365. Välj vilka grupper du vill tillåta att se ämnen:
  - Alla i organisationen. "Alla" inkluderar inte gäster, det är alla interna användare i katalogen
  - Endast valda personer eller säkerhets grupper (det här alternativet är bra när du fortfarande rullar ut avsnitts upplevelser, så att du kan testa med en delmängd användare). Om du vill att gäster ska Visa ämnen måste du använda alternativet "valda personer eller säkerhets grupper" och ge dem en licens.
  - Ingen.

    Alla användare, även gäst användare, måste ha en licens för att kunna se avsnitts upplevelsen. Kom ihåg att behörigheter alltid styr vad som visas.

- Vilka avsnitt är synliga? Du kan välja att:
  - Visa alla kandidat avsnitt.
  - Visa endast bekräftade avsnitt.

Nu när vi har cheferna, experterna och användarna kan vi prata om själva avsnitten.

- Det är en bra idé att dirigera ämnen till din ämnes lista. Kvaliteten och mängden av ämnena är baserat på ditt innehåll-det skapas bara som ett ämne om det ingår i innehållet i omfånget. Om det finns tillräckligt med information och bevis för ämnet skapas det av AI-filen. Med hjälp av dirigerade ämnen kan kunskaps chef och ämnes experter hjälpa dig. Att kombinera människo kunskap med AI är den bästa vägen för kvalitets ämnen. Om det finns ämnen som du förväntar dig kan du skapa dessa manuellt i ämnes centret. Om du gör det får du en stark ljus signal om det ämnets relevans och det identifierar resurser och personer som ska kopplas till det avsnittet.
- Använd befintliga taxonomier för att lättare kunna planera, från SharePoint eller på andra platser. Befintliga taxonomier inkluderar ofta organisations villkor, produkter, ämnes områden och så vidare. Källor till ämnen kan också komma från listor med projekt, befintliga Sök bok märken och så vidare.
