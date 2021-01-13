---
title: Enhetskonfiguration
description: Läs mer om standard principerna som används på Microsoft Managed Station ära enheter.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7086774c046ac28ffa467168e3b5b1affb508ec8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840339"
---
# <a name="device-configuration"></a>Enhetskonfiguration


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

När en ny Microsoft-hanterad stationär enhet konfigureras kontrollerar vi att den har rätt konfiguration som är optimerad för Microsoft Managed Desktop. Denna konfiguration innehåller en uppsättning standard principer som anges som en del av registrerings processen. Dessa principer levereras med hantering av mobila enheter (MDM) när så är möjligt. Mer information finns i [Hantera mobila enheter](https://docs.microsoft.com/windows/client-management/mdm/). 

>[!NOTE]
>För att undvika konflikter bör du inte ändra dessa principer.

Enheter kommer med en disksignatur och ansluter sedan till Azure Active Directory-domänen när den första användaren loggar in. Enheten installerar automatiskt nödvändiga principer och program utan att behöva göra något från din IT-personal.

## <a name="default-policies"></a>Standard principer

I den här tabellen står det standard principer som används för alla Microsoft-hanterade Skriv bords enheter under enhets etablering. Alla upptäckta ändringar som inte har godkänts av Microsoft Managed Desktop Operations team för objekt som hanteras av Microsoft Managed Desktop återställs.

Autentiseringsprincip | Beskrivning
--- | ---
Säkerhets bas linje | [Microsofts säkerhets bas linje](https://docs.microsoft.com/windows/device-security/windows-security-baselines) för MDM är konfigurerat för alla Microsoft-hanterade Skriv bords enheter. Denna bas linje är den branschstandardiserade konfigurationen. Den är offentlig, väl testad och har granskats av Microsofts säkerhets experter för att hålla Microsoft Managed Station ära enheter och appar säkra på den moderna arbets platsen. <br><br>För att minska riskerna i den ständigt växande säkerhets hotet, kommer Microsofts säkerhets bas linje att uppdateras och distribueras till Microsoft Managed Desktop-enheter med varje Windows 10-funktions uppdatering.<br><br>Mer information finns i [säkerhets bas linjer för Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines).
Microsoft Managed Desktop-Rekommenderad säkerhetsmall | En uppsättning rekommenderade ändringar av säkerhets bas linjen som optimerar användar upplevelsen.  Dessa ändringar dokumenteras i [säkerhets tillägget](#security-addendum). Uppdateringar av princip tillägget sker på ett lämpligt sätt.  
Uppdaterings distribution | Använd Windows Update för företag för att utföra en successiv distribution av program varu uppdateringar. IT-administratörer kan inte ändra inställningar för grup principer för distribution. Mer information om gruppbaserad distribution finns i [hur uppdateringar hanteras på Microsoft Managed Desktop](updates.md).
Anslutningar med datapriser | Uppdateringar över anslutningar med datapriser (till exempel LTE-nätverk) är inaktiverade som standard, även om varje användare kan aktivera den här funktionen i **inställningar > uppdateringar > avancerade alternativ**. Om du vill tillåta att alla användare aktiverar uppdateringar via anslutningar med datapriser [skickar du en ändringsbegäran](../working-with-managed-desktop/admin-support.md)och aktiverar den här inställningen för alla enheter.
| Kompatibilitet med enheter | Dessa principer är konfigurerade för alla Microsoft-hanterade Skriv bords enheter. En enhet rapporteras som icke-kompatibel när vår säkerhets konfiguration används.

## <a name="windows-diagnostic-data"></a>Windows-diagnostikdata

 Enheter ställs in för att tillhandahålla utökade diagnostikdata till Microsoft under ett känt handels-ID. Som en del av Microsoft Managed Desktop kan IT-administratörer inte ändra de här inställningarna. För kunder i GDPR-regioner (General Data Protection förordning) kan användarna minska den nivå med diagnostikdata som tillhandahålls, men tjänsten minskar också. Microsoft Managed Desktop kan till exempel inte samla in de data som behövs för att iterera efter inställningar och policyer för bästa prestanda och säkerhets behov. Mer information finns i [Konfigurera diagnostikdata för Windows i organisationen.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Säkerhets tillägg

 I det här avsnittet beskrivs de principer som ska distribueras utöver de vanliga Microsoft Managed Desktop-principerna i [standard principer](#default-policies). Denna konfiguration är utvecklad med finans tjänster och högreglerade branscher och optimerar för högsta säkerheten samtidigt som användar produktiviteten upprätthålls.

 ### <a name="additional-security-policies"></a>Ytterligare säkerhets principer

 Dessa principer läggs till för att öka säkerheten för högreglerade branscher. 
 - **Säkerhets övervakning**: Microsoft övervakar enheter med [Microsoft Defender för slut punkter](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Om ett hot identifieras meddelar Microsoft kunden, isolerar enheten och kan lösa problemet från fjärran. 
 - **Inaktivera PowerShell V2**: Microsoft har tagit bort PowerShell V2 i augusti 2017. Den här funktionen har inaktiverats på alla Microsoft-hanterade Skriv bords enheter. Mer information om den här ändringen finns i [Windows PowerShell 2,0-utfasning](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).
