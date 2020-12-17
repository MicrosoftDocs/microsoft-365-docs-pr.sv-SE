---
title: Förhindra dataförlust
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
description: Lär dig hur du hanterar inställningar för att förhindra data förlust.
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702908"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="19626-103">Förhindra data förlust med DLP</span><span class="sxs-lookup"><span data-stu-id="19626-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="19626-104">Principer för skydd mot data förlust hjälper dig att identifiera och skydda företagets känslig information, till exempel sociala säkerhets nummer eller medicinska uppgifter.</span><span class="sxs-lookup"><span data-stu-id="19626-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="19626-105">Prova!</span><span class="sxs-lookup"><span data-stu-id="19626-105">Try it!</span></span>

1. <span data-ttu-id="19626-106">För att komma igång går du till [administrations centret](https://admin.microsoft.com)och väljer **Installera**.</span><span class="sxs-lookup"><span data-stu-id="19626-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="19626-107">Rulla ned för att **Konfigurera data förlust skydd** och välj sedan **Visa** och sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="19626-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="19626-108">Om du vill redigera en princip markerar du den, väljer **Redigera princip** och väljer sedan vad du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="19626-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="19626-109">Välj till exempel **platser** för att ändra vad som ska skannas.</span><span class="sxs-lookup"><span data-stu-id="19626-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="19626-110">Om du vill aktivera genomsökning av innehåll i Microsoft Teams aktiverar du växlings knappen **till position och** väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="19626-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="19626-111">Om du vill redigera princip inställningar väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="19626-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="19626-112">Du måste ange separata regler som gäller för små och stora mängder av känsligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="19626-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="19626-113">Utöka din regel för dålig volym.</span><span class="sxs-lookup"><span data-stu-id="19626-113">Expand your low volume rule.</span></span> <span data-ttu-id="19626-114">Välj **Edit Rule**.</span><span class="sxs-lookup"><span data-stu-id="19626-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="19626-115">Granska inställningarna och justera dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="19626-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="19626-116">Du kan till exempel välja att **Anpassa e-** postmeddelandet och **Anpassa princip Tips texten**.</span><span class="sxs-lookup"><span data-stu-id="19626-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="19626-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="19626-117">Select **Save**.</span></span>
1. <span data-ttu-id="19626-118">Upprepa för den högsta volym regeln.</span><span class="sxs-lookup"><span data-stu-id="19626-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="19626-119">Välj **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="19626-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="19626-120">Om du vill skapa en ny princip väljer du **skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="19626-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="19626-121">Du kan skapa en anpassad princip eller börja med en mall.</span><span class="sxs-lookup"><span data-stu-id="19626-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="19626-122">Om du till exempel vill skapa en HIPAA policy väljer du hälso mal len **medicin och hälsa** och väljer sedan **amerikansk sjukförsäkring Act (HIPAA)**.</span><span class="sxs-lookup"><span data-stu-id="19626-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="19626-123">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="19626-123">Select **Next**.</span></span>
1. <span data-ttu-id="19626-124">Ange ett namn och en beskrivning för policyn.</span><span class="sxs-lookup"><span data-stu-id="19626-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="19626-125">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="19626-125">Select **Next**.</span></span>
1. <span data-ttu-id="19626-126">Välj var du vill skanna.</span><span class="sxs-lookup"><span data-stu-id="19626-126">Choose the locations to scan.</span></span> <span data-ttu-id="19626-127">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="19626-127">Select **Next**.</span></span>
1. <span data-ttu-id="19626-128">Välj den typ av innehåll som du vill skydda.</span><span class="sxs-lookup"><span data-stu-id="19626-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="19626-129">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="19626-129">Select **Next**.</span></span>
1. <span data-ttu-id="19626-130">Välj vad du vill ska hända om känslig information upptäcks.</span><span class="sxs-lookup"><span data-stu-id="19626-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="19626-131">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="19626-131">Select **Next**.</span></span>
1. <span data-ttu-id="19626-132">Anpassa dina åtkomst-och behörighets behörigheter.</span><span class="sxs-lookup"><span data-stu-id="19626-132">Customize your access and override permissions.</span></span> <span data-ttu-id="19626-133">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="19626-133">Select **Next**.</span></span>
1. <span data-ttu-id="19626-134">Välj när du vill att principen ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="19626-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="19626-135">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="19626-135">Select **Next**.</span></span>
1. <span data-ttu-id="19626-136">Granska inställningarna och välj **skapa**.</span><span class="sxs-lookup"><span data-stu-id="19626-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="19626-137">När din policy har verkställts blockeras e-post som innehåller den beskrivna känslig informationen och avsändaren som försökte skicka den informationen får ett varnings meddelande.</span><span class="sxs-lookup"><span data-stu-id="19626-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>