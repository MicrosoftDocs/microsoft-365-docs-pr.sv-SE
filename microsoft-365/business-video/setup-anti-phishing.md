---
title: Konfigurera skydd mot nätfiske
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Lär dig hur du konfigurerar skydd mot nätfiske.
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702893"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="7bb39-103">Konfigurera anti-nätfiske</span><span class="sxs-lookup"><span data-stu-id="7bb39-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="7bb39-104">Nätfiske är en skadlig attack där en e-postadress ser ut som om den skickades från en bekant källa, men försöker samla in personlig information.</span><span class="sxs-lookup"><span data-stu-id="7bb39-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="7bb39-105">Som standard inkluderar Microsoft 365 ett visst skydd mot nätfiske, men du kan öka detta skydd genom att förfina inställningarna.</span><span class="sxs-lookup"><span data-stu-id="7bb39-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="7bb39-106">Låt oss ta en titt.</span><span class="sxs-lookup"><span data-stu-id="7bb39-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="7bb39-107">Prova!</span><span class="sxs-lookup"><span data-stu-id="7bb39-107">Try it!</span></span>

1. <span data-ttu-id="7bb39-108">I Admin Center på [https://admin.microsoft.com](https://admin.microsoft.com) väljer du **säkerhet**, **Threat Management**, **policy** och sedan **ATP-nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="7bb39-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="7bb39-109">Välj **standard princip** för att förfina den.</span><span class="sxs-lookup"><span data-stu-id="7bb39-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="7bb39-110">I avsnittet **personifiering** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="7bb39-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="7bb39-111">Gå till **Lägg till domäner för att skydda** och välj växlings knappen för att automatiskt inkludera de domäner du äger.</span><span class="sxs-lookup"><span data-stu-id="7bb39-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="7bb39-112">Gå till **åtgärder**, öppna List rutan **om e-post skickas av en personifierad användare** och välj den åtgärd du vill använda.</span><span class="sxs-lookup"><span data-stu-id="7bb39-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="7bb39-113">Öppna List rutan **om e-post skickas av en domänkontrollant** och välj den åtgärd du vill använda.</span><span class="sxs-lookup"><span data-stu-id="7bb39-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="7bb39-114">Välj **Aktivera säkerhets tips**.</span><span class="sxs-lookup"><span data-stu-id="7bb39-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="7bb39-115">Välj om du vill få tips för användarna när systemet identifierar personifierade användare, domäner eller ovanliga tecken.</span><span class="sxs-lookup"><span data-stu-id="7bb39-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="7bb39-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bb39-116">Select **Save**.</span></span>
1. <span data-ttu-id="7bb39-117">Välj **post lådans intelligens** och kontrol lera att den är aktive rad.</span><span class="sxs-lookup"><span data-stu-id="7bb39-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="7bb39-118">Detta gör att din e-post blir mer effektiv genom användnings mönster.</span><span class="sxs-lookup"><span data-stu-id="7bb39-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="7bb39-119">Välj **Lägg till betrodda avsändare och domäner**.</span><span class="sxs-lookup"><span data-stu-id="7bb39-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="7bb39-120">Här kan du lägga till e-postadresser eller domäner som inte ska klassificeras som en personifiering.</span><span class="sxs-lookup"><span data-stu-id="7bb39-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="7bb39-121">Välj **Granska dina inställningar**, kontrol lera att alla stämmer, Välj **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7bb39-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="7bb39-122">Nu har din organisation bättre skydd mot nätfiske-hot.</span><span class="sxs-lookup"><span data-stu-id="7bb39-122">Your organization now has better protection from phishing threats.</span></span>