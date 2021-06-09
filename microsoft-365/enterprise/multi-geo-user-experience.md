---
title: Användarupplevelse i en miljö med flera geografiska miljöer
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
description: Läs mer SharePoint, OneDrive och Exchange i en miljö med flera geografiska Microsoft 365.
ms.openlocfilehash: 558e5a1f7ff2f6f5485a9f32d6e2b43b552b7f17
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749581"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Användarupplevelse i en miljö med flera geografiska miljöer

Det här ser dina användare i en OneDrive Multi-Geo konfiguration:

## <a name="exchange-mailbox"></a>Exchange postlåda

En användares e Exchange postlåda etableras till den önskade dataplatsen och flyttas automatiskt om deras PDL ändras. Användare kan använda Outlook och Outlook på webben normalt utan att ändra användarupplevelsen i en geomiljö med flera webbplatser.

## <a name="hub-sites"></a>Navplatser

SharePoint Navplatser förbättrar identifieringen och engagemanget med innehåll för anställda, samtidigt som en komplett och enhetlig representation av projekt, avdelningar eller regioner skapas. I flera geomiljöer kan webbplatser från satellitplatser enkelt kopplas till en navplats oavsett navplatsens geoplats. Användare kan söka och få resultat i hela navet genom en enda sökupplevelse, oavsett platsens geoplats.

## <a name="microsoft-365-app-launcher"></a>Microsoft 365 för appar

Startprogrammet är multi-geomedvetet och dirigerar varje panel till rätt geografisk plats för arbetsbelastningen. Med SharePoint och OneDrive-paneler pekar användaren på den plats som motsvarar användarens etablerade geoplats. Det innebär att användaren har ett OneDrive på den centrala platsen. Deras SharePoint-panel pekar dem på SP Home på den centrala platsen men gruppwebbplatsen etableras på den plats som motsvarar deras PDL. 

## <a name="office-applications"></a>Office-program

Office program som Word, Excel och PowerPoint identifierar automatiskt rätt OneDrive för företag geoplats för varje användare när de loggar in. Användarna behöver inte ange den geospecifika URL-adressen för sina OneDrive eller SharePoint webbplatser.

## <a name="onedrive-for-business-sync-client"></a>OneDrive för företag Synkroniseringsklient

Synkroniseringsklienten OneDrive för företag (version 17.3.6943.0625 och senare) identifierar automatiskt rätt OneDrive för företag geoplats för användaren. Stöd för synkroniseringsklienten omfattar möjligheten att synkronisera gruppbaserade webbplatser oavsett deras geografiska position. Observera att Groove synkroniseringsklienten inte stöds för multi-geo. 

## <a name="onedrive-for-business-location"></a>OneDrive för företag plats

Användarna får sina OneDrive för företag tillhandahållas på den dataplats de föredrar. Om en användare navigerar till en URL-adress för OneDrive som innehåller en felaktig geoplats (till exempel ett bokmärke från en tidigare geoplats) omdirigeras de automatiskt till OneDrive på lämplig geoplats.

## <a name="onedrive-ios-and-android"></a>OneDrive iOS och Android 

I OneDrive iOS- och Android-mobilapparna visas dina OneDrive filer och filer som delas med dig oavsett var de befinner sig. Sök från OneDrive mobilappar visar relevanta resultat från alla geoplatser. Ladda ned den senaste versionen av dessa appar.

Mer information OneDrive Använda OneDrive [iOS och Använda OneDrive för Android.](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) [](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247)

## <a name="onedrive-mobile-client"></a>OneDrive Mobilklient 

The OneDrive Mobile Client is multi-geo aware and will display relevant content and results from all geo locations.

## <a name="search"></a>Söka

Varje geoplats har ett eget sökindex och sökcenter. När en användare söker skickas frågan till alla geografiska platser och de returnerade resultaten sammanfogas och rangordnas så att användaren får enhetliga resultat. Användare får resultat från alla geoplatser oavsett var de befinner sig. Mer [information finns i OneDrive för företag för](configure-search-for-multi-geo.md) sökning med multi-geo.

Följande sökklienter stöds:

-   OneDrive för företag

-   Delve

-   SharePoint Home

-   Sökcenter

-   Anpassade sökprogram som använder SharePoint Search API

## <a name="sharepoint-home"></a>SharePoint Home 

I SharePoint Multi-Geo ditt SharePoint ligger hemma på den plats där användaren finns enligt användarens OneDrive för företag. Exempel: Om användaren har en OneDrive på en europeisk satellitplats återges deras SharePoint från Europa. SharePoint innehåller allt innehåll som är relevant för användaren, oavsett dess geografiska position. 

**Webbplatser du följer, nyheter från webbplatser, senaste webbplatser, vanliga webbplatser och föreslagna webbplatser**

Alla dessa komponenter visas för användaren oavsett den geoplats där innehållet finns, så länge användaren har behörighet till innehållet. 

**Länkar till funktioner**

Administratörer kan konfigurera aktuella länkar i SharePoint efter behov för varje geoplats. Det gör att administratören kan använda länkarna som är lämpliga för användare i regionen i SP Home för varje region. 

## <a name="sharepoint-mobile-client"></a>SharePoint Mobilklient 

The SharePoint Mobile Client is multi-geo aware and will display relevant content and results from all geo locations.

## <a name="sharing"></a>Delning

I väljaren för personer visas alla användare oavsett var de befinner sig. Det gör att en användare kan dela med en annan användare i samma geo eller på någon annan av klientorganisationens geoplatser. Innehåll från olika geografiska platser visas  i vyn Delas med mig i användarens OneDrive för företag och kan nås med single Sign-On-upplevelse oavsett vilken geoplats den finns på.

## <a name="teams-experience"></a>Teams Upplevelse

Teams är multi-geomedveten. OneDrive filer och senast visade filer visas oavsett användarens geografiska position. @ omnämnanden fungerar med användare från alla geografiska platser.

## <a name="user-profiles"></a>Användarprofiler

Användarprofilinformation kan lagras på användarens geoplats. När du väljer en användare dirigeras du till lämplig geoplats för användaren, där du ser den fullständiga profilinformationen.

Om Delve är inaktiverat visas det klassiska profilupplevelsen i SharePoint, som inte är multigeografiska.


