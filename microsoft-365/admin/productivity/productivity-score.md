---
title: Microsoft produktivitets Poäng
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Översikt över Microsoft produktivitets poäng.
ms.openlocfilehash: 3d014cd0eb3a3ceed3b3f3b48f126453e4ced193
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "48794971"
---
# <a name="microsoft-productivity-score"></a>Microsoft produktivitets Poäng 

Produktivitets poäng gör det lättare för organisationer att omvandla hur arbete görs med insikter om hur människor använder Microsoft 365 och de teknik funktioner som har stöd för dem. Poängen reflekterar organisationens prestanda mot folk-och teknik upplevelser och jämför poängen med organisationer som ditt.

Poängen inkluderar:

- **Mått** för att se hur andra använder Microsoft 365-produkter för att samar beta, kommunicera och arbeta på olika plattformar.
- **Insikter** om data för att hjälpa dig att identifiera möjligheter för att förbättra produktivitet och tillfredsställelse hos din personal.
- **Rekommenderade åtgärder** du kan vidta för att hjälpa personer i din organisation att använda Microsoft 365-produkter effektivt så att alla kan göra sitt bästa arbete.

Vi tillhandahåller data, insikter och rekommendationer i två områden: 

- **Personer upplever:** Mäter hur personer samarbetar med innehåll, hur de använder Microsoft 365-produkter för att kommunicera och om de använder Microsoft 365 på flera plattformar. 

    Vi tillhandahåller dessa insikter eftersom när personer samarbetar online sparar de tid och med friheten att arbeta på alla enheter blir det mer produktivt och uppfyllt. Möjligheten att kommunicera på ett flexibelt sätt gör det lättare för människor att effektivisera, kunna bilda bättre relationer och göra organisationen mer enhetlig. Mer information finns i [Forrester Report](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

- **Teknik upplevelser:** Produktiviteten beror på pålitlig och välpresterande teknologi samt effektiv användning av Microsoft 365. Vi tillhandahåller [slut punkts analys](https://aka.ms/endpointanalytics), som hjälper dig att förstå hur användarnas produktivitet kan påverkas av prestanda-och hälso problem med slut punktens maskin vara och program vara. Vi tillhandahåller också rekommenderade åtgärder för att åtgärda dem samt Microsoft 365 Network Connectivity Insights för din organisation.

Se [Vad är slut punkts analys](https://docs.microsoft.com/mem/analytics/overview) för en översikt och krav uppgifter. Om du vill veta mer om Microsoft 365 Network Connectivity kan du läsa [Översikt över nätverks anslutningen](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-networking-overview).
  

## <a name="how-the-score-is-calculated"></a>Så här beräknas poängen

Produktivitets poängen baseras på de kombinerade poängen från kategorierna kontakter och teknik. Varje kategori viktas lika, med totalt 100 poäng. Högsta möjliga produktivitets Poäng är 500.

### <a name="score-categories"></a>Poäng kategorier 

- Innehålls samarbete (100 poäng)
- Kommunikation (100 poäng)
- Mobilitet (100 poäng)
- Slut punkts analys (100 poäng)
- Nätverks anslutning (100 poäng)
- **Totalt antal möjliga = 500 punkter**
 
 I varje kategori identifierar vi mönster för viktiga aktiviteter som är symboler för hur folk använder Microsoft 365-produkter för att samar beta, kommunicera och arbeta på olika plattformar. Vi tillhandahåller 28-dagars-och 180-dagars visningar av viktiga aktiviteter. Vi tillhandahåller också stödjande mått som inte är en del av poängen och som är viktiga för att du ska kunna identifiera underliggande beteenden och inställningar som du kan vidta.

### <a name="products-included-in-productivity-score"></a>Produkter inkluderade i produktivitets Poäng 

Produktivitets Poäng inkluderar data från Exchange, SharePoint, OneDrive, teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer och Skype.

Ditt resultat uppdateras dagligen och återspeglar användar åtgärderna som har slutförts under de senaste 28 (inklusive den aktuella dagen).


## <a name="pre-requisites"></a>Förutsättningar 

För att få folk att använda data måste du ha Microsoft 365 för företag eller Office 365 för Enterprise-prenumeration, och du behöver ha flera klient organisationer. För att få slut punkts analys data för din klient organisation måste du lägga till Microsoft Intune i ditt abonnemang. Intune hjälper dig att skydda organisationens data genom att hantera enheter och appar.       När du har Intune kan du aktivera slut punkts analys i Intune-upplevelsen. Läs mer om Microsoft Intune. 

Om du vill visa produktivitets poängen för din organisation måste du ha av någon av följande roller: 

- Global administratör 
- Exchange-administratörer
- SharePoint-administratör 
- Skype för företag-administratör 
- Teams-administratör 
- Global läsare 
- Rapport läsare 

Du kan komma åt upplevelsen från Microsoft 365 admin Home under **rapporter** om  >  **produktivitets Poäng** .

## <a name="interpreting-productivity-score"></a>Tolka Poäng för produktivitet 

På Start sidan för produktivitets Poäng visas din totala poäng-och Poäng historik och huvud inblick för varje kategori.

![Start sida för produktivitets Poäng](../../media/pslanding.png)

**Poängen** visas som ett procent värde och i punkter. Du kan se dina Points i täljaren och maximalt antal möjliga punkter i nämnaren.

Med funktioner för **peer-prestandatest** kan du jämföra poängen med organisationer som dina egna. För kategorierna personer som använder beräknas funktionen för peer-benchmark som medelvärdet av mått inom en uppsättning likartade organisationer. Uppsättningen består av organisationer i din region med ett liknande antal licensierade användare, typer av licenser, bransch och besittning med Microsoft 365. 

Resurs benchmark för slut punkts analys inkluderar mål för start prestanda och Rekommenderad program konfiguration baserat på aggregerade median värden för alla klienter.

För nätverks anslutning är det rekommenderade benchmark 80-poäng.

I avsnittet **Poäng indelning** får du en uppdelning av din produktivitets poäng med benchmarks i områdena personer och teknik.

Resultat historik visar hur poängen i varje kategori har ändrats under de senaste sex månaderna.

**Folk upplevelse** och **teknik upplevelser** innehåller de primära insikterna för kategorierna i dessa områden. Du kan klicka på varje kategori för att se djupare insikter.

## <a name="category-details-pages"></a>Kategori informations sidor

Varje kategori informations sida visar huvud inblick och stödjande mått samt relaterade undersökningar och åtgärder som du kan vidta för att driva en ändring i organisationen. Forskningen har funktioner för betydelse och rationellt bakom primär insikter för varje kategori. Mer information finns [i Forrester-rapporten](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

Informations sidorna är:
- [Innehålls samarbete – folk upplevelse](content-collaboration.md)
- [Kommunikation – folk upplevelse](communication.md)
- [Möten – folk upplevelse](meetings.md)
- [Rörlighet – människor upplever](mobility.md)
- [Samarbete – folk upplevelse](teamwork.md)
- [Microsoft 365-appar hälsa – teknik upplevelse](apps-health.md)

## <a name="business-continuity-special-report"></a>Special rapport för affärs kontinuitet

Rapporten kontinuitet för företag är en begränsad tids rapport för arbets plats information som är tillgänglig för alla Microsoft 365-kunder så att de kan hjälpa dem att vägleda sina organisationer under denna utmanande tid.  

Den här rapporten hjälper företags ledare att förstå: 

- Hur samarbete och kommunikation påverkas av SKIFT för fjärrarbete. 

- Det påverkar arbetets livs längd och det går att arbeta hemifrån. 

- Om fjärrsamtal-möten har stöd för effektivt beslut.

[Lär dig mer om kontinuitets rapporten för företag](https://aka.ms/bcrps)

[Lär dig mer om Microsoft Graph](https://docs.microsoft.com/graph/)

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Dela dina tankar om produktivitets Poäng och dina idéer om hur du kan förbättra det. Använd **feedback** -avsnitten i produkten och/eller nå produktivitets gruppen på ProductivityScorePreview@service.microsoft.com.
