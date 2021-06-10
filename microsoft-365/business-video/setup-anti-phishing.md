---
title: Konfigurera skydd mot nätfiske
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Lär dig hur du ställer in skydd mot nätfiske.
ms.openlocfilehash: 32494eda4496d99e5e5f4def213ba7876f6c3183
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580420"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="6a1b2-103">Konfigurera skydd mot nätfiske och ATP-principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="6a1b2-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="6a1b2-104">Nätfiske är en skadlig attack där ett e-postmeddelande ser ut som det skickats från en välbekant källa, men som försöker samla in din personliga information.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="6a1b2-105">Som standard innehåller Microsoft 365 visst skydd mot nätfiske, men du kan öka det skyddet genom att förfina inställningarna.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="6a1b2-106">Vi tar en titt.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="6a1b2-107">Prova själv!</span><span class="sxs-lookup"><span data-stu-id="6a1b2-107">Try it!</span></span>

1. <span data-ttu-id="6a1b2-108">I administrationscentret för [https://admin.microsoft.com](https://admin.microsoft.com) väljer du **Säkerhet**, **Hothantering**, **Policy** och sedan **ATP - nätfiskeskydd.**</span><span class="sxs-lookup"><span data-stu-id="6a1b2-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="6a1b2-109">Välj **Standardprincip för** att förfina den.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="6a1b2-110">Välj **Redigera i avsnittet** **Personifiering.**</span><span class="sxs-lookup"><span data-stu-id="6a1b2-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="6a1b2-111">Gå till **Lägg till domäner att skydda** och välj växlingsknappen för att automatiskt inkludera de domäner du äger.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="6a1b2-112">Gå till **Åtgärder**, öppna listrutan Om e-post **skickas av en imiterad** användare och välj den åtgärd du vill använda.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="6a1b2-113">Öppna listrutan Om **e-post skickas från en imiterad domän och** välj den åtgärd du vill använda.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="6a1b2-114">Välj **Aktivera säkerhetstips för personifiering**.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="6a1b2-115">Välj om tips ska ges till användare när systemet identifierar imiterade användare, domäner eller ovanliga tecken.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="6a1b2-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-116">Select **Save**.</span></span>
1. <span data-ttu-id="6a1b2-117">Välj **Inkorgsinformation** och kontrollera att det är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="6a1b2-118">På så sätt kan din e-post bli effektivare genom inlärning av användningsmönster.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="6a1b2-119">Välj **Lägg till betrodda avsändare och domäner.**</span><span class="sxs-lookup"><span data-stu-id="6a1b2-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="6a1b2-120">Här kan du lägga till e-postadresser eller domäner som inte ska klassificeras som en personifiering.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="6a1b2-121">Välj **Granska dina inställningar**, kontrollera att allt är korrekt, välj **Spara** och sedan **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="6a1b2-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="6a1b2-122">Din organisation har nu bättre skydd mot nätfiskehot.</span><span class="sxs-lookup"><span data-stu-id="6a1b2-122">Your organization now has better protection from phishing threats.</span></span>