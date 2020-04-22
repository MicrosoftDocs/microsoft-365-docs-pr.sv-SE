---
title: 'Steg 7: Konfigurera hantering av privilegierad åtkomst'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Förstå och konfigurera hantering av privilegierad åtkomst.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636994"
---
# <a name="step-7-configure-privileged-access-management"></a>Steg 7: Konfigurera hantering av privilegierad åtkomst

*Det här steget är valfritt och gäller endast E5- och Advanced Compliance-versionerna av Microsoft 365 Enterprise*

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Hantering av privilegierad åtkomst aktiveras genom att konfigurera principer som anger just-in-time-åtkomst för aktivitetsbaserade aktiviteter i din klientorganisation. Det kan hjälpa dig att skydda din organisation från intrång som kan använda befintliga privilegierade administratörskonton med ständig åtkomst till känsliga data eller åtkomst till kritiska konfigurationsinställningar. Du kan till exempel konfigurera en princip för hantering av privilegierad åtkomst som kräver uttryckligt godkännande för åtkomst och ändring av inställningar för organisationspostlådan i din klientorganisation.

I det här steget aktiverar du hantering av privilegierad åtkomst i din klientorganisation och konfigurerar principer för privilegierad åtkomst som ger ytterligare säkerhet för uppgiftsbaserad åtkomst till data- och konfigurationsinställningar för din organisation. Det finns tre grundläggande steg för att komma igång med privilegierad åtkomst i organisationen:
- Skapa en godkännargrupp
- Aktivera privilegierad åtkomst
- Skapa godkännandeprinciper

När du har konfigurerat Privileged Access Management kan din organisation fungera helt utan ständiga privilegier, och ger ett skydd mot säkerhetsproblem som uppstår på grund av sådan ständig administratörsåtkomst. Privilegierad åtkomst kräver godkännanden för att kunna utföra en aktivitet som har en kopplad och definierad godkännandeprincip. Användare som behöver utföra aktiviteter som ingår i en godkännandeprincip måste begära och beviljas åtkomstgodkännande för att få behörigheter för att utföra aktiviteter som definierats i principen.

Om du vill aktivera hantering av privilegierad åtkomst finns i avsnittet [Konfigurera privilegierad åtkomsthantering.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)

Mer information finns i avsnittet [Hantering av privilegierad åtkomst.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)


|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Information om hur du testar den här konfigurationen i en testlabbmiljö finns i [Privileged Access Management – testlabbguide](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](infoprotect-exit-criteria.md#crit-infoprotect-step7) som motsvarar det här steget.

## <a name="next-step"></a>Nästa steg

[Avslutsvillkor för informationsskyddets infrastruktur](infoprotect-exit-criteria.md)
