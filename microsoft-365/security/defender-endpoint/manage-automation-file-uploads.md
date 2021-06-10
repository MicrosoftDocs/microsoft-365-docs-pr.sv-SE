---
title: Hantera uppladdningar av automationsfil
description: Aktivera innehållsanalys och konfigurera filnamnstillägg och e-posttillägg för bifogade filer som ska skickas för analys
keywords: automation, fil, uppladdningar, innehåll, analys, fil, anknytning, e-post, bifogad fil
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
ms.openlocfilehash: c8935368e4439221f2ce21cfa620e540c02165f8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185855"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="02cb3-104">Hantera uppladdningar av automationsfil</span><span class="sxs-lookup"><span data-stu-id="02cb3-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="02cb3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="02cb3-105">**Applies to:**</span></span>
- [<span data-ttu-id="02cb3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="02cb3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="02cb3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02cb3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="02cb3-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="02cb3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="02cb3-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="02cb3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="02cb3-110">Aktivera funktionen för innehållsanalys så att vissa filer och e-postbilagor automatiskt kan laddas upp till molnet för ytterligare kontroll i Automatiserad undersökning.</span><span class="sxs-lookup"><span data-stu-id="02cb3-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="02cb3-111">Identifiera filerna och e-postbilagor genom att ange filnamnstillägget och filnamnstillägget för e-post.</span><span class="sxs-lookup"><span data-stu-id="02cb3-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="02cb3-112">Om du till exempel lägger till *exe* och *bat* som filnamnstillägg för filer eller bifogade filer, skickas alla filer eller bifogade filer med dessa tillägg automatiskt till molnet för ytterligare kontroll under Automatisk undersökning.</span><span class="sxs-lookup"><span data-stu-id="02cb3-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="02cb3-113">Lägg till filnamnstillägg och filnamn för bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02cb3-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="02cb3-114">I navigeringsfönstret väljer du **Inställningar**  >  **automationsfiluppladdningar**.</span><span class="sxs-lookup"><span data-stu-id="02cb3-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="02cb3-115">Ändra inställningen för innehållsanalys mellan **På** och **Av.**</span><span class="sxs-lookup"><span data-stu-id="02cb3-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="02cb3-116">Konfigurera följande tilläggsnamn och separata tilläggsnamn med kommatecken:</span><span class="sxs-lookup"><span data-stu-id="02cb3-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="02cb3-117">**Filnamnstillägg** – Misstänkta filer utom e-postbilagor skickas för ytterligare kontroll</span><span class="sxs-lookup"><span data-stu-id="02cb3-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="02cb3-118">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="02cb3-118">Related topics</span></span>
- [<span data-ttu-id="02cb3-119">Hantera undantag från automationsmappar</span><span class="sxs-lookup"><span data-stu-id="02cb3-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
