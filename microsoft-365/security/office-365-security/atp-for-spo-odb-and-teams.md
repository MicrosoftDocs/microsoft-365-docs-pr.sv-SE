---
title: ATP för SharePoint, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Lär dig mer om Microsoft Defender för Office 365 för filer i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.openlocfilehash: 7b007671a7fecb3ae074fd07ce38d17fb025f6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844338"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="f9e8d-103">ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9e8d-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f9e8d-104">ATP för SharePoint-, OneDrive-och Microsoft Teams i [Microsoft Defender för Office 365](office-365-atp.md) ger dig ett ytterligare skydd mot filer som redan har skannats vid uppladdning av den [vanliga antivirus motorn i Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="f9e8d-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="f9e8d-105">ATP för SharePoint, OneDrive och Microsoft Teams hjälper till att upptäcka och blockera befintliga filer som identifieras som skadligt för grupp webbplatser och dokument bibliotek.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-105">ATP for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="f9e8d-106">ATP för SharePoint, OneDrive och Microsoft Teams är inte aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-106">ATP for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="f9e8d-107">Information om hur du aktiverar funktionen finns i [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f9e8d-107">To turn it on, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="f9e8d-108">Så fungerar ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9e8d-108">How ATP for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="f9e8d-109">När ATP för SharePoint, OneDrive och Microsoft Teams är aktiverat och identifierar en fil som skadligt är filen låst med hjälp av direkt integrering med fil arkiven.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-109">When ATP for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="f9e8d-110">Följande bild visar ett exempel på en skadlig fil som identifieras i ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Filer i OneDrive för företag med en identifierad som skadlig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="f9e8d-112">Även om den blockerade filen fortfarande visas i dokument biblioteket och i webb-, mobil-eller Skriv bords program kan de inte öppna, kopiera, flytta eller dela filen.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-112">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="f9e8d-113">Men de kan ta bort den blockerade filen.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-113">But they can delete the blocked file.</span></span>

<span data-ttu-id="f9e8d-114">Här är ett exempel på hur en blockerad fil ser ut på en mobil enhet:</span><span class="sxs-lookup"><span data-stu-id="f9e8d-114">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Ta bort en blockerad fil från OneDrive för företag från OneDrive-mobilappen](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="f9e8d-116">Som standard kan folk Ladda ned en blockerad fil.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-116">By default, people can download a blocked file.</span></span> <span data-ttu-id="f9e8d-117">Så här laddar du ned en blockerad fil på en mobil enhet:</span><span class="sxs-lookup"><span data-stu-id="f9e8d-117">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Ladda ned en blockerad fil i OneDrive för företag](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="f9e8d-119">SharePoint Online-administratörer kan förhindra att personer laddar ned skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-119">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="f9e8d-120">Anvisningar finns i [använda SharePoint Online PowerShell för att förhindra att användare laddar ned skadliga filer](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="f9e8d-120">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="f9e8d-121">Om du vill veta mer om användar upplevelsen när en fil har identifierats som skadlig, se [vad du kan göra när en skadlig fil finns i SharePoint Online, OneDrive eller Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="f9e8d-121">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="f9e8d-122">Visa information om skadliga filer som identifieras av ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9e8d-122">View information about malicious files detected by ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="f9e8d-123">Filer som identifieras som skadliga av Microsoft Defender för Office 365 visas i [rapporter om Microsoft Defender för office 365](view-reports-for-atp.md) och i [Utforskaren (och real tids identifieringar)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="f9e8d-123">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="f9e8d-124">Från och med den 2018 maj kan filen också vara tillgänglig i karantän när en fil identifieras som skadlig för Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-124">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="f9e8d-125">Mer information finns i [använda säkerhets & Compliance Center för att hantera filer i karantän](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="f9e8d-125">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="f9e8d-126">Tänk på följande saker</span><span class="sxs-lookup"><span data-stu-id="f9e8d-126">Keep these points in mind</span></span>

- <span data-ttu-id="f9e8d-127">Defender för Office 365 söker inte igenom alla filer i SharePoint Online, OneDrive för företag eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-127">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="f9e8d-128">Detta är avsiktligt.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-128">This is by design.</span></span> <span data-ttu-id="f9e8d-129">Filer skannas asynkront.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-129">Files are scanned asynchronously.</span></span> <span data-ttu-id="f9e8d-130">Processen använder delnings-och gäst aktiviteter tillsammans med smarta heuristik och hot signaler för att identifiera skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-130">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="f9e8d-131">Kontrol lera att dina SharePoint-webbplatser är konfigurerade för att använda den [moderna upplevelsen](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="f9e8d-131">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="f9e8d-132">Defender för Office 365-skydd gäller om den moderna upplevelsen eller den klassiska vyn används; visuella indikatorer som en fil är blockerade är bara tillgängliga i den moderna upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-132">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="f9e8d-133">ATP för SharePoint, OneDrive och Microsoft Teams är en del av organisationens övergripande hot skydds strategi, som inkluderar skydd mot skräp post och skyddar mot skadlig program vara i Exchange Online Protection (EOP), samt säkra länkar och säkra bifogade filer i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9e8d-133">ATP for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f9e8d-134">Mer information finns i [skydda mot hot i Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="f9e8d-134">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
