---
title: Automatiserad undersökning och svars funktioner i Microsoft Threat Protection
description: Få en översikt över automatiserade undersökningar och svars funktioner i Microsoft Threat Protection
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, reparation
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 9fc4c99254f4f27b476930a555b237be093bff24
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950730"
---
# <a name="automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Automatiserad undersökning och svars funktioner i Microsoft Threat Protection

**Gäller för:**
- Microsoft Hotskydd

När säkerhets varningar utlöses är det upp till din säkerhets åtgärds grupp för att titta på dessa meddelanden och vidta åtgärder för att skydda din organisation. Det kan ta väldigt lång tid att prioritera och undersöka aviseringar, särskilt när nya meddelanden fortsätter när en undersökning pågår. Säkerhets Operations team kan känna av sig som skir volymen av de hot som de måste övervaka och skydda mot. Automatiserade undersökningar och svars funktioner (kallas även för *själv lagning* ) i Microsoft Threat Protection kan hjälpa dig. 

Titta på följande video för att se hur automatisk återställning fungerar:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Den automatiska undersökningen och svaret är som att ha en virtuell analytiker i säkerhets åtgärds centret.

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

> [!TIP]
> Om du tror att något har missats eller upptäckts felaktigt av den automatiska undersöknings-och svars funktionerna i Microsoft Threat Protection, tala om det för oss! Lär dig [hur du rapporterar falskta positiva eller negativa negativ i automatiserad undersökning och svars funktioner i Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

När en undersökning körs läggs eventuella andra relaterade aviseringar till i undersökningen tills den är klar. Om en incriminated-enhet visas någon annan stans expanderar den automatiserade undersökningen dess omfattning för att inkludera den enheten och en allmän säkerhets Playbook körs. 

> [!NOTE]
> Alla notifieringar utlöser en automatiserad undersökning och alla undersöknings resultat leder till automatiska reparations åtgärder; Detta beror på hur automatisk undersökning och svar är konfigurerat för din organisation. 

## <a name="requirements-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Krav för automatisk undersökning och svar i skydd mot Microsoft-hotet

|Krav |Information |
|--|--|
|Abonnemangs krav |Något av följande: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5-säkerhet<br/>-Microsoft 365 A5-säkerhet<br/>-Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>Se [licens krav för Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Nätverks krav |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) aktiverat<br/>- [Microsoft Cloud App-säkerhet](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) har kon figurer ATS<br/>- [MCAS integrerad med Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|System krav för Windows |-Windows 10, version 1709 eller senare installerad (se [Windows 10](https://docs.microsoft.com/windows/release-information/)-versions information) med följande skydds tjänster konfigurerade:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Skydd för e-postinnehåll och Office-filer |[Office 365 Avancerat skydd för skyddare](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|Behörigheter |-För att konfigurera automatisk undersökning och svar måste du ha rollen global administratör eller säkerhets administratör tilldelad i antingen Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) eller i Microsoft 365 Admin Center ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>-För att använda automatiska undersökningar och svars funktioner, se [nödvändiga behörigheter för åtgärds Center uppgifter](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Nästa steg

- [Godkänna eller avvisa åtgärder relaterade till automatiserad undersökning och svar](mtp-autoir-actions.md)
- [Läs mer om åtgärds Center](mtp-action-center.md)
