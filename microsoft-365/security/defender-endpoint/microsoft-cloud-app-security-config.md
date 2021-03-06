---
title: Konfigurera integration av Microsoft Cloud App Security
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
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844760"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Konfigurera Microsoft Cloud App Security i Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Om du vill dra nytta av Microsoft Defender för identifieringssignaler för slutpunktsmolnappen aktiverar du Microsoft Cloud App Security integration.

>[!NOTE]
>Den här funktionen kommer att vara tillgänglig med en E5-licens för [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) på enheter med Windows 10, version 1709 (OS-version 16299.1085 med [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, version 1803 (OS Version 17134.704 med [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 med [KB4489899)](https://support.microsoft.com/help/4489899)eller senare Windows 10 versioner.

> Se [Microsoft Defender för slutpunktsintegrering med Microsoft Cloud App Security](/cloud-app-security/mde-integration) för detaljerad integrering av Microsoft Defender för Endpoint med Microsoft Cloud App Security. 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Aktivera Microsoft Cloud App Security i Microsoft Defender för Slutpunkt

1. I navigeringsfönstret väljer du **Inställningar inställningar Avancerade**  >  **funktioner**.
2. Välj **Microsoft Cloud App Security** och ändra växlingsknappen till **På**.
3. Klicka **på Spara inställningar.**

När den har aktiverats börjar Microsoft Defender för Endpoint omedelbart vidarebefordra identifieringssignaler till Cloud App Security.

## <a name="view-the-data-collected"></a>Visa data som samlats in

Information om hur du visar och kommer åt Microsoft Defender för slutpunktsdata i Säkerhet i Microsoft Cloud Apps [finns i Undersöka enheter i Cloud App Security](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).


Mer information om molnidentifiering finns i [Arbeta med identifierade appar.](/cloud-app-security/discovered-apps)

Om du är intresserad av att prova att Microsoft Cloud App Security kan du gå till [Microsoft Cloud App Security utvärderingsversion](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).

## <a name="related-topic"></a>Relaterat ämne
- [Microsoft Cloud App Security-integrering](microsoft-cloud-app-security-integration.md)
