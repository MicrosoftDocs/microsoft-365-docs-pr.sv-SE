---
title: Användar upplevelse i en multi-geo-miljö
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Läs mer om användar upplevelsen för SharePoint, OneDrive och Exchange i en multi-geo-miljö för Microsoft 365.
ms.openlocfilehash: c94fc5569a5444ca6361712f57460cf0c977b18e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694479"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Användar upplevelse i en multi-geo-miljö

Så här ser användarna i en konfiguration med OneDrive multi-geo:

## <a name="exchange-mailbox"></a>Exchange-postlåda

En användares Exchange-postlåda etableras till deras önskade data plats och flyttas automatiskt om den ändras. Användare kan använda Outlook och Outlook på webben normalt utan någon ändring i användar miljön i en multi-geo-miljö.

## <a name="hub-sites"></a>NAV webbplatser

SharePoint Hub-webbplatser förbättrar identifieringen och åtagandet med innehållet för de anställda, samtidigt som du skapar en komplett och konsekvent presentation av projekt, avdelningar eller regioner. I en multi-geo-miljö kan webbplatser från satellit platser enkelt kopplas till en nav webbplats oavsett dess geo-plats. Användare kan söka efter och få resultat över navet genom en enda Sök funktion, oavsett webbplatsernas Geo-plats.

## <a name="microsoft-365-app-launcher"></a>Start ikon för Microsoft 365

Start programmet är multi-geo-känsligt och dirigerar varje bricka till en lämplig Geo-plats för arbets belastningen. SharePoint-och OneDrive-paneler kommer att peka användaren på platsen som motsvarar användarens provisioed Geo-plats. Det innebär att användaren har en OneDrive i den centrala platsen, att deras SharePoint-panel pekar på SP Home på Central platsen, men deras grupp webbplats etableras på den plats som motsvarar deras PDL. 

## <a name="office-applications"></a>Office-program

Office-program som Word, Excel och PowerPoint identifierar automatiskt den korrekta OneDrive för företag-geo-platsen för varje användare när de loggar in. Användare behöver inte ange den geo-specifika URL-adressen för sina OneDrive-eller SharePoint-webbplatser.

## <a name="onedrive-for-business-sync-client"></a>Synkroniseringsklient för OneDrive för företag

Synkroniseringsklienten för OneDrive för företag (version 17.3.6943.0625 och senare) identifierar automatiskt rätt OneDrive för företag Geo-plats för användaren. Stöd för Synch client inkluderar möjligheten att synkronisera grupperade webbplatser oavsett deras Geo-plats. Observera att synkroniseringsklienten för Groove inte stöds för multi-geo. 

## <a name="onedrive-for-business-location"></a>OneDrive för företag-plats

Användare kommer att få sin OneDrive för företag-etablerad på sin data plats. Om en användare navigerar till en OneDrive-URL som innehåller en felaktig Geo-plats (till exempel ett bok märke från en tidigare Geo-plats) omdirigeras de automatiskt till OneDrive på lämplig Geo-plats.

## <a name="onedrive-ios-and-android"></a>OneDrive iOS och Android 

I OneDrive iOS-och Android-mobilappar visas dina OneDrive-filer och filer som delas med dig oavsett var de befinner sig. Sökning i OneDrive-mobilappen visar relevanta resultat från alla geo-platser. Ladda ner den senaste versionen av dessa program.

Mer information finns i använda [OneDrive för iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) och [använda OneDrive för Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) .

## <a name="onedrive-mobile-client"></a>OneDrive-mobilapp 

OneDrive-mobilappen är en geo medveten och visar relevant innehåll och resultat från alla geo platser.

## <a name="search"></a>Sökmotor

Varje Geo-plats har ett eget Sök index och Sök Center. När en användare söker skickas frågan till alla geo-platser, och de returnerade resultaten kopplas och rangordnas sedan så att användaren får enhetliga resultat. Användare får resultat från alla geo platser oavsett deras egna Geo-plats. Se [Konfigurera sökning i OneDrive för företag multi-geo](configure-search-for-multi-geo.md) för specifika nyheter.

Följande Sök klienter stöds:

-   OneDrive för företag

-   Delve

-   Start sidan för SharePoint

-   Sök Center

-   Anpassade Sök program som använder SharePoint Search API

## <a name="sharepoint-home"></a>Start sidan för SharePoint 

I SharePoint multi-geo är SharePoint-hem platsen placerad på den plats där användaren finns som den definieras av OneDrive för företag-platsen. Till exempel: om användaren har OneDrive-värd på en europeisk satellit plats kommer deras SharePoint-hem att renderas från Europa. SharePoint Home inkluderar allt innehåll som är relevant för användaren oavsett dess geo-plats. 

**Följda webbplatser, nyheter från webbplatser, senaste webbplatser, vanliga webbplatser och föreslagna webbplatser**

Alla de här komponenterna visas för användaren oavsett vilken Geo-plats som innehållet hanteras på, så länge användaren har behörighet till innehåll. 

**Funktions länkar**

Administratörer kan konfigurera aktuella länkar i SharePoint Home efter behov till varje Geo-plats. På så sätt kan administratören i SP hem för varje region de länkar som är lämpliga för användarna i regionen. 

## <a name="sharepoint-mobile-client"></a>SharePoint Mobile-klient 

SharePoint Mobile-klienten är en geo medveten och visar relevant innehåll och resultat från alla geo-platser.

## <a name="sharing"></a>Delning

Person väljaren visar alla användare oavsett deras Geo-plats. Det gör det möjligt för en användare att dela med sig av sina geo-eller andra användares geo-platser. Innehåll från olika geo-platser visas i vyn **delas med mig** i användarens OneDrive för företag och kan nås med enkel inloggnings upplevelse oavsett vilken Geo-plats den finns i.

## <a name="teams-experience"></a>Teams Experience

Teams är multi-geo-känsligt. OneDrive-filer och nyligen visade filer visas oavsett användarens Geo-plats. @ omnämnanden fungerar tillsammans med användare från alla geo-platser.

## <a name="user-profiles"></a>Användar profiler

Användar profil informationen hanteras i användarens Geo-plats. När du väljer en användare omdirigeras du till en lämplig Geo-plats för användaren, där du kan se deras fullständiga profil uppgifter.

Om Delve är inaktiverat visas den klassiska profil upplevelsen i SharePoint, som inte är särskilt kompatibel.


