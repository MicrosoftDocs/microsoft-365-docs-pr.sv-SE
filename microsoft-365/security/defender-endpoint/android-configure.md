---
title: Konfigurera funktioner i Microsoft Defender ATP för Android
description: Här beskrivs hur du konfigurerar Microsoft Defender ATP för Android
keywords: microsoft, defender, atp, android, konfiguration
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4325020e653f14898ece4192e03cbf8b90131136
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163453"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a><span data-ttu-id="3f0ae-104">Konfigurera Defender för slutpunkt för Android-funktioner</span><span class="sxs-lookup"><span data-stu-id="3f0ae-104">Configure Defender for Endpoint for Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3f0ae-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3f0ae-105">**Applies to:**</span></span>
- [<span data-ttu-id="3f0ae-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3f0ae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3f0ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f0ae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a><span data-ttu-id="3f0ae-108">Villkorsstyrd åtkomst med Defender för Slutpunkt för Android</span><span class="sxs-lookup"><span data-stu-id="3f0ae-108">Conditional Access with Defender for Endpoint for Android</span></span>  
<span data-ttu-id="3f0ae-109">Microsoft Defender för slutpunkt för Android tillsammans med Microsoft Intune och Azure Active Directory gör det möjligt att tillämpa enhetsefterlevnad och villkorsstyrda åtkomstprinciper baserat på risknivåer för enheter.</span><span class="sxs-lookup"><span data-stu-id="3f0ae-109">Microsoft Defender for Endpoint for Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="3f0ae-110">Defender för Endpoint är en MTD-lösning (Mobile Threat Defense) som du kan distribuera för att utnyttja den här funktionen via Intune.</span><span class="sxs-lookup"><span data-stu-id="3f0ae-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="3f0ae-111">Mer information om hur du konfigurera Defender för Slutpunkt för Android och Villkorsstyrd åtkomst finns [i Defender för Endpoint och Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="3f0ae-111">For more information about how to set up Defender for Endpoint for Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="3f0ae-112">Konfigurera anpassade indikatorer</span><span class="sxs-lookup"><span data-stu-id="3f0ae-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="3f0ae-113">Defender för slutpunkt för Android har endast stöd för att skapa anpassade indikatorer för IP-adresser och URL:er/domäner.</span><span class="sxs-lookup"><span data-stu-id="3f0ae-113">Defender for Endpoint for Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="3f0ae-114">Med Defender för slutpunkt för Android kan administratörer även konfigurera anpassade indikatorer som stöder Android-enheter.</span><span class="sxs-lookup"><span data-stu-id="3f0ae-114">Defender for Endpoint for Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="3f0ae-115">Mer information om hur du konfigurerar anpassade indikatorer finns [i Hantera indikatorer.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="3f0ae-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="3f0ae-116">Konfigurera webbskydd</span><span class="sxs-lookup"><span data-stu-id="3f0ae-116">Configure web protection</span></span>
<span data-ttu-id="3f0ae-117">Med Defender för slutpunkt för Android kan IT-administratörer konfigurera webbskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="3f0ae-117">Defender for Endpoint for Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="3f0ae-118">Den här funktionen är tillgänglig i administrationscentret för Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="3f0ae-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="3f0ae-119">Defender för Endpoint för Android skulle använda ett VPN för att tillhandahålla Web Protection-funktionen.</span><span class="sxs-lookup"><span data-stu-id="3f0ae-119">Defender for Endpoint for Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="3f0ae-120">Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="3f0ae-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="3f0ae-121">Mer information finns i [Konfigurera webbskydd på enheter som kör Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="3f0ae-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3f0ae-122">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3f0ae-122">Related topics</span></span>
- [<span data-ttu-id="3f0ae-123">Översikt över Microsoft Defender för Slutpunkt för Android</span><span class="sxs-lookup"><span data-stu-id="3f0ae-123">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="3f0ae-124">Distribuera Microsoft Defender för slutpunkt för Android med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3f0ae-124">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span>](android-intune.md)
