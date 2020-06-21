---
title: Enhetskonfiguration
description: Lär dig mer om standardprinciperna för Microsoft Managed Desktop-enheter.
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e0e5c003ed78b78c5f259eae7e08478d523b5b12
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773793"
---
# <a name="device-configuration"></a>Enhetskonfiguration


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

När en ny Microsoft Managed Desktop-enhet konfigureras ser vi till att den har rätt konfiguration optimerad för Microsoft Managed Desktop. Detta inkluderar en uppsättning standardprinciper som anges som en del av introduktionsprocessen. Dessa principer levereras med hjälp av MDM (Mobile Device Management) när det är möjligt. Mer information finns i [Hantering av mobila enheter](https://docs.microsoft.com/windows/client-management/mdm/). 

>[!NOTE]
>Ändra inte dessa principer för att undvika konflikter.

Enheter kommer fram med en signaturavbildning och ansluter sedan till Azure Active Directory-domänen när den första användaren loggar in. Enheten installerar automatiskt nödvändiga principer och program utan att din IT-personal behöver ingripa.

## <a name="default-policies"></a>Standardprinciper

I den här tabellen visas standardprinciper som tillämpas på alla Microsoft-hanterade skrivbordsenheter under enhetsetablering. Alla identifierade ändringar som inte godkänts av Microsoft Managed Desktop Operations Team till objekt som hanteras av Microsoft Managed Desktop återställs.

Politik | Beskrivning
--- | ---
Säkerhetsbaslinje | [Microsofts säkerhetsbaslinje](https://docs.microsoft.com/windows/device-security/windows-security-baselines) för MDM är konfigurerad för alla Microsoft Managed Desktop-enheter. Den här baslinjen är konfigurationen av branschstandard. Det är offentligt släppt, väl testat och har granskats av Microsofts säkerhetsexperter för att hålla Microsoft Managed Desktop-enheter och appar säkra på den moderna arbetsplatsen. <br><br>För att minska hoten i det ständigt föränderliga säkerhetshotlandskapet uppdateras och distribueras Microsofts säkerhetsbaslinje till Microsoft Hanterade stationära enheter med varje Windows 10-funktionsuppdatering.<br><br>Mer information finns i [Windows säkerhetsbaslinjer](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines).
Microsoft Managed Desktop rekommenderad säkerhetsmall | En uppsättning rekommenderade ändringar av säkerhetsbaslinjen som optimerar användarupplevelsen.  Dessa ändringar dokumenteras i [säkerhetstillägget](#security-addendum). Uppdateringar av principtillägget sker efter behov.  
Uppdatera distribution | Använd Windows Update för företag för att utföra gradvis distribution av programuppdateringar. IT-administratörer kan inte ändra inställningarna för distributionsgruppsprinciperna. Mer information om gruppbaserad distribution finns i Så här [hanteras uppdateringar i Microsoft Managed Desktop](updates.md).
Anslutningar med datapriser | Som standard inaktiveras uppdateringar över anslutningar med datapriser (till exempel LTE-nätverk), även om varje användare självständigt kan aktivera den här funktionen i **Inställningar > Uppdateringar > Avancerade alternativ**. Om du vill tillåta alla användare att aktivera uppdateringar via anslutningar med datapriser [skickar du en ändringsbegäran](../working-with-managed-desktop/admin-support.md)som aktiverar den här inställningen för alla enheter.
| Enhetsefterlevnad | Dessa principer är konfigurerade för alla Microsoft Managed Desktop-enheter. En enhet rapporteras som icke-kompatibel när den driver från vår nödvändiga säkerhetskonfiguration.

## <a name="diagnostic-data"></a>Diagnostikdata

 Enheter kommer att ställas in för att ge förbättrade diagnostikdata till Microsoft under en känd kommersiell identifierare. Som en del av Microsoft Managed Desktop kan IT-administratörer inte ändra dessa inställningar. För kunder i allmänna dataskyddsförordning (GDPR) regioner, slutanvändare kan minska nivån på diagnostiska data som tillhandahålls, men det kommer att bli en minskning av tjänsten. Microsoft Managed Desktop kan till exempel inte samla in de data som krävs för att iterera om inställningar och principer för att bäst tillgodose prestanda- och säkerhetsbehov. Mer information finns [i Konfigurera Windows-diagnostikdata i organisationen.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Tillägg för säkerhet

 I det här avsnittet beskrivs de principer som ska distribueras utöver standardprinciperna för Microsoft Managed Desktop som anges i [standardprinciper](#default-policies). Den här konfigurationen är utformad med finansiella tjänster och högt reglerade branscher i åtanke, optimera för högsta säkerhet samtidigt som användarnas produktivitet bibehålls.

 ### <a name="additional-security-policies"></a>Ytterligare säkerhetsprinciper

 Denna politik läggs till för att öka säkerheten för starkt reglerade industrier. 
 - **Säkerhetsövervakning:** Microsoft övervakar enheter med [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Om ett hot upptäcks meddelar Microsoft kunden, isolerar enheten och åtgärdar problemet på distans. 
 - **Inaktivera PowerShell V2**: Microsoft tog bort PowerShell V2 i augusti 2017. Den här funktionen har inaktiverats på alla Microsoft Managed Desktop-enheter. Mer information om den här ändringen finns i [Windows PowerShell 2.0 Deprecation](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).
