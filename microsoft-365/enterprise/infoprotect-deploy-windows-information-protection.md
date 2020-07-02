---
title: 'Steg 4: Konfigurera Windows-informationsskydd'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och distribuera Windows informationsskydd i Microsoft 365.
ms.openlocfilehash: c7b76ef28d41810d6e9e45e98adb7a94cf8ae2f4
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005728"
---
# <a name="step-4-configure-windows-information-protection"></a>Steg 4: Konfigurera Windows-informationsskydd

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Med fler personliga enheter som används för arbete finns det en ökad risk för att appar och enheter ska läcka privata organisationsdata. En anställd skickar exempelvis av misstag en bild av en marknadsföringsplan för en kommande produkt till en social mediefil eller sparar en fil som innehåller känslig information i molnet. 

Windows information Protection (WIP) hjälper till att skydda mot den här typen av dataläckage på Windows 10-enheter. Mer information finns i [Skydda ditt företags data med hjälp av WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

I Microsoft 365 Enterprise är WIP en kombination av Windows 10 Enterprise och Microsoft Intune, som ingår i prenumerationen. 

Så här distribuerar du WIP i din organisation med Microsoft 365 Enterprise:

1. Registrera dina Windows-enheter i Intune. Du bör ha gjort detta i [steg 5: Hantering av mobila enhet](mobility-infrastructure.md).

2. Skapa en [Intune-princip för WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).

   -    Kontrollera att du har fyllt i listan med skyddade appar.
  
   - Välj nivån för ditt WIP-skydd.

Du kan också använda WIP med [Konfigurationshanteraren för Microsoft Endpoint](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr). 

Mer information finns i [metodtips för WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](infoprotect-exit-criteria.md#crit-infoprotect-step4) som motsvarar det här steget.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 5](../media/stepnumbers/Step5.png)|[Konfigurera dataförlustskydd](infoprotect-data-loss-prevention.md)|


