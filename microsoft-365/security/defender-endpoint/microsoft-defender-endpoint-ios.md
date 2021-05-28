---
title: Microsoft Defender för Endpoint för iOS
ms.reviewer: ''
description: Beskriver hur du installerar och använder Microsoft Defender för Slutpunkt i iOS
keywords: microsoft, defender, Microsoft Defender för slutpunkt, ios, översikt, installation, distribuera, avinstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a051742775c3d4e8b36bf0ba7a4fd2502763014
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694467"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender för Endpoint för iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender för Slutpunkt för iOS** skyddar mot nätfiske och osäkra nätverksanslutningar från webbplatser, e-postmeddelanden och appar. Alla aviseringar är tillgängliga i ett enda fönster med Microsoft Defender Säkerhetscenter. Portalen ger säkerhetsteamen en centraliserad bild av hot på iOS-enheter samt andra plattformar.

> [!CAUTION]
> Att köra andra slutpunktsskyddsprodukter från tredje part tillsammans med Defender för Endpoint på iOS kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.

## <a name="pre-requisites"></a>Förutsättningar

**För slutanvändare**

- Microsoft Defender för slutpunktslicens tilldelad till slutanvändare av programmet. Se [Microsoft Defender för Slutpunktslicensieringskrav](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).

- Enheter registreras via appen [Intune-företagsportal](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) för att tillämpa efterlevnadsprinciper för Intune-enheter. Det kräver att användaren tilldelas en Microsoft Intune licens.
    - Intune-företagsportal-appen kan laddas ned från [Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Observera att Apple inte tillåter omdirigering av användare att ladda ned andra appar från app store, och därför måste detta steg utföras av användaren innan användaren börjar använda Microsoft Defender för slutpunktsappen.

- Mer information om hur du tilldelar licenser finns i [Tilldela användare licenser.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

**För administratörer**

- Åtkomst till Microsoft Defender Säkerhetscenter portalen.

    > [!NOTE]
    > Microsoft Intune är den enda MDM-lösning (Mobile Device Management) som stöds för distribution av Microsoft Defender för slutpunkt i iOS. För närvarande stöds endast registrerade enheter för tvingande Defender för Slutpunkt på iOS-relaterade efterlevnadsprinciper för enheter i Intune.

- Åtkomst till [Microsoft Endpoint Manager ,](https://go.microsoft.com/fwlink/?linkid=2109431)för att distribuera programmet till registrerade användargrupper i organisationen.

**Systemkrav**

- iOS-enheter med iOS 11.0 och högre. iPad officiellt från och med version 1.1.15010101.

- Enheten är registrerad med Intune-företagsportal [appen](https://apps.apple.com/us/app/intune-company-portal/id719171358).

> [!NOTE]
> **Microsoft Defender för slutpunkt i iOS är tillgängligt på [Apple App Store.](https://aka.ms/mdatpiosappstore)**

## <a name="installation-instructions"></a>Installationsanvisningar

Distribution av Microsoft Defender för Endpoint på iOS sker via Microsoft Intune (MDM) och både övervakade och ej övervakade enheter stöds.
Mer information finns i Distribuera [Microsoft Defender för slutpunkt i iOS.](ios-install.md)

## <a name="resources"></a>Resurser

- Håll dig informerad om kommande versioner genom [att besöka Vad är nytt i Microsoft Defender för Endpoint i iOS](ios-whatsnew.md) eller vår [blogg](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).

- Ge feedback via feedbacksystem i appen eller via [SecOps-portalen](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Nästa steg

- [Distribuera Microsoft Defender för Slutpunkt i iOS](ios-install.md)
- [Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner](ios-configure-features.md)
