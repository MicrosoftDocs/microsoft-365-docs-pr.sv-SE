---
title: Konfigurera Microsoft Defender för Endpoint för Android-funktioner
description: Här beskrivs hur du konfigurerar Microsoft Defender för slutpunkt på Android
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mde, android, konfiguration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935323"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Konfigurera Defender för slutpunkt på Android-funktioner

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Villkorsstyrd åtkomst med Defender för slutpunkt på Android  
Microsoft Defender för slutpunkt på Android tillsammans med Microsoft Intune och Azure Active Directory gör det möjligt att tillämpa enhetsefterlevnad och villkorsstyrd åtkomstprincip baserat på risknivåer för enheter. Defender för Endpoint är en MTD-lösning (Mobile Threat Defense) som du kan distribuera för att utnyttja den här funktionen via Intune.

Mer information om hur du konfigurera Defender för Slutpunkt på Android och Villkorsstyrd åtkomst finns [i Defender för Endpoint och Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>Konfigurera anpassade indikatorer  

> [!NOTE]
> Defender för slutpunkt på Android har endast stöd för att skapa anpassade indikatorer för IP-adresser och URL:er/domäner.

Med Defender för slutpunkt på Android kan administratörer även konfigurera anpassade indikatorer som stöder Android-enheter. Mer information om hur du konfigurerar anpassade indikatorer finns [i Hantera indikatorer.](manage-indicators.md)

## <a name="configure-web-protection"></a>Konfigurera webbskydd
Med Defender för slutpunkt på Android kan IT-administratörer konfigurera webbskyddsfunktionen. Den här funktionen är tillgänglig i administrationscentret för Microsoft Endpoint Manager.

> [!NOTE]
> Defender för Endpoint på Android skulle använda ett VPN för att tillhandahålla Web Protection-funktionen. Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten. Mer information finns i [Konfigurera webbskydd på enheter som kör Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över Microsoft Defender för Endpoint för Android](microsoft-defender-endpoint-android.md)
- [Distribuera Microsoft Defender för Endpoint för Android med Microsoft Intune](android-intune.md)
