---
title: Anslut din domän till Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du ansluter din domän till Microsoft 365.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794708"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="a7d66-103">Ansluta din domän till Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="a7d66-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="a7d66-104">När du har konfigurerat Microsoft 365 och flyttat dina e-postdata från Google Workspace kan du ansluta domänen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7d66-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="a7d66-105">Först måste du ta bort befintliga DNS-poster från Google och sedan kan vi lägga till nya DNS-poster från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7d66-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="a7d66-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="a7d66-106">Try it!</span></span>

1. <span data-ttu-id="a7d66-107">Logga in på din Google Workspace-administratörskonsolen på [admin.Google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="a7d66-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="a7d66-108">Välj **domäner**, **hantera domäner**, **Visa information**, **Hantera domän** och sedan **DNS** i det vänstra navigerings fältet.</span><span class="sxs-lookup"><span data-stu-id="a7d66-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="a7d66-109">Bläddra ned till **syntetiska poster**, öppna **Google Workspace**, Välj **ta bort** och sedan **ta bort** igen.</span><span class="sxs-lookup"><span data-stu-id="a7d66-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="a7d66-110">Bläddra ned till **anpassade resurs poster** och ta bort alla befintliga DNS-poster som visas, inklusive de som du tidigare har skapat för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7d66-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="a7d66-111">Gå till [administrations centret för Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a7d66-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="a7d66-112">I det vänstra navigerings fältet väljer du, **Visa alla**, **Inställningar**, **domäner**.</span><span class="sxs-lookup"><span data-stu-id="a7d66-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="a7d66-113">Välj sedan standard domänen.</span><span class="sxs-lookup"><span data-stu-id="a7d66-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="a7d66-114">Välj **Fortsätt installationen** och välj sedan  **Fortsätt** för att ansluta domänen.</span><span class="sxs-lookup"><span data-stu-id="a7d66-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="a7d66-115">Bläddra nedåt för att visa de DNS-poster som måste kopieras till Google.</span><span class="sxs-lookup"><span data-stu-id="a7d66-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="a7d66-116">Öppna **MX-poster** och kopiera posten under **pekar på adress eller värde**.</span><span class="sxs-lookup"><span data-stu-id="a7d66-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="a7d66-117">Gå tillbaka till Google och öppna avsnittet **anpassade resurs poster** och välj **MX**.</span><span class="sxs-lookup"><span data-stu-id="a7d66-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="a7d66-118">Klistra in den post du kopierade i fältet **data** .</span><span class="sxs-lookup"><span data-stu-id="a7d66-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="a7d66-119">Välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="a7d66-119">Then select **Add**.</span></span>
1. <span data-ttu-id="a7d66-120">Upprepa processen för CNAME-och TXT-poster och Lägg till värdena på sidan Google DNS Management.</span><span class="sxs-lookup"><span data-stu-id="a7d66-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="a7d66-121">Gå tillbaka till administrations centret för Microsoft 365 och välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="a7d66-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="a7d66-122">Domän konfigurationen är klar.</span><span class="sxs-lookup"><span data-stu-id="a7d66-122">Your domain setup is complete.</span></span>