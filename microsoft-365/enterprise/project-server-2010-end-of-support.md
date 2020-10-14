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
ms.openlocfilehash: 2cf18c5e91c095c92230a33f1b8a19fa26840777
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464330"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 slut på support översikt

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Project Server 2010 når supporten den **13 April 2021**. Detta datum har förlängts från föregående slut av support dagen den 13 oktober 2020. Om du för närvarande använder Project Server 2010 ska du tänka på att dessa andra relaterade produkter har följande slut på support datum:

|Produkt |Slut på support datumet|
|---|---|
|Project 2010-standard|Den 13 oktober 2020|
|Project 2010 Professional|Den 13 oktober 2020|

Mer information om Office 2010-servrar som når support finns i [Uppgradera från Office 2010-servrar och-klient produkter](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>Vad innebär slut på support?

Project Server, till exempel nästan alla Microsoft-produkter, har en support livs cykel under vilken vi tillhandahåller nya funktioner, fel korrigeringar och säkerhets uppdateringar. Denna livs cykel räcker normalt i 10 år från datumet för produktens första utgivning och slutet av den här livs cykeln kallas produkt Supportens slut. När Project Server 2010 når Supportens slut den 13 april 2021 kommer Microsoft inte längre att tillhandahålla:

- Teknisk support för problem som kan uppstå.

- Program korrigeringar för problem som upptäcks och som kan påverka serverns stabilitet och användbarhet.

- Säkerhets korrigeringar för säkerhets problem som upptäcks och som kan göra servern sårbar för säkerhets brott.

- Tids zons uppdateringar.

Din installation av Project Server 2010 fortsätter att köras efter detta datum. Vi rekommenderar att du migrerar från Project Server 2010 så snart som möjligt.

## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Om du använder Project Server 2010 måste du utforska alternativen för migrering, som är:

- Migrera till Project Online

- Migrera till en nyare lokal version av Project Server (helst Project Server 2019).

Här är de två sökvägar du kan vidta för att undvika att stöd saknas för Project Server 2010.

![Uppgraderings vägar för Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Varför skulle jag föredra att migrera till Project Server 2019?|Varför skulle jag föredra att migrera till Project Online?|
|---|---|
|Företags regler begränsar mig från att arbeta mitt företag i molnet.  <br/>  Jag behöver kontroll över uppdateringar av min miljö.|Jag har mobila användare eller fjärran vändare.  <br/>  Kostnader för att migrera lokala servrar är en stor angelägenhet (maskin vara, program vara, tid och ansträngning att genomföra).  <br/>  Efter migreringen är kostnader för att underhålla min miljö en stor angelägenhet (till exempel automatiska uppdateringar, garanterad drifts tid osv.).|

> [!NOTE]
> Mer information om alternativ för att flytta från dina Office 2010-servrar finns i [resurser som hjälper dig att uppgradera från office 2010-servrar och-klienter](upgrade-from-office-2010-servers-and-products.md). Observera att Project Server inte stöder en hybrid konfiguration eftersom Project Server och Project Online inte kan dela samma resurspool.

### <a name="what-are-my-options-for-project-client"></a>Vilka är mina alternativ för Project-klienten?

Om du använder Project Professional 2010 eller Project Standard 2010 och vill utforska alternativen för migrering kan du välja mellan:

- Flytta till en nyare version av Project Professional eller Project Standard.
- Flytta till en online-lösning, till exempel Project Online eller Project för webben.

#### <a name="moving-to-a-newer-version-of-project-client"></a>Flytta till en nyare version av Project-klienten

Om du migrerar från Project Standard 2010 kan du migrera till en nyare version av Project Standard (Project Standard 2016 eller Project Standard 2019).  Vi rekommenderar att du flyttar till den senaste versionen för att kunna använda de senaste funktionerna. Om du migrerar till en mindre aktuell version (Project Standard 2016) innebär det att du måste migrera från den här versionen när support datumet uppfylls.

Om du migrerar från Project Professional 2010 kan du till och med välja att migrera till en nyare version (Project Professional 2019 eller Project Professional 2016). Vi rekommenderar att du flyttar till den senaste versionen om det är möjligt.  Om du använder Project Professional för att ansluta till Project Server bör du kontrol lera att du migrerar till en version av Project Professional som stöds för att ansluta till den version av Project Server som du använder.

Project Professional 2010-användare kan också välja att migrera till Project Online-klienten. Det är en programbaserad version av Project Professional 2019 och ingår i Project plan 3-och Project abonnemang 5-prenumerationer.

#### <a name="moving-to-an-online-solution"></a>Flytta till en online-lösning

Du kan också välja att migrera från Project Professional 2010 eller Project Standard 2010 till projektets prenumerations online-lösningar. Både Project-abonnemang 3 och abonnemang 5 inkluderar Project Online och det senaste moln erbjudandet, [Project för webben](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Båda erbjuder ett antal nya funktioner som är värda att utforska.

Mer information om funktioner som ingår i både och även projekt planerings licenser som de ingår i finns i Beskrivning av [Microsoft Project-tjänsten](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2010"></a>Viktigt att tänka på när du planerar att migrera från Project Server 2010

Du måste tänka på följande när du planerar att migrera från Project Server 2010:

- **Få hjälp från en Microsoft Solution-leverantör** – uppgradering från Project Server 2010 kan vara en utmaning och kräver förberedelser och planering. Det kan vara särskilt svårt om du inte var den som är konfigurerad för att installera och konfigurera Project Server 2010. Som tur är, det finns Microsoft Solution providers som du kan göra till en boende, oavsett om du planerar att migrera till Project Server 2019 eller Project Online. Du kan söka efter en Microsoft Solution-leverantör för att få hjälp med migreringen i [Microsoft Solution Provider Center](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Planera för dina anpassningar** -Tänk på att många av de anpassningar som du har arbetat med i project Server 2010-miljön kanske inte fungerar när du migrerar till project Server 2019 eller Project Online. Det finns stora skillnader i Project Server-arkitekturen mellan versioner, samt nödvändiga operativ system, databas servrar och klient webbläsare som stöds för att fungera med den nyare versionen. Få en plan på plats för hur du kan testa eller återskapa anpassningarna som behövs i din nya miljö. Planering för din uppgradering kommer också att vara en god chans att kontrol lera om en viss anpassning behövs när du går vidare. [Skapa en plan för aktuella anpassningar under uppgradering till SharePoint 2013]( https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013) har lite allmän information om utvärdering och planering av dina aktuella anpassningar när du uppgraderar.

- **Tid och tålamod** -uppgradering, exekvering och testning tar mycket tid och ansträngning, särskilt om du uppgraderar till Project Server 2019. Om du till exempel migrerar från Project Server 2010 till Project Server 2019 måste du först migrera från Project Server 2010 till Project Server 2013 och sedan kontrol lera dina data och sedan göra samma sak när du migrerar till varje senare version (till Project Server 2016 och sedan till Project Server 2019). Det kan vara bra att kontrol lera om du har en Microsoft Solution Provider som jämför dina beräknade kostnader med deras uppskattningar av hur lång tid det tar för dem att göra det och hur mycket det kostar.

## <a name="migrate-to-project-online"></a>Migrera till Project Online

Om du väljer att migrera från Project Server 2010 till Project Online kan du göra följande för att manuellt migrera dina projekt Plans data:

1. Spara dina projektplaner från Project Server 2010 till. MPP-format.

2. Använd Project Professional 2016, Project Professional 2019 eller Project Online-klienten, öppna alla. mpp-filer och spara och publicera dem i Project Online.

Du kan skapa din PWA-konfiguration manuellt i Project Online (om du till exempel vill skapa eventuella anpassade fält eller företags kalendrar). Microsoft Solution providers kan också hjälpa dig med detta.

Viktiga resurser:

|Resurspool|Beskrivning|
|---|---|
|[Komma igång med Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Hur du installerar och använder Project Online.|
|[Tjänstbeskrivning för Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Information om de olika Project Online-abonnemangen som är tillgängliga för dig.|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrera till en nyare lokal version av Project Server

Vi tror att du kan nå det bästa värdet och användar upplevelsen genom att migrera till Project Online, men vi förstår också att vissa organisationer måste ha projekt data i en lokal miljö. Om du väljer att hålla dina Project-data lokala kan du migrera din Project Server 2010-miljö till Project Server 2013, Project Server 2016 eller Project Server 2019.

Vi rekommenderar att du migrerar till Project Server 2019 om du inte kan migrera till Project Online. Project Server 2019 innehåller de flesta nycklar som är de funktioner och framsteg som ingår i tidigare versioner av Project Server, och det stämmer närmast de funktioner som är tillgängliga med Project Online

När du har slutfört varje migrering bör du kontrol lera att dina data har migrerats.

> [!NOTE]
> Om du funderar på att bara migrera till Project Server 2013 om du är begränsad till en lokal lösning är det viktigt att Observera att det bara har några fler års support kvar. Project Server 2013 med Service Pack 2 slut på support datumet är 10/13/2023. Mer information om slut på support datum finns i [Microsofts produkt livs cykel policy](https://go.microsoft.com/fwlink/p/?linkid=842066).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Hur migrerar jag till Project Server 2019?

Arkitekturen mellan Project Server 2010 och Project Server 2019 förhindrar en direkt migrering. Det innebär att du måste migrera dina Project Server 2010-data till nästa efterföljande version av Project Server tills du uppgraderar till Project Server 2019.

Du måste göra följande för att uppgradera Project Server 2010 till Project Server 2019:

1. Migrera till Project Server 2013.

2. Migrera från Project servar 2013 till Project Server 2016.

3. Migrera från Project Server 2016 till Project Server 2019.

När du har slutfört varje migrering bör du kontrol lera att dina data har migrerats.


### <a name="step-1-migrate-to-project-server-2013"></a>Steg 1: migrera till Project Server 2013

Ditt första steg med att migrera Project Server 2010-data till Project Server 2019 är att först migrera till Project Server 2013.

Mer information om vad du behöver göra för att uppgradera från Project Server 2010 till Project Server 2013 finns i [Uppgradera till Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822).

Viktiga resurser:

- [Översikt över uppgraderings processen för Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Läs mer om vad du behöver göra för att uppgradera från Project Server 2010 till Project Server 2013.
- [Planera att uppgradera till Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Titta på de överväganden du behöver göra när du uppgraderar från Project Server 2010 till Project Server 2013, inklusive system krav.

[Nyheter i 2013-uppgraderingen för Project Server](https://go.microsoft.com/fwlink/p/?linkid=841824) visar en del viktiga ändringar för uppgraderingen för den här versionen, som är viktigast:

- Det finns ingen uppgradering på plats för Project Server 2013. Metoden databas koppling är den enda metod som stöds för uppgradering från Project Server 2010 till Project Server 2013.

- Uppgraderings processen konverterar inte bara Project Server 2010-data till Project Server 2013-format, men den sammanlänkas också de fyra Project Server 2010-databaserna till en enda Project Web App-databas.

- Både SharePoint Server 2013 och Project Server 2013 ändras till anspråksbaserad auktorisering från den föregående versionen. Du måste tänka på när du uppgraderar om du använder klassisk behörighet. Mer information finns i [Migrera från klassiskt läge till anspråksbaserad identifiering i SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Viktiga resurser:

- [Översikt över uppgraderings processen till Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Uppgradera dina databaser och webbplats samlingar för Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Microsoft Project Server-uppgraderings process diagram](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Den fantastiska databas konsolideringen, Project Server 2010 till 2013-migrering i 8 enkla steg](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Steg 2: migrera till Project Server 2016

När du har migrerat till Project Server 2013 och kontrollerat att dina data har migrerats, är nästa steg att migrera dina data till Project Server 2016.

Mer information om vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016 finns i [Uppgradera till Project server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Viktiga resurser:

- [Översikt över uppgraderings processen för Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Läs mer om vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016.

- [Planera för uppgradering till Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Titta på de överväganden du behöver göra när du uppgraderar från Project Server 2013 till Project Server 2016.

[Saker du behöver veta om Project Server 2016-uppgraderingen](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) ger dig viktiga ändringar för att uppgradera till den här versionen, som omfattar:

- När du skapar din Project Server 2016-miljö som du migrerar dina Project Server 2013-data till kan du tänka på att Project Server 2016-installationsfilerna ingår i SharePoint Server 2016. Mer information finns i [distribuera Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).

- Resurs planer är föråldrade i Project Server 2016. Resurs abonnemang för Project Server 2013 migreras till resurs åtaganden i Project Server 2016 och i Project Online. Se [Översikt: eventuella resurs åtaganden](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) för mer information.

### <a name="step-3-migrate-to-project-server-2019"></a>Steg 3: migrera till Project Server 2019

När du har migrerat till Project Server 2016 och kontrollerat att dina data har migrerats, är nästa steg att migrera dina data till Project Server 2019.

Mer information om vad du behöver göra för att uppgradera från Project Server 2016 till Project Server 2019 finns i [Uppgradera till Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Viktiga resurser:

- [Översikt över uppgraderings processen för Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Läs mer om vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016.

- [Planera för uppgradering till Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Titta på de överväganden du behöver göra när du uppgraderar från Project Server 2016 till Project Server 2019.

[Saker du behöver veta om Project Server 2019-uppgraderingen](https://go.microsoft.com/fwlink/p/?linkid=841827) ger dig viktiga ändringar för att uppgradera till den här versionen, som omfattar:

- Uppgraderings processen migrerar data från din Project Server 2016-databas till SharePoint Server 2019-innehålls databasen.  Project Server 2019 kommer inte längre att skapa en egen Project Server-databas i SharePoint Server-gruppen.

- Efter uppgraderingen bör du tänka på flera ändringar i Project Web App.  En beskrivning av dessa finns i [Nyheter i Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Andra resurser**:

- [Beskrivningar för Project Online-tjänster](https://go.microsoft.com/fwlink/p/?linkid=841280): se de funktioner för portfölj hantering som ingår i project Server 2016 och Project Online Premium.

- [Migreringsguiden för Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Översikt över alternativ för Office 2010-klient och servrar och Windows 7

En visuell Sammanfattning av alternativen uppgradera, migrera och flytta till moln för Office 2010-klienter och-servrar och Windows 7 finns i avsnittet [support affisch](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Bild på affischen för supportens upphörande för Office 2010-klienter/servrar och Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Den här affischen är ett snabbt sätt att förstå de olika vägarna som du kan vidta för att förhindra att Office 2010-klient och Server produkter och Windows 7 når supporten, med önskade sökvägar och alternativ support i Microsoft 365 Enterprise markerat.

Du kan också [Ladda ned](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) den här affischen och skriva ut den i Letter-, Legal-och Tabloid-format (11 x 17).

## <a name="related-topics"></a>Relaterade ämnen

[Uppgraderar från SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Uppgradera från Office 2010-servrar och -klienter](upgrade-from-office-2010-servers-and-products.md)
