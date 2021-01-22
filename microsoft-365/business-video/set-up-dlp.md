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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du hanterar konfigurera principer för skydd mot dataförlust.
ms.openlocfilehash: e963cf85fee887b6e91c6e54b00aaa9e5174e3b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927964"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="fcbd0-103">Förhindra dataförlust med DLP</span><span class="sxs-lookup"><span data-stu-id="fcbd0-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="fcbd0-104">Principer för dataförlustskydd hjälper till att identifiera och skydda känslig information inom företaget, t.ex. personnummer eller journaler.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="fcbd0-105">Prova!</span><span class="sxs-lookup"><span data-stu-id="fcbd0-105">Try it!</span></span>

1. <span data-ttu-id="fcbd0-106">Kom igång genom att gå till [administrationscentret](https://admin.microsoft.com)och välja **Installation.**</span><span class="sxs-lookup"><span data-stu-id="fcbd0-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="fcbd0-107">Rulla ned till **Konfigurera skydd mot dataförlust** och välj sedan **Visa** och sedan **Hantera.**</span><span class="sxs-lookup"><span data-stu-id="fcbd0-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="fcbd0-108">Om du vill redigera en princip markerar du den, **väljer Redigera princip** och sedan vad du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="fcbd0-109">Välj till exempel Platser **om du vill** ändra det som genomsöks.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="fcbd0-110">Om du vill aktivera genomsökning av innehåll i Microsoft Teams ändrar du växlingsknappen till **läget** På och väljer sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="fcbd0-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="fcbd0-111">Om du vill redigera principinställningarna väljer du **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="fcbd0-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="fcbd0-112">Du måste ange separata regler som gäller för små och stora mängder känsligt innehåll som upptäckts.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="fcbd0-113">Utöka regeln för låg volym.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-113">Expand your low volume rule.</span></span> <span data-ttu-id="fcbd0-114">Välj **Redigera regel.**</span><span class="sxs-lookup"><span data-stu-id="fcbd0-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="fcbd0-115">Granska inställningarna och justera dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="fcbd0-116">Du kan till exempel välja att anpassa **texten i e-postmeddelandet** **och anpassa texten i principtipset.**</span><span class="sxs-lookup"><span data-stu-id="fcbd0-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="fcbd0-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-117">Select **Save**.</span></span>
1. <span data-ttu-id="fcbd0-118">Upprepa för regeln med hög volym.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="fcbd0-119">Välj **Spara** och sedan **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="fcbd0-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="fcbd0-120">Om du vill skapa en ny princip väljer **du Skapa en princip.**</span><span class="sxs-lookup"><span data-stu-id="fcbd0-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="fcbd0-121">Du kan skapa en anpassad princip eller utgå från en mall.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="fcbd0-122">Om du till exempel vill skapa en  HIPAA-policy väljer du mallen Medicinskt och hälsa och sedan **U.S. Health Insurance Act (HIPAA).**</span><span class="sxs-lookup"><span data-stu-id="fcbd0-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="fcbd0-123">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-123">Select **Next**.</span></span>
1. <span data-ttu-id="fcbd0-124">Ange ett namn och en beskrivning för principen.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="fcbd0-125">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-125">Select **Next**.</span></span>
1. <span data-ttu-id="fcbd0-126">Välj platser att söka igenom.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-126">Choose the locations to scan.</span></span> <span data-ttu-id="fcbd0-127">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-127">Select **Next**.</span></span>
1. <span data-ttu-id="fcbd0-128">Välj den typ av innehåll som du vill skydda.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="fcbd0-129">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-129">Select **Next**.</span></span>
1. <span data-ttu-id="fcbd0-130">Välj vad du vill ska hända om känslig information identifieras.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="fcbd0-131">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-131">Select **Next**.</span></span>
1. <span data-ttu-id="fcbd0-132">Anpassa åtkomst och åsidosätta behörigheter.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-132">Customize your access and override permissions.</span></span> <span data-ttu-id="fcbd0-133">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-133">Select **Next**.</span></span>
1. <span data-ttu-id="fcbd0-134">Välj när principen ska gälla.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="fcbd0-135">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-135">Select **Next**.</span></span>
1. <span data-ttu-id="fcbd0-136">Granska inställningarna och välj **Skapa.**</span><span class="sxs-lookup"><span data-stu-id="fcbd0-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="fcbd0-137">När principen börjar gälla blockeras e-postmeddelanden som innehåller den beskrivande känsliga informationen och avsändaren som försökte skicka informationen visas ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="fcbd0-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>