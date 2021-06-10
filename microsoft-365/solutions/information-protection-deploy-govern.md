---
title: Reglera information som omfattas av datasekretess
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Använd Microsoft 365 och bevarandeprinciper för att hantera personliga data i din Microsoft 365 miljö.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928442"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Reglera information som omfattas av datasekretess

Informationsstyrningskontroller kan användas i din miljö för att tillgodose behov av datasekretessefterlevnad, inklusive ett nummer som är specifikt för Allmän dataskyddsförordning (GDPR), HIPAA-HITECH (United States Health Care Privacy Act), California Consumer Protection Act (CCPA) och Brazil Data Protection Act (LGPD). 

Dessa kontroller faller främst inom följande lösningsområden:

- Kvarhållningsprinciper
- Kvarhållningsetiketter
- Hantering av arkivhandlingar

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Datasekretessförordningar som påverkar kontroll av informationsstyrning

Här är ett exempel på en lista med regler för datasekretess som kan relatera till kontroller för informationsstyrning:

- GDPR-artikel (13)(2)(a)
- GDPR-artikel (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))
- LGPD, artikel 46

Mer information om dessa bestämmelser finns i artikeln om att [bedöma datasekretess och identifiera känslig information.](information-protection-deploy-assess.md)

För informationsstyrning anropar datasekretessföreskrifter vanligtvis följande:

- Du bör använda ett tekniskt system för lagring och borttagning av personuppgifter som lagras i Microsoft 365.
- Om du kommer att lagra personlig information informerar du ämnet om hur länge data kommer att lagras, vilket är en standardmetod nu på frontend-webbsystem.
- Personuppgifter bör skyddas mot oavsiktlig bearbetning, förlust eller ändring med hjälp av verifierbara metoder.
- Alla åtgärder som utförs mot personuppgifter ska dokumenteras och att dokumentationen ska behållas under en viss tidsperiod.

Eftersom bestämmelser om datasekretess inte är särskilt specifika när det gäller lagring och borttagning av data måste andra faktorer beaktas som kan diktera riktlinjer för informationsstyrning för personlig information som lagras i Microsoft 365-prenumerationen. Här är några exempel:

- Föråldring av konsumentkonton efter 5 års inaktivitet och kräver borttagning eller anonymisering av kontodata efter den tidpunkten, vilket kräver att data och arbetsflöden som är relaterade till meddelanden och annan automation behöver fördelas mellan systemet.
- Konfigurera regler för att behålla principer och procedurer relaterade till GDPR i tre år efter att de har ersatts, vilket överensstämmer med organisationens kvarhållningsschema för principer och procedurer.
- Ett separat abonnemang för kommunikation med konsumenter via supportorganisationen. All e-postkommunikation behålls och raderas efter två veckor för att minska eventuella problem med att skapa sekretess i systemet.

En viktig fråga att besvara är: 

- Hur länge måste information som innehåller personuppgifter sparas av giltiga affärsorsaker för att undvika att använda det för alltid? Det måste balanseras med bevarandebehov för affärskontinualitet.

Oavsett juridiska skäl och affärsorsaker till att ha personlig information runt om eller ta bort den tillhandahåller Microsoft ett antal funktioner för att implementera ditt datastyrningsschema i Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Hantera informationsstyrning i Microsoft 365

Börja med att gå [till Hantera informationsstyrning](../compliance/manage-information-governance.md) [och datalagring, borttagning och bevarande i Microsoft 365.](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Utveckla datalagringsscheman för behållare, e-post och innehåll

Tänk på följande:

- Att upprätta ett datalagringsschema för definierade informationstyper bör vara en förutsättning för att implementera ett bevarande- eller borttagningsschema.

- Med hänsyn till antalet informationstyper som de flesta organisationer anser vara viktiga och de motsvarande stora arkiveringsscheman som följer med dem, måste du planera för att implementera en strategi för datalagring och hantering av arkivhandlingar. 

- Nyckeln till att upprätta en effektiv datastyrningsstrategi av den här typen är att fokusera på de affärsfunktioner och informationstyper med högsta prioritet som kräver mer formell hantering. Några exempel är juridiska kontrakt, ekonomiska rapporter och dokumentation om regelefterlevnad. Försök att undvika ett separat kvarhållningsschema för varje enskild informationstyp. Försök att använda allmänna kategorier så mycket som möjligt, till exempel med kvarhållningsscheman på 7 år för allmänt affärsinnehåll.

- När typerna av personlig information i din miljö är mer kända bör du upprätta scheman för bevarande och borttagning för den här typen av innehåll och justera informationsarkitekturen för att göra styrning av den här typen av information enklare. Isolera till exempel personlig information på separata webbplatser, i bibliotek eller i mappar med kontrollerad åtkomst.

### <a name="retention-policies-and-retention-labels"></a>Kvarhållningsprinciper och -etiketter

Använd [bevarandeprinciper och bevarandeetiketter](../compliance/retention.md) för att behålla eller ta bort Microsoft 365 innehåll som innehåller eller förväntas innehålla personuppgifter.

### <a name="records-management"></a>Hantering av arkivhandlingar

Använd bevarandeetiketter som deklarerar innehåll för en arkivering för att implementera en lösning [för hantering](../compliance/records-management.md) av arkivhandlingar för data i Microsoft 365.

För datasekretess deklareras de DSR-förfrågningar som tas emot av den juridiska avdelningen och kan lagras på obestämd tid eller kasseras med bevis, för att följa bevarandespecifikationer för regelaktivitet.