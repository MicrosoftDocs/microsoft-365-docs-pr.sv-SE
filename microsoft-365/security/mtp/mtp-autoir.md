---
title: Automatiserade funktioner för undersökning och svar i Microsofts hotskydd
description: Få en översikt över automatiska funktioner för undersökningar och svar i Microsoft Threat Protection
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
ms.openlocfilehash: c45b7d1b01ee776e9519d67ee52d36b8f48bf0ef
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552360"
---
# <a name="automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Automatiserade funktioner för undersökning och svar i Microsofts hotskydd

**Gäller:**
- Microsoft Hotskydd

När säkerhetsaviseringar utlöses är det upp till säkerhetsoperationsteamet att titta på dessa aviseringar och vidta åtgärder för att skydda din organisation. Att prioritera och utreda varningar kan vara mycket tidskrävande, särskilt när nya varningar fortsätter att komma in medan en utredning pågår. Säkerhetsteam kan känna sig överväldigade av den stora mängd hot de måste övervaka och skydda sig mot. Automatiserade funktioner för undersökning och svar (kallas även *automatiska självläkningsfunktioner)* i Microsoft Threat Protection kan hjälpa dig. 

Titta på följande video för att se hur automatiserade självläkningsfunktioner fungerar:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Automatiserad undersökning och svar är som att ha en virtuell analytiker i ditt säkerhetscenter.

## <a name="your-virtual-analyst"></a>Din virtuella analytiker

Tänk dig att ha en virtuell analytiker i din Nivå 1 / Tier 2 säkerhetsoperationer team. Den virtuella analytikern härmar de idealiska åtgärder som säkerhetsåtgärder skulle vidta för att undersöka och åtgärda hot. Den virtuella assistenten kan arbeta 24x7, med obegränsad kapacitet, och ta på en betydande belastning av utredningar och hot sanering. En sådan virtuell assistent kan avsevärt minska tiden för att svara, vilket frigör ditt säkerhetsoperationsteam för andra viktiga strategiska projekt. Om detta scenario låter som science fiction, det är det inte! En sådan virtuell analytiker är en del av din Microsoft Threat Protection suite, och dess namn är *automatiserad undersökning och svar*.

Automatiserad undersökning och svar gör det möjligt för din säkerhetsoperationsgrupp att dramatiskt öka organisationens kapacitet att hantera säkerhetsaviseringar och incidenter. Med automatiserad undersökning och svar kan du minska kostnaderna för att hantera utrednings- och saneringsaktiviteter och få ut det mesta av din hotskyddssvit. automatisk undersökning och svar hjälper ditt säkerhetsteam genom att:

1. Avgöra om ett hot kräver åtgärder.
2. Utföra (eller rekommendera) nödvändiga saneringsåtgärder;
3. Fastställande av vilka ytterligare undersökningar som bör ske. Och
4. Upprepa processen efter behov för andra aviseringar.

## <a name="the-automated-investigation-process"></a>Den automatiserade utredningsprocessen

**Varning**  >  **incident**  >  **automatiserad undersökning**  >  **dom**  >  **åtgärder för att åtgärda**

En utlöst avisering skapar en incident som kan starta en automatiserad undersökning. Den undersökningen kan resultera i en eller flera åtgärder. I Microsoft Threat Protection korrelerar varje automatiserad undersökning signaler över Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) och Office 365 Advanced Threat Protection (Office 365 ATP), som sammanfattas i följande tabell: 

|Enheter |Tjänster för skydd av hot  |
|---------|---------|
|Enheter (kallas även slutpunkter)     |[Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-postinnehåll (filer och meddelanden i postlådor)     |[Skaffa Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Varje undersökning genererar domar (*Malicious*, *Suspicious*, or *No threats found*) för varje bevis som undersökts. Beroende på vilken typ av hot och resulterande dom, reparationsåtgärder sker automatiskt eller efter godkännande av organisationens säkerhetsoperationer team. Väntande och slutförda åtgärder visas i [åtgärdscentret](mtp-action-center.md).

> [!TIP]
> Om du tror att något missades eller felaktigt upptäcktes av automatiska undersöknings- och svarsfunktioner i Microsoft Threat Protection, låt oss veta! Se [Så här rapporterar du falska positiva identifieringar/negativ i automatiska funktioner för undersökningar och svar i Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Medan en undersökning pågår läggs alla andra relaterade aviseringar som uppstår till i undersökningen tills den är klar. Om en angripen enhet visas någon annanstans utökas dess omfattning till att omfatta den enheten och en allmän säkerhetsspelbok körs. 

> [!NOTE]
> Inte varje varning utlöser en automatiserad undersökning, och inte varje undersökning resulterar i automatiserade saneringsåtgärder; Allt detta beror på hur automatisk undersökning och svar är konfigurerad för din organisation. 

## <a name="requirements-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Krav för automatisk undersökning och svar i Microsoft Threat Protection

|Krav |Information |
|--|--|
|Krav på prenumeration |Något av följande: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 A5 <br/>- Microsoft 365 E5 Säkerhet<br/>- Microsoft 365 A5 Säkerhet<br/>- Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>Se [Licenskraven för Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Nätverkskrav |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) aktiverat<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) konfigurerad<br/>- [MCAS integrerat med Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Krav på Windows-datorer |- Windows 10, version 1709 eller senare installerad (Se [Windows 10-utgivningsinformation)](https://docs.microsoft.com/windows/release-information/)med följande hotskyddstjänster konfigurerade:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Antivirusprogram för Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Skydd för e-postinnehåll och Office-filer |[Office 365 Avancerat skydd mot hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|Behörigheter |- Om du vill konfigurera automatisk undersökning och svar måste rollen Global administratör eller säkerhetsadministratör tilldelas i Antingen Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) eller i Microsoft 365 administrationscenter ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>- Information om hur du använder automatiska funktioner för undersökning och svar finns [i Obligatoriska behörigheter för åtgärdscenteruppgifter](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Nästa steg

- [Godkänna eller avvisa åtgärder relaterade till automatisk undersökning och svar](mtp-autoir-actions.md)
- [Läs mer om Åtgärdscentret](mtp-action-center.md)
