---
title: Reglerar informationen som lyder under data integritets förordning
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
description: Använd Microsoft 365 bevarande etiketter och principer för att hantera person uppgifter i din Microsoft 365-miljö.
ms.openlocfilehash: c2a933e556213ae4b78db9dc5f903885df969b27
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377051"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Reglerar informationen som lyder under data integritets förordning

Du kan använda informations styrning i din miljö för att hjälpa dig att adressera data integritets behovet, inklusive ett nummer som är specifikt för allmänt om allmänna data skydds regler (GDPR), HIPAA-HITECH (Health värna om sjukvård), California konsument skydd Act (CCPA) och Brasilien Data Protection Act (LGPD). 

Dessa kontroller är främst i följande lösnings områden:

- Kvarhållningsprinciper
- Kvarhållningsetiketter
- Hantering av arkivhandlingar

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Data integritets regler som påverkar informations styrnings kontroller

Här är ett exempel på en lista över data integritets regler som kan gälla för informations styrnings kontroller:

- GDPR-artikel (13) (2) (a)
- GDPR-artikel (5) (1) (f)
- HIPAA-HITECH (45 CFR 164.312 (c) (2))
- HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))
- HIPAA-HITECH (45 CFR 164.316 (b) (1) (II))
- LGPD artikel 46

Mer information om dessa regler finns i [bedöma riskerna för data integritet och identifiera känslig information](information-protection-deploy-assess.md).

För informations hantering kan data integritets reglerna normalt ringa till följande:

- Du bör använda en teknisk stödordning för bevarande och borttagning av person uppgifter som lagras i Microsoft 365.
- Om du ska lagra person uppgifter kan du informera om hur länge informationen lagras, vilket är en standard övning nu på front webb system.
- Person uppgifter bör skyddas mot oavsiktlig behandling, förlust eller ändring med kontrollerbara metoder.
- Alla åtgärder som utförs mot person uppgifter bör dokumenteras och dokumentationen bör bevaras under en viss tid.

Eftersom reglerna för data integritet inte är särskilt specifika när det gäller data lagring och borttagning måste andra faktorer beaktas som kan diktera informations styrnings rikt linjer för person uppgifter som lagras i Microsoft 365-prenumerationen. Här följer några exempel:

- Åldrande av konsument konton efter fem års inaktivitet och borttagnings-eller anonymisering av konto data efter den punkten, som kräver dirigering mellan systemet som lagrar data och arbets flöden relaterade till meddelanden och annan automatisering.
- Konfigurera regler för att behålla principer och procedurer relaterade till GDPR i tre år efter det att de har ersatts, som justeras efter organisationens bevarande schema för principer och procedurer.
- Upprätthålla ett separat abonnemang för kommunikation med konsumenter via dess support organisation. All e-postkommunikation behålls och togs bort efter två veckor för att minska eventuell sekretess skuld buildup i systemet.

En viktig fråga är: 

- Hur länge ska information som innehåller person uppgifter behöva behållas i ett giltigt företags skäl för att undvika "Behåll det för alltid". Detta måste bal anse ras för att behålla behovet av affärs kontinuitet.

Oberoende av juridiska och affärsmässiga skäl för att hålla person uppgifter eller ta bort den, erbjuder Microsoft ett antal funktioner för att implementera ditt data styrnings schema i Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Hantera informations styrning i Microsoft 365

För att börja läser du [Hantera informations styrning](../compliance/manage-information-governance.md) och [data lagring, borttagning och förstörelse i Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Utveckla data lagrings scheman för behållare, e-post och innehåll

Tänk på följande:

- Att skapa ett schema för data lagring för definierade informations typer bör anses vara en förutsättning för att du ska kunna genomföra ett bevarande-eller borttagnings schema.

- Baserat på det antal informations typer som de flesta organisationer anser vara viktiga och de motsvarande stora poster för bevarande av Arkiv handlingar som visas, måste du planera. 

- När det gäller att upprätta en effektiv data hanterings strategi av den här typen är att fokusera på de företags funktioner och informations typer som kräver mer formell hantering. Exempel är juridiska avtal, finansiella rapporter och dokumentation om överensstämmelse. Försök att undvika ett separat bevarande schema för varje enskild informations typ. Försök att använda allmänna kategorier så mycket som möjligt, till exempel med bevarande scheman på 7 år för allmänt företags innehåll.

- När de personliga informations typerna i miljön är bättre kända kan du skapa scheman för bevarande och borttagning av den här typen av innehåll och justera din informations arkitektur så att den blir lättare att använda. Du kan till exempel isolera personlig information i separata webbplatser, bibliotek eller mappar med styrd åtkomst.

### <a name="retention-policies-and-retention-labels"></a>Bevarande principer och bevarande etiketter

Använd [bevarande principer och bevarande etiketter](../compliance/retention.md) för att behålla eller ta bort innehåll i Microsoft 365 som innehåller eller förväntas innehålla person uppgifter.

### <a name="records-management"></a>Hantering av arkivhandlingar

Använd lagrings etiketter som deklarerar innehåll en post för att implementera en [lösning för hantering av Arkiv handlingar](../compliance/records-management.md) för data i Microsoft 365.

För data integritet förklaras en post med DSRs som tagits emot av den juridiska avdelningen och kan lagras obegränsat eller avyttrade med bevis, för att följa gällande bestämmelser om bevarande av tvister.

