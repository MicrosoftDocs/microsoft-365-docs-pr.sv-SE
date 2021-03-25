---
title: Översikt över Microsoft Defender ATP för iOS
ms.reviewer: ''
description: Här beskrivs hur du installerar och använder Microsoft Defender ATP för iOS
keywords: microsoft, defender, atp, ios, overview, installation, deploy, avinstallation, intune
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
ms.openlocfilehash: 72c3cfd51e472bbbda61f0084e131c4298633193
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186995"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a>Microsoft Defender för slutpunkt för iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender för Endpoint för iOS** skyddar mot nätfiske och osäkra nätverksanslutningar från webbplatser, e-postmeddelanden och appar. Alla aviseringar är tillgängliga i ett enda fönster med fönster i Microsoft Defender Säkerhetscenter. Portalen ger säkerhetsteamen en centraliserad bild av hot på iOS-enheter samt andra plattformar.

> [!CAUTION]
> Att köra andra produkter med slutpunktsskydd från tredje part tillsammans med Defender för Endpoint för iOS kan sannolikt orsaka prestandaproblem och oförutsägbara systemfel.

## <a name="pre-requisites"></a>Förutsättningar

**För slutanvändare**

- Microsoft Defender för slutpunktslicens tilldelad till slutanvändare av programmet. Se [Microsoft Defender för Slutpunktslicensieringskrav](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).

- Enheter registreras via [appen](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) Intune-företagsportal för att framtvinga Intune-efterlevnadsprinciper för enheter. Det kräver att användaren tilldelas en Microsoft Intune-licens.
    - Appen Intune-företagsportal kan laddas ned från [Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Observera att Apple inte tillåter omdirigering av användare att ladda ned andra appar från app store, och därför måste detta steg utföras av användaren innan användaren börjar använda Microsoft Defender för slutpunktsappen.

- Mer information om hur du tilldelar licenser finns i [Tilldela användare licenser.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

**För administratörer**

- Åtkomst till Microsoft Defender Säkerhetscenter-portalen.

    > [!NOTE]
    > Microsoft Intune är den enda mdm-lösning (Mobile Device Management) som stöds för distribution av Microsoft Defender för Slutpunkt för iOS. För närvarande stöds endast registrerade enheter för tvingande Defender för Endpoint för iOS-relaterade efterlevnadsprinciper för enheter i Intune.

- Åtkomst till [administrationscentret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)för att distribuera programmet till registrerade användargrupper i organisationen.

**Systemkrav**

- iOS-enheter med iOS 11.0 och högre. iPad-enheter stöds officiellt från och med version 1.1.15010101 och framåt.

- Enheten är registrerad med appen [Intune-företagsportal.](https://apps.apple.com/us/app/intune-company-portal/id719171358)

> [!NOTE]
> **Microsoft Defender ATP (Microsoft Defender för slutpunkt) för iOS är nu tillgängligt på [Apple App Store.](https://aka.ms/mdatpiosappstore)**

## <a name="installation-instructions"></a>Installationsanvisningar

Distribution av Microsoft Defender för Endpoint för iOS sker via Microsoft Intune (MDM) och både övervakade och ej övervakade enheter stöds.
Mer information finns i Distribuera [Microsoft Defender för slutpunkt för iOS.](ios-install.md)

## <a name="resources"></a>Resurser

- Håll dig informerad om kommande versioner genom att besöka vår [blogg](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).

- Ge feedback via feedbacksystem i appen eller via [SecOps-portalen](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Nästa steg

- [Distribuera Microsoft Defender för slutpunkt för iOS](ios-install.md)
- [Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner](ios-configure-features.md)
