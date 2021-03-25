---
title: Skapa indikatorer för filer
ms.reviewer: ''
description: Skapa indikatorer för en filhash som definierar identifiering, skydd och undantag för enheter.
keywords: fil, hash, hantera, tillåten, blockerad, blockera, rensa, skadlig, filshashar, ip-adress, url:er, domän
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
ms.openlocfilehash: 35a0b66a4cdc4cf39c15329eda2e0aafced79f34
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199615"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="92c16-104">Skapa indikatorer för filer</span><span class="sxs-lookup"><span data-stu-id="92c16-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="92c16-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="92c16-105">**Applies to:**</span></span>
- [<span data-ttu-id="92c16-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="92c16-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="92c16-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92c16-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="92c16-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="92c16-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="92c16-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="92c16-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="92c16-110">Du kan förhindra ytterligare spridning av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="92c16-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="92c16-111">Om du vet en potentiellt skadlig körbar fil (PE) kan du blockera den.</span><span class="sxs-lookup"><span data-stu-id="92c16-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="92c16-112">Den här åtgärden förhindrar att den läses, skrivs eller körs på datorer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="92c16-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="92c16-113">Du kan skapa indikatorer för filer på två sätt:</span><span class="sxs-lookup"><span data-stu-id="92c16-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="92c16-114">Genom att skapa en indikator via inställningssidan</span><span class="sxs-lookup"><span data-stu-id="92c16-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="92c16-115">Genom att skapa en sammanhangsberoende indikator med knappen lägg till indikator från filinformationssidan</span><span class="sxs-lookup"><span data-stu-id="92c16-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="92c16-116">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="92c16-116">Before you begin</span></span>
<span data-ttu-id="92c16-117">Det är viktigt att förstå följande förutsättningar innan du skapar indikatorer för filer:</span><span class="sxs-lookup"><span data-stu-id="92c16-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="92c16-118">Den här funktionen är tillgänglig om din organisation använder Windows Defender Antivirus och Molnbaserat skydd är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="92c16-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="92c16-119">Mer information finns i [Använda nästa generations teknik i Microsoft Defender Antivirus via moln levererat skydd.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="92c16-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="92c16-120">Klientversionen av Antimalware måste vara 4.18.1901.x eller senare.</span><span class="sxs-lookup"><span data-stu-id="92c16-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="92c16-121">Stöds på datorer med Windows 10, version 1703 eller senare, Windows Server 2016 och 2019.</span><span class="sxs-lookup"><span data-stu-id="92c16-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="92c16-122">För att börja blockera filer måste du först [aktivera funktionen Spärra eller **tillåt**](advanced-features.md) i Inställningar.</span><span class="sxs-lookup"><span data-stu-id="92c16-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="92c16-123">Den här funktionen är utformad för att förhindra att misstänkt skadlig programvara (eller potentiellt skadliga filer) laddas ned från webben.</span><span class="sxs-lookup"><span data-stu-id="92c16-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="92c16-124">Den har för närvarande stöd för bärbara körbara (PE) filer, inklusive _.exe-_ _och .dll-filer._</span><span class="sxs-lookup"><span data-stu-id="92c16-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="92c16-125">Täckningen utökas med tiden.</span><span class="sxs-lookup"><span data-stu-id="92c16-125">The coverage will be extended over time.</span></span>

<span data-ttu-id="92c16-126">Prestandan kan påverkas om du kopierar stora filer från en nätverksresurs till din lokala enhet, särskilt via en VPN-anslutning.</span><span class="sxs-lookup"><span data-stu-id="92c16-126">Performance can be affected if you are copying large files from a network share onto your local device, especially over a VPN connection.</span></span> 

> [!IMPORTANT]
> - <span data-ttu-id="92c16-127">Funktionen tillåt eller blockera kan inte utföras för filer om filens klassificering finns på enhetens cache innan åtgärden för att tillåta eller blockera</span><span class="sxs-lookup"><span data-stu-id="92c16-127">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
> - <span data-ttu-id="92c16-128">Betrodda signerade filer behandlas annorlunda.</span><span class="sxs-lookup"><span data-stu-id="92c16-128">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="92c16-129">Defender för Endpoint är optimerad för att hantera skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="92c16-129">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="92c16-130">Att försöka blockera betrodda signerade filer kan i vissa fall ha prestandakonsekvenser.</span><span class="sxs-lookup"><span data-stu-id="92c16-130">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>
> - <span data-ttu-id="92c16-131">Vanligtvis används filblock inom några minuter, men det kan ta upp till 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="92c16-131">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> - <span data-ttu-id="92c16-132">Om det finns filindikatorprinciper som står i konflikt tillämpas den säkrare principens tillämpningsprincip.</span><span class="sxs-lookup"><span data-stu-id="92c16-132">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="92c16-133">En SHA-256-princip för hash-kod för filer har till exempel företräde framför en MD5-princip för hash-hash-kod för filer om båda hash-typerna definierar samma fil.</span><span class="sxs-lookup"><span data-stu-id="92c16-133">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="92c16-134">Skapa en indikator för filer från inställningssidan</span><span class="sxs-lookup"><span data-stu-id="92c16-134">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="92c16-135">Välj Inställningar Indikatorer i  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="92c16-135">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="92c16-136">Välj fliken **Filhash.**</span><span class="sxs-lookup"><span data-stu-id="92c16-136">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="92c16-137">Välj **Lägg till indikator**.</span><span class="sxs-lookup"><span data-stu-id="92c16-137">Select **Add indicator**.</span></span>

4. <span data-ttu-id="92c16-138">Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="92c16-138">Specify the following details:</span></span>
   - <span data-ttu-id="92c16-139">Indikator – Ange entitetsinformation och definiera indikatorns förfallotid.</span><span class="sxs-lookup"><span data-stu-id="92c16-139">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="92c16-140">Åtgärd – Ange vilken åtgärd som ska vidtas och ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="92c16-140">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="92c16-141">Omfattning – Definiera datorgruppens omfattning.</span><span class="sxs-lookup"><span data-stu-id="92c16-141">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="92c16-142">Granska informationen på fliken Sammanfattning och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="92c16-142">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="92c16-143">Skapa en sammanhangsberoende indikator från filinformationssidan</span><span class="sxs-lookup"><span data-stu-id="92c16-143">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="92c16-144">Ett av alternativen när du vidtar [svarsåtgärder för en fil är](respond-file-alerts.md) att lägga till en indikator för filen.</span><span class="sxs-lookup"><span data-stu-id="92c16-144">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="92c16-145">När du lägger till en indikatorhash för en fil kan du välja att avisering ska visas och blockera filen när en dator i organisationen försöker köra den.</span><span class="sxs-lookup"><span data-stu-id="92c16-145">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="92c16-146">Filer som blockeras automatiskt av en indikator visas inte i filens Åtgärdscenter, men aviseringarna visas fortfarande i kön Aviseringar.</span><span class="sxs-lookup"><span data-stu-id="92c16-146">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="92c16-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="92c16-147">Related topics</span></span>
- [<span data-ttu-id="92c16-148">Skapa indikatorer</span><span class="sxs-lookup"><span data-stu-id="92c16-148">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="92c16-149">Skapa indikatorer för IP-adresser och URL:er/domäner</span><span class="sxs-lookup"><span data-stu-id="92c16-149">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="92c16-150">Skapa indikatorer baserade på certifikat</span><span class="sxs-lookup"><span data-stu-id="92c16-150">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="92c16-151">Hantera indikatorer</span><span class="sxs-lookup"><span data-stu-id="92c16-151">Manage indicators</span></span>](indicator-manage.md)
