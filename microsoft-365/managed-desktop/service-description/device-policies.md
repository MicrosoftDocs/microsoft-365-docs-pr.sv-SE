---
title: Enhetskonfiguration
description: Läs mer om standardprinciper som används för Microsoft Managed Desktop-enheter.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e4f07adb051dde24d374055d206955ad61df432a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920498"
---
# <a name="device-configuration"></a>Enhetskonfiguration


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

När en ny Microsoft Managed Desktop-enhet håller på att konfigureras ser vi till att den har rätt konfiguration optimerad för Microsoft Managed Desktop. Den konfigurationen innehåller en uppsättning standardprinciper som angetts som en del av onboarding-processen. Dessa principer levereras med mdm (Mobile Device Management) när det är möjligt. Mer information finns i [Hantering av mobila enheter.](/windows/client-management/mdm/) 

>[!NOTE]
>Ändra inte dessa principer för att undvika konflikter.

Enheter får en signaturbild och ansluter sedan till Azure Active Directory-domänen när den första användaren loggar in. Enheten kommer automatiskt att installera nödvändiga principer och program utan åtgärder från din IT-personal.

## <a name="default-policies"></a>Standardprinciper

I den här tabellen markeras de standardprinciper som tillämpas på alla Microsoft Managed Desktop-enheter vid enhetsetablering. Alla ändringar som inte godkänts av Microsoft Managed Desktop Operations Team för objekt som hanteras av Microsoft Managed Desktop återställs.

Princip | Beskrivning
--- | ---
Baslinje för säkerhet | [Microsofts säkerhetsbaslinje](/windows/device-security/windows-security-baselines) för MDM är konfigurerad för alla Microsoft Managed Desktop-enheter. Den här baslinjen är standardkonfigurationen för branschen. Det är offentligt släppt, väl testat och har granskats av Microsofts säkerhetsexperter för att hålla Microsoft Managed Desktop-enheter och -appar säkra på den moderna arbetsplatsen. <br><br>Microsofts säkerhetsbaslinje kommer att uppdateras och distribueras till Microsoft Managed Desktop-enheter med varje funktionsuppdatering för Windows 10 för att minimera hot i det ständigt föränderliga landskapet för säkerhetshot.<br><br>Mer information finns i [Windows säkerhetsbaslinjer](/windows/security/threat-protection/windows-security-baselines).
Rekommenderad säkerhetsmall för Microsoft Managed Desktop | En uppsättning rekommenderade ändringar av säkerhetsbaslinjen som optimerar användarupplevelsen.  Dessa ändringar har dokumenterats [i Säkerhets addendum.](#security-addendum) Uppdateringar av principuppdateringen sker efter behov.  
Uppdatera distribution | Använd Windows Update för företag för gradvis distribution av programuppdateringar. IT-administratörer kan inte ändra inställningarna för distributionsgruppsprinciperna. Mer information om gruppbaserad distribution finns i Hur [uppdateringar hanteras i Microsoft Managed Desktop.](updates.md)
Anslutningar med datamätare | Som standard är uppdateringar över anslutningar med databeroende data (t.ex. LTE-nätverk) inaktiverade, men varje användare kan aktivera den här funktionen oberoende **> i > Uppdateringar > Avancerade alternativ.** Om du vill tillåta alla användare att aktivera uppdateringar via anslutningar med dataanslutning [kan](../working-with-managed-desktop/admin-support.md)du skicka en ändringsbegäran , vilket aktiverar den här inställningen för alla enheter.
| Enhetsefterlevnad | De här principerna är konfigurerade för alla Microsoft Managed Desktop-enheter. En enhet rapporteras som icke-kompatibel när den körs från vår nödvändiga säkerhetskonfiguration.

## <a name="windows-diagnostic-data"></a>Windows-diagnostikdata

 Enheter kommer att tillhandahålla förbättrade diagnostikdata till Microsoft med en känd kommersiell identifierare. Som en del av Microsoft Managed Desktop kan IT-administratörer inte ändra de här inställningarna. För kunder i GDPR-regionerna (General Data Protection Regulation) kan användare minska nivån på diagnostikdata som tillhandahålls, men det kommer att minska antalet tjänster. Microsoft Managed Desktop kommer till exempel inte att kunna samla in de data som behövs för att iterera inställningar och principer för bästa möjliga prestanda och säkerhetsbehov. Mer information finns i Konfigurera [Windows-diagnostikdata i organisationen.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Säkerhetsandum

 I det här avsnittet beskrivs de principer som ska distribueras utöver standardprinciperna för Microsoft Managed Desktop som listas i [Standardprinciper.](#default-policies) Den här konfigurationen är utformad med finansiella tjänster och mycket reglerade branscher i åtanke, och optimerar för högsta säkerhet samtidigt som användarnas produktivitet bibehålls.

 ### <a name="additional-security-policies"></a>Ytterligare säkerhetsprinciper

 Dessa principer läggs till för att öka säkerheten för starkt reglerade branscher. 
 - **Säkerhetsövervakning**: Microsoft övervakar enheter med hjälp av [Microsoft Defender för Slutpunkt.](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) Om ett hot upptäcks meddelar Microsoft kunden, isolerar enheten och fjärrstyr problemet. 
 - **Inaktivera PowerShell V2**: Microsoft tog bort PowerShell V2 i augusti 2017. Den här funktionen har inaktiverats på alla Microsoft Managed Desktop-enheter. Mer information om den här ändringen finns i [Utfasning av Windows PowerShell 2.0.](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)