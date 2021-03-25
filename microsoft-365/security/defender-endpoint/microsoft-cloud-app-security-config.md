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
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076570"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="47b35-104">Konfigurera Microsoft Cloud App-säkerhet i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="47b35-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="47b35-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="47b35-105">**Applies to:**</span></span>
- [<span data-ttu-id="47b35-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="47b35-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="47b35-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47b35-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="47b35-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="47b35-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="47b35-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="47b35-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="47b35-110">Aktivera Microsoft Cloud App Security-integrering för att dra nytta av Microsoft Defender för identifieringssignaler för slutpunktsmolnapp.</span><span class="sxs-lookup"><span data-stu-id="47b35-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="47b35-111">Den här funktionen är tillgänglig med en E5-licens för [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) på enheter som kör Windows 10, version 1709 (OS-version 16299.1085 med [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, version 1803 (OS Version 17134.704 med [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 med [KB4489899)](https://support.microsoft.com/help/4489899)eller senare Windows 10-versioner.</span><span class="sxs-lookup"><span data-stu-id="47b35-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="47b35-112">Se [Microsoft Defender för slutpunktsintegrering med Microsoft Cloud App Security för](https://docs.microsoft.com/cloud-app-security/mde-integration) detaljerad integrering av Microsoft Defender för Endpoint med Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="47b35-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="47b35-113">Aktivera Microsoft Cloud App-säkerhet i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="47b35-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="47b35-114">I navigeringsfönstret väljer du **Inställningar inställningar Avancerade**  >  **funktioner**.</span><span class="sxs-lookup"><span data-stu-id="47b35-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="47b35-115">Välj **Microsoft Cloud App Security** och ändra växlingsknappen till **På**.</span><span class="sxs-lookup"><span data-stu-id="47b35-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="47b35-116">Klicka **på Spara inställningar.**</span><span class="sxs-lookup"><span data-stu-id="47b35-116">Click **Save preferences**.</span></span>

<span data-ttu-id="47b35-117">När den har aktiverats börjar Microsoft Defender för Endpoint omedelbart vidarebefordra identifieringssignaler till Molnappsäkerhet.</span><span class="sxs-lookup"><span data-stu-id="47b35-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="47b35-118">Visa data som samlats in</span><span class="sxs-lookup"><span data-stu-id="47b35-118">View the data collected</span></span>

<span data-ttu-id="47b35-119">Information om hur du visar och kommer åt Microsoft Defender för slutpunktsdata i Säkerhet i Microsoft Cloud Apps finns i [Undersöka enheter i Molnappsäkerhet.](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="47b35-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="47b35-120">Mer information om molnidentifiering finns i [Arbeta med identifierade appar.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="47b35-120">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="47b35-121">Om du är intresserad av att prova Microsoft Cloud App Security kan du gå till [Utvärderingsversion av Microsoft Cloud App Security](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span><span class="sxs-lookup"><span data-stu-id="47b35-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="47b35-122">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="47b35-122">Related topic</span></span>
- [<span data-ttu-id="47b35-123">Microsoft Cloud App-säkerhetsintegrering</span><span class="sxs-lookup"><span data-stu-id="47b35-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
