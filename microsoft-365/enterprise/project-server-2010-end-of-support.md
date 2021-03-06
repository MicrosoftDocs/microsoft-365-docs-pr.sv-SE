---
title: Project Server 2010 – översikt för slutet av supporten
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: Supporten upphör Project Server 2010 upphör den 13 april 2021. Använd den här artikeln som en guide för Project Online eller en nyare version Project server lokalt.
ms.openlocfilehash: 0ca37d00ee670a8a3f7c83d75864b5af19587951
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229761"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 – översikt för slutet av supporten

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Project Supporten för Server 2010 avslutas **den 13 april 2021.** Datumet utökades från det tidigare supportdatumet den 13 oktober 2020. Om du för närvarande använder Project Server 2010, observera att dessa relaterade produkter har följande supportdatum:

|Produkt |Supportdatum för slutet|
|---|---|
|Project 2010 Standard|13 oktober 2020|
|Project 2010 Professional|13 oktober 2020|

Mer information om hur du når slutet av supporten finns [i Uppgradera från Office 2010-servrar och klientprodukter.](plan-upgrade-previous-versions-office.md)

## <a name="what-does-end-of-support-mean"></a>Vad innebär *slutet av supporten?*

Nästan alla Microsoft-produkter har en supportlivscykel under vilken de får nya funktioner, programkorrigeringar och säkerhetsuppdateringar. En livscykel varar vanligtvis i tio år från produktens första version. Slutet av perioden kallas för slutet av supporten för produkten. När Project Server 2010 når slutet av supporten den 13 april 2021 tillhandahåller Microsoft inte längre:

- Teknisk support för problem som kan uppstå.

- Programkorrigeringar för problem som upptäcks och kan påverka servrars stabilitet och användbarhet.

- Säkerhetskorrigeringar för säkerhetsproblem som upptäcks och som kan göra servrar sårbara för säkerhetsbrister.

- Tidszonsuppdateringar.

Din installation av Project Server 2010 fortsätter att köras efter detta datum. På grund av ändringarna ovan rekommenderar vi dock starkt att du migrerar från Project Server 2010 så snart som möjligt.

## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Migreringsalternativen är:

- Migrera till Project Online

- Migrera till en nyare lokal version av Project Server (helst Project Server 2019)

Här är de två sätt du kan gå till för att undvika att supporten för Project Server 2010 tar slut.

![Project Uppgraderingsvägar för Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Varför skulle jag föredra att migrera till Project Server 2019?|Varför skulle jag föredra att migrera till Project Online?|
|---|---|
|Affärsregler hindrar mig från att använda mitt företag i molnet.  <br/><br/>  Jag behöver kontrollera uppdateringarna av miljön.|Jag har mobila användare eller fjärranvändare.<br/><br/>  Kostnaderna för att migrera lokala servrar är ett betydande problem (maskinvara, programvara, tid och arbete med att implementera och så vidare). <br/><br/>  Efter migreringen är kostnaderna för att underhålla miljön ett problem (till exempel automatiska uppdateringar, garanterad drifttid och så vidare).|

> [!NOTE]
> Mer information om migreringsalternativ finns i Resurser som hjälper dig att uppgradera från [Office 2010-servrar och -klienter.](upgrade-from-office-2010-servers-and-products.md) Observera att Project Server inte har stöd för hybridkonfiguration eftersom Project Server och Project Online inte kan dela samma resurspool.

### <a name="what-are-my-options-for-project-client"></a>Vilka alternativ har jag för Project klient?

Om du använder Project Professional 2010 eller Project Standard 2010 är alternativen:

- Flytta till en nyare version av Project Professional eller Project Standard
- Gå över till en onlinelösning, Project Online eller Project för webben

#### <a name="move-to-a-newer-version-of-project-client"></a>Flytta till en nyare version av Project klient

Om du migrerar från Project Standard 2010 kan du flytta till en nyare version av Project Standard (Project Standard 2016 eller Project Standard 2019). Vi rekommenderar att du flyttar till den senaste versionen för att kunna dra nytta av de senaste funktionerna. Att migrera till en mindre aktuell version (Project Standard 2016) innebär också att du måste migrera igen tidigare.

Om du migrerar från Project Professional 2010 kan du på samma sätt flytta till en nyare version (Project Professional 2019 eller Project Professional 2016). Gå återigen till den senaste versionen om möjligt. Om du använder Project Professional för att ansluta till Project Server måste du migrera till en version av Project Professional som ansluter till den version av Project server som du använder.

Project Professional 2010-användare kan också migrera till Project Online Desktop-klienten, som är en prenumerationsbaserad version av Project Professional 2019. Det ingår i Project Abonnemang 3 och Project Abonnemang 5 prenumerationer.

#### <a name="move-to-an-online-solution"></a>Flytta till en onlinelösning

Du kan också migrera från Project Professional 2010 eller Project Standard 2010 till en Project prenumerationsbaserad onlinelösning. Både Project Abonnemang 3 och Abonnemang 5 innehåller Project Online och det senaste molnerbjudandet, [Project för webben.](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) Båda har nya funktioner och fördelar som du kan utforska.

Mer information om funktioner och licenser finns i Microsoft Project [tjänstbeskrivning](/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Viktiga överväganden vid migrering från Project Server 2010

Tänk på följande när du planerar att migrera från Project Server 2010:

- **Få hjälp från en leverantör av Microsoft-lösningar** – En uppgradering från Project Server 2010 kan vara en utmaning. Det kräver mycket förberedelse och planering. Det kan vara särskilt svårt om du inte var den person som ursprungligen konfigurerade Project Server 2010. Det finns tillgängliga Microsoft-lösningsleverantörer som kan hjälpa dig, oavsett om du planerar att migrera till Project Server 2019 eller till Project Online. Sök efter en lösningsleverantör i [Microsoft Solution Provider Center](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Planera för anpassningarna** – Anpassningar i din Project Server 2010-miljö kanske inte fungerar när du migrerar till Project Server 2019 eller Project Online. Det finns betydande skillnader i Project Server-arkitekturen mellan olika versioner. Dessutom skiljer sig de operativsystem, databasservrar och webbläsare som fungerar med versionerna åt. Ha en plan för hur du ska testa eller återskapa anpassningarna i den nya miljön. Ta den här möjligheten för att avgöra om specifika anpassningar fortfarande behövs. Mer information finns i [Skapa en plan för aktuella anpassningar under uppgraderingen till SharePoint 2013.](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)

- **Tid och tålamod –** Uppgraderingsplanering, uppgraderingskörning och -testning kommer att ta lång tid och arbete, särskilt för en uppgradering till Project Server 2019. Om du migrerar från Project Server 2010 till Project Server 2019 måste du först migrera till Project Server 2013, kontrollera dina data, sedan migrera till Project Server 2016 och sedan till Project Server 2019. Du kanske vill kontrollera med en Leverantör av Microsoft-lösningar under en tidsperiod och beräkna deras kostnad.

## <a name="migrate-to-project-online"></a>Migrera till Project Online

Om du väljer att migrera från Project Server 2010 till Project Online kan du följa de här anvisningarna för att migrera dina projektplansdata manuellt:

1. Spara dina projektplaner från Project Server 2010 till .mpp-format.

2. Med Project Professional 2016, Project Professional 2019 eller Project Online-skrivbordsklienten öppnar du varje MPP-fil och sparar och publicerar den sedan Project Online.

Du kan manuellt skapa PWA konfiguration i Project Online (till exempel återskapa alla nödvändiga anpassade fält eller företagskalendrar). Leverantörer av Microsoft-lösningar kan också hjälpa dig med den här processen.

Viktiga resurser:

|Resurs|Beskrivning|
|---|---|
|[Komma igång med Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Konfigurera och använda Project Online|
|[Tjänstbeskrivning för Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Information om de Project Online tillgängliga|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrera till en nyare lokal version av Project Server

Vi tror att du får ut mer och en bättre upplevelse genom att migrera till Project Online. Men vi förstår också att vissa organisationer måste ha projektdata lokalt. Om du väljer att behålla dina projektdata lokalt kan du migrera din Project Server 2010-miljö till Project Server 2013, Project Server 2016 eller Project Server 2019.

Om du inte kan migrera till Project Online rekommenderar vi att du migrerar till Project Server 2019. Project Server 2019 innehåller de flesta av de viktigaste funktionerna i tidigare versioner Project Server. Och den motsvarar bäst den upplevelse som finns med Project Online, även om vissa funktioner endast är tillgängliga i Project Online.

När du har slutfört varje migrering ska du kontrollera att dina data har migrerats korrekt.

> [!NOTE]
> Om du är begränsad till en lokal lösning och överväger att endast migrera till Project Server 2013 bör du vara försiktig så att den här versionen bara har några få års stöd kvar. Supportdatumet för Den Project Server 2013 med Service Pack den 13 oktober 2023. Mer information om supportdatum för slutet på livscykeln finns i [Microsofts produktlivscykelpolicy.](/lifecycle/)

### <a name="how-do-i-migrate-to-project-server-2019"></a>Hur migrerar jag till Project Server 2019?

De arkitektoniska skillnaderna mellan Project Server 2010 och Project Server 2019 förhindrar en direkt migreringväg. Du måste därför migrera dina Project Server 2010-data till varje efterföljande version av Project Server tills du kommer till Project Server 2019. Steg för uppgradering Project Server 2010 till Project Server 2019:

1. Migrera till Project Server 2013.

2. Migrera från Project 2013 till Project Server 2016.

3. Migrera från Project Server 2016 till Project Server 2019.

När du har slutfört varje migrering ska du kontrollera att dina data har migrerats korrekt.

### <a name="step-1-migrate-to-project-server-2013"></a>Steg 1: Migrera till Project Server 2013

Mer information om hur du uppgraderar från Project Server 2010 till Project Server 2013 finns i [Uppgradera till Project Server 2013.](/project/upgrade-to-project-server-2016)

Viktiga resurser:

- [Översikt över Project server 2013-uppgraderingen](/project/upgrade-to-project-server-2016)

  Få en översikt över hur du uppgraderar från Project Server 2010 till Project Server 2013.
- [Planera att uppgradera till Project Server 2013](/project/plan-for-upgrade-to-project-server-2016)

  Ta en titt på hur du planerar när du uppgraderar från Project Server 2010 till Project Server 2013, inklusive systemkrav.

- [Vad är nytt i Project Server 2013-uppgraderingen](/project/what-s-new-in-project-server-2013-upgrade) omfattar viktiga ändringar för den här versionen, inklusive:

  - Det finns ingen på plats-uppgradering till Project Server 2013. Metoden med databas bifoga är det enda sättet att uppgradera från Project Server 2010 till Project Server 2013.

  - Uppgraderingen kommer inte bara att konvertera dina Project Server 2010-data till Project Server 2013-format, utan kommer också att konsolidera de fyra Project Server 2010-databaserna till en Project Web App databas.

  - Både SharePoint Server 2013 och Project Server 2013 har ändrats till anspråksbaserad autentisering från den föregående versionen. Om du använder klassisk autentisering måste du tänka på detta när du uppgraderar. Mer information finns i [Migrera från klassiskt läge till anspråksbaserad autentisering i SharePoint 2013.](/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)

Viktiga resurser:

- [Översikt över uppgraderingsprocessen till Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)

- [Uppgradera dina databaser och Project Web App webbplatssamlingar (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project Diagram över serveruppgraderingsprocess](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Den stora databaskonsolideringen, Project Server 2010 till 2013-migrering i 8 enkla steg](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Steg 2: Migrera till Project Server 2016

När du har flyttat Project Server 2013 och verifierat att dina data har migrerats korrekt blir nästa steg att migrera till Project Server 2016.

Mer information finns i [Uppgradera till Project Server 2016](/Project/upgrade-to-project-server-2016).

Viktiga resurser:

- [Översikt över Project Server 2016 uppgraderingsprocessen](/Project/overview-of-the-project-server-2016-upgrade-process)

  Förstå vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016.

- [Planera för uppgradering till Project Server 2016](/Project/plan-for-upgrade-to-project-server-2016)

  Ta en titt på vad du bör tänka på när du planerar en uppgradering Project Server 2013 och Project Server 2016.

[Det du behöver veta om Project Server 2016 omfattar](/project/plan-for-upgrade-to-project-server-2016#thingknow) viktiga ändringar för uppgradering till den här versionen, bland annat:

- När du skapar Project Server 2016 miljö är installationsfilerna Project Server 2016 inkluderas i SharePoint Server 2016. Mer information finns i [Distribuera Project Server 2016](/project/deploy-project-server-2016).

- Resursplaner är inaktuella i Project Server 2016. Dina Project Server 2013-resursplaner migreras till Resurs åtaganden i Project Server 2016 och i Project Online. Mer information [finns i Översikt: Resurs](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) åtaganden.

### <a name="step-3-migrate-to-project-server-2019"></a>Steg 3: Migrera till Project Server 2019

När du migrerat till Project Server 2016 och verifierat att dina data har migrerats korrekt blir nästa steg att migrera dina data till Project Server 2019.

Mer information om vad du behöver göra för att uppgradera från Project Server 2016 till Project Server 2019 finns i [Uppgradera till Project Server 2019.](/Project/upgrade-to-project-server-2016)

Viktiga resurser:

- [Översikt över Project server 2019-uppgraderingen](/project/overview-of-the-project-server-2019-upgrade-process)

  Få en bra förståelse för vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016.

- [Planera för uppgradering till Project Server 2019](/project/plan-for-upgrade-to-project-server-2019)

  Ta en titt på överväganden vid planeringen av uppgradering Project Server 2016 till Project Server 2019.

- [Saker du behöver veta om Project Server 2019-uppgraderingen](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>Läs mer om viktiga ändringar när du uppgraderar till den här versionen, bland annat:

  - Under uppgraderingen migreras dina data från din Project Server 2016 till innehållsdatabasen SharePoint Server 2019 Innehåll.  Project Server 2019 skapar inte längre en egen Project i servergruppen SharePoint Server.

  - Efter uppgraderingen bör du vara medveten om flera ändringar i Project Web App.  Mer information finns [i Vad är nytt i Project Server 2019.](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)

**Andra resurser:**

- [Project Online Tjänstbeskrivningar](/office365/servicedescriptions/project-online-service-description/project-online-service-description): Se vilka portfoliohanteringsfunktioner som ingår i Project Server 2016 och Project Online Premium.

- [Microsoft Office Project Portfolio Server 2010-migrering](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Sammanfattning av alternativ för Office 2010 klient och servrar och Windows 7

En visuell sammanfattning av alternativen för uppgradering, migrering och flytt till molnet för Office 2010-klienter och -servrar och Windows 7 finns i slutet av [supportaffischen](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Supporten för Office 2010-klienter och -servrar och Windows 7-affisch](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Den här affischen illustrerar de olika sätt du kan gå för att undvika att supporten för Office 2010-klient- och serverprodukterna och Windows 7 avslutas, med föredragen sökvägar och supportalternativ i Microsoft 365 Enterprise markerat.

Du kan också [ladda ned](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) den här affischen och skriva ut den i letter-, legal- eller tabloidformat (11 x 17).

## <a name="related-topics"></a>Relaterade ämnen

[Uppgradering från SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Uppgradera från Office 2010-servrar och -klienter](upgrade-from-office-2010-servers-and-products.md)
