---
title: Automatiserade undersöknings- och svarsfunktioner i Microsoft Threat Protection
description: Få en översikt över automatiska undersöknings- och svarsfunktioner i Microsoft Threat Protection
keywords: automatiserad, utredning, varning, utlösande åtgärder, sanering
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
ms.openlocfilehash: f7ae1a285e22ad18d292d37aab0bba0b4a441461
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857457"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Funktioner för automatisk undersökning och svar (AIR) i Microsoft Threat Protection

**Gäller:**
- Skydd av Hot mot Microsoft

När säkerhetsaviseringar utlöses är det upp till säkerhetsgruppen att undersöka aviseringarna och vidta åtgärder för att skydda din organisation. Att prioritera och utreda varningar kan vara mycket tidskrävande, särskilt när nya varningar fortsätter att komma in medan en utredning pågår. Säkerhetsoperationer team kan känna sig överväldigad av den stora mängden hot som de måste övervaka och skydda mot. Det kan hjälpa med funktioner för automatisk undersökning och svar (AIR) i Microsoft Threat Protection. AIR är som att ha en virtuell analytiker i ditt säkerhetsoperationscenter.

## <a name="your-virtual-analyst"></a>Din virtuella analytiker

Tänk dig att ha en virtuell analytiker i din Tier 1 / Tier 2 säkerhetsoperationer team. Den virtuella analytikern härmar de idealiska steg som säkerhetsoperationer skulle vidta för att undersöka och åtgärda hot. Den virtuella assistenten skulle kunna arbeta 24x7, med obegränsad kapacitet, och ta på sig en betydande belastning av utredningar och hot sanering. En sådan virtuell assistent kan avsevärt minska tiden att svara, frigöra din säkerhetsverksamhet team för andra viktiga strategiska projekt. Om detta scenario låter som science fiction, är det inte! En sådan virtuell analytiker är en del av din Microsoft Threat Protection suite, och dess namn är *automatiserad undersökning och svar* (AIR).

AIR gör det möjligt för din säkerhetsinsatsteam att dramatiskt öka organisationens kapacitet att hantera säkerhetsvarningar och incidenter. Med AIR kan du minska kostnaderna för att hantera utrednings- och saneringsaktiviteter och få ut det mesta av din hotskyddssvit. AIR hjälper din säkerhetsinsatsteam genom att:

1. Att avgöra om ett hot kräver åtgärder.
2. Utföra (eller rekommendera) nödvändiga saneringsåtgärder;
3. Fastställande av vilka ytterligare undersökningar som bör göras. Och
4. Upprepa processen efter behov för andra aviseringar.

## <a name="the-automated-investigation-process"></a>Den automatiserade utredningsprocessen

**Alert** > **incident** > **automatiserad utredning** > **dom** > sanering**svars**

En utlöst avisering skapar en incident som kan starta en automatiserad undersökning. Denna undersökning kan leda till en eller flera saneringsåtgärder. I Microsoft Threat Protection korrelerar varje automatiserad undersökning signaler över Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) och Office 365 Advanced Threat Protection (Office 365 ATP), som sammanfattas i följande tabell: 

|Enheter |Tjänster för skydd av hot  |
|---------|---------|
|Enheter (även kallade slutpunkter)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-postinnehåll (filer och meddelanden i postlådor)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Varje undersökning genererar domar (*Malicious*, *Suspicious*, eller *Clean*) för varje del av bevis som undersökts. Beroende på vilken typ av hot och beföljd adkande dom som följer sker reparationsåtgärder automatiskt eller efter godkännande av organisationens säkerhetsinsatsgrupp. Väntande och slutförda åtgärder visas i [åtgärdscentret](mtp-action-center.md).

> [!TIP]
> Om du tror att något har missats eller upptäckts felaktigt genom automatiskundersökning och svarsfunktioner i Microsoft Threat Protection, låt oss veta! Se [Hur du rapporterar falska positiva/negativa effekter i AIR-funktioner (Automated Investigation and Response) i Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Medan en utredning pågår läggs alla andra relaterade aviseringar som uppstår till utredningen tills den är klar. Om en anstöten entitet ses någon annanstans, kommer den automatiska undersökningen att utöka dess omfattning till att omfatta den entiteten, och en allmän säkerhetsspelbok körs. 

> [!NOTE]
> Inte varje avisering utlöser en automatiserad undersökning, och inte alla undersökningar resulterar i automatiserade saneringsåtgärder; Allt detta beror på hur AIR är konfigurerat för din organisation. 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Krav för AIR i Microsoft Threat Protection

| | |
|--|--|
|Abonnemangskrav |Något av följande: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 A5 <br/>- Microsoft 365 E5-säkerhet<br/>- Microsoft 365 A5-säkerhet<br/>- Office 365 E5 plus företagsmobilitet + Säkerhet E5 plus Windows E5<br/><br/>Se [Licenskrav för Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Nätverkskrav |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) aktiverat<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) konfigurerad<br/>- [MCAS integrerat med Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Krav på Windows-dator |- Windows 10, version 1709 eller senare installerat (Se [Windows 10 release information)](https://docs.microsoft.com/windows/release-information/)med följande hotskyddstjänster konfigurerade:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Skydd för e-postinnehåll och Office-filer |[Office 365 Avancerat hotskydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) konfigurerat |
|Behörigheter |- Om du vill konfigurera AIR måste du ha rollen Global Administratör[https://portal.azure.com](https://portal.azure.com)eller Säkerhetsadministratör tilldelad antingen[https://admin.microsoft.com](https://admin.microsoft.com)Azure Active Directory ( ) eller i administrationscentret för Microsoft 365 ( ).<br/><br/>- Om du vill använda AIR-funktioner läser du [obligatoriska behörigheter för åtgärdscenteruppgifter](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Nästa steg

- [Godkänna eller avvisa åtgärder som rör automatiserad undersökning och svar](mtp-autoir-actions.md)
- [Läs mer om Åtgärdscentret](mtp-action-center.md)
