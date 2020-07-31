---
title: Reglera information som omfattas av dataskyddsförordningen
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
ms.custom: ''
description: Använd Microsoft 365-lagringsetiketter och policyer för att hantera personuppgifter i microsoft 365-miljön.
ms.openlocfilehash: a7a0d6e00d29d80dfd0cb72ba217177aa6029a2c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522307"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Reglera information som omfattas av dataskyddsförordningen

Kontroller för informationsstyrning kan användas i din miljö för att hjälpa till att tillgodose behoven av efterlevnad av datasekretess, inklusive ett nummer som är specifikt för General Data Protection Regulation (GDPR), HIPAA-HITECH (United States health care privacy act), California Consumer Protection Act (CCPA) och Brazil Data Protection Act (LGPD). 

Dessa kontroller faller främst in i följande lösningsområden:

- Kvarhållningsprinciper
- Kvarhållningsetiketter
- Hantering av arkivhandlingar

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Regler för datasekretess som påverkar kontroller för informationsstyrning

Här är ett exempel på datasekretessregler som kan relatera till informationsstyrningskontroller:

- GDPR Artikel 13.2 a
- GDPR Artikel 5.1 f
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316 b(1)(i))
- HIPAA-HITECH (45 CFR 164.316 b.1)(ii))
- LGPD Artikel 46

Mer information om dessa föreskrifter finns i [artikeln för att bedöma datasekretessen och identifiera en artikel om känslig information](information-protection-deploy-assess.md).

För informationsstyrning kräver datasekretessregler vanligtvis följande:

- Du bör använda ett tekniskt schema för lagring och radering av personuppgifter som lagras i Microsoft 365.
- Om du ska lagra personuppgifter, informera ämnet om hur länge uppgifterna kommer att lagras, vilket är en vanlig praxis nu på frontend webbsystem.
- Personuppgifter bör skyddas mot oavsiktlig behandling, förlust eller ändring med hjälp av kontrollerbara metoder.
- Alla åtgärder som utförs mot personuppgifter bör dokumenteras och denna dokumentation bör behållas under en viss period.

Eftersom reglerna för datasekretess inte är särskilt specifika när det gäller lagring och radering av data måste andra faktorer beaktas som kan diktera riktlinjer för informationsstyrning för personlig information som lagras i din Microsoft 365-prenumeration. Här är några exempel:

- Åldrande ut konsumentkonton efter 5 års inaktivitet och kräver radering eller anonymisering av kontodata efter den punkten, vilket kräver orkestrering mellan systemet som lagrar data och arbetsflöden relaterade till meddelanden och annan automatisering.
- Konfigurera regler för att hålla principer och procedurer relaterade till GDPR runt i tre år efter att de har ersatts, vilket överensstämmer med organisationens bevarandeschema för principer och procedurer.
- Upprätthålla en separat prenumeration för att kommunicera med konsumenter genom sin supportorganisation. All e-postkommunikation behölls och raderades efter två veckor för att minska eventuella integritetsskulder i systemet.

En viktig fråga att besvara är: 

- Hur länge behöver information som innehåller personuppgifter bevaras av giltiga affärsskäl för att undvika "keep it forever"-metoder? Detta måste balanseras med bevarandebehov för kontinuitet i verksamheten.

Oavsett de juridiska och affärsmässiga skälen för att hålla personlig information runt eller ta bort den, tillhandahåller Microsoft ett antal funktioner för att implementera ditt datastyrningssystem i Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Hantera informationsstyrning i Microsoft 365

Börja med att se [Hantera informationsstyrning](../compliance/manage-information-governance.md) och [datalagring, borttagning och destruktion i Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Utveckla datalagringsscheman för behållare, e-post och innehåll

Tänk på följande:

- Upprättande av en datalagringsplan för definierade informationstyper bör betraktas som en förutsättning för att genomföra ett lagrings- eller raderingsschema.

- Med tanke på antalet informationstyper som de flesta organisationer anser vara viktiga och motsvarande stora lagringsscheman för stora poster som följer med dem, kräver implementering av en strategi för datalagring och datahantering planering. 

- Nyckeln till att upprätta en effektiv strategi för datastyrning av den här typen är att fokusera på de högsta prioriterade affärsfunktioner och informationstyper som kräver mer formell hantering. Exempel är juridiska kontrakt, bokslut och dokumentation om regelefterlevnad. Försök att undvika att ha ett separat kvarhållningsschema för varje enskild informationstyp. Försök att använda allmänna kategorier så mycket som möjligt, till exempel med kvarhållningsscheman på 7 år för allmänt affärsinnehåll.

- När de personliga informationstyperna i din miljö är mer kända, upprätta kvarhållnings- och borttagningsscheman för den här typen av innehåll och justera din informationsarkitektur för att göra styrningen av den här typen av information enklare. Isolera till exempel personlig information på separata platser, bibliotek eller mappar med kontrollerad åtkomst.

### <a name="retention-policies"></a>Kvarhållningsprinciper

Skapa och distribuera [bevarandeprinciper](../compliance/retention-policies.md) för innehåll på webbplatser som tillämpas automatiskt.

För datasekretess för webbplatser som innehåller eller förväntas innehålla personuppgifter anger du lagrings- eller raderingsregler för att hantera organisationsstandarder.

### <a name="retention-labels"></a>Kvarhållningsetiketter

Skapa och distribuera [kvarhållningsetiketter](../compliance/labels.md) för innehåll och e-post.

För datasekretess för webbplatser, bibliotek, mappar och e-post som innehåller eller förväntas innehålla personuppgifter anger du regler för automatisk lagring eller radering för att hantera organisationsstandarder.

### <a name="records-management"></a>Hantering av arkivhandlingar

Skapa och distribuera kvarhållningsetiketter för arkivhantering baserat på ett schema för bevarande av poster och filplan.

För datasekretess, registrerade förfrågningar (DSRs) emot av den juridiska avdelningen förklaras en post och lagras på obestämd tid för att följa regulatoriska specifikationer aktivitet lagring.

Mer information finns i de här resurserna: 

- [Hantering av arkivhandlingar](../compliance/records-management.md)
- [Filplanshanterare](../compliance/file-plan-manager.md)
- [Händelsebaserad kvarhållning för registerhantering](../compliance/automate-event-driven-retention.md)
- [Disposition av innehåll](../compliance/disposition-reviews.md)
