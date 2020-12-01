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
description: Den 10 oktober 2017 har stöd för Project Server 2007, Project Portfolio Server och Project 2007. Använd den här artikeln för att planera uppgraderingen nu.
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519805"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Översikt över supporten som upphör för Project Server 2007

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Stöd upphörde för Office 2007-servrar och-program i 2017 och du måste överväga abonnemang för migrering. Om du redan använder Project Server 2007 och relaterade produkter bör du tänka på följande slut för support datum:
  
|**Produkt**|**Slut på support datumet**|
|:-----|:-----|
|Project Server 2007  <br/> |10 oktober 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 oktober 2017  <br/> |
|Project 2007-standard  <br/> |10 oktober 2017  <br/> |
|Project 2007 Professional  <br/> |10 oktober 2017  <br/> |
   
Mer information om Office 2007-servrar som kommer att dras tillbaka finns i [Uppgradera från Office 2007-servrar och-klient produkter](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>Vad innebär *slut på support* ?

De flesta Microsoft-produkter har en support livs cykel under vilken de får nya funktioner, korrigeringar, säkerhets korrigeringar och så vidare. Denna livs cykel räcker vanligt vis i 10 år från produkten första gången. Slutet av livs cykeln kallas produkt Supportens slut. Eftersom Project Server 2007 nådde Supportens slut den 10 oktober 2017 tillhandahåller Microsoft inte längre:
  
- Teknisk support för problem som kan uppstå.
    
- Program korrigeringar för problem som kan påverka serverns stabilitet och användbarhet.
    
- Säkerhets korrigeringar för säkerhets problem som kan göra servern sårbar för säkerhets brott.
    
- Tids zons uppdateringar.
    
Din installation av Project Server 2007 fortsätter att köras efter detta datum. Vi rekommenderar att du migrerar från Project Server 2007 så snart som möjligt.
  
## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Om du använder Project Server 2007 måste du utforska alternativen för migrering, som är:
  
- Migrera till Project Online
    
- Migrera till en nyare lokal version av Project Server (helst Project Server 2016)
    
|**Varför skulle jag hellre migrera till Project Online**|**Varför skulle jag föredra att migrera till Project Server 2016**|
|:-----|:-----|
| Jag har mobila användare.  <br/> <br/>Kostnader att migrera är ett betydelsefullt problem (maskin vara, program vara, timmar och ansträngning att genomföra). <br/><br/>  Efter migreringen är kostnader för att underhålla min miljö ett huvud problem (till exempel automatiska uppdateringar, garanti drift tid och så vidare).  <br/> | Företags regler begränsar mig från att arbeta mitt företag i molnet.<br/><br/>  Jag behöver kontroll över uppdateringar av min miljö.  |
   
> [!NOTE]
> Mer information om alternativ för att flytta från dina Office 2007-servrar finns i [resurser som hjälper dig att uppgradera från office 2007-servrar och-klienter](upgrade-from-office-2007-servers-and-products.md). Observera att Project Server inte stöder en hybrid konfiguration eftersom Project Server och Project Online inte kan dela samma resurspool. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Viktigt att tänka på när du migrerar från Project Server 2007

Tänk på följande när du planerar att migrera från Project Server 2007:
  
- **Få hjälp från en Microsoft-partner** – uppgradering från Project Server 2007 kan vara utmanande och kräver förberedelser och planering. Det kan vara särskilt svårt om du inte har den person som installerade Project Server 2007 ursprungligen. Som tur är finns Microsoft-partners som kan hjälpa dig, oavsett om du planerar att migrera till Project Server 2016 eller Project Online. Sök efter en Microsoft-partner för att få hjälp med migreringen i [Microsoft Partner Center](https://go.microsoft.com/fwlink/p/?linkid=841249). Sök på termen  *guld projekt och portfölj hantering* för att visa en lista över alla Microsoft-partners som har kunskaper i Project. 
    
- **Planera för dina anpassningar** -många av de anpassningar som du har gjort i project Server 2007-miljön kanske inte fungerar när du migrerar till Project Server 2016 eller Project Online. Det finns väsentliga skillnader mellan olika versioner av Project Server-arkitekturen. De operativ system, databas servrar och klient webbläsare som stöds är också olika. Planera hur du ska testa eller återskapa dina anpassningar för den nya miljön. Planering ger också en god chans att överväga om varje anpassning fortfarande behövs. Mer information finns i [skapa en plan för aktuella anpassningar under uppgradering till SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061). 
    
- **Tid och tålamod** -uppgradering, utförande och testning tar tid och kraft, särskilt om du uppgraderar till Project Server 2016. Om du till exempel migrerar från Project Server 2007 till Project Server 2016 måste du först migrera till Project Server 2010, kontrol lera dina data och sedan göra samma sak när du migrerar till varje ny version. Du kanske vill kontrol lera med en Microsoft-partner för att få en uppskattning av hur lång tid det kommer att ta och vad det kommer att kosta.
    
## <a name="migrate-to-project-online"></a>Migrera till Project Online

Om du väljer att migrera från Project Server 2007 till Project Online kan du göra följande för att manuellt migrera dina projekt Plans data:
  
1. Spara dina projektplaner från Project Server 2003 till. MPP-format.
    
2. I Project Professional 2013, Project Professional 2016 eller Project Online-skrivbordet öppnar du varje. mpp-fil och sparar och publicerar den sedan i Project Online.
    
Du kan skapa din Microsoft Project Web App (PWA)-konfiguration manuellt i Project Online. Skapa till exempel de anpassade fälten eller företags kalendrarna igen. Microsoft-partners kan också hjälpa dig med den här processen.
  
Viktiga resurser:
  
|**Resurspool**|**Beskrivning**|
|:-----|:-----|
|[Komma igång med Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Konfigurera och använda Project Online <br/> |
|[Beskrivningar för Project Online-tjänster](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Information om de olika Project Online-abonnemangen som är tillgängliga för dig <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrera till en nyare lokal version av Project Server

Vi tror att du får bästa möjliga värde och användar upplevelse genom att migrera till Project Online. Men vi förstår också att vissa organisationer måste ha projekt data i en lokal miljö. Om du väljer att hålla dina Project-data lokala kan du migrera din Project Server 2007-miljö till Project Server 2010, Project Server 2013 eller Project Server 2016.
  
Om du inte kan migrera till Project Online rekommenderar vi att du migrerar till Project Server 2016. Project Server 2016 innehåller alla funktioner i tidigare versioner av Project Server. Det stämmer bäst med den upplevelse som är tillgänglig med Project Online, även om vissa funktioner endast är tillgängliga i Project Online.
  
Efter varje migrering bör du kontrol lera att dina data har migrerats.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Hur migrerar jag till Project Server 2016?

Arkitektur skillnader mellan Project Server 2007 och Project Server 2016 hindrar en direkt migrering. Därför måste du migrera dina Project Server 2007-data till varje ny version av Project Server tills du når Project Server 2016.
  
Följ de här anvisningarna för Project Server 2016:
  
1. Migrera från Project Server 2007 till Project Server 2010.
    
2. Migrera från Project servar 2010 till Project Server 2013.
    
3. Migrera från Project Server 2013 till Project Server 2016.
    
Kontrol lera att dina data har migrerats efter varje migrering.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Steg 1: Migrera från Project Server 2007 till Project Server 2010

En fullständig beskrivning av vad du måste göra för att uppgradera från Project Server 2007 till Project Server 2010 finns i [Uppgradera till Project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812).
  
Viktiga resurser:
  
|**Resurspool**|**Beskrivning**|
|:-----|:-----|
|[Uppgraderings översikt för Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |En högkvalitativ vy av vad du måste göra för att uppgradera från Project Server 2007 till Project Server 2010 <br/> |
|[Planera att uppgradera till Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Överväganden när du uppgraderar från Project Server 2007 till Project Server 2010, inklusive system krav  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Hur uppgraderar jag?

Mer information finns i [Uppgradera till Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812). Men det är viktigt att förstå att det finns två olika metoder att uppgradera:
  
- **Databas-koppla uppgradering:** Med den här metoden uppgraderas endast innehållet för din miljö, inte konfigurations inställningarna. Det är obligatoriskt om du uppgraderar från Office Project Server 2007 som är distribuerad på maskin vara som endast har stöd för ett 32-bitars serveroperativ system. Det finns två typer av databas-koppla uppgraderings metoder:
    
  - ***Fullständig uppgradering*** – migrera de projekt data som finns lagrade i Office Project Server 2007-databaserna, plus webbplats data för Microsoft Project Web App som lagras i en SharePoint-innehålls databas.
    
  - **Databas-bifogad *Core-uppgradering*** – migrerar bara de projekt data som finns lagrade i Project Server-databaserna.
    
- **På-plats-uppgradering**: konfigurations data för Server gruppen och allt innehåll i Server gruppen uppgraderas på den befintliga hård varu beställningen. När du startar uppgraderings processen kommer hela Server gruppen att vara offline. Webbplatserna webbplatser och Microsoft Project Web App är inte tillgängliga förrän uppgraderingen är klar och sedan startas servern om. När du har påbörjat en uppgradering på plats kan du inte pausa uppgraderingen eller återställa till den föregående versionen. Det bästa är att göra en speglad bild av din produktions miljö och sköta uppgraderingen till den här miljön, inte i din produktions miljö. 
    
Fler resurser:
  
- [Superflöde för uppgradering av Microsoft Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Migrering från Project Server 2007 till Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Uppgraderings överväganden för Project Web App-webbdelar](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Project Software Development Kit (SDK)](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Steg 2: migrera till Project Server 2013

Nästa steg är att migrera till Project Server 2013 när du har kontrollerat att dina data har migrerats.
  
En fullständig beskrivning av vad du måste göra för att uppgradera från Project Server 2010 till Project Server 2013 finns i [Uppgradera till Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822). 
  
Viktiga resurser:
  
|**Resurspool**|**Beskrivning**|
|:-----|:-----|
|[Översikt över uppgraderings processen för Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Översikt över vad du måste göra för att uppgradera från Project Server 2010 till Project Server 2013  <br/> |
|[Planera att uppgradera till Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Överväganden när du uppgraderar från Project Server 2010 till Project Server 2013, inklusive system krav <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Saker du bör veta om att uppgradera till den här versionen

[Nyheter i Project Server 2013-uppgraderingen](https://go.microsoft.com/fwlink/p/?linkid=841824) beskriver viktiga ändringar för uppgraderingen för den här versionen. De mest viktiga är: 
  
- Det finns ingen uppgradering på plats till Project Server 2013. Metoden databas koppling är den enda metod som stöds för uppgradering från Project Server 2010 till Project Server 2013.
    
- Uppgraderings processen konverterar inte bara Project Server 2010-data till Project Server 2013-format, men den sammanlänkas också de fyra Project Server 2010-databaserna till en enda Project Web App-databas.
    
- I 2013-versionerna ändras både SharePoint Server och Project Server till anspråksbaserad identifiering. Om du använder den klassiska autentiseringsprocessen måste du överväga denna faktor för uppgraderingen. Mer information finns i [Migrera från klassiskt läge till anspråksbaserad identifiering i SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825).
    
Fler resurser:
  
- [Översikt över uppgraderings processen till Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Uppgradera dina databaser och webbplats samlingar för Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Microsoft Project Server-uppgraderings process diagram](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Den fantastiska databas konsolideringen, Project Server 2010 till 2013-migrering i 8 enkla steg](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Steg 3: migrera till Project Server 2016

Nästa steg är att migrera till Project Server 2016 när du har kontrollerat att dina data har migrerats.
  
En fullständig beskrivning av vad du måste göra för att uppgradera från Project Server 2013 till Project Server 2016 finns i [Uppgradera till Project server 2016](https://docs.microsoft.com//project/upgrading-to-project-server-2016).
  
Viktiga resurser:
  
|**Resurspool**|**Beskrivning**|
|:-----|:-----|
|[Översikt över uppgraderings processen för Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Översikt över vad du måste göra för att uppgradera från Project Server 2013 till Project Server 2016 <br/> |
|[Planera för uppgradering till Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Överväganden vid planering uppgradering från Project Server 2013 till Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Saker du bör veta om att uppgradera till den här versionen

[Saker du behöver veta om Project Server 2016-uppgraderingen](https://go.microsoft.com/fwlink/p/?linkid=841827) ger dig viktiga ändringar för uppgradering för den här versionen, som omfattar:
  
- När du skapar din Project Server 2016-miljö som du migrerar dina Project Server 2013-data till är Project Server 2016-installationsfilerna inkluderade i SharePoint Server 2016. Mer information finns i [distribuera Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Resurs planer är föråldrade i Project Server 2016. Resurs abonnemang för Project Server 2013 migreras till resurs åtaganden i Project Server 2016 och i Project Online. Se [Översikt: eventuella resurs åtaganden](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) för mer information. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrera från Portfolio Server 2007

Project Portfolio Server 2007 användes med Project Server 2007 för portfölj strategi, prioritering och optimering. Ingen ytterligare version av Project Portfolio Server skapades efter den här versionen. Funktionerna för portfölj hantering finns i Project Server 2016 och Premium-versionen av Project Online. Men data från Project Portfolio Server 2007 kan inte migreras till. Data som affärs drivande faktorer måste återskapas.
  
Andra resurser:
  
- [Beskrivningar för Project Online-tjänster:](https://go.microsoft.com/fwlink/p/?linkid=841280) Se de funktioner för portfölj hantering som ingår i Project Server 2016 och Project Online Premium.
    
- [Migreringsguiden för Microsoft Office Project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Relaterade ämnen

[SharePoint Server 2007 slut på support översikt](sharepoint-2007-end-of-support.md)
  
[Resurser som hjälper dig att uppgradera från Office 2007-servrar och-klienter](upgrade-from-office-2007-servers-and-products.md)
  
