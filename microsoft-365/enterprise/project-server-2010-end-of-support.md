---
title: Support översikt för Project Server 2010
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
description: Support för Project Server 2010 upphör 13 april 2021. Använd den här artikeln som en guide för att uppgradera till Project Online eller en nyare version av Project Server lokalt.
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519709"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 slut på support översikt

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Project Server 2010 når supporten den **13 April 2021**. Detta datum utökades från föregående slut datum den 13 oktober 2020. Om du för närvarande använder Project Server 2010 ska du tänka på att dessa relaterade produkter har följande slut för support datum:

|Produkt |Slut på support datumet|
|---|---|
|Project 2010-standard|Den 13 oktober 2020|
|Project 2010 Professional|Den 13 oktober 2020|

Mer information om Supportens slut finns i [Uppgradera från Office 2010-servrar och-klient produkter](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>Vad innebär *slut på support* ?

Nästan alla Microsoft-produkter har en support livs cykel, under vilken de får nya funktioner, program korrigeringar och säkerhets uppdateringar. Denna livs cykel räcker vanligt vis i 10 år från produkten första gången. Slutet av livs cykeln kallas produkt Supportens slut. Efter att Project Server 2010 har nått Supportens slut den 13 april 2021, kommer Microsoft inte längre att tillhandahålla:

- Teknisk support för problem som kan uppstå.

- Program korrigeringar för problem som upptäcks och som kan påverka serverns stabilitet och användbarhet.

- Säkerhets korrigeringar för säkerhets problem som upptäcks och som kan göra servern sårbar för säkerhets brott.

- Tids zons uppdateringar.

Din installation av Project Server 2010 fortsätter att köras efter detta datum. Men på grund av ovanstående ändringar rekommenderar vi starkt att du migrerar från Project Server 2010 så snart som möjligt.

## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Alternativen för migrering är:

- Migrera till Project Online

- Migrera till en nyare lokal version av Project Server (helst Project Server 2019)

Här är de två sökvägar du kan vidta för att undvika att stöd saknas för Project Server 2010.

![Uppgraderings vägar för Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Varför skulle jag föredra att migrera till Project Server 2019?|Varför skulle jag föredra att migrera till Project Online?|
|---|---|
|Företags regler begränsar mig från att arbeta mitt företag i molnet.  <br/><br/>  Jag behöver kontroll över uppdateringar av min miljö.|Jag har mobila användare eller fjärran vändare.<br/><br/>  Kostnaderna för att migrera lokala servrar är avgörande (maskin vara, program vara, tid och ansträngning att implementera, och så vidare). <br/><br/>  Efter migreringen är kostnader för att underhålla min miljö ett problem (till exempel automatiska uppdateringar, garanterad drift tid och så vidare).|

> [!NOTE]
> Mer information om alternativen för migrering finns i [resurser som hjälper dig att uppgradera från Office 2010-servrar och-klienter](upgrade-from-office-2010-servers-and-products.md). Observera att Project Server inte stöder hybrid konfiguration eftersom Project Server och Project Online inte kan dela samma resurspool.

### <a name="what-are-my-options-for-project-client"></a>Vilka är mina alternativ för Project-klienten?

Om du använder Project Professional 2010 eller Project Standard 2010 är alternativen:

- Gå till en nyare version av Project Professional eller Project Standard
- Gå till en online-lösning, till exempel Project Online eller Project för webben

#### <a name="move-to-a-newer-version-of-project-client"></a>Gå till en nyare version av Project-klienten

Om du migrerar från Project Standard 2010 kan du flytta till en nyare version av Project Standard (Project Standard 2016 eller Project Standard 2019). Vi rekommenderar att du går till den senaste versionen för att kunna använda de senaste funktionerna. Om du migrerar till en mindre aktuell version (Project Standard 2016) måste du också migrera igen tidigare.

Om du migrerar från Project Professional 2010 kan du till och med flytta till en nyare version (Project Professional 2019 eller Project Professional 2016). Gå till den senaste versionen om det är möjligt. Om du använder Project Professional för att ansluta till Project Server bör du kontrol lera att du migrerar till en version av Project Professional som ansluter till den version av Project Server som du använder.

Project Professional 2010-användare kan även migrera till Project Online-skrivbordet, som är en prenumeration baserad version av Project Professional 2019. Det ingår i Project plan 3 och abonnemanget för Project 5.

#### <a name="move-to-an-online-solution"></a>Flytta till en online-lösning

Du kan också migrera från Project Professional 2010 eller Project Standard 2010 till en webbaserad online-lösning. Både Project-abonnemang 3 och abonnemang 5 inkluderar Project Online och det senaste moln erbjudandet, [Project för webben](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Båda erbjuder nya funktioner och fördelar som är värda att utforska.

Mer information om funktioner och licenser finns i [Beskrivning av Microsoft Project-tjänsten](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Viktigt att tänka på när du migrerar från Project Server 2010

Tänk på följande när du planerar att migrera från Project Server 2010:

- **Få hjälp från en Microsoft Solution-leverantör** – en uppgradering från Project Server 2010 kan vara en utmaning. Det kräver en mängd förberedelse och planering. Det kan vara särskilt svårt om du inte är den person som ursprungligen konfigurerade Project Server 2010. Microsoft Solution-leverantörer kan hjälpa dig, oavsett om du planerar att migrera till Project Server 2019 eller Project Online. Sök efter en lösnings leverantör i [Microsoft Solution Provider Center](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Planera anpassningar** – anpassningar i 2010-miljön för Project Server kanske inte fungerar när du migrerar till Project Server 2019 eller Project Online. Det finns väsentliga skillnader mellan olika versioner av Project Server-arkitekturen. Dessutom är nödvändiga operativ system, databas servrar och webbläsare som fungerar tillsammans med olika versioner. Få en plan för att testa eller återskapa dina anpassningar i den nya miljön. Gör så här för att avgöra om specifika anpassningar fortfarande behövs. Mer information finns i [skapa en plan för aktuella anpassningar under uppgradering till SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- **Tid och tålamod** -uppgradering, utförande och testning tar avsevärd tid och ansträngning, särskilt för uppgradering till Project Server 2019. Om du migrerar från Project Server 2010 till Project Server 2019 måste du först migrera till Project Server 2013, kontrol lera dina data, sedan migrera till Project Server 2016 och sedan till Project Server 2019. Det kan vara en bra idé att kontrol lera om det finns en tidsram och uppskattad kostnad för dem.

## <a name="migrate-to-project-online"></a>Migrera till Project Online

Om du väljer att migrera från Project Server 2010 till Project Online kan du följa de här stegen för att migrera dina projekt Plans data manuellt:

1. Spara dina projektplaner från Project Server 2010 till. MPP-format.

2. Använd Project Professional 2016, Project Professional 2019 eller Project Online-klienten, öppna alla. mpp-filer och spara och publicera dem i Project Online.

Du kan skapa din PWA-konfiguration manuellt i Project Online (om du till exempel vill skapa eventuella anpassade fält eller företags kalendrar). Microsoft Solution providers kan också hjälpa dig med den här processen.

Viktiga resurser:

|Resurspool|Beskrivning|
|---|---|
|[Komma igång med Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Konfigurera och använda Project Online|
|[Tjänstbeskrivning för Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Information om de olika Project Online-abonnemangen tillgängliga|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrera till en nyare lokal version av Project Server

Vi tror att du får bästa möjliga värde och användar upplevelse genom att migrera till Project Online. Men vi förstår också att vissa organisationer måste hålla projekt data lokala. Om du väljer att hålla dina Project-data lokala kan du migrera din Project Server 2010-miljö till Project Server 2013, Project Server 2016 eller Project Server 2019.

Om du inte kan migrera till Project Online rekommenderar vi att du migrerar till Project Server 2019. Project Server 2019 innehåller de flesta viktigaste funktionerna i tidigare versioner av Project Server. Och det stämmer bäst med den upplevelse som är tillgänglig med Project Online, även om vissa funktioner endast är tillgängliga i Project Online.

När du är klar med migreringen kontrollerar du att dina data har migrerats.

> [!NOTE]
> Om du är begränsad till en lokal lösning och funderar på att bara migrera till Project Server 2013, är det bara att ha några fler års support kvar i den här versionen. Slut på support datumet för Project Server 2013 med Service Pack 2 oktober 2023. Mer information om slutdatum finns i [Microsofts produkt livs cykel policy](https://go.microsoft.com/fwlink/p/?linkid=842066).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Hur migrerar jag till Project Server 2019?

Arkitekturen mellan Project Server 2010 och Project Server 2019 hindrar en direkt migrering. Därför måste du migrera dina Project Server 2010-data till varje ny version av Project Server tills du når Project Server 2019. Så här uppgraderar du Project Server 2010 till Project Server 2019:

1. Migrera till Project Server 2013.

2. Migrera från Project servar 2013 till Project Server 2016.

3. Migrera från Project Server 2016 till Project Server 2019.

När du är klar med migreringen kontrollerar du att dina data har migrerats.

### <a name="step-1-migrate-to-project-server-2013"></a>Steg 1: migrera till Project Server 2013

Mer information om hur du uppgraderar från Project Server 2010 till Project Server 2013 finns i [Uppgradera till Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822).

Viktiga resurser:

- [Översikt över uppgraderings processen för Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Få en översikt över hur du uppgraderar från Project Server 2010 till Project Server 2013.
- [Planera att uppgradera till Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Titta på planeringsfrågor när du uppgraderar från Project Server 2010 till Project Server 2013, inklusive system krav.

- [Nyheter i Project Server 2013 uppgraderingen](https://go.microsoft.com/fwlink/p/?linkid=841824) täcker viktiga ändringar för den här versionen, inklusive:

   - Det finns ingen uppgradering på plats till Project Server 2013. Metoden databas koppling är det enda sättet att uppgradera från Project Server 2010 till Project Server 2013.

   - Uppgraderings processen konverterar inte bara Project Server 2010-data till Project Server 2013-format, men den sammanlänkas också de fyra Project Server 2010-databaserna till en enda Project Web App-databas.

   - Både SharePoint Server 2013 och Project Server 2013 ändras till anspråksbaserad auktorisering från den föregående versionen. Om du använder den klassiska autentiseringsprocessen måste du tänka på det när du uppgraderar. Mer information finns i [Migrera från klassiskt läge till anspråksbaserad identifiering i SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Viktiga resurser:

- [Översikt över uppgraderings processen till Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Uppgradera dina databaser och webbplats samlingar för Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Microsoft Project Server-uppgraderings process diagram](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Den fantastiska databas konsolideringen, Project Server 2010 till 2013-migrering i 8 enkla steg](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Steg 2: migrera till Project Server 2016

När du har flyttat till Project Server 2013 och kontrollerat att dina data har migrerats, är nästa steg att migrera till Project Server 2016.

Mer information finns i [Uppgradera till Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Viktiga resurser:

- [Översikt över uppgraderings processen för Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Få reda på vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016.

- [Planera för uppgradering till Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Se vad du kan göra när du uppgraderar från Project Server 2013 till Project Server 2016.

[Saker du måste känna till när du uppgraderar Project Server 2016](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) viktiga ändringar för uppgradering till den här versionen, till exempel:

- När du skapar en Project Server 2016-miljö kontrollerar du att installationsfilerna för Project Server 2016 ingår i SharePoint Server 2016. Mer information finns i [distribuera Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).

- Resurs planer är föråldrade i Project Server 2016. Resurs abonnemang för Project Server 2013 migreras till resurs åtaganden i Project Server 2016 och i Project Online. Se [Översikt: eventuella resurs åtaganden](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) för mer information.

### <a name="step-3-migrate-to-project-server-2019"></a>Steg 3: migrera till Project Server 2019

När du har migrerat till Project Server 2016 och kontrollerat att dina data har migrerats, är nästa steg att migrera dina data till Project Server 2019.

Information om vad du behöver göra för att uppgradera från Project Server 2016 till Project Server 2019 finns i [Uppgradera till Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Viktiga resurser:

- [Översikt över uppgraderings processen för Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Läs mer om vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016.

- [Planera för uppgradering till Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Titta på planeringsfrågor för uppgradering från Project Server 2016 till Project Server 2019.

- [Saker du behöver veta om Project Server 2019-uppgradering](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>Lär dig mer om viktiga ändringar för att uppgradera till den här versionen, till exempel:

   - Uppgraderings processen migrerar data från din Project Server 2016-databas till SharePoint Server 2019-innehålls databasen.  Project Server 2019 kommer inte längre att skapa en egen Project Server-databas i SharePoint Server-gruppen.

   - Efter uppgraderingen måste du ha flera ändringar i Project Web App.  Mer information finns i [Nyheter i Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Andra resurser**:

- [Beskrivningar för Project Online-tjänster](https://go.microsoft.com/fwlink/p/?linkid=841280): se de funktioner för portfölj hantering som ingår i project Server 2016 och Project Online Premium.

- [Migreringsguiden för Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Översikt över alternativ för Office 2010-klient och servrar och Windows 7

En visuell Sammanfattning av alternativen uppgradera, migrera och flytta till moln för Office 2010-klienter och-servrar och Windows 7 finns i avsnittet [support affisch](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Slut på support för Office 2010-klienter och-servrar och Windows 7-affisch](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Denna affisch visar de olika vägarna du kan vidta för att slippa support för Office 2010-klient och Server produkter och Windows 7, med önskade sökvägar och alternativ support i Microsoft 365 Enterprise markerat.

Du kan också [Ladda ned](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) den här affischen och skriva ut den i Letter-, Legal-och Tabloid-format (11 x 17).

## <a name="related-topics"></a>Relaterade ämnen

[Uppgraderar från SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Uppgradera från Office 2010-servrar och -klienter](upgrade-from-office-2010-servers-and-products.md)
