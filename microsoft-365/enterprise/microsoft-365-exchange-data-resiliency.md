---
title: Exchange Online data återhämtning i Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln hittar du en förklaring av de olika aspekterna av data återhämtning i Exchange Online och Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02a28a9099c329b943ab1f015326a674c79cf46e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332538"
---
# <a name="exchange-online-data-resiliency-in-microsoft-365"></a>Exchange Online data återhämtning i Microsoft 365

Det finns två typer av skador som kan påverka en Exchange-databas: fysisk skada, som vanligt vis orsakas av maskin varu problem (särskilt lagrings hård vara) och logiskt fel, som beror på andra faktorer. Vanligt vis finns det två typer av logiska skador som kan uppstå i en Exchange-databas: 
- **Logisk databas skada** – sid kontroll summan för databasen matchar, men data på sidan är fel logiskt. Det här kan inträffa om databas motorn (Extensible Storage Engine (ESE) försöker skriva en databas sida och trots att operativ systemet returnerar ett meddelande om att det är lyckat, har data antingen aldrig skrivits till disken eller så har de skrivits till fel plats. Detta kallas för *förlorad tömning*. ESE innehåller flera funktioner och säkerhets åtgärder som är avsedda att förhindra fysisk skada av en databas och andra scenarier för data förlust. För att förhindra förlorad rensning från att förlora data innehåller ESE en förlorad funktion för dubblettidentifiering i databasen tillsammans med en funktion (återställning med enkel sida) för att korrigera det. 
- **Lagra logisk skada** – data läggs till, tas bort eller ändras på ett sätt som användaren inte förväntar dig. Dessa fall orsakas normalt av tredjepartsprogram. Det är vanligt vis bara problem med att användaren visar den som skador. I Exchange-arkivet behandlas den transaktion som gav upphov till det logiska skada som en serie giltiga MAPI-åtgärder. [In-Place Hold](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) -funktioner i Exchange Online ger skydd mot lagring av logiska skador (eftersom innehållet inte tas bort permanent av en användare eller ett program). 

Exchange Online utför flera konsekvens kontroller av replikerade loggfiler under både granskning och utloggning. Dessa konsekvens kontroller hindrar fysiska skador från att replikeras av systemet. Under en gransknings inspektion är exempelvis en fysisk integritets kontroll som verifierar logg filen och verifierar att den kontroll summa som är registrerad i logg filen matchar den kontroll summa som genererats i minnet. Dessutom kontrol leras logg filens rubrik för att se till att logg filens signatur är Sparad i logg rubriken. Under den här återuppspelningen kan logg filen gå vidare. Databas huvudet innehåller till exempel även loggens signatur som jämförs med logg filens signatur för att se till att den matchar. 

Skydd mot korruption från post lådor i Exchange Online uppnås med hjälp av Exchange ursprungligt data skydd, en återhämtnings strategi som använder replikering på flera servrar och flera data Center tillsammans med andra funktioner som hjälper dig att skydda data på grund av skador eller andra orsaker. De här funktionerna inkluderar inbyggda funktioner som hanteras av Microsoft eller själva Exchange Online-programmet, till exempel:

- [Data tillgänglighets grupper](https://docs.microsoft.com/exchange/back-up-email)
- Enkel bit korrigering 
- Online-databas genomsökning 
- Förlorad dubblettidentifiering 
- Återställning med en enda sida 
- Tjänsten Mailbox Replication 
- Logg fils kontroller 
- Distribution av elastiskt fil system 

Om du vill ha mer information om de inbyggda funktionerna ovan klickar du på ovanstående hyperlänkar och läser nedan för ytterligare information och information om objekt utan hyperlänkar. Utöver dessa inbyggda funktioner inkluderar Exchange Online även data återhämtnings funktioner som kunder kan hantera, till exempel: 
- [Återställning av enskilt objekt (aktiverat som standard)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages) 
- [Håll på plats och tvist](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds) 
- [Borttagna objekt, lagrings-och borttagnings bara brev lådor (både aktiverade som standard)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 

## <a name="database-availability-groups"></a>Databas tillgänglighets grupper 
Varje Mailbox-databas i Microsoft 365 finns i en [databas tillgänglighets grupp (dag)](https://docs.microsoft.com/exchange/back-up-email) och replikeras till geografiskt åtskilda Data Center inom samma region. Den vanligaste konfigurationen är fyra databas kopior i fyra Data Center; i vissa regioner finns det emellertid färre data Center (databaserna replikeras till tre Data Center i Indien och två Data Center i Australien och Japan). I alla fall innehåller alla post lådor fyra kopior som fördelas på flera data källor, och säkerställer därmed att post lådorna skyddas från program vara, hård vara och till och med data Center. 

Med de här fyra kopiorna är tre av dem konfigurerade med hög tillgänglighet. Den fjärde kopian är konfigurerad som en neddelad [databas kopia](https://docs.microsoft.com/Exchange/high-availability/manage-ha/activate-lagged-db-copies). Den avvecklade databas kopian är inte avsedd för återställning av enskilda post lådor eller återställning av post låda. Dess syfte är att tillhandahålla en återställnings funktion för den sällsynta händelsen i systemomfattande oåterkalleligt logiskt fel. 

Inspelade databas kopior i Exchange Online har kon figurer ATS med en sjunde dag i en dygns lång tid. Dessutom är Exchange Replay-fördröjningen aktive rad för att tillhandahålla dynamisk logg fil för utskrivna kopior för att tillåta att databas kopior i en utskriven fil för sig själv repare ras och hanteras. Trots att databas kopior med penna används i Exchange Online är det viktigt att förstå att de inte är en garanterad säkerhets kopia. Insamlade databas kopior i Exchange Online har ett tröskelvärde för tillgänglighet, vanligt vis omkring 90%, på grund av att den disk som innehåller en avbruten kopia förloras på grund av ett diskfel, att den utskrivna kopian blir ett mycket tillgängligt exemplar (på grund av automatisk nedrullningsbarning), samt de perioder där den nedbrutna databas kopian återskapar logg uppspelnings kön 

## <a name="transport-resilience"></a>Transport återhämtning 
Exchange Online inkluderar två primära funktioner för överförings återhämtning: skugg redundans och säkerhets nät. Skugg redundans ger en redundant kopia av ett meddelande när det är i transit. Säkerhets nät bevarar ett redundant meddelande när meddelandet har levererats. 

Om du har skugg redundans gör varje Exchange Online Transport Server en kopia av varje meddelande som tas emot innan det bekräftar att meddelandet skickades till den sändande servern. Då blir alla meddelanden i transport förloppet redundanta under överföring. Om Exchange Online bestämmer att det ursprungliga meddelandet förlorades under överföringen omlevereras en överflödig kopia av meddelandet. 

Säkerhets nät är en transport kö som är kopplad till transport tjänsten på en post låda. I den här kön lagras kopior av meddelanden som bearbetades av servern. När en post låda-databas eller server fel måste aktivera en gammal kopia av post lådans databas, skickas meddelanden i säkerhets kön automatiskt till den nya aktiva kopian av post lådan. Säkerhets nätet är också överflödigt och eliminerar transport som en enda fel källa. Den använder begreppet primära säkerhets nät och en skugg säkerhet net om det primära säkerhets nätet inte är tillgängligt i mer än 12 timmar blir omsändnings begär Anden om omsändning av en skugg kopia och meddelanden skickas vidare igen från säkerheten på säkerhets nätet.

Meddelande om att meddelanden tas ut från säkerhets nät automatiskt initieras av den Active Manager-komponenten i Microsoft Exchange-replikeringstjänsten som hanterar DAGs-och post lådans databas kopior. Inga manuella åtgärder krävs för att skicka om meddelanden från säkerhets nätet. 

## <a name="single-bit-correction"></a>Enkel bit korrigering 
ESE innehåller en mekanism för att upptäcka och lösa problem med enkel bit (aka Single bit-kast) som är resultatet av maskin varu fel (och som sådana representerar fysiska skador). När de här felen inträffar rättas de automatiskt och loggar en händelse i händelse loggen. 

## <a name="online-database-scanning"></a>Online-databas genomsökning 
Databas genomsökning online (kallas även *databas*kontroll bild) är den process där en databas konsekvens kontroll används för att läsa varje sida och kontrol lera om sidan är skadad. Det primära syftet är att upptäcka fysiska skador och förlorade tömningar som kanske inte identifieras av transaktions åtgärder. Databas genomsökning utför också en krasch åtgärd efter en post. Utrymmet kan läckas på grund av kraschar och online-databas genomsökningen hittar och återställer förlorade utrymmen. Systemet är utformat med den förväntade att varje databas är fullständigt skannad en gång var sjunde dag. 

## <a name="lost-flush-detection"></a>Förlorad dubblettidentifiering 
En förlorad tömning sker när en databas skrivnings åtgärd, som disk under systemet/operativ systemet returnerade som färdigt, faktiskt inte skrevs till disken eller skrevs in på fel plats. Förlorade tömnings incidenter kan resultera i logisk databas skada, så för att förhindra förlorade tömningar från resulterade förlorade data innehåller ESE en förlorad funktion för dubblettidentifiering. Eftersom databas sidor skrivs till passiva kopior utförs en kontroll för förlorade tömningar på den aktiva kopian. Om en förlorad tömning identifieras kan ESE reparera processen med en sid korrigerings process. 

## <a name="single-page-restore"></a>Återställning med en enda sida 
Återställning av en enda sida, aka *sid korrigering*, är en automatisk process där skadade databas sidor ersätts med friska kopior från en felfri replik. Reparations processen för en skadad sida beror på om databas kopian är aktiv eller passiv. När en aktiv databas kopia stöter på en skadad sida kan den kopiera en sida från en av dess repliker, förutsatt att sidan den kopierar är helt uppdaterad. Det gör du genom att skicka en begäran om sidan till logg strömmen, som är grunden för databas replikering för post lådor. Så fort en replik påträffar sidans begäran svarar den genom att skicka en kopia av sidan till den begärda databas kopian. En enkel sid återställning ger också asynkron kommunikation för Active för att begära en sida från repliker, även om replikerna för närvarande är offline. 

Om det är skadat i en passiv databas kopia, inklusive en nedskriven databas kopia, eftersom dessa kopior alltid ligger bakom sina aktiva kopior är det alltid säkert att kopiera en sida från den aktiva kopian till en passiv kopia. En passiv databas kopia är med hög tillgänglighet, så under processen för sid korrigering avbryts loggningen, men kopieringen fortsätter. Den passiva databas kopian hämtar en kopia av den skadade sidan från den aktiva kopian, men väntar tills logg filen som uppfyller det maximala kravet för loggnings skapande är kopierad och inspekterad och sedan patchar den skadade sidan. När sidan har uppdaterats fortsätter loggningen. Processen är densamma för den avvecklade databas kopian, förutom att den nedarbetade databasen först spelar upp alla loggfiler som behövs för att du ska kunna göra ett korrigerings känsligt tillstånd. 

## <a name="mailbox-replication-service"></a>Tjänsten Mailbox Replication 
Att flytta post lådor är en viktig del av att hantera en storskalig e-posttjänst. Det finns alltid uppdaterade teknologier och hård varu-och versions uppgraderingar att hantera, så det är ett robust, begränsat system som gör att våra tekniker kan utföra detta arbete samtidigt som post lådan flyttas transparent till användarna (genom att se till att de är online hela processen) är en nyckel och se till att processen blir större och större. 

Replikeringstjänsten för Exchange-postlådan (MRS) är ansvarig för att flytta post lådor mellan databaser. Under flytten MRS utför en konsekvens kontroll av alla objekt i post lådan. Om det finns ett konsekvens problem kan MRS antingen rätta till problemet eller hoppa över de skadade objekten och därmed ta bort skadan från post lådan. 

Eftersom MRS är en komponent i Exchange Online kan vi göra ändringar i dess kod för att åtgärda nya skador som upptäcks i framtiden. Om vi till exempel upptäcker ett problem med konsekvens som MRS inte kan lösa kan vi analysera skadan, ändra MRS-koden och korrigera inkonsekvensen (om vi förstår hur du gör). 

## <a name="log-file-checks"></a>Logg fils kontroller 
Alla transaktionsloggfiler som genereras av en Exchange-databas genomgår flera olika former av konsekvens kontroller. När en loggfil skapas är det första som färdigt är ett bit mönster som skrivs och sedan utförs en serie loggnings skrivningar. Det gör det möjligt för Exchange Online att utföra en serie kontroller (förlorad tömning, CRC och andra kontroller) för att verifiera varje loggfil medan den är skriven och igen. 

## <a name="deployment-on-resilient-file-system"></a>Distribution av elastiskt fil system 
För att förhindra att skador uppstår på fil Systems nivå distribueras Exchange Online på ReFS-partitioner (elastiska fil system) för bättre återställnings kapacitet. ReFS är ett fil system i Windows Server 2012 och senare som är utformat för att vara mer elastiskt mot datafel för att maximera data tillgänglighet och integritet. Specifikt ger ReFS förbättringar av hur metadata uppdateras och ger bättre skydd för data och minskar risken för skadade data. Dessutom används kontroll summor för att verifiera att fildata och metadata garanterar att skadade data är enkla att hitta och reparera. 

Exchange Online drar nytta av flera ReFS-fördelar: 
- Mer återhämtning i data integritet innebär färre incidenter för datafel. Om du minskar antalet skade tillbud innebär det färre onödiga återfröer. 
- Kontroll summa som körs på metadata som möjliggör identifiering av skade fall och mer deterministically, vilket gör att vi kan åtgärda kundens datafel innan grått fungerar på data volymer.
- Utformad för att fungera bra med extremt stora data uppsättningar – petabytes och större – utan prestanda påverkan
- Stöd för andra funktioner som används i Exchange Online, till exempel BitLocker-kryptering. 

Exchange Online har också nytta av andra ReFS-funktioner: 
- **Integritet (integritets strömmar)** – ReFS lagrar data på ett sätt som skyddar det från flera vanliga fel som kan orsaka data förlust. I Microsoft 365 search används integritets strömmar för att hjälpa till med tidig identifiering av skadade diskar och kontroll summor för fil innehåll. Funktionen minskar också skade händelser som orsakas av "ofullständiga skrivningar" (när en Skriv åtgärd inte slutförs på grund av strömavbrott etc.). 
- **Tillgänglighet (restvärde)** -ReFS prioriterar tillgängligheten av data. Historiskt, fil system är ofta mottagligt för datafel som skulle kräva att systemet kommer att tas offline för reparation. Trots att det är skadat implementerar ReFS i sällsynta fall en funktion som tar bort skadade data från namn området på en Live Volume och ser till att bra data inte påverkas negativt av icke-reparerade skadade data. Om du använder funktionen restvärde och isolerade datafel till Exchange Online-databas volymer innebär det att vi kan behålla icke-berörda databaser på en skadad volym mellan tiden för skada och reparation. Detta gör att databasens tillgänglighet blir mer lättillgänglig. 