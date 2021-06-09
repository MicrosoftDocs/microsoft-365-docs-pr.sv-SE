---
title: Krav & behörigheter – Hantering av hot och säkerhetsrisker
description: Innan du börjar Hantering av hot och säkerhetsrisker bör du kontrollera att du har rätt konfigurationer och behörigheter.
keywords: behörighet & hantering av säkerhetsrisker, behörighetsbehörigheter Hantering av hot och säkerhetsrisker, Microsoft Defender för slutpunkt-TVM-behörighetskrav och hantering av säkerhetsrisker
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843956"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="bbfbc-104">Krav & behörigheter – Hantering av hot och säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="bbfbc-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bbfbc-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bbfbc-105">**Applies to:**</span></span>

- [<span data-ttu-id="bbfbc-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbfbc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bbfbc-107">Hot och hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="bbfbc-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="bbfbc-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbfbc-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bbfbc-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="bbfbc-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bbfbc-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="bbfbc-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="bbfbc-111">Kontrollera att dina enheter:</span><span class="sxs-lookup"><span data-stu-id="bbfbc-111">Ensure that your devices:</span></span>

- <span data-ttu-id="bbfbc-112">Introduceras till Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="bbfbc-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="bbfbc-113">Kör [operativsystem och plattformar som stöds](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="bbfbc-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="bbfbc-114">Ha följande obligatoriska uppdateringar installerade och distribuerade i nätverket för att förbättra utvärderingsfrekvensen för sårbarheter:</span><span class="sxs-lookup"><span data-stu-id="bbfbc-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="bbfbc-115">Version</span><span class="sxs-lookup"><span data-stu-id="bbfbc-115">Release</span></span> | <span data-ttu-id="bbfbc-116">Säkerhetsuppdatering, KB-nummer och länk</span><span class="sxs-lookup"><span data-stu-id="bbfbc-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="bbfbc-117">Windows 10 Version 1709</span><span class="sxs-lookup"><span data-stu-id="bbfbc-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="bbfbc-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) och [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="bbfbc-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="bbfbc-119">Windows 10 Version 1803</span><span class="sxs-lookup"><span data-stu-id="bbfbc-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="bbfbc-120">[KB4493464](https://support.microsoft.com/help/4493464) och [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="bbfbc-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="bbfbc-121">Windows 10 Version 1809</span><span class="sxs-lookup"><span data-stu-id="bbfbc-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="bbfbc-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="bbfbc-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="bbfbc-123">Windows 10 Version 1903</span><span class="sxs-lookup"><span data-stu-id="bbfbc-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="bbfbc-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="bbfbc-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="bbfbc-125">Förs över [till Microsoft Intune](/mem/intune/fundamentals/what-is-intune) och [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) för att hjälpa till att åtgärda hot som Hantering av hot och säkerhetsrisker.</span><span class="sxs-lookup"><span data-stu-id="bbfbc-125">Are onboarded to [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="bbfbc-126">Om du använder Konfigurationshanteraren uppdaterar du konsolen till den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="bbfbc-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="bbfbc-127">**Obs!** Om Intune-anslutningen är aktiverad får du ett alternativ för att skapa en Intune-säkerhetsaktivitet när du skapar en åtgärdsbegäran.</span><span class="sxs-lookup"><span data-stu-id="bbfbc-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="bbfbc-128">Det här alternativet visas inte om anslutningen inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="bbfbc-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="bbfbc-129">Ha minst en rekommendation för säkerhet som kan visas på sidan enhet</span><span class="sxs-lookup"><span data-stu-id="bbfbc-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="bbfbc-130">Är märkta eller markerade som hanterade tillsammans</span><span class="sxs-lookup"><span data-stu-id="bbfbc-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="bbfbc-131">Relevanta behörighetsalternativ</span><span class="sxs-lookup"><span data-stu-id="bbfbc-131">Relevant permission options</span></span>

1. <span data-ttu-id="bbfbc-132">Logga in på Microsoft Defender Säkerhetscenter konto med en tilldelad säkerhetsadministratör eller global administratörsroll.</span><span class="sxs-lookup"><span data-stu-id="bbfbc-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="bbfbc-133">I navigeringsfönstret väljer du **Inställningar > Roller**.</span><span class="sxs-lookup"><span data-stu-id="bbfbc-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="bbfbc-134">Mer information finns i [Skapa och hantera roller för rollbaserad åtkomstkontroll](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="bbfbc-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="bbfbc-135">Visa data</span><span class="sxs-lookup"><span data-stu-id="bbfbc-135">View data</span></span>

- <span data-ttu-id="bbfbc-136">**Säkerhetsåtgärder** – visa alla data i säkerhetsåtgärder i portalen</span><span class="sxs-lookup"><span data-stu-id="bbfbc-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="bbfbc-137">**Hot och hantering av säkerhetsrisker** – Hantering av hot och säkerhetsrisker data i portalen</span><span class="sxs-lookup"><span data-stu-id="bbfbc-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="bbfbc-138">Aktiva åtgärdsåtgärder</span><span class="sxs-lookup"><span data-stu-id="bbfbc-138">Active remediation actions</span></span>

- <span data-ttu-id="bbfbc-139">**Säkerhetsåtgärder** – Vidta svarsåtgärder, godkänna eller stänga väntande åtgärder, hantera tillåtna/blockerade listor för automatisering och indikatorer</span><span class="sxs-lookup"><span data-stu-id="bbfbc-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="bbfbc-140">**Hot och hantering av säkerhetsrisker – Undantagshantering** – Skapa nya undantag och hantera aktiva undantag</span><span class="sxs-lookup"><span data-stu-id="bbfbc-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="bbfbc-141">**Hot och hantering av säkerhetsrisker - Åtgärdshantering** - Skicka in nya begäran om åtgärder, skapa ärenden och hantera befintliga åtgärdsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="bbfbc-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="bbfbc-142">Mer information finns i [Behörighetsalternativ för RBAC](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="bbfbc-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="bbfbc-143">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="bbfbc-143">Related articles</span></span>

- [<span data-ttu-id="bbfbc-144">Översikt över hantering av säkerhetsrisker hot och hot</span><span class="sxs-lookup"><span data-stu-id="bbfbc-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="bbfbc-145">Operativsystem och plattformar som stöds</span><span class="sxs-lookup"><span data-stu-id="bbfbc-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="bbfbc-146">Tilldela enhetsvärde</span><span class="sxs-lookup"><span data-stu-id="bbfbc-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="bbfbc-147">Hot och hantering av säkerhetsrisker instrumentpanel</span><span class="sxs-lookup"><span data-stu-id="bbfbc-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

