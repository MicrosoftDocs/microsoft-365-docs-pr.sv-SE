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
ms.openlocfilehash: 82dc26aea5c573b63bb66d087b332e3301e71409
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48376979"
---
# <a name="microsoft-productivity-score-preview"></a>Microsoft produktivitets Poäng (för hands version)

Produktivitets poäng gör det lättare för organisationer att omvandla hur arbete görs med insikter om hur människor använder Microsoft 365 och de teknik funktioner som har stöd för dem. Poängen reflekterar organisationens prestanda mot folk-och teknik upplevelser och jämför poängen med organisationer som ditt.

Poängen inkluderar:

- **Mått** för att se hur andra använder Microsoft 365-produkter för att samar beta, kommunicera och arbeta på olika plattformar.
- **Insikter** om data för att hjälpa dig att identifiera möjligheter för att förbättra produktivitet och tillfredsställelse hos din personal.
- **Rekommenderade åtgärder** du kan vidta för att hjälpa personer i din organisation att använda Microsoft 365-produkter effektivt så att alla kan göra sitt bästa arbete.

Vi tillhandahåller data, insikter och rekommendationer i två områden: 

- **Personer upplever:** Vi mäter hur personer samarbetar med innehåll, hur de använder Microsoft 365-produkter för att kommunicera och om de använder Microsoft 365 på olika plattformar. 

    Vi tillhandahåller dessa insikter eftersom de när folk samarbetar online sparar tid. Med friheten att arbeta på alla enheter är det mer produktivt och uppfyllt. Kommunikation på ett flexibelt sätt gör det lättare för människor att effektivisera, bilda bättre relationer och organisationen är mer enhetlig. Mer information finns i [Forrester Report](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

- **Teknik upplevelser:** Produktiviteten beror på tillförlitlig och högpresterande teknologi samt användning av Microsoft 365. Vi tillhandahåller [slut punkts analys](https://aka.ms/endpointanalytics), som hjälper dig att förstå hur användarnas produktivitet kan påverkas av prestanda-och hälso problem med slut punktens maskin vara och program vara. Vi tillhandahåller också rekommenderade åtgärder för att åtgärda dem samt Microsoft 365 Network Connectivity Insights för din organisation.

Se [Vad är slut punkts analys](https://docs.microsoft.com/mem/analytics/overview) för en översikt och krav uppgifter. Om du vill veta mer om Microsoft 365 Network Connectivity kan du läsa [Översikt över nätverks anslutningen](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-networking-overview).
  

## <a name="how-the-score-is-calculated"></a>Så här beräknas poängen

Produktivitets poängen baseras på de kombinerade poängen från kategorierna kontakter och teknik. Varje kategori viktas lika, med totalt 100 poäng per kategori. De totala möjliga poängen för produktivitets Poäng är 500.

### <a name="score-categories"></a>Poäng kategorier 

- Innehålls samarbete (100 poäng)
- Kommunikation (100 poäng)
- Mobilitet (100 poäng)
- Slut punkts analys (100 poäng)
- Nätverks anslutning (100 poäng)
- **Totalt antal möjliga = 500 punkter**
 
 I varje kategori identifierar vi mönster för viktiga aktiviteter som är symboler för hur folk använder Microsoft 365-produkter för att samar beta, kommunicera och arbeta på olika plattformar. Vi tillhandahåller 28-dagars-och 180-dagars visningar av viktiga aktiviteter. Vi tillhandahåller också stödjande mått som inte är en del av poängen och som är viktiga för att du ska kunna identifiera underliggande beteenden och inställningar som du kan vidta för att göra en ändring.

### <a name="products-included-in-productivity-score"></a>Produkter inkluderade i produktivitets Poäng 

Produktivitets Poäng inkluderar data från Exchange, SharePoint, OneDrive, teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer och Skype.

Ditt resultat uppdateras dagligen och återspeglar användar åtgärderna som har slutförts under de senaste 28 (inklusive den aktuella dagen).


## <a name="pre-requisites"></a>Förutsättningar 

Du behöver ett Microsoft 365 för företag eller Office 365 för Enterprise-abonnemang för att få folk att använda data, och du behöver ha flera klient organisationer. För att få slut punkts analys data för din klient organisation måste du lägga till Microsoft Intune i ditt abonnemang. Intune hjälper dig att skydda organisationens data genom att hantera enheter och appar.       När du har Intune kan du aktivera slut punkts analys i Intune-upplevelsen. Läs mer om Microsoft Intune. 

Om du vill visa produktivitets poängen för din organisation måste du ha av någon av följande roller: 

- Global administratör 
- Exchange-administratörer
- SharePoint-administratör 
- Skype för företag-administratör 
- Teams-administratör 
- Global läsare 
- Rapport läsare 

Du kan komma åt upplevelsen från Microsoft 365 admin Home under **rapporter**om  >  **produktivitets Poäng**.

## <a name="interpreting-productivity-score"></a>Tolka Poäng för produktivitet 

På Start sidan för produktivitets Poäng visas ditt totala poäng-och Poäng historik samt den främsta inblicken för varje kategori

![Start sida för produktivitets Poäng](../../media/pslanding.png)

**Poängen** visas som ett procentuellt värde samt i punkter så att du kan se dina Points (täljare) och högsta möjliga poäng (nämnare).

Med funktioner för **peer-prestandatest** kan du jämföra poängen med organisationer som dina egna. För kategorierna personer som använder beräknas funktionen för peer-benchmark som medelvärdet av mått inom en uppsättning likartade organisationer. Uppsättningen består av organisationer i din region med ett liknande antal licensierade användare, typer av licenser, bransch och besittning med Microsoft 365. 

Resurs benchmark för slut punkts analys inkluderar mål för start prestanda och Rekommenderad program konfiguration baserat på aggregerade median värden för alla klienter.

För nätverks anslutning är det rekommenderade benchmark 80-poäng.

I avsnittet **Poäng indelning** får du en uppdelning av din produktivitets poäng med benchmarks i områdena personer och teknik.

Resultat historik visar hur poängen i varje kategori har ändrats under de senaste sex månaderna.

**Folk upplevelse** och **teknik upplevelser** innehåller de primära insikterna för kategorierna i dessa områden. Du kan klicka på varje kategori för att se djupare insikter.

## <a name="category-details-pages"></a>Kategori informations sidor

Varje kategori informations sida visar huvud inblick och stödjande mått samt relaterade undersökningar och åtgärder som du kan vidta för att driva en ändring i organisationen. Forskningen har funktioner för betydelse och rationellt bakom primär insikter för varje kategori. Mer information finns [i Forrester-rapporten](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

### <a name="content-collaboration-details"></a>Information om innehålls samarbete

Den främsta inblicken för innehålls samarbete är antalet personer som skapar, läser och samarbetar (redigera och dela) online. De här åtgärderna är viktiga eftersom forskningen visar att när personer samarbetar med online-filer sparar varje person ett medelvärde på nästan två timmar per vecka.

Vi definierar innehålls samarbete som en person som skapar och delar en Office-fil och sedan åtminstone en annan person som läser den. 

**Läsare**: personer som får till gång till eller laddar ned online-filer i OneDrive eller SharePoint.

**Skapare:** Personer som skapar, ändrar, laddar upp, synkroniserar, checkar in, kopierar eller flyttar OneDrive-eller SharePoint-filer online.

**Samarbetsor**: personer som samarbetar med online-filer med OneDrive eller SharePoint. Två personer är kollegor om en av dem läser eller redigerar ett Office-program eller ett PDF-moln-dokument efter att den andra personen har skapat eller ändrat det, inom ett fönster med 28 dagar.

De filtyper som behandlas för samarbete är Word-, Excel-, PowerPoint-, OneNote-och PDF-filer.

Vi tillhandahåller insikter i Start tiderna och konfigurerar enheter i din organisation såväl som nätverks anslutnings insikter för innehålls samarbete eftersom online-filsamarbete kräver tillförlitliga enheter som kan komma att startas snabbt och ha en bra förbindelse till Microsoft 365.

### <a name="communication-details"></a>Kommunikations uppgifter

Den främsta inblicken för kommunikation är hur ofta folk i din organisation använder e-post, chatt och gemenskaps inlägg för kommunikation. När personer använder en mängd olika kommunikations verktyg i real tid kan de välja kommunikations läget som hjälper dem att vara mest effektiva, som chatt och communities som hjälper dem att utveckla relationer mellan olika Office-platser.

### <a name="mobility-details"></a>Information om mobilitet

Den främsta inblicken för rörlighet är antalet personer som får till gång till filer och använder e-post och chatt på flera plattformar. Möjligheten att arbeta från vilken plats som helst på vilken enhet de väljer är viktig för personer med Sälj roller, chefs chefer, konsulter och andra som behöver göra jobbet borta från kontoret. Förbättringar av dessa arbets tagare har stor betydelse. 

Vi mäter det procenttal och det absoluta antalet personer som använder minst en Microsoft 365-produktivitet på två eller fler plattformar, inklusive skriv bord, mobil och Internet. Produktivitets programmen vi mäter är Outlook, teams, Word, Excel, PowerPoint, OneNote, Yammer och Skype. Personer måste ha Microsoft 365-appar för Enterprise-, Exchange-, Yammer-, Skype-eller teams-licenser. 

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
