---
title: Skapa indikatorer baserade på certifikat
ms.reviewer: ''
description: Skapa indikatorer baserade på certifikat som definierar identifiering, skydd och undantag för enheter.
keywords: ioc, certificate, certificates, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164687"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="15423-104">Skapa indikatorer baserade på certifikat</span><span class="sxs-lookup"><span data-stu-id="15423-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="15423-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="15423-105">**Applies to:**</span></span>
- [<span data-ttu-id="15423-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="15423-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="15423-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15423-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="15423-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="15423-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="15423-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="15423-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="15423-110">Du kan skapa indikatorer för certifikat.</span><span class="sxs-lookup"><span data-stu-id="15423-110">You can create indicators for certificates.</span></span> <span data-ttu-id="15423-111">Några vanliga användningsfall är:</span><span class="sxs-lookup"><span data-stu-id="15423-111">Some common use cases include:</span></span>

- <span data-ttu-id="15423-112">Scenarier när du behöver distribuera blockeringstekniker, till [](controlled-folders.md) exempel minskningsregler för [attackytan](attack-surface-reduction.md) och kontrollerad mappåtkomst, men behöver tillåta beteenden från signerade program genom att lägga till certifikatet i listan över tillåtna mappar.</span><span class="sxs-lookup"><span data-stu-id="15423-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="15423-113">Blockera användningen av ett visst signerat program i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="15423-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="15423-114">Genom att skapa en indikator för att blockera certifikatet för programmet förhindrar Windows Defender AV filkörningar (blockering och åtgärd) och automatisk undersökning och åtgärd fungerar på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="15423-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="15423-115">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="15423-115">Before you begin</span></span>

<span data-ttu-id="15423-116">Det är viktigt att förstå följande krav innan du skapar indikatorer för certifikat:</span><span class="sxs-lookup"><span data-stu-id="15423-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="15423-117">Den här funktionen är tillgänglig om din organisation använder Windows Defender Antivirus och Molnbaserat skydd är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="15423-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="15423-118">Mer information finns i [Hantera molnbaserat skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="15423-118">For more information, see [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="15423-119">Klientversionen av Antimalware måste vara 4.18.1901.x eller senare.</span><span class="sxs-lookup"><span data-stu-id="15423-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="15423-120">Stöds på datorer med Windows 10, version 1703 eller senare, Windows Server 2016 och 2019.</span><span class="sxs-lookup"><span data-stu-id="15423-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="15423-121">Definitionerna för skydd mot virus och hot måste vara uppdaterade.</span><span class="sxs-lookup"><span data-stu-id="15423-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="15423-122">Den här funktionen har för närvarande stöd för att ange . CER eller . PEM-filnamnstillägg.</span><span class="sxs-lookup"><span data-stu-id="15423-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="15423-123">Ett giltigt certifikat för blad är ett signeringscertifikat som har en giltig certifieringssökväg och måste länkas till den rotcertifikatutfärdare (CA) som Microsoft litar på.</span><span class="sxs-lookup"><span data-stu-id="15423-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="15423-124">Alternativt kan ett anpassat (själv signerat) certifikat användas så länge det är betrott av klienten (Root CA-certifikat har installerats under den lokala datorns betrodda rotcertifikatutfärdare).</span><span class="sxs-lookup"><span data-stu-id="15423-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="15423-125">Underordnade eller överordnade till IOC-certifikaten (tillåt/blockera) ingår inte i IoC-funktionen tillåt/blockera, endast certifikat för löv stöds.</span><span class="sxs-lookup"><span data-stu-id="15423-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="15423-126">Microsoft-signerade certifikat kan inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="15423-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="15423-127">Skapa en indikator för certifikat från inställningssidan:</span><span class="sxs-lookup"><span data-stu-id="15423-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="15423-128">Det kan ta upp till 3 timmar att skapa och ta bort ett certifikat-IoC.</span><span class="sxs-lookup"><span data-stu-id="15423-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="15423-129">Välj Inställningar Indikatorer i  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="15423-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="15423-130">Välj **fliken** Certifikat.</span><span class="sxs-lookup"><span data-stu-id="15423-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="15423-131">Välj **Lägg till indikator**.</span><span class="sxs-lookup"><span data-stu-id="15423-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="15423-132">Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="15423-132">Specify the following details:</span></span>
   - <span data-ttu-id="15423-133">Indikator – Ange entitetsinformation och definiera indikatorns förfallotid.</span><span class="sxs-lookup"><span data-stu-id="15423-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="15423-134">Åtgärd – Ange vilken åtgärd som ska vidtas och ange en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="15423-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="15423-135">Omfattning – Definiera datorgruppens omfattning.</span><span class="sxs-lookup"><span data-stu-id="15423-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="15423-136">Granska informationen på fliken Sammanfattning och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="15423-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="15423-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="15423-137">Related topics</span></span>
- [<span data-ttu-id="15423-138">Skapa indikatorer</span><span class="sxs-lookup"><span data-stu-id="15423-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="15423-139">Skapa indikatorer för filer</span><span class="sxs-lookup"><span data-stu-id="15423-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="15423-140">Skapa indikatorer för IP-adresser och URL:er/domäner</span><span class="sxs-lookup"><span data-stu-id="15423-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="15423-141">Hantera indikatorer</span><span class="sxs-lookup"><span data-stu-id="15423-141">Manage indicators</span></span>](indicator-manage.md)