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
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="88f77-104">Konfigurera Defender för slutpunkt på Android-funktioner</span><span class="sxs-lookup"><span data-stu-id="88f77-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="88f77-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="88f77-105">**Applies to:**</span></span>
- [<span data-ttu-id="88f77-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="88f77-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="88f77-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88f77-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="88f77-108">Villkorsstyrd åtkomst med Defender för slutpunkt på Android</span><span class="sxs-lookup"><span data-stu-id="88f77-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="88f77-109">Microsoft Defender för slutpunkt på Android tillsammans med Microsoft Intune och Azure Active Directory gör det möjligt att tillämpa enhetsefterlevnad och villkorsstyrd åtkomstprincip baserat på risknivåer för enheter.</span><span class="sxs-lookup"><span data-stu-id="88f77-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="88f77-110">Defender för Endpoint är en MTD-lösning (Mobile Threat Defense) som du kan distribuera för att utnyttja den här funktionen via Intune.</span><span class="sxs-lookup"><span data-stu-id="88f77-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="88f77-111">Mer information om hur du konfigurera Defender för Slutpunkt på Android och Villkorsstyrd åtkomst finns [i Defender för Endpoint och Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="88f77-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="88f77-112">Konfigurera anpassade indikatorer</span><span class="sxs-lookup"><span data-stu-id="88f77-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="88f77-113">Defender för slutpunkt på Android har endast stöd för att skapa anpassade indikatorer för IP-adresser och URL:er/domäner.</span><span class="sxs-lookup"><span data-stu-id="88f77-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="88f77-114">Med Defender för slutpunkt på Android kan administratörer även konfigurera anpassade indikatorer som stöder Android-enheter.</span><span class="sxs-lookup"><span data-stu-id="88f77-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="88f77-115">Mer information om hur du konfigurerar anpassade indikatorer finns [i Hantera indikatorer.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="88f77-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="88f77-116">Konfigurera webbskydd</span><span class="sxs-lookup"><span data-stu-id="88f77-116">Configure web protection</span></span>
<span data-ttu-id="88f77-117">Med Defender för slutpunkt på Android kan IT-administratörer konfigurera webbskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="88f77-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="88f77-118">Den här funktionen är tillgänglig i administrationscentret för Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="88f77-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="88f77-119">Defender för Endpoint på Android skulle använda ett VPN för att tillhandahålla Web Protection-funktionen.</span><span class="sxs-lookup"><span data-stu-id="88f77-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="88f77-120">Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="88f77-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="88f77-121">Mer information finns i [Konfigurera webbskydd på enheter som kör Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="88f77-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="88f77-122">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="88f77-122">Related topics</span></span>
- [<span data-ttu-id="88f77-123">Översikt över Microsoft Defender för Endpoint för Android</span><span class="sxs-lookup"><span data-stu-id="88f77-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="88f77-124">Distribuera Microsoft Defender för Endpoint för Android med Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="88f77-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
