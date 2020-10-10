---
title: Automatisk undersökning och svar i skydd mot Microsoft Threat
description: Få en översikt över automatiserade undersökningar och svars funktioner, som även kallas själv återställning, i Microsoft Threat Protection
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, reparation, själv återställning
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: ee5616f79df35ebff2713538bae7fb42fd755287
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413584"
---
# <a name="automated-investigation-and-response-in-microsoft-threat-protection"></a>Automatisk undersökning och svar i skydd mot Microsoft Threat

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

När säkerhets varningar utlöses är det upp till din säkerhets åtgärds grupp för att titta på dessa meddelanden och vidta åtgärder för att skydda din organisation. Det kan ta väldigt lång tid att prioritera och undersöka aviseringar, särskilt när nya meddelanden fortsätter när en undersökning pågår. Säkerhets Operations team kan känna av sig som skir volymen av de hot som de måste övervaka och skydda mot. Automatiserade undersökningar och svars funktioner, med själv återställning, kan hjälpa dig.

Titta på följande video för att se hur själv återställning fungerar:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

I Microsoft Threat Protection kan automatisk undersökning och svar med själv lagnings funktion fungera på dina enheter, e-& innehåll och identiteter. Microsoft Threat Protection sammanställer möjligheter från: 
- [Automatisk undersökning och reparation i Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Automatisk undersökning och svar i Office 365 Avancerat skydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Avancerad hot identifiering för Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
I den här artikeln beskrivs hur automatisk undersökning och svar fungerar. Information om hur du konfigurerar de här funktionerna finns i [Konfigurera automatiserade undersökningar och svars funktioner i Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).

## <a name="your-virtual-analyst"></a>Din virtuella analytiker

Föreställ dig att du har en virtuell analys i ditt team för säkerhets åtgärder för nivå 1/nivå 2. Den virtuella analytikern imiterar de idealiska stegen som säkerhets åtgärder skulle vidta för att undersöka och åtgärda hot. Den virtuella assistenten kan arbeta dygnet runt, med obegränsad kapacitet och få en omfattande inläsning av undersökningar och hot. En sådan virtuell assistent kan avsevärt minska tiden för att svara och på så sätt frigöra dina säkerhets åtgärder för andra viktiga strategiska projekt. Om det här scenariot liknar vetenskaps gilla är det inte! Sådan virtuell analytiker är en del av ditt Microsoft Threat Protection Suite och dess namn är en *Automatisk undersökning och ett svar*.

Med den automatiska undersökningen och svaret kan säkerhets åtgärds gruppen markant öka organisationens kapacitet att hantera säkerhets varningar och-händelser. Genom att automatisera undersökningar och svar kan du minska kostnaderna för att hantera undersökningar och reparations aktiviteter och få ut mesta möjliga av skydds paketet. automatisk undersökning och svar hjälper din säkerhets åtgärd att:

1. Avgöra om ett hot kräver en åtgärd;
2. Utföra (eller rekommendera) alla nödvändiga reparations åtgärder;
3. Avgöra vilka ytterligare undersökningar som bör uppstå; och
4. Upprepa processen när det behövs för andra aviseringar.

## <a name="the-automated-investigation-process"></a>Den automatiserade gransknings processen

**Avisering**  >  **incident**  >  **Automatisk undersökning**  >  **Verdict**  >  **reparations åtgärd**

En utlöst varning skapar en olycka som kan starta en automatiserad undersökning. Denna undersökning kan resultera i en eller flera reparations åtgärder. I Microsoft hot Protection är varje automatiserad undersökning en uppdelad över hela Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Avancerat skydd (Microsoft Defender ATP) och Office 365 Avancerat skydd (Office 365 ATP), som sammanfattas i följande tabell: 

|Posterna |Hot Protection Services  |
|---------|---------|
|Enheter (kallas även slut punkter)     |[Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-postinnehåll (filer och meddelanden i post lådor)     |[Skaffa Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Varje undersökning ger upphov till verdicts (*skadlig*, *misstänkt*eller *Inga hot*) för varje undersöknings bevis. Beroende på typen av hot och resulterande Verdict inträffar reparations åtgärder automatiskt eller efter godkännande av organisationens säkerhets åtgärds team. Pågående och slutförda åtgärder visas i [Åtgärds centret](mtp-action-center.md).

När en undersökning körs läggs eventuella andra relaterade aviseringar till i undersökningen tills den är klar. Om en incriminated-enhet visas någon annan stans expanderar den automatiserade undersökningen dess omfattning för att inkludera den enheten och en allmän säkerhets Playbook körs. 

> [!NOTE]
> Alla notifieringar utlöser en automatiserad undersökning och alla undersöknings resultat leder till automatiska reparations åtgärder; Detta beror på hur automatisk undersökning och svar är konfigurerat för din organisation. Mer information finns [i Konfigurera automatiska undersökningar och svars funktioner i Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).


## <a name="next-steps"></a>Nästa steg

- [Se förutsättningarna för automatisk undersökning och svar i skydd mot Microsoft-hotet](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)
- [Konfigurera automatisk undersökning och svar för organisationen](mtp-configure-auto-investigation-response.md)
- [Läs mer om åtgärds Center](mtp-action-center.md)
