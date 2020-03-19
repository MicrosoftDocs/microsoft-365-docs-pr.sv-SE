---
title: 'Steg 7: Konfigurera hantering av privilegierad åtkomst för Office 365'
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
description: Förstå och konfigurera hantering av privilegierad åtkomst för Office 365.
ms.openlocfilehash: f29b1e0934a4b9a6d4e3347584f39423d446ed58
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811101"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a>Steg 7: Konfigurera hantering av privilegierad åtkomst för Office 365

*Det här steget är valfritt och gäller endast E5- och Advanced Compliance-versionerna av Microsoft 365 Enterprise*

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Hantering av privilegierad åtkomst aktiveras genom att konfigurera principer som anger just-in-time-åtkomst för uppgiftsbaserade aktiviteter i office 365-klienten. Det kan hjälpa till att skydda din organisation från överträdelser som kan använda befintliga privilegierade administratörskonton med stående åtkomst till känsliga data eller åtkomst till viktiga konfigurationsinställningar. Du kan till exempel konfigurera en princip för hantering av privilegierad åtkomst som kräver uttryckligt godkännande för åtkomst till och ändring av inställningar för organisationspostlådan i office 365-klienten.

I det här steget aktiverar du hantering av privilegierad åtkomst i office 365-klienten och konfigurerar principer för privilegierad åtkomst som ger ytterligare säkerhet för uppgiftsbaserad åtkomst till Office 365-data och konfigurationsinställningar för din organisation. Det finns tre grundläggande steg för att komma igång med privilegierad åtkomst i office 365-organisationen:
- Skapa en godkännargrupp
- Aktivera privilegierad åtkomst
- Skapa principer för godkännande

En konfigurerad, privilegierad åtkomsthantering gör det möjligt för din organisation att arbeta med noll stående privilegier och tillhandahålla ett lager av försvar mot sårbarheter som uppstår på grund av sådan stående administrativ åtkomst. Privilegierad åtkomst kräver godkännanden för att utföra en aktivitet som har en associerad godkännandeprincip definierad. Användare som behöver utföra uppgifter som ingår i en godkännandeprincip måste begära och beviljas åtkomstgodkännande för att ha behörigheter som krävs för att utföra uppgifter som definierats i principen.

Om du vill aktivera hantering av privilegierad åtkomst för Office 365 läser du [avsnittet Konfigurera privilegierad åtkomsthantering i Office 365.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)

Mer information finns [i avsnittet Privilegierad åtkomsthantering i Office 365.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)


|||
|:-------|:-----|
|![Testlabbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Mer om du vill öva den här konfigurationen i en testlabbmiljö finns i [testlabbguiden för hantering av privilegierad åtkomst](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Som en interimskontrollpunkt, se [exitkriterier som](infoprotect-exit-criteria.md#crit-infoprotect-step7) motsvarar detta steg.

## <a name="next-step"></a>Nästa steg

[Exitkriterier för informationsskyddsinfrastruktur](infoprotect-exit-criteria.md)
