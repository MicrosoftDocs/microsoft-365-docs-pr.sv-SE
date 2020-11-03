---
title: Inbyggt virus skydd i SharePoint Online, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Lär dig mer om hur SharePoint Online identifierar virus i filer som användare laddar upp och förhindrar att användare laddar ned och synkroniserar filerna.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f774c9afd0988c504d6207b0e71ee9561312e6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844242"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="e0733-103">Inbyggt virus skydd i SharePoint Online, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0733-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e0733-104">I Microsoft 365 används en vanlig antivirus motor för genomsökning av filer som användare laddar upp till SharePoint Online, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0733-104">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="e0733-105">Detta skydd ingår i alla abonnemang som innehåller SharePoint Online, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0733-105">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0733-106">De inbyggda Antivirus funktionerna är ett sätt att hjälpa dig att skapa virus.</span><span class="sxs-lookup"><span data-stu-id="e0733-106">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="e0733-107">De är inte avsedda som en enda försvars punkt mot skadlig program vara för din miljö.</span><span class="sxs-lookup"><span data-stu-id="e0733-107">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="e0733-108">Vi uppmuntrar alla kunder att undersöka och implementera skydd mot skadlig program vara på olika lager och tillämpa metod tips för att skydda sin företags infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="e0733-108">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="e0733-109">Mer information om strategier och metod tips finns i [säkerhets översikt](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="e0733-109">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="e0733-110">Vad händer när en angripen fil laddas upp till SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="e0733-110">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="e0733-111">Microsoft 365-Antivirus motorn körs asynkront i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e0733-111">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="e0733-112">**Alla filer skannas inte automatiskt vid uppladdning**.</span><span class="sxs-lookup"><span data-stu-id="e0733-112">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="e0733-113">Heuristiken bestämmer vilka filer som ska genomsökas.</span><span class="sxs-lookup"><span data-stu-id="e0733-113">Heuristics determine the files to scan.</span></span> <span data-ttu-id="e0733-114">När en fil hittas som innehåller ett virus flaggas filen så att den inte kan hämtas igen.</span><span class="sxs-lookup"><span data-stu-id="e0733-114">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="e0733-115">I april 2018 tog vi bort 25 MB-gränsen för inlästa filer.</span><span class="sxs-lookup"><span data-stu-id="e0733-115">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="e0733-116">Så här gör du:</span><span class="sxs-lookup"><span data-stu-id="e0733-116">Here's what happens:</span></span>

1. <span data-ttu-id="e0733-117">En användare laddar upp en fil till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e0733-117">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="e0733-118">SharePoint Online bestämmer om filen uppfyller villkoren för en sökning.</span><span class="sxs-lookup"><span data-stu-id="e0733-118">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="e0733-119">Antivirus verktyget söker igenom filen.</span><span class="sxs-lookup"><span data-stu-id="e0733-119">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="e0733-120">Om ett virus hittas anger Antivirus motorn en egenskap för filen som anger att den är smittad.</span><span class="sxs-lookup"><span data-stu-id="e0733-120">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="e0733-121">Vad händer när en användare försöker ladda ned en infekterad fil med webbläsaren?</span><span class="sxs-lookup"><span data-stu-id="e0733-121">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="e0733-122">Om en fil är infekterad kan användare inte ladda ned filen från SharePoint Online med hjälp av en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="e0733-122">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="e0733-123">Så här gör du:</span><span class="sxs-lookup"><span data-stu-id="e0733-123">Here's what happens:</span></span>

1. <span data-ttu-id="e0733-124">En användare öppnar en webbläsare och försöker ladda ned en angripen fil från SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e0733-124">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="e0733-125">Användaren får ett varnings meddelande om att ett virus har hittats.</span><span class="sxs-lookup"><span data-stu-id="e0733-125">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="e0733-126">Som standard ges användaren möjlighet att ladda ner filen och försöka rensa den med antivirus programmet på egen hand.</span><span class="sxs-lookup"><span data-stu-id="e0733-126">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="e0733-127">Administratörer kan använda parametern *DisallowInfectedFileDownload* i cmdleten [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) i SharePoint Online PowerShell för att förhindra att användare laddar ner infekterade filer även i varnings fönstret mot virus.</span><span class="sxs-lookup"><span data-stu-id="e0733-127">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="e0733-128">Anvisningar finns i [använda SharePoint Online PowerShell för att förhindra att användare laddar ned skadliga filer](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="e0733-128">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="e0733-129">Så fort du aktiverar *DisallowInfectedFileDownload* -parametern blockeras åtkomst till de identifierade/blockerade filerna helt för användare och administratörer.</span><span class="sxs-lookup"><span data-stu-id="e0733-129">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="e0733-130">Vad händer när en OneDrive-synkroniseringsklient försöker synkronisera en infekterad fil?</span><span class="sxs-lookup"><span data-stu-id="e0733-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="e0733-131">För OneDrive-synkroniseringsklienten hämtas inte filer som innehåller virus.</span><span class="sxs-lookup"><span data-stu-id="e0733-131">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="e0733-132">Synkroniseringsklienten visar ett meddelande om att filen inte kan synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="e0733-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="e0733-133">Utökade funktioner i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="e0733-133">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="e0733-134">Microsoft 365-organisationer som har [Microsoft Defender för Office 365](office-365-atp.md) inkluderade i deras abonnemang eller köpt som ett tillägg kan aktivera ATP för SharePoint-, OneDrive-och Microsoft Teams för bättre rapportering och skydd.</span><span class="sxs-lookup"><span data-stu-id="e0733-134">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable ATP for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="e0733-135">Mer information finns i [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e0733-135">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="e0733-136">Mer information</span><span class="sxs-lookup"><span data-stu-id="e0733-136">More information</span></span>

<span data-ttu-id="e0733-137">Mer information om antivirus i SharePoint Online, OneDrive och Microsoft Teams finns i [skydda mot hot](protect-against-threats.md) och [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e0733-137">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
