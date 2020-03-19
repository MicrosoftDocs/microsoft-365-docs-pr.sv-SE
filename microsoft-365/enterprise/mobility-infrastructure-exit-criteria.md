---
title: Exitkriterier för hantering av mobila enheter
description: Microsoft 365 Enterprise inkluderar hantering av mobila enheter med Microsoft Intune. Granska kraven och förutsättningarna, konfigurera Intune med din Azure Active Directory-resurs, registrera iOS-, macOS-, Android- och Windows-enheter, distribuera appar, skapa en konfigurera profil, använda en efterlevnadsprincip och aktivera villkorlig åtkomst för mobila enheter enhetshantering med Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-dokumentation, hantering av mobila enheter, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 3e8013426983584783488e6f937f8ba5b02d7a1a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805628"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Exitkriterier för hantering av mobila enheter

![Fas 5: Hantering av mobila enheter](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Detta gäller E3- och E5-versionerna av Microsoft 365 Enterprise*

Se till att konfigurationen uppfyller följande krav för infrastruktur för hantering av mobila enheter.

- Intune är konfigurerat, inklusive skapandet av Azure Active Directory (Azure AD) användare och grupper för att tillämpa organisationens regler för enheter.
- Du har registrerat enheter i Intune så att enheterna kan ta emot de principer du skapar.
- Appar läggs till på enheter så att användarna får åtkomst till organisationens Microsoft 365-molntjänster, till exempel Exchange Online och SharePoint Online.
- Funktioner och inställningar konfigureras och tillämpas på dina enheter med hjälp av Azure AD-användare och grupper som du skapar, vilket kan innefatta att aktivera antivirusprogram och begränsa specifika appar.
- Efterlevnadsprinciper finns för att kräva en brandvägg eller en lösenordslängd på en enhet. Om enheterna inte är kompatibla blockerar villkorlig åtkomst åtkomst till organisationens data.

## <a name="results-and-next-steps"></a>Resultat och nästa steg

Dina enheter är registrerade i Intune och konfigureras med lämpliga principer.

|||
|:-------|:-----|
|![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Om du följer faserna för distributionen från slutna till slutskede av Microsoft 365 Enterprise är nästa fas [informationsskydd](infoprotect-infrastructure.md). |
