---
title: Översikt över integrering av Microsoft Cloud App-säkerhet
ms.reviewer: ''
description: Microsoft Defender för Endpoint integreras med Cloud App Security genom att vidarebefordra alla nätverksaktiviteter i molnet.
keywords: moln, app, nätverk, synlighet, användning
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: d756c738f9f61638a9e7424aa3fdf639f8f02f2a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185605"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="3883a-104">Översikt över Microsoft Cloud App Security i Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="3883a-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3883a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3883a-105">**Applies to:**</span></span>
- [<span data-ttu-id="3883a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3883a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3883a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3883a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="3883a-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3883a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3883a-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3883a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3883a-110">Microsoft Cloud App Security (Cloud App Security) är en omfattande lösning som ger insyn i molnappar och -tjänster genom att kontrollera och begränsa åtkomsten till molnappar, samtidigt som efterlevnadskraven för data som lagras i molnet upprätthålls.</span><span class="sxs-lookup"><span data-stu-id="3883a-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="3883a-111">Mer information finns i [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="3883a-111">For more information, see [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="3883a-112">Den här funktionen är tillgänglig med en E5-licens för [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) på enheter med Windows 10 version 1809 eller senare.</span><span class="sxs-lookup"><span data-stu-id="3883a-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="3883a-113">Microsoft Defender för slutpunkts- och molnappens säkerhetsintegrering</span><span class="sxs-lookup"><span data-stu-id="3883a-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="3883a-114">Identifiering av Molnappsäkerhet förlitar sig på att molntrafikloggar vidarebefordras till den från företagets brandvägg och proxyservrar.</span><span class="sxs-lookup"><span data-stu-id="3883a-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="3883a-115">Microsoft Defender för Endpoint integreras med Cloud App Security genom att samla in och vidarebefordra alla nätverksaktiviteter i molnet, vilket ger enastående synlighet till användning av molnappen.</span><span class="sxs-lookup"><span data-stu-id="3883a-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="3883a-116">Övervakningsfunktionerna är inbyggda i enheten, vilket ger fullständig täckning av nätverksaktivitet.</span><span class="sxs-lookup"><span data-stu-id="3883a-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="3883a-117">Integreringen innehåller följande större förbättringar av den befintliga Cloud App Security-identifieringen:</span><span class="sxs-lookup"><span data-stu-id="3883a-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="3883a-118">Tillgängligt överallt – Eftersom nätverksaktiviteten samlas in direkt från slutpunkten är den tillgänglig oavsett var enheten finns, på eller utanför företagsnätverket, eftersom den inte längre är beroende av trafik som dirigeras genom företagsbrandväggen eller proxyservrarna.</span><span class="sxs-lookup"><span data-stu-id="3883a-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="3883a-119">Fungerar utan att konfiguration krävs – Vidarebefordra molntrafikloggar till Cloud App Security kräver brandväggs- och proxyserverkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="3883a-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="3883a-120">Det krävs ingen konfiguration med Defender för slutpunkts- och molnappens säkerhetsintegrering.</span><span class="sxs-lookup"><span data-stu-id="3883a-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="3883a-121">Det är bara att slå på den i inställningarna för Microsoft Defender Säkerhetscenter så är du redo.</span><span class="sxs-lookup"><span data-stu-id="3883a-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="3883a-122">Enhetskontext – Molntrafikloggar saknar enhetskontext.</span><span class="sxs-lookup"><span data-stu-id="3883a-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="3883a-123">Defender för slutpunktsnätverksaktivitet rapporteras med enhetskontexten (vilken enhet som kom åt molnappen) så att du kan förstå exakt var (enhet) nätverksaktiviteten utfördes, utöver vem (användaren) som utförde den.</span><span class="sxs-lookup"><span data-stu-id="3883a-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="3883a-124">Mer information om molnidentifiering finns i [Arbeta med identifierade appar.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="3883a-124">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="3883a-125">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="3883a-125">Related topic</span></span>

- [<span data-ttu-id="3883a-126">Konfigurera Microsoft Cloud App-säkerhetsintegrering</span><span class="sxs-lookup"><span data-stu-id="3883a-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
