---
title: Konfigurera Microsoft Cloud App-säkerhetsintegrering
ms.reviewer: ''
description: Lär dig hur du aktiverar inställningarna för att aktivera Microsoft Defender för slutpunktsintegrering med Microsoft Cloud App Security.
keywords: moln, app, säkerhet, inställningar, integrering, identifiering, rapport
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f5e2919ae3fcbbb443f6d160c68633ee3427ae5a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187535"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Konfigurera Microsoft Cloud App-säkerhet i Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Aktivera Microsoft Cloud App Security-integrering för att dra nytta av Microsoft Defender för identifieringssignaler för slutpunktsmolnapp.

>[!NOTE]
>Den här funktionen är tillgänglig med en E5-licens för [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) på enheter som kör Windows 10, version 1709 (OS-version 16299.1085 med [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, version 1803 (OS Version 17134.704 med [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 med [KB4489899)](https://support.microsoft.com/help/4489899)eller senare Windows 10-versioner.

> Se [Microsoft Defender för slutpunktsintegrering med Microsoft Cloud App Security för](https://docs.microsoft.com/cloud-app-security/mde-integration) detaljerad integrering av Microsoft Defender för Endpoint med Microsoft Cloud App Security. 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Aktivera Microsoft Cloud App-säkerhet i Microsoft Defender för Endpoint

1. I navigeringsfönstret väljer du **Inställningar inställningar Avancerade**  >  **funktioner**.
2. Välj **Microsoft Cloud App Security** och ändra växlingsknappen till **På**.
3. Klicka **på Spara inställningar.**

När den har aktiverats börjar Microsoft Defender för Endpoint omedelbart vidarebefordra identifieringssignaler till Molnappsäkerhet.

## <a name="view-the-data-collected"></a>Visa data som samlats in

Information om hur du visar och kommer åt Microsoft Defender för slutpunktsdata i Säkerhet i Microsoft Cloud Apps finns i [Undersöka enheter i Molnappsäkerhet.](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)


Mer information om molnidentifiering finns i [Arbeta med identifierade appar.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

Om du är intresserad av att prova Microsoft Cloud App Security kan du gå till [Utvärderingsversion av Microsoft Cloud App Security](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).

## <a name="related-topic"></a>Relaterat ämne
- [Microsoft Cloud App-säkerhetsintegrering](microsoft-cloud-app-security-integration.md)
