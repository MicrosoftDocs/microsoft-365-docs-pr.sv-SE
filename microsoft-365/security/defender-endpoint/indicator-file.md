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
ms.openlocfilehash: 4edff7a9c7f541e31363519e4bafc2a21602e011
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075753"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="54f6e-104">Skapa indikatorer för filer</span><span class="sxs-lookup"><span data-stu-id="54f6e-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="54f6e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="54f6e-105">**Applies to:**</span></span>
- [<span data-ttu-id="54f6e-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="54f6e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="54f6e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54f6e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="54f6e-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="54f6e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="54f6e-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="54f6e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="54f6e-110">Du kan förhindra ytterligare spridning av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="54f6e-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="54f6e-111">Om du vet en potentiellt skadlig körbar fil (PE) kan du blockera den.</span><span class="sxs-lookup"><span data-stu-id="54f6e-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="54f6e-112">Den här åtgärden förhindrar att den läses, skrivs eller körs på datorer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="54f6e-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="54f6e-113">Du kan skapa indikatorer för filer på två sätt:</span><span class="sxs-lookup"><span data-stu-id="54f6e-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="54f6e-114">Genom att skapa en indikator via inställningssidan</span><span class="sxs-lookup"><span data-stu-id="54f6e-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="54f6e-115">Genom att skapa en sammanhangsberoende indikator med knappen lägg till indikator från filinformationssidan</span><span class="sxs-lookup"><span data-stu-id="54f6e-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="54f6e-116">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="54f6e-116">Before you begin</span></span>
<span data-ttu-id="54f6e-117">Det är viktigt att förstå följande förutsättningar innan du skapar indikatorer för filer:</span><span class="sxs-lookup"><span data-stu-id="54f6e-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="54f6e-118">Den här funktionen är tillgänglig om din organisation använder Windows Defender Antivirus och Molnbaserat skydd är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="54f6e-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="54f6e-119">Mer information finns i [Använda nästa generations teknik i Microsoft Defender Antivirus via moln levererat skydd.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="54f6e-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="54f6e-120">Klientversionen av Antimalware måste vara 4.18.1901.x eller senare.</span><span class="sxs-lookup"><span data-stu-id="54f6e-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="54f6e-121">Stöds på datorer med Windows 10, version 1703 eller senare, Windows Server 2016 och 2019.</span><span class="sxs-lookup"><span data-stu-id="54f6e-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="54f6e-122">För att börja blockera filer måste du först [aktivera funktionen Spärra eller **tillåt**](advanced-features.md) i Inställningar.</span><span class="sxs-lookup"><span data-stu-id="54f6e-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="54f6e-123">Den här funktionen är utformad för att förhindra att misstänkt skadlig programvara (eller potentiellt skadliga filer) laddas ned från webben.</span><span class="sxs-lookup"><span data-stu-id="54f6e-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="54f6e-124">Den har för närvarande stöd för bärbara körbara (PE) filer, inklusive _.exe-_ _och .dll-filer._</span><span class="sxs-lookup"><span data-stu-id="54f6e-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="54f6e-125">Täckningen utökas med tiden.</span><span class="sxs-lookup"><span data-stu-id="54f6e-125">The coverage will be extended over time.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="54f6e-126">Funktionen tillåt eller blockera kan inte utföras för filer om filens klassificering finns på enhetens cache innan åtgärden för att tillåta eller blockera</span><span class="sxs-lookup"><span data-stu-id="54f6e-126">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
>- <span data-ttu-id="54f6e-127">Betrodda signerade filer behandlas annorlunda.</span><span class="sxs-lookup"><span data-stu-id="54f6e-127">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="54f6e-128">Defender för Endpoint är optimerad för att hantera skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="54f6e-128">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="54f6e-129">Att försöka blockera betrodda signerade filer kan i vissa fall ha prestandakonsekvenser.</span><span class="sxs-lookup"><span data-stu-id="54f6e-129">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>

 
>[!NOTE]
><span data-ttu-id="54f6e-130">Vanligtvis används filblock inom några minuter, men det kan ta upp till 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="54f6e-130">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="54f6e-131">Skapa en indikator för filer från inställningssidan</span><span class="sxs-lookup"><span data-stu-id="54f6e-131">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="54f6e-132">Välj Inställningar Indikatorer i  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="54f6e-132">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="54f6e-133">Välj fliken **Filhash.**</span><span class="sxs-lookup"><span data-stu-id="54f6e-133">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="54f6e-134">Välj **Lägg till indikator**.</span><span class="sxs-lookup"><span data-stu-id="54f6e-134">Select **Add indicator**.</span></span>

4. <span data-ttu-id="54f6e-135">Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="54f6e-135">Specify the following details:</span></span>
   - <span data-ttu-id="54f6e-136">Indikator – Ange entitetsinformation och definiera indikatorns förfallotid.</span><span class="sxs-lookup"><span data-stu-id="54f6e-136">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="54f6e-137">Åtgärd – Ange vilken åtgärd som ska vidtas och ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="54f6e-137">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="54f6e-138">Omfattning – Definiera datorgruppens omfattning.</span><span class="sxs-lookup"><span data-stu-id="54f6e-138">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="54f6e-139">Granska informationen på fliken Sammanfattning och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="54f6e-139">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="54f6e-140">Skapa en sammanhangsberoende indikator från filinformationssidan</span><span class="sxs-lookup"><span data-stu-id="54f6e-140">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="54f6e-141">Ett av alternativen när du vidtar [svarsåtgärder för en fil är](respond-file-alerts.md) att lägga till en indikator för filen.</span><span class="sxs-lookup"><span data-stu-id="54f6e-141">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="54f6e-142">När du lägger till en indikatorhash för en fil kan du välja att avisering ska visas och blockera filen när en dator i organisationen försöker köra den.</span><span class="sxs-lookup"><span data-stu-id="54f6e-142">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="54f6e-143">Filer som blockeras automatiskt av en indikator visas inte i filens Åtgärdscenter, men aviseringarna visas fortfarande i kön Aviseringar.</span><span class="sxs-lookup"><span data-stu-id="54f6e-143">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="54f6e-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="54f6e-144">Related topics</span></span>
- [<span data-ttu-id="54f6e-145">Skapa indikatorer</span><span class="sxs-lookup"><span data-stu-id="54f6e-145">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="54f6e-146">Skapa indikatorer för IP-adresser och URL:er/domäner</span><span class="sxs-lookup"><span data-stu-id="54f6e-146">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="54f6e-147">Skapa indikatorer baserade på certifikat</span><span class="sxs-lookup"><span data-stu-id="54f6e-147">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="54f6e-148">Hantera indikatorer</span><span class="sxs-lookup"><span data-stu-id="54f6e-148">Manage indicators</span></span>](indicator-manage.md)
