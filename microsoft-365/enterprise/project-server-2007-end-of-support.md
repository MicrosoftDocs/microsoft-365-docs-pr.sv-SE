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
ms.openlocfilehash: 81588f803813d0da938d709e93e26b7dadc3b993
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696700"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Översikt över supporten som upphör för Project Server 2007

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Stöd upphörde för Office 2007-servrar och-program i 2017 och du måste överväga abonnemang för migrering. Om du för närvarande använder Project Server 2007 ska du tänka på att den och de andra relaterade produkterna hade följande slut för support datum:
  
|**Produkt**|**Slut på support datumet**|
|:-----|:-----|
|Project Server 2007  <br/> |10 oktober 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 oktober 2017  <br/> |
|Project 2007-standard  <br/> |10 oktober 2017  <br/> |
|Project 2007 Professional  <br/> |10 oktober 2017  <br/> |
   
Mer information om Office 2007-servrar som kommer att dras tillbaka finns i [Uppgradera från Office 2007-servrar och-klient produkter](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>Vad innebär slut på support?

Project Server, till exempel nästan alla Microsoft-produkter, har en support livs cykel under vilken vi tillhandahåller nya funktioner, korrigeringar, säkerhets korrigeringar och så vidare. Denna livs cykel räcker normalt i 10 år från datumet för produktens första utgivning och slutet av den här livs cykeln kallas produkt Supportens slut. Eftersom Project Server 2007 nådde Supportens slut den 10 oktober 2017 tillhandahåller Microsoft inte längre:
  
- Teknisk support för problem som kan uppstå.
    
- Program korrigeringar för problem som upptäcks och som kan påverka serverns stabilitet och användbarhet.
    
- Säkerhets korrigeringar för säkerhets problem som upptäcks och som kan göra servern sårbar för säkerhets brott.
    
- Tids zons uppdateringar.
    
Din installation av Project Server 2007 fortsätter att köras efter detta datum. Vi rekommenderar att du migrerar från Project Server 2007 så snart som möjligt.
  
## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Om du använder Project Server 2007 måste du utforska alternativen för migrering, som är:
  
- Migrera till Project Online
    
- Migrera till en nyare lokal version av Project Server (helst Project Server 2016).
    
|**Varför skulle jag hellre migrera till Project Online**|**Varför skulle jag föredra att migrera till Project Server 2016**|
|:-----|:-----|
| Jag har mobila användare.  <br/>  Kostnader att migrera är en stor betydelse (maskin vara, program vara, tid och ansträngning att genomföra).  <br/>  Efter migreringen är kostnader för att underhålla min miljö en stor angelägenhet (till exempel automatiska uppdateringar, garanterad drifts tid osv.).  <br/> | Företags regler begränsar mig från att arbeta mitt företag i molnet.  <br/>  Jag behöver kontroll över uppdateringar av min miljö.  <br/> |
   
> [!NOTE]
> Mer information om alternativ för att flytta från dina Office 2007-servrar finns i [resurser som hjälper dig att uppgradera från office 2007-servrar och-klienter](upgrade-from-office-2007-servers-and-products.md). Observera att Project Server inte stöder en hybrid konfiguration eftersom Project Server och Project Online inte kan dela samma resurspool. 
  
## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2007"></a>Viktigt att tänka på när du planerar att migrera från Project Server 2007

Du måste tänka på följande när du planerar att migrera från Project Server 2007:
  
- **Få hjälp från en Microsoft-partner** – uppgradering från Project Server 2007 kan vara utmanande och kräver mycket förberedelse och planering. Det kan vara särskilt svårt om du inte var den som är konfigurerad för att installera och konfigurera Project Server 2007. Som tur är, det finns Microsoft-partners som du kan använda för att göra det till en boende, oavsett om du planerar att migrera till Project Server 2016 eller Project Online. Du kan söka efter en Microsoft-partner för att få hjälp med migreringen i [Microsoft Partner Center](https://go.microsoft.com/fwlink/p/?linkid=841249). Du kan hämta en lista över alla Microsoft-partner med expertis i Project genom att söka på termen  *Gold Project and portfölj hantering*  . 
    
- **Planera för dina anpassningar** -Tänk på att många av de anpassningar som du har arbetat med i project Server 2007-miljön kanske inte fungerar när du migrerar till project Server 2016 eller Project Online. Det finns stora skillnader i Project Server-arkitekturen mellan versioner, samt nödvändiga operativ system, databas servrar och klient webbläsare som stöds för att fungera med den nyare versionen. Få en plan på plats för hur du kan testa eller återskapa anpassningarna som behövs i din nya miljö. Planering för din uppgradering kommer också att vara en god chans att kontrol lera om en viss anpassning behövs när du går vidare. [Skapa en plan för aktuella anpassningar under uppgradering till SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061) har lite allmän information om utvärdering och planering av dina aktuella anpassningar när du uppgraderar. 
    
- **Tid och tålamod** -uppgradering, utförande och testning tar mycket tid och ansträngning, särskilt om du uppgraderar till Project Server 2016. Om du till exempel migrerar från Project Server 2007 till Project Server 2016 måste du först migrera från Project Server 2007 till Project Server 2010 och sedan kontrol lera dina data och sedan göra samma sak när du migrerar till varje ny version. Du kanske vill kontrol lera med en Microsoft-partner för att jämföra dina kostnader med deras uppskattningar av hur lång tid det tar för dem att göra det och på vilken kostnad. 
    
## <a name="migrate-to-project-online"></a>Migrera till Project Online

Om du väljer att migrera från Project Server 2007 till Project Online kan du göra följande för att manuellt migrera dina projekt Plans data:
  
1. Spara dina projektplaner från Project Server 2003 till. MPP-format.
    
2. Använd Project Professional 2013, Project Professional 2016 eller Project Online-klienten, öppna alla. mpp-filer och spara och publicera dem i Project Online.
    
Du kan skapa din PWA-konfiguration manuellt i Project Online (om du till exempel vill skapa eventuella anpassade fält eller företags kalendrar). Microsoft-partners kan också hjälpa dig med detta.
  
Viktiga resurser:
  
|**Resurspool**|**Beskrivning**|
|:-----|:-----|
|[Komma igång med Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Hur du installerar och använder Project Online.  <br/> |
|[Beskrivningar för Project Online-tjänster](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Information om de olika Project Online-abonnemangen som är tillgängliga för dig.  <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrera till en nyare lokal version av Project Server

Vi tror att du kan nå det bästa värdet och användar upplevelsen genom att migrera till Project Online, men vi förstår också att vissa organisationer måste ha projekt data i en lokal miljö. Om du väljer att hålla dina Project-data lokala kan du migrera din Project Server 2007-miljö till Project Server 2010, Project Server 2013 eller Project Server 2016.
  
Vi rekommenderar att du migrerar till Project Server 2016 om du inte kan migrera till Project Online. Project Server 2016 innehåller alla funktioner och framsteg som ingår i tidigare versioner av Project Server och det stämmer närmast det som är tillgängligt med Project Online (även om vissa funktioner endast är tillgängliga i Project Online).
  
När du har slutfört varje migrering bör du kontrol lera att dina data har migrerats.
  
> [!NOTE]
> Om du funderar på att bara migrera till Project Server 2010 om du är begränsad till en lokal lösning är det viktigt att Observera att det bara har några fler års support kvar. Project Server 2010 med Service Pack 2 slut på support datumet är 10/13/2020. Mer information om slut på support datum finns i [Microsofts produkt livs cykel policy](https://go.microsoft.com/fwlink/p/?linkid=842066). 
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Hur migrerar jag till Project Server 2016?

Arkitekturen mellan Project Server 2007 och Project Server 2016 förhindrar en direkt migrering. Det innebär att du måste migrera dina Project Server 2007-data till nästa efterföljande version av Project Server tills du uppgraderar till Project Server 2016.
  
Du måste göra följande för att uppgradera till Project Server 2016:
  
1. Steg 1: Migrera från Project Server 2007 till Project Server 2010.
    
2. Steg 2: Migrera från Project servar 2010 till Project Server 2013.
    
3. Steg 3: Migrera från Project Server 2013 till Project Server 2016.
    
När du har slutfört varje migrering bör du kontrol lera att dina data har migrerats.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Steg 1: Migrera från Project Server 2007 till Project Server 2010

Om du vill ha mer information om vad du behöver göra för att uppgradera från Project Server 2007 till Project Server 2010 kan du läsa om hur du [uppgraderar till Project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812) på TechNet. 
  
Viktiga resurser:
  
|**Resurspool**|**Beskrivning**|
|:-----|:-----|
|[Uppgraderings översikt för Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Läs mer om vad du behöver göra för att uppgradera från Project Server 2007 till Project Server 2010.  <br/> |
|[Planera att uppgradera till Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Titta på de överväganden du behöver göra när du uppgraderar från Project Server 2007 till Project Server 2010, inklusive system krav.  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Hur uppgraderar jag?

Information om hur du uppgraderar finns i [Uppgradera till Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812) -innehålls uppsättning, men det är viktigt att förstå att det finns två olika metoder att uppgradera: 
  
- **Databas-koppla uppgradering:** Med den här metoden uppgraderas endast innehållet för din miljö och inte konfigurations inställningarna. Det är obligatoriskt om du uppgraderar från Office Project Server 2007 som är distribuerad på maskin vara som endast har stöd för ett 32-bitars serveroperativ system. Det finns två typer av databas-koppla uppgraderings metoder: 
    
  - **Fullständig uppgradering** – migrera de projekt data som finns lagrade i Office project Server 2007-databaserna plus den Microsoft Project Web App (PWA)-webbplats data som lagras i en SharePoint-innehålls databas. 
    
  - **Databas-bifogad Core-uppgradering** – migrerar bara de projekt data som finns lagrade i Project Server-databaserna. 
    
- **Uppgradering på plats**: konfigurations data för Server gruppen och allt innehåll i Server gruppen uppgraderas på den befintliga hård varan, i en fast ordning. När du startar uppgraderings processen på plats körs hela Server gruppen offline och webbplatserna och Microsoft Project Web App-webbapparna är inte tillgängliga förrän uppgraderingen är klar och sedan startas servern om. När du har påbörjat en uppgradering på plats kan du inte pausa uppgraderingen eller återställa till den föregående versionen. Det är starkt möjligt att göra en speglad bild av din produktions miljö och att genomföra en uppgradering till den här miljön på plats, och inte din produktions miljö. 
    
Ytterligare resurser:
  
- [Superflöde för uppgradering av Microsoft Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Migrering från Project Server 2007 till Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Uppgraderings överväganden för Project Web App-webbdelar](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Project Software Development Kit (SDK)](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Steg 2: migrera till Project Server 2013

När du har migrerat till Project Server 2010 och kontrollerat att dina data har migrerats, är nästa steg att migrera dina data till Project Server 2013.
  
Om du vill ha mer information om vad du behöver göra för att uppgradera från Project Server 2010 till Project Server 2013 kan du läsa om hur du [uppgraderar till Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) på TechNet. 
  
Viktiga resurser:
  
|**Resurspool**|**Beskrivning**|
|:-----|:-----|
|[Översikt över uppgraderings processen för Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Läs mer om vad du behöver göra för att uppgradera från Project Server 2010 till Project Server 2013.  <br/> |
|[Planera att uppgradera till Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Titta på de överväganden du behöver göra när du uppgraderar från Project Server 2010 till Project Server 2013, inklusive system krav.  <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Saker du bör veta om att uppgradera till den här versionen

[Nyheter i 2013-uppgraderingen för Project Server](https://go.microsoft.com/fwlink/p/?linkid=841824) visar en del viktiga ändringar för uppgraderingen för den här versionen, som är viktigast: 
  
- Det finns ingen uppgradering på plats för Project Server 2013. Metoden databas koppling är den enda metod som stöds för uppgradering från Project Server 2010 till Project Server 2013.
    
- Uppgraderings processen konverterar inte bara Project Server 2010-data till Project Server 2013-format, men den sammanlänkas också de fyra Project Server 2010-databaserna till en enda Project Web App-databas.
    
- Både SharePoint Server 2013 och Project Server 2013 ändras till anspråksbaserad auktorisering från den föregående versionen. Du måste tänka på när du uppgraderar om du använder klassisk behörighet. Mer information finns i [Migrera från klassiskt läge till anspråksbaserad identifiering i SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825).
    
Ytterligare resurser:
  
- [Översikt över uppgraderings processen till Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Uppgradera dina databaser och webbplats samlingar för Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Microsoft Project Server-uppgraderings process diagram](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Den fantastiska databas konsolideringen, Project Server 2010 till 2013-migrering i 8 enkla steg](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Steg 3: migrera till Project Server 2016

När du har migrerat till Project Server 2013 och kontrollerat att dina data har migrerats, är nästa steg att migrera dina data till Project Server 2016.
  
Om du vill ha mer information om vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016 kan du läsa om hur du uppgraderar till Project Server 2016 på TechNet.
  
Viktiga resurser:
  
|**Resurspool**|**Beskrivning**|
|:-----|:-----|
|[Översikt över uppgraderings processen för Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Läs mer om vad du behöver göra för att uppgradera från Project Server 2013 till Project Server 2016.  <br/> |
|[Planera för uppgradering till Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Titta på de överväganden du behöver göra när du uppgraderar från Project Server 2013 till Project Server 2016, inklusive.  <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Saker du bör veta om att uppgradera till den här versionen

[Saker du behöver veta om Project Server 2016-uppgraderingen](https://go.microsoft.com/fwlink/p/?linkid=841827) ger dig viktiga ändringar för uppgradering för den här versionen, som omfattar: 
  
- När du skapar din Project Server 2016-miljö som du migrerar dina Project Server 2013-data till kan du tänka på att Project Server 2016-installationsfilerna ingår i SharePoint Server 2016. Mer information finns i [distribuera Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Resurs planer är föråldrade i Project Server 2016. Resurs abonnemang för Project Server 2013 migreras till resurs åtaganden i Project Server 2016 och i Project Online. Se [Översikt: eventuella resurs åtaganden](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) för mer information. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrera från Portfolio Server 2007

Project Portfolio Server 2007 användes med Project Server 2007 för portfölj strategi, prioritering och optimering. Ingen ytterligare version av Project Portfolio Server skapades efter den här versionen. Funktionerna för portfölj hantering finns i både Project Server 2016 och Premium-versionen av Project Online. Data från Project Portfolio Server 2007 kan inte migreras till båda. Data som affärs drivande faktorer måste återskapas.
  
Andra resurser:
  
- [Beskrivningar för Project Online-tjänster](https://go.microsoft.com/fwlink/p/?linkid=841280): se de funktioner för portfölj hantering som ingår i project Server 2016 och Project Online Premium.
    
- [Migreringsguiden för Microsoft Office Project Portfolio Server 2007](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Relaterade ämnen

[SharePoint Server 2007 slut på support översikt](sharepoint-2007-end-of-support.md)
  
[Resurser som hjälper dig att uppgradera från Office 2007-servrar och-klienter](upgrade-from-office-2007-servers-and-products.md)
  

