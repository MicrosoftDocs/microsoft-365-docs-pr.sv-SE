---
title: Krav & - hantering av hot och sårbarhet
description: Innan du börjar använda hantering av hot och hot bör du kontrollera att du har rätt konfigurationer och behörigheter.
keywords: hot & säkerhetshanteringsbehörigheter förutsättningar, behörigheter för hot och sårbarhetshantering, MDATP TVM-behörighetsförutsättningarna, hantering av säkerhetsbrister
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ca095a7a65a114182d736176840fdd4e651a8646
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074842"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="f75b7-104">Krav & - hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="f75b7-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f75b7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f75b7-105">**Applies to:**</span></span>

- [<span data-ttu-id="f75b7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f75b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f75b7-107">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="f75b7-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f75b7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f75b7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f75b7-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f75b7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f75b7-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f75b7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="f75b7-111">Kontrollera att dina enheter:</span><span class="sxs-lookup"><span data-stu-id="f75b7-111">Ensure that your devices:</span></span>

- <span data-ttu-id="f75b7-112">Introduceras till Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f75b7-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f75b7-113">Kör [operativsystem och plattformar som stöds](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="f75b7-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="f75b7-114">Ha följande obligatoriska uppdateringar installerade och distribuerade i nätverket för att förbättra utvärderingsfrekvensen för sårbarheter:</span><span class="sxs-lookup"><span data-stu-id="f75b7-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="f75b7-115">Version</span><span class="sxs-lookup"><span data-stu-id="f75b7-115">Release</span></span> | <span data-ttu-id="f75b7-116">Säkerhetsuppdatering, KB-nummer och länk</span><span class="sxs-lookup"><span data-stu-id="f75b7-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="f75b7-117">Windows 10 Version 1709</span><span class="sxs-lookup"><span data-stu-id="f75b7-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="f75b7-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) och [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="f75b7-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="f75b7-119">Windows 10 Version 1803</span><span class="sxs-lookup"><span data-stu-id="f75b7-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="f75b7-120">[KB4493464](https://support.microsoft.com/help/4493464) och [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="f75b7-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="f75b7-121">Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="f75b7-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="f75b7-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="f75b7-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="f75b7-123">Windows 10 version 1903</span><span class="sxs-lookup"><span data-stu-id="f75b7-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="f75b7-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="f75b7-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="f75b7-125">Är onboarded to [Microsoft Intune and](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span><span class="sxs-lookup"><span data-stu-id="f75b7-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="f75b7-126">Om du använder Konfigurationshanteraren uppdaterar du konsolen till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="f75b7-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="f75b7-127">**Obs!** Om Intune-anslutningen är aktiverad får du ett alternativ för att skapa en Intune-säkerhetsaktivitet när du skapar en åtgärdsbegäran.</span><span class="sxs-lookup"><span data-stu-id="f75b7-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="f75b7-128">Det här alternativet visas inte om anslutningen inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="f75b7-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="f75b7-129">Ha minst en rekommendation för säkerhet som kan visas på sidan enhet</span><span class="sxs-lookup"><span data-stu-id="f75b7-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="f75b7-130">Är märkta eller markerade som hanterade tillsammans</span><span class="sxs-lookup"><span data-stu-id="f75b7-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="f75b7-131">Relevanta behörighetsalternativ</span><span class="sxs-lookup"><span data-stu-id="f75b7-131">Relevant permission options</span></span>

1. <span data-ttu-id="f75b7-132">Logga in på Microsoft Defender Säkerhetscenter med ett konto med en tilldelad säkerhetsadministratör eller global administratörsroll.</span><span class="sxs-lookup"><span data-stu-id="f75b7-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="f75b7-133">I navigeringsfönstret väljer du **Inställningar > Roller**.</span><span class="sxs-lookup"><span data-stu-id="f75b7-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="f75b7-134">Mer information finns i [Skapa och hantera roller för rollbaserad åtkomstkontroll](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f75b7-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="f75b7-135">Visa data</span><span class="sxs-lookup"><span data-stu-id="f75b7-135">View data</span></span>

- <span data-ttu-id="f75b7-136">**Säkerhetsåtgärder** – visa alla data i säkerhetsåtgärder i portalen</span><span class="sxs-lookup"><span data-stu-id="f75b7-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="f75b7-137">**Hantering av hot och sårbarhet** – visa data om hot och sårbarhetshantering i portalen</span><span class="sxs-lookup"><span data-stu-id="f75b7-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="f75b7-138">Aktiva åtgärdsåtgärder</span><span class="sxs-lookup"><span data-stu-id="f75b7-138">Active remediation actions</span></span>

- <span data-ttu-id="f75b7-139">**Säkerhetsåtgärder** – Vidta svarsåtgärder, godkänna eller stänga väntande åtgärder, hantera tillåtna/blockerade listor för automatisering och indikatorer</span><span class="sxs-lookup"><span data-stu-id="f75b7-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="f75b7-140">**Hantering av hot och sårbarhet – Undantagshantering** – Skapa nya undantag och hantera aktiva undantag</span><span class="sxs-lookup"><span data-stu-id="f75b7-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="f75b7-141">**Hantering av hot och sårbarhet - Åtgärdshantering** - Skicka in nya åtgärdsförfrågningar, skapa ärenden och hantera befintliga åtgärdsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="f75b7-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="f75b7-142">Mer information finns i [Behörighetsalternativ för RBAC](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="f75b7-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="f75b7-143">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="f75b7-143">Related articles</span></span>

- [<span data-ttu-id="f75b7-144">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="f75b7-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f75b7-145">Operativsystem och plattformar som stöds</span><span class="sxs-lookup"><span data-stu-id="f75b7-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="f75b7-146">Tilldela enhetsvärde</span><span class="sxs-lookup"><span data-stu-id="f75b7-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="f75b7-147">Instrumentpanel för hantering av hot och hot</span><span class="sxs-lookup"><span data-stu-id="f75b7-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

