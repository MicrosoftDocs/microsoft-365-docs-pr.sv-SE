---
title: Bildtaggning i SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Läs mer om bildtaggning i SharePoint Syntex
ms.openlocfilehash: 0fba54db6a16a9a8571c7e1ced61b7620cf5113e
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975871"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="80582-103">Bildtaggning i SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="80582-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="80582-104">(Kommer snart)</span><span class="sxs-lookup"><span data-stu-id="80582-104">(Coming soon)</span></span>

<span data-ttu-id="80582-105">Med bildtaggning i SharePoint Syntex kan användare hitta bilder genom sökning genom att söka på bildtaggar och skapa arbetsflöden baserat på bildtaggar..</span><span class="sxs-lookup"><span data-stu-id="80582-105">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="80582-106">Som standard är grundläggande bildtaggning aktiverat för SharePoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="80582-106">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="80582-107">Bilder som laddas upp till endera platsen skannas automatiskt och lämpliga taggar används, om de är tillgängliga, från en lista på 37 grundläggande taggar.</span><span class="sxs-lookup"><span data-stu-id="80582-107">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="80582-108">Användare kan hitta bilder via sök genom att söka på bildtaggarna.</span><span class="sxs-lookup"><span data-stu-id="80582-108">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="80582-109">När en användare laddar upp en bild körs taggningsprocessen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="80582-109">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="80582-110">Om en bild redigeras körs taggningsprocessen igen för att uppdatera taggarna.</span><span class="sxs-lookup"><span data-stu-id="80582-110">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="80582-111">Användare som har behörigheter till bildfilen kan visa och redigera taggarna i filens informationspanel eller i sidan för sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="80582-111">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="80582-112">När en användare har redigerat en bilds taggar, märker inte systemet automatiskt bilden, även om den redigeras.</span><span class="sxs-lookup"><span data-stu-id="80582-112">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="80582-113">Om du inaktiverar taggningen kommer bilderna inte längre att taggas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="80582-113">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="80582-114">Befintliga taggar tas inte bort.</span><span class="sxs-lookup"><span data-stu-id="80582-114">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="80582-115">Systemgenererade taggar kan ändras med uppdateringar av bilden eller vår tagg-teknik.</span><span class="sxs-lookup"><span data-stu-id="80582-115">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="80582-116">Konfigurera bildtaggning</span><span class="sxs-lookup"><span data-stu-id="80582-116">Configure image tagging</span></span>

<span data-ttu-id="80582-117">När du [konfigurera SharePoint Syntex](set-up-content-understanding.md) kan du konfigurera bildtaggning i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80582-117">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="80582-118">Aktivera eller inaktivera bildtaggning</span><span class="sxs-lookup"><span data-stu-id="80582-118">To turn image tagging on or off</span></span>

1. <span data-ttu-id="80582-119">I Administrationscenter för Microsoft 365 klicka på **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="80582-119">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="80582-120">Under **Organisationskunskap** klickar du på **Automatisera innehållstolkning**.</span><span class="sxs-lookup"><span data-stu-id="80582-120">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="80582-121">Klicka på **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="80582-121">Click **Manage**.</span></span>

4. <span data-ttu-id="80582-122">Klicka på **Bildtaggningsfliken**, klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="80582-122">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="80582-123">Välj för att tillåta **Grundläggande taggning** eller avaktivera taggningen **Av**.</span><span class="sxs-lookup"><span data-stu-id="80582-123">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="80582-124">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="80582-124">Click **Save**.</span></span>

    ![Skärmbild på bildtaggningskontrollen](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
