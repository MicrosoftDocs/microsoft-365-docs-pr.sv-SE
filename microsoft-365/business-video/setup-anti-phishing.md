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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig konfigurera skydd mot nätfiske.
ms.openlocfilehash: bcb6b8bac316b4b74c505656cb9a93e7a87e0830
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927880"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="ef58b-103">Konfigurera skydd mot nätfiske och ATP-principer för skydd mot nätfiske</span><span class="sxs-lookup"><span data-stu-id="ef58b-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="ef58b-104">Nätfiske är en skadlig attack där ett e-postmeddelande ser ut som det skickats från en välbekant källa, men som försöker samla in din personliga information.</span><span class="sxs-lookup"><span data-stu-id="ef58b-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="ef58b-105">Som standard innehåller Microsoft 365 ett visst skydd mot nätfiske, men du kan öka skyddet genom att förfina inställningarna.</span><span class="sxs-lookup"><span data-stu-id="ef58b-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="ef58b-106">Vi tar en titt.</span><span class="sxs-lookup"><span data-stu-id="ef58b-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="ef58b-107">Prova!</span><span class="sxs-lookup"><span data-stu-id="ef58b-107">Try it!</span></span>

1. <span data-ttu-id="ef58b-108">I administrationscentret väljer du [https://admin.microsoft.com](https://admin.microsoft.com) Säkerhet, **Hothantering,**  **Policy** och sedan **ATP – skydd mot nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="ef58b-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="ef58b-109">Välj **Standardprincip för** att förfina den.</span><span class="sxs-lookup"><span data-stu-id="ef58b-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="ef58b-110">Välj Redigera i avsnittet **Personifiering.** </span><span class="sxs-lookup"><span data-stu-id="ef58b-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="ef58b-111">Gå till **Lägg till domäner för att** skydda och välj växlingsknappen för att automatiskt inkludera de domäner du äger.</span><span class="sxs-lookup"><span data-stu-id="ef58b-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="ef58b-112">Gå till **Åtgärder,** öppna listrutan Om e-post skickas av **en imiterad** användare och välj den åtgärd du vill använda.</span><span class="sxs-lookup"><span data-stu-id="ef58b-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="ef58b-113">Öppna listrutan Om **e-post skickas med en imiterad domän** och välj den åtgärd du vill använda.</span><span class="sxs-lookup"><span data-stu-id="ef58b-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="ef58b-114">Välj **Aktivera säkerhetstips för personifiering.**</span><span class="sxs-lookup"><span data-stu-id="ef58b-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="ef58b-115">Välj om tips ska ges till användare när systemet identifierar imiterade användare, domäner eller ovanliga tecken.</span><span class="sxs-lookup"><span data-stu-id="ef58b-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="ef58b-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-116">Select **Save**.</span></span>
1. <span data-ttu-id="ef58b-117">Välj **Inkorgsinformation** och kontrollera att den är påslagen.</span><span class="sxs-lookup"><span data-stu-id="ef58b-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="ef58b-118">Det gör att din e-post kan bli effektivare genom inlärning av användningsmönster.</span><span class="sxs-lookup"><span data-stu-id="ef58b-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="ef58b-119">Välj **Lägg till betrodda avsändare och domäner.**</span><span class="sxs-lookup"><span data-stu-id="ef58b-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="ef58b-120">Här kan du lägga till e-postadresser eller domäner som inte ska klassificeras som en personifiering.</span><span class="sxs-lookup"><span data-stu-id="ef58b-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="ef58b-121">Välj **Granska dina inställningar,** kontrollera att allt är korrekt, **välj Spara** och **sedan Stäng.**</span><span class="sxs-lookup"><span data-stu-id="ef58b-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="ef58b-122">Din organisation har nu bättre skydd mot nätfiskehot.</span><span class="sxs-lookup"><span data-stu-id="ef58b-122">Your organization now has better protection from phishing threats.</span></span>