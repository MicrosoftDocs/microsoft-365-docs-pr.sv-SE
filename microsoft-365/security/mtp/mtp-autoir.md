---
title: Automatiserade funktioner för undersökning och svar i Microsoft Threat Protection
description: Få en översikt över automatiska undersöknings- och svarsfunktioner i Microsoft Threat Protection
keywords: automatiserad, utredning, alert, utlösa, åtgärder, sanering
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
ms.openlocfilehash: 6ac6d74b027cc533f689c1d67c7fce246c73984f
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166167"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Funktioner för automatisk undersökning och respons (AIR) i Microsoft Threat Protection

**Gäller:**
- Microsoft Hotskydd

När säkerhetsaviseringar utlöses är det upp till säkerhetsoperationsteamet att titta på dessa aviseringar och vidta åtgärder för att skydda din organisation. Att prioritera och utreda varningar kan vara mycket tidskrävande, särskilt när nya varningar fortsätter att komma in medan en utredning pågår. Säkerhetsteam kan känna sig överväldigade av den stora mängd hot de måste övervaka och skydda sig mot. Funktioner för automatisk undersökning och svar (AIR) i Microsoft Threat Protection kan hjälpa dig. AIR är som att ha en virtuell analytiker i ditt säkerhetscenter.

## <a name="your-virtual-analyst"></a>Din virtuella analytiker

Tänk dig att ha en virtuell analytiker i din Nivå 1 / Tier 2 säkerhetsoperationer team. Den virtuella analytikern härmar de idealiska åtgärder som säkerhetsåtgärder skulle vidta för att undersöka och åtgärda hot. Den virtuella assistenten kan arbeta 24x7, med obegränsad kapacitet, och ta på en betydande belastning av utredningar och hot sanering. En sådan virtuell assistent kan avsevärt minska tiden för att svara, vilket frigör ditt säkerhetsoperationsteam för andra viktiga strategiska projekt. Om detta scenario låter som science fiction, det är det inte! En sådan virtuell analytiker är en del av microsofts programsvit för hotskydd och namnet är *automatisk undersökning och svar* (AIR).

AIR gör det möjligt för din säkerhetsoperationsgrupp att dramatiskt öka organisationens kapacitet att hantera säkerhetsvarningar och incidenter. Med AIR kan du minska kostnaderna för att hantera utrednings- och saneringsaktiviteter och få ut det mesta av din hotskyddssvit. AIR hjälper ditt säkerhetsteam genom att:

1. Avgöra om ett hot kräver åtgärder.
2. Utföra (eller rekommendera) nödvändiga saneringsåtgärder;
3. Fastställande av vilka ytterligare undersökningar som bör ske. Och
4. Upprepa processen efter behov för andra aviseringar.

## <a name="the-automated-investigation-process"></a>Den automatiserade utredningsprocessen

**Alert** > **incident** > **automatiserad utredning** > **dom** > sanering**åtgärder**

En utlöst avisering skapar en incident som kan starta en automatiserad undersökning. Den undersökningen kan resultera i en eller flera åtgärder. I Microsoft Threat Protection korrelerar varje automatiserad undersökning signaler över Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) och Office 365 Advanced Threat Protection (Office 365 ATP), som sammanfattas i följande tabell: 

|Enheter |Tjänster för skydd av hot  |
|---------|---------|
|Enheter (kallas även slutpunkter)     |[Microsoft Defender Avancerat skydd.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-postinnehåll (filer och meddelanden i postlådor)     |[Skaffa Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Varje undersökning genererar domar (*Malicious*, *Suspicious*, or *No threats found*) för varje bit av bevis som undersökts. Beroende på vilken typ av hot och resulterande dom, reparationsåtgärder sker automatiskt eller efter godkännande av organisationens säkerhetsoperationer team. Väntande och slutförda åtgärder visas i [åtgärdscentret](mtp-action-center.md).

> [!TIP]
> Om du tror att något har missats eller felaktigt upptäckts av automatiska undersöknings- och svarsfunktioner i Microsoft Threat Protection, låt oss veta! Se [Så här rapporterar du falska positiva identifieringar/negativ i automatiska funktioner för undersökning och svar (AIR) i Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Medan en undersökning pågår läggs alla andra relaterade aviseringar som uppstår till i undersökningen tills den är klar. Om en angripen enhet visas någon annanstans utökas dess omfattning till att omfatta den enheten och en allmän säkerhetsspelbok körs. 

> [!NOTE]
> Inte varje varning utlöser en automatiserad undersökning, och inte varje undersökning resulterar i automatiserade saneringsåtgärder; Allt beror på hur AIR är konfigurerat för din organisation. 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Krav för AIR i Microsoft Threat Protection

| | |
|--|--|
|Krav på prenumeration |Något av följande: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 A5 <br/>- Microsoft 365 E5 Säkerhet<br/>- Microsoft 365 A5 Säkerhet<br/>- Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>Se [licenskrav för Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Nätverkskrav |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) aktiverat<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) konfigurerad<br/>- [MCAS integrerat med Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Krav på Windows-datorer |- Windows 10, version 1709 eller senare installerad (Se [Windows 10 release information)](https://docs.microsoft.com/windows/release-information/)med följande hot skydd tjänster konfigureras:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Antivirusprogram för Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Skydd för e-postinnehåll och Office-filer |[Office 365 Avancerat skydd mot hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|Behörigheter |- Om du vill konfigurera AIR måste rollen Global administratör eller säkerhetsadministratör tilldelas i Antingen Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) eller i Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).<br/><br/>- Information om hur du använder AIR-funktioner finns [i Obligatoriska behörigheter för åtgärdscenteraktiviteter](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Nästa steg

- [Godkänna eller avvisa åtgärder relaterade till automatisk undersökning och svar](mtp-autoir-actions.md)
- [Läs mer om Åtgärdscentret](mtp-action-center.md)
