---
title: Inbyggt virusskydd i SharePoint Online, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Lär dig mer om hur SharePoint Online identifierar virus i filer som användare laddar upp och hindrar användare från att ladda ned eller synkronisera filerna.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd38b196c106a36fb1a1bfc0a441620b1c5b8ba5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070938"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="13d83-103">Inbyggt virusskydd i SharePoint Online, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13d83-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="13d83-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="13d83-104">**Applies to**</span></span>
- [<span data-ttu-id="13d83-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="13d83-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="13d83-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="13d83-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="13d83-107">Microsoft 365 använder en vanlig motor för virusidentifiering för att söka igenom filer som användarna laddar upp till SharePoint Online, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="13d83-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="13d83-108">Det här skyddet ingår i alla prenumerationer som inkluderar SharePoint Online, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="13d83-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13d83-109">De inbyggda virusfunktionerna är ett sätt att förhindra virus.</span><span class="sxs-lookup"><span data-stu-id="13d83-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="13d83-110">De är inte avsedda som det enda skydd mot skadlig programvara i din miljö.</span><span class="sxs-lookup"><span data-stu-id="13d83-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="13d83-111">Vi rekommenderar alla kunder att undersöka och implementera skydd mot skadlig programvara på olika nivåer och tillämpa de bästa metoderna för att skydda företagsinfrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="13d83-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="13d83-112">Mer information om strategier och metodtips finns i Översikt [över säkerhet.](security-roadmap.md)</span><span class="sxs-lookup"><span data-stu-id="13d83-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="13d83-113">Vad händer om en smittad fil laddas upp till SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="13d83-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="13d83-114">Microsoft 365-motor för virusidentifiering körs asynkront (oberoende av filuppladdningar) i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="13d83-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="13d83-115">**Alla filer genomsöks inte automatiskt.**</span><span class="sxs-lookup"><span data-stu-id="13d83-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="13d83-116">Heuristics bestäm vilka filer som ska skannas.</span><span class="sxs-lookup"><span data-stu-id="13d83-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="13d83-117">När en fil påträffas som innehåller virus flaggas filen.</span><span class="sxs-lookup"><span data-stu-id="13d83-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="13d83-118">I april 2018 tog vi bort gränsen på 25 MB för skannade filer.</span><span class="sxs-lookup"><span data-stu-id="13d83-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="13d83-119">Så här går det till:</span><span class="sxs-lookup"><span data-stu-id="13d83-119">Here's what happens:</span></span>

1. <span data-ttu-id="13d83-120">En användare laddar upp en fil till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="13d83-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="13d83-121">SharePoint Online, som en del av virusskanningsprocesserna, avgör senare om filen uppfyller villkoren för en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="13d83-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="13d83-122">Om filen uppfyller villkoren för en genomsökning söker virusidentifieringsmotorn igenom filen.</span><span class="sxs-lookup"><span data-stu-id="13d83-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="13d83-123">Om ett virus påträffas i den skannade filen anger virusmotorn en egenskap på filen som anger att den är smittad.</span><span class="sxs-lookup"><span data-stu-id="13d83-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="13d83-124">Vad händer när en användare försöker hämta en smittad fil med hjälp av webbläsaren?</span><span class="sxs-lookup"><span data-stu-id="13d83-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="13d83-125">Om en fil är smittad kan användare inte hämta filen från SharePoint Online med hjälp av en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="13d83-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="13d83-126">Så här går det till:</span><span class="sxs-lookup"><span data-stu-id="13d83-126">Here's what happens:</span></span>

1. <span data-ttu-id="13d83-127">En användare öppnar en webbläsare och försöker hämta en smittad fil från SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="13d83-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="13d83-128">Användaren får en varning om att ett virus har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="13d83-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="13d83-129">Som standard får användaren möjlighet att ladda ned filen och försöka rensa den med hjälp av antivirusprogrammet på sin egen enhet.</span><span class="sxs-lookup"><span data-stu-id="13d83-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="13d83-130">Administratörer kan använda parametern *DisallowInfectedFileDownload* i cmdleten [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) i SharePoint Online PowerShell för att hindra användare från att hämta smittade filer, även i varningsfönstret för virus.</span><span class="sxs-lookup"><span data-stu-id="13d83-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="13d83-131">Instruktioner finns i Använda [SharePoint Online PowerShell för att hindra användare från att hämta skadliga filer.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)</span><span class="sxs-lookup"><span data-stu-id="13d83-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="13d83-132">Så snart du aktiverar *parametern DisallowInfectedFileDownload* blockeras åtkomsten till de identifierade/blockerade filerna helt och hållet för användare och administratörer.</span><span class="sxs-lookup"><span data-stu-id="13d83-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="13d83-133">Vad händer när OneDrive-synkroniseringsklienten försöker synkronisera en smittad fil?</span><span class="sxs-lookup"><span data-stu-id="13d83-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="13d83-134">OneDrive-synkroniseringsklienter laddar inte ned filer som innehåller virus.</span><span class="sxs-lookup"><span data-stu-id="13d83-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="13d83-135">Synkroniseringsklienten visar ett meddelande om att filen inte kan synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="13d83-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="13d83-136">Utökade funktioner med Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="13d83-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="13d83-137">Microsoft 365-organisationer som har Microsoft Defender för [Office 365](defender-for-office-365.md) i sin prenumeration eller köpt som ett tillägg kan aktivera Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams för bättre rapportering och skydd.</span><span class="sxs-lookup"><span data-stu-id="13d83-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](defender-for-office-365.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="13d83-138">Mer information finns i [Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="13d83-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="13d83-139">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="13d83-139">Related Articles</span></span>

[<span data-ttu-id="13d83-140">Skydd mot skadlig programvara och utpressningstrojaner i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="13d83-140">Malware and ransomware protection in Microsoft 365</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="13d83-141">Mer information om antivirus i SharePoint Online, OneDrive och [](protect-against-threats.md) Microsoft Teams finns i Skydda mot hot och Aktivera säkra bifogade filer för [SharePoint, OneDrive](turn-on-mdo-for-spo-odb-and-teams.md)och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="13d83-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>
