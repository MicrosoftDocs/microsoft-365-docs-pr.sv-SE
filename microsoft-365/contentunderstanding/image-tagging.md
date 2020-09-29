---
title: Bildtaggning i SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Läs mer om bildtaggning i SharePoint Syntex
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296237"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="20262-103">Bildtaggning i SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="20262-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="20262-104">Som standard är grundläggande bildtaggning aktiverat för SharePoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="20262-104">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="20262-105">Bilder som laddas upp till endera platsen skannas automatiskt och lämpliga taggar används, om de är tillgängliga, från en lista på 37 grundläggande taggar.</span><span class="sxs-lookup"><span data-stu-id="20262-105">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="20262-106">Användare kan hitta bilder via sök genom att söka på bildtaggarna.</span><span class="sxs-lookup"><span data-stu-id="20262-106">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="20262-107">När en användare laddar upp en bild körs taggningsprocessen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="20262-107">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="20262-108">Om en bild redigeras körs taggningsprocessen igen för att uppdatera taggarna.</span><span class="sxs-lookup"><span data-stu-id="20262-108">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="20262-109">Användare som har behörigheter till bildfilen kan visa och redigera taggarna i filens informationspanel eller i sidan för sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="20262-109">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="20262-110">När en användare redigerar en bilds taggar kommer systemet inte längre tagga automatiskt på den bilden, även om den har redigerats.</span><span class="sxs-lookup"><span data-stu-id="20262-110">Once a user edits an image's tags, the system no longer performs auto-tagging on that image, even if it is edited.</span></span>

<span data-ttu-id="20262-111">Om du inaktiverar taggningen kommer bilderna inte längre att taggas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="20262-111">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="20262-112">Befintliga taggar tas inte bort.</span><span class="sxs-lookup"><span data-stu-id="20262-112">Existing tags will not be removed.</span></span>

## <a name="configure-image-tagging"></a><span data-ttu-id="20262-113">Konfigurera bildtaggning</span><span class="sxs-lookup"><span data-stu-id="20262-113">Configure image tagging</span></span>

<span data-ttu-id="20262-114">Du kan konfigurera bildtaggning i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20262-114">You can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="20262-115">Aktivera eller inaktivera bildtaggning</span><span class="sxs-lookup"><span data-stu-id="20262-115">To turn image tagging on or off</span></span>

1. <span data-ttu-id="20262-116">I Administrationscenter för Microsoft 365 klicka på **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="20262-116">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="20262-117">Under **Organisationskunskap**klickar du på **Automatisera innehållstolkning**.</span><span class="sxs-lookup"><span data-stu-id="20262-117">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="20262-118">Klicka på **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="20262-118">Click **Manage**.</span></span>

4. <span data-ttu-id="20262-119">Klicka på **Bildtaggningsfliken**, klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="20262-119">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="20262-120">Välj för att tillåta **Grundläggande taggning** eller avaktivera taggningen **Av**.</span><span class="sxs-lookup"><span data-stu-id="20262-120">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="20262-121">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20262-121">Click **Save**.</span></span>

    ![Skärmbild på bildtaggningskontrollen](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a><span data-ttu-id="20262-123">Se även</span><span class="sxs-lookup"><span data-stu-id="20262-123">See also</span></span>

[<span data-ttu-id="20262-124">Ställa in innehållstolkning</span><span class="sxs-lookup"><span data-stu-id="20262-124">Set up content understanding</span></span>](set-up-content-understanding.md)