---
title: Översikt över informationsskydd i Windows
ms.reviewer: ''
description: Läs mer om hur informationsskydd fungerar i Windows identifiera och skydda känslig information
keywords: information, skydd, dlp, data, förlust, skydd, skydda
search.product: eADQiWindows 10XVcnh
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
ms.technology: mde
ms.openlocfilehash: 9d68f879fe8fd9379b286c106ed9229895f91b9a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841116"
---
# <a name="information-protection-in-windows-overview"></a><span data-ttu-id="151e6-104">Översikt över informationsskydd i Windows</span><span class="sxs-lookup"><span data-stu-id="151e6-104">Information protection in Windows overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="151e6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="151e6-105">**Applies to:**</span></span>

- [<span data-ttu-id="151e6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="151e6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="151e6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="151e6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="151e6-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="151e6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="151e6-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="151e6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="151e6-110">Informationsskydd är en viktig del av Microsoft 365 Enterprise-programsviten, som ger intelligent skydd för att skydda känsliga data samtidigt som produktivitet på arbetsplatsen möjliggörs.</span><span class="sxs-lookup"><span data-stu-id="151e6-110">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span>


>[!TIP]
> <span data-ttu-id="151e6-111">Läs vårt blogginlägg om hur Microsoft Defender för Endpoint integreras med Microsoft Information Protection för att upptäcka, skydda och [övervaka känsliga data på Windows enheter.](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)</span><span class="sxs-lookup"><span data-stu-id="151e6-111">Read our blog post about how Microsoft Defender for Endpoint integrates with Microsoft Information Protection to [discover, protect, and monitor sensitive data on Windows devices](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/).</span></span>

<span data-ttu-id="151e6-112">Defender för Endpoint tillämpar följande metoder för att identifiera, klassificera och skydda data:</span><span class="sxs-lookup"><span data-stu-id="151e6-112">Defender for Endpoint applies the following methods to discover, classify, and protect data:</span></span>

- <span data-ttu-id="151e6-113">**Dataidentifiering** – Identifiera känsliga data på Windows-enheter som är i riskabelt</span><span class="sxs-lookup"><span data-stu-id="151e6-113">**Data discovery** - Identify sensitive data on Windows devices at risk</span></span>
- <span data-ttu-id="151e6-114">**Dataklassificering** – Klassificera data automatiskt utifrån vanliga MicrosoftS informationsskyddsprinciper (MIP) som hanteras Office 365 säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="151e6-114">**Data classification** - Automatically classify data based on common Microsoft Information Protection (MIP) policies managed in Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="151e6-115">Med automatisk klassificering kan du skydda känsliga data även om slutanvändaren inte har klassificerat dem manuellt.</span><span class="sxs-lookup"><span data-stu-id="151e6-115">Auto-classification allows you to protect sensitive data even if the end user hasn’t manually classified it.</span></span>


## <a name="data-discovery-and-data-classification"></a><span data-ttu-id="151e6-116">Dataidentifiering och dataklassificering</span><span class="sxs-lookup"><span data-stu-id="151e6-116">Data discovery and data classification</span></span>

<span data-ttu-id="151e6-117">Defender för Slutpunkt identifierar automatiskt filer med känslighetsetiketter och filer som innehåller typer av känslig information.</span><span class="sxs-lookup"><span data-stu-id="151e6-117">Defender for Endpoint automatically discovers files with sensitivity labels and files that contain sensitive information types.</span></span>

<span data-ttu-id="151e6-118">Känslighetsetiketter klassificerar och hjälper till att skydda känsligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="151e6-118">Sensitivity labels classify and help protect sensitive content.</span></span>

<span data-ttu-id="151e6-119">Typer av känslig information i Office 365 DLP-implementering (Data Loss Prevention) faller under två kategorier:</span><span class="sxs-lookup"><span data-stu-id="151e6-119">Sensitive information types in the Office 365 data loss prevention (DLP) implementation fall under two categories:</span></span>

- <span data-ttu-id="151e6-120">Standard</span><span class="sxs-lookup"><span data-stu-id="151e6-120">Default</span></span>
- <span data-ttu-id="151e6-121">Anpassad</span><span class="sxs-lookup"><span data-stu-id="151e6-121">Custom</span></span>

<span data-ttu-id="151e6-122">Standardtyper för känslig information är t.ex. bankkontonummer, personnummer och nationella IT-nummer.</span><span class="sxs-lookup"><span data-stu-id="151e6-122">Default sensitive information types include information such as bank account numbers, social security numbers, or national IDs.</span></span> <span data-ttu-id="151e6-123">Mer information finns i Vilken [typ av känslig information letar efter](/office365/securitycompliance/what-the-sensitive-information-types-look-for).</span><span class="sxs-lookup"><span data-stu-id="151e6-123">For more information, see [What the sensitive information type look for](/office365/securitycompliance/what-the-sensitive-information-types-look-for).</span></span>

<span data-ttu-id="151e6-124">Anpassade typer är sådana som du definierar och som har utformats för att skydda olika typer av känslig information (till exempel anställnings-ID eller projektnummer).</span><span class="sxs-lookup"><span data-stu-id="151e6-124">Custom types are ones that you define and is designed to protect a different type of sensitive information (for example, employee IDs or project numbers).</span></span> <span data-ttu-id="151e6-125">Mer information finns i Skapa [en anpassad typ av känslig information.](/office365/securitycompliance/create-a-custom-sensitive-information-type)</span><span class="sxs-lookup"><span data-stu-id="151e6-125">For more information see, [Create a custom sensitive information type](/office365/securitycompliance/create-a-custom-sensitive-information-type).</span></span>

<span data-ttu-id="151e6-126">När en fil skapas eller redigeras på en Windows söker Defender för Slutpunkt igenom innehållet för att utvärdera om det innehåller känslig information.</span><span class="sxs-lookup"><span data-stu-id="151e6-126">When a file is created or edited on a  Windows device, Defender for Endpoint scans the content to evaluate if it contains sensitive information.</span></span>

<span data-ttu-id="151e6-127">Aktivera Azure Information Protection-integreringen så att när en fil som innehåller känslig information upptäcks av Defender för Endpoint, även om etiketter eller informationstyper, vidarebefordras den automatiskt till Azure Information Protection från enheten.</span><span class="sxs-lookup"><span data-stu-id="151e6-127">Turn on the Azure Information Protection integration so that when a file that contains sensitive information is discovered by Defender for Endpoint though labels or information types, it is automatically forwarded to Azure Information Protection from the device.</span></span>

![Bild på inställningssidan med Azure Information Protection](images/atp-settings-aip.png)

<span data-ttu-id="151e6-129">De rapporterade signalerna kan visas på Azure Information Protection – Instrumentpanelen för dataidentifiering.</span><span class="sxs-lookup"><span data-stu-id="151e6-129">The reported signals can be viewed on the Azure Information Protection – Data discovery dashboard.</span></span>

## <a name="azure-information-protection---data-discovery-dashboard"></a><span data-ttu-id="151e6-130">Azure Information Protection – Instrumentpanel för dataidentifiering</span><span class="sxs-lookup"><span data-stu-id="151e6-130">Azure Information Protection - Data discovery dashboard</span></span>

<span data-ttu-id="151e6-131">Den här instrumentpanelen visar en sammanfattad identifieringsinformation av data som upptäcks av både Defender för Endpoint och Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="151e6-131">This dashboard presents a summarized discovery information of data discovered by both Defender for Endpoint and Azure Information Protection.</span></span> <span data-ttu-id="151e6-132">Data från Defender för slutpunkt markeras med Platstyp – Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="151e6-132">Data from Defender for Endpoint is marked with Location Type - Endpoint.</span></span>

![Bild av Azure Information Protection – Dataidentifiering](images/azure-data-discovery.png)

<span data-ttu-id="151e6-134">Lägg märke till kolumnen Enhetsrisk till höger. Den här enhetsrisken härleds direkt från Defender för Endpoint, vilket anger risknivån för säkerhetsenheten där filen identifierats, baserat på de aktiva säkerhetshot som upptäckts av Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="151e6-134">Notice the Device Risk column on the right, this device risk is derived directly from Defender for Endpoint, indicating the risk level of the security device where the file was discovered, based on the active security threats detected by Defender for Endpoint.</span></span>

<span data-ttu-id="151e6-135">Klicka på en enhet för att visa en lista med filer som observerats på enheten med deras känslighetsetiketter och informationstyper.</span><span class="sxs-lookup"><span data-stu-id="151e6-135">Click on a device to view a list of files observed on this device, with their sensitivity labels and information types.</span></span>

>[!NOTE]
><span data-ttu-id="151e6-136">Det kan ta ungefär 15–20 minuter innan identifieringen av Azure Information Protection Dashboard återspeglar identifierade filer.</span><span class="sxs-lookup"><span data-stu-id="151e6-136">Please allow approximately 15-20 minutes for the Azure Information Protection Dashboard Discovery to reflect discovered files.</span></span>

## <a name="log-analytics"></a><span data-ttu-id="151e6-137">Logganalys</span><span class="sxs-lookup"><span data-stu-id="151e6-137">Log Analytics</span></span>

<span data-ttu-id="151e6-138">Dataidentifiering baserat på Defender för slutpunkt är också tillgängligt i [Azure Log Analytics](/azure/log-analytics/log-analytics-overview), där du kan utföra komplexa frågor över rådata.</span><span class="sxs-lookup"><span data-stu-id="151e6-138">Data discovery based on Defender for Endpoint is also available in [Azure Log Analytics](/azure/log-analytics/log-analytics-overview), where you can perform complex queries over the raw data.</span></span>

<span data-ttu-id="151e6-139">Mer information om Azure Information Protection-analyser finns i [Central rapportering för Azure Information Protection.](/azure/information-protection/reports-aip)</span><span class="sxs-lookup"><span data-stu-id="151e6-139">For more information on Azure Information Protection analytics, see [Central reporting for Azure Information Protection](/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="151e6-140">Öppna Azure Log Analytics i Azure Portal och öppna ett frågeverktyg (standard eller klassisk).</span><span class="sxs-lookup"><span data-stu-id="151e6-140">Open Azure Log Analytics in Azure portal and open a query builder (standard or classic).</span></span>

<span data-ttu-id="151e6-141">Om du vill visa Defender för slutpunktsdata utför du en fråga som innehåller:</span><span class="sxs-lookup"><span data-stu-id="151e6-141">To view Defender for Endpoint data, perform a query that contains:</span></span>

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

<span data-ttu-id="151e6-142">**Krav:**</span><span class="sxs-lookup"><span data-stu-id="151e6-142">**Prerequisites:**</span></span>

- <span data-ttu-id="151e6-143">Kunder måste ha en prenumeration på Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="151e6-143">Customers must have a subscription for Azure Information Protection.</span></span>
- <span data-ttu-id="151e6-144">Aktivera Azure Information Protection-integrering i Microsoft Defender Säkerhetscenter:</span><span class="sxs-lookup"><span data-stu-id="151e6-144">Enable Azure Information Protection integration in Microsoft Defender Security Center:</span></span>
    - <span data-ttu-id="151e6-145">Gå till **Inställningar** i Microsoft Defender Säkerhetscenter, klicka på **Avancerat Inställningar** under **Allmänt.**</span><span class="sxs-lookup"><span data-stu-id="151e6-145">Go to **Settings** in Microsoft Defender Security Center, click on **Advanced Settings** under **General**.</span></span>



