---
title: Översikt över supporten som upphör för Project Server 2007
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
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
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: Supporten för Project Server 2007, Project Portfolio Server och Project 2007 upphörde den 10 oktober 2017. Använd den här artikeln för att planera uppgraderingen.
ms.openlocfilehash: 12447eb2a021b3f92e3557b2c3ea87e859841346
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927354"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Översikt över supporten som upphör för Project Server 2007

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Supporten för Office 2007-servrar och -program upphörde 2017, och du måste planera för migrering. Om du för närvarande använder Project Server 2007 och relaterade produkter bör du observera följande supportdatum:
  
|**Produkt**|**Supportdatum för slutet**|
|:-----|:-----|
|Project Server 2007  <br/> |10 oktober 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 oktober 2017  <br/> |
|Project 2007 Standard  <br/> |10 oktober 2017  <br/> |
|Project 2007 Professional  <br/> |10 oktober 2017  <br/> |
   
Mer information om Office 2007-servrar som kommer att gå tillbaka finns i Uppgradera från [Office 2007-servrar och klientprodukter.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-does-end-of-support-mean"></a>Vad innebär *slutet av supporten?*

De flesta Microsoft-produkter har en supportlivscykel under vilken de får nya funktioner, programkorrigeringar, säkerhetskorrigeringar och så vidare. En livscykel varar vanligtvis i tio år från produktens första version. Slutet av perioden kallas för slutet av supporten för produkten. Eftersom supporten för Project Server 2007 tog slut den 10 oktober 2017 tillhandahåller Microsoft inte längre:
  
- Teknisk support för problem som kan uppstå.
    
- Programkorrigeringar för problem som kan påverka servrars stabilitet och användbarhet.
    
- Säkerhetskorrigeringar för säkerhetsproblem som kan göra servern sårbar för säkerhetsbrister.
    
- Tidszonsuppdateringar.
    
Din installation av Project Server 2007 fortsätter att köras efter detta datum. På grund av ändringarna som anges tidigare rekommenderar vi dock starkt att du migrerar från Project Server 2007 så snart det är praktiskt möjligt.
  
## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Om du använder Project Server 2007 måste du utforska dina migreringsalternativ, som är:
  
- Migrera till Project Online
    
- Migrera till en nyare lokal version av Project Server (helst Project Server 2016)
    
|**Varför skulle jag föredra att migrera till Project Online**|**Varför skulle jag föredra att migrera till Project Server 2016**|
|:-----|:-----|
| Jag har mobila användare.  <br/> <br/>Kostnaderna för att migrera är ett betydande problem (maskinvara, programvara, timmar och arbete med att implementera). <br/><br/>  Efter migreringen är kostnaderna för att underhålla miljön ett stort problem (till exempel automatiska uppdateringar, garanterad drifttid och så vidare).  <br/> | Affärsregler hindrar mig från att använda mitt företag i molnet.<br/><br/>  Jag behöver kontrollera uppdateringarna av miljön.  |
   
> [!NOTE]
> Mer information om alternativ för att flytta från Office 2007-servrar finns i Resurser som hjälper dig att uppgradera från [Office 2007-servrar och -klienter.](upgrade-from-office-2007-servers-and-products.md) Observera att Project Server inte har stöd för en hybridkonfiguration, eftersom Project Server och Project Online inte kan dela samma resurspool. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Viktiga överväganden när du migrerar från Project Server 2007

Tänk på följande när du planerar att migrera från Project Server 2007:
  
- **Få hjälp från en Microsoft-partner** – Det kan vara svårt att uppgradera från Project Server 2007 och kräver stora förberedelser och planering. Det kan vara särskilt svårt om du inte var den som ursprungligen konfigurerade Project Server 2007. Som tur är finns det Microsoft-partner som kan hjälpa till, oavsett om du planerar att migrera till Project Server 2016 eller Project Online. Sök efter en Microsoft-partner som kan hjälpa dig med migreringen i [Microsoft Partner Center.](https://go.microsoft.com/fwlink/p/?linkid=841249) Sök på termen  *Gold Project and Portfolio Management om* du vill visa en lista över alla Microsoft-partner som är experter inom Project. 
    
- **Planera för anpassningarna** – Många av de anpassningar som du gjort i Project Server 2007-miljön kanske inte fungerar när du migrerar till Project Server 2016 eller Project Online. Det finns betydande skillnader i Project Server-arkitekturen mellan olika versioner. Vilka operativsystem, databasservrar och klientwebbläsare som stöds varierar också. Planera hur du testar eller återskapar anpassningarna i den nya miljön. Planering ger också ett bra tillfälle att överväga om varje anpassning fortfarande behövs. Mer information finns i [Skapa en plan för aktuella anpassningar under uppgraderingen till SharePoint 2013.](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013) 
    
- **Tid och tålamod –** Det krävs tid och arbete för att planera, utföra och testa uppgraderingen, särskilt om du uppgraderar till Project Server 2016. Om du till exempel migrerar från Project Server 2007 till Project Server 2016 måste du först migrera till Project Server 2010, kontrollera dina data och sedan göra samma sak när du migrerar till varje efterföljande version. Du kanske vill få uppskattningar av hur lång tid det kan ta och vad det kostar med en Microsoft-partner.
    
## <a name="migrate-to-project-online"></a>Migrera till Project Online

Om du väljer att migrera från Project Server 2007 till Project Online kan du göra följande för att migrera dina projektplansdata manuellt:
  
1. Spara dina projektplaner från Project Server 2003 till .mpp-format.
    
2. Öppna varje .mpp-fil i Project Professional 2013, Project Professional 2016 eller Project Online Desktop Client och spara och publicera den sedan i Project Online.
    
Du kan skapa din Microsoft Project Web App-konfiguration (PWA) manuellt i Project Online. Återskapa till exempel alla nödvändiga anpassade fält eller företagskalendrar. Microsoft-partner kan också hjälpa dig med den här processen.
  
Viktiga resurser:
  
|**Resurs**|**Beskrivning**|
|:-----|:-----|
|[Komma igång med Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Konfigurera och använda Project Online <br/> |
|[Tjänstbeskrivningar för Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |Information om de olika Project Online-abonnemangen som är tillgängliga för dig <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrera till en nyare lokal version av Project Server

Vi tror att du får ut mer och en bättre upplevelse genom att migrera till Project Online. Men vi förstår också att vissa organisationer måste ha projektdata i en lokal miljö. Om du väljer att behålla dina projektdata lokalt kan du migrera din Project Server 2007-miljö till Project Server 2010, Project Server 2013 eller Project Server 2016.
  
Om du inte kan migrera till Project Online rekommenderar vi att du migrerar till Project Server 2016. Project Server 2016 innehåller alla funktioner från tidigare versioner av Project Server. Den motsvarar bäst den upplevelse du kan få med Project Online, även om vissa funktioner endast är tillgängliga i Project Online.
  
Efter varje migrering bör du kontrollera att dina data har migrerats korrekt.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Hur migrerar jag till Project Server 2016?

De arkitektoniska skillnaderna mellan Project Server 2007 och Project Server 2016 förhindrar en direkt migreringväg. Du måste alltså migrera dina Project Server 2007-data till varje efterföljande version av Project Server tills du kommer till Project Server 2016.
  
Följ de här stegen för Project Server 2016:
  
1. Migrera från Project Server 2007 till Project Server 2010.
    
2. Migrera från Project Serve 2010 till Project Server 2013.
    
3. Migrera från Project Server 2013 till Project Server 2016.
    
Efter varje migrering kontrollerar du att dina data har migrerats korrekt.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Steg 1: Migrera från Project Server 2007 till Project Server 2010

En omfattande beskrivning av vad du behöver göra för att uppgradera från Project Server 2007 till Project Server 2010 finns i Uppgradera till [Project Server 2010.](/previous-versions/office/project-server-2010/gg502590(v=office.14))
  
Viktiga resurser:
  
|**Resurs**|**Beskrivning**|
|:-----|:-----|
|[Uppgraderingsöversikt för Project Server 2010](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |En bra vy över vad du behöver göra för att uppgradera från Project Server 2007 till Project Server 2010 <br/> |
|[Planera för uppgradering till Project Server 2010](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |Att tänka på när du uppgraderar från Project Server 2007 till Project Server 2010, inklusive systemkrav  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Hur uppgraderar jag?

Mer information finns i [Uppgradera till Project Server 2010.](/previous-versions/office/project-server-2010/gg502590(v=office.14)) Men det är viktigt att förstå att det finns två olika metoder du kan använda för att uppgradera:
  
- **Uppgradering med databas bifoga:** Med den här metoden uppgraderas bara innehållet för miljön, inte konfigurationsinställningarna. Det är obligatoriskt om du uppgraderar från Office Project Server 2007 som är distribuerad på maskinvara som bara stöder 32-bitars serveroperativsystemet. Det finns två typer av uppgraderingsmetoder med databas bifoga:
    
  - Fullständig uppgradering med databas ***bifogar*** – Migrerar de projektdata som lagras i Office Project Server 2007-databaser, plus webbplatsdata för Microsoft Project Web App som lagras i en SharePoint-innehållsdatabas.
    
  - **Grundläggande uppgradering med *databas bifogad*** fil – Migrerar bara de projektdata som lagras i Project Server-databaser.
    
- **Uppgradering på plats:** Konfigurationsdata för servergruppen och allt innehåll i servergruppen uppgraderas på den befintliga maskinvaran i en fast ordning. När du startar uppgraderingen tar konfigurationen hela servergruppen offline. Webbplatserna och Webbplatserna för Microsoft Project Web App är inte tillgängliga förrän uppgraderingen är klar och sedan startar installationen om servern. När du påbörjar en på plats-uppgradering kan du inte pausa uppgraderingen eller gå tillbaka till den tidigare versionen. Det är bäst att göra en speglad bild av produktionsmiljön och uppgradera till den miljön på plats, inte i produktionsmiljön. 
    
Fler resurser:
  
- [SuperFlow för Microsoft Project Server 2010-uppgradering](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Migrering från Project Server 2007 till Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Uppgraderingsöverväganden för Project Web App-webbdelar](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Project Software Development Kit (SDK)](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>Steg 2: Migrera till Project Server 2013

När du har verifierat att dina data har migrerats är nästa steg att migrera till Project Server 2013.
  
En omfattande beskrivning av vad du behöver göra för att uppgradera från Project Server 2010 till Project Server 2013 finns i Uppgradera till [Project Server 2013.](/project/upgrade-to-project-server-2016) 
  
Viktiga resurser:
  
|**Resurs**|**Beskrivning**|
|:-----|:-----|
|[Översikt över uppgraderingsprocessen för Project Server 2013](/project/upgrade-to-project-server-2016) <br/> |Översikt över vad du behöver göra för att uppgradera från Project Server 2010 till Project Server 2013  <br/> |
|[Planera att uppgradera till Project Server 2013](/project/plan-for-upgrade-to-project-server-2016) <br/> |Att tänka på när du uppgraderar från Project Server 2010 till Project Server 2013, inklusive systemkrav <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Saker du bör veta om att uppgradera till den här versionen

[I artikeln om vad som är nytt i Project Server 2013-uppgraderingen](/project/what-s-new-in-project-server-2013-upgrade) beskrivs viktiga ändringar för uppgradering för den här versionen. De mest märkbara är: 
  
- Det finns ingen på plats-uppgradering till Project Server 2013. Metoden med databas bifoga är den enda metod som stöds för uppgradering från Project Server 2010 till Project Server 2013.
    
- Uppgraderingen kommer inte bara att konvertera dina Project Server 2010-data till Project Server 2013-formatet, utan kommer också att konsolidera de fyra Project Server 2010-databaserna till en enda Project Web App-databas.
    
- I 2013-versionerna ändrades både SharePoint Server och Project Server till anspråksbaserad autentisering. Om du använder klassisk autentisering måste du tänka på den här faktorn för uppgraderingen. Mer information finns i [Migrera från klassiskt läge till anspråksbaserad autentisering i SharePoint 2013.](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server)
    
Fler resurser:
  
- [Översikt över uppgraderingsprocessen till Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [Uppgradera dina databaser och webbplatssamlingar för Project Web App (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Diagram över uppgraderingsprocessen för Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Den stora databaskonsolideringen, Project Server 2010 till 2013-migrering i 8 enkla steg](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Steg 3: Migrera till Project Server 2016

När du har verifierat att dina data har migrerats är nästa steg att migrera till Project Server 2016.
  
En fullständig beskrivning av vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016 finns i Uppgradera till [Project Server 2016.](//project/upgrading-to-project-server-2016)
  
Viktiga resurser:
  
|**Resurs**|**Beskrivning**|
|:-----|:-----|
|[Översikt över uppgraderingsprocessen för Project Server 2016](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |Översikt över vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016 <br/> |
|[Planera för uppgradering till Project Server 2016](/project/plan-for-upgrade-to-project-server-2016) <br/> |Överväganden vid uppgradering från Project Server 2013 till Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Saker du bör veta om att uppgradera till den här versionen

[Information om saker du behöver veta om Project Server 2016-uppgraderingen](/project/plan-for-upgrade-to-project-server-2016) innebär att du får information om några viktiga uppgraderingsändringar för den här versionen, bland annat:
  
- När du skapar project server 2016-miljön som du ska migrera dina Project Server 2013-data till, inkluderas installationsfilerna för Project Server 2016 i SharePoint Server 2016. Mer information finns i [Distribuera Project Server 2016.](/project/deploy-project-server-2016)
    
- Resursplaner är inaktuella i Project Server 2016. Dina Project Server 2013-resursplaner migreras till Resurs åtaganden i Project Server 2016 och i Project Online. Mer information [finns i Översikt: Resurs](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) åtaganden. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrera från Portfolio Server 2007

Project Portfolio Server 2007 användes med Project Server 2007 för portföljstrategi, prioritering och optimering. Inga ytterligare versioner av Project Portfolio Server har skapats efter den här versionen. Portfoliohanteringsfunktioner är emellertid tillgängliga i Project Server 2016 och Premium-versionen av Project Online. Men data från Project Portfolio Server 2007 kan inte migreras till vare sig den ena eller den andra. Data som affärsdrivrutiner måste återskapas.
  
Andra resurser:
  
- [Tjänstbeskrivningar för Project Online:](/office365/servicedescriptions/project-online-service-description/project-online-service-description) Se vilka portfoliohanteringsfunktioner som ingår i Project Server 2016 och Project Online Premium.
    
- [Migreringsguide för Microsoft Office Project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Relaterade ämnen

[Översikt över slutet på supporten för SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Resurser som hjälper dig att uppgradera från Office 2007-servrar och -klienter](upgrade-from-office-2007-servers-and-products.md)
