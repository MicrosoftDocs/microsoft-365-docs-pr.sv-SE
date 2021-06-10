---
title: Förhindra dataförlust
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
description: Lär dig hur du hanterar principer för skydd mot dataförlust.
ms.openlocfilehash: 04dbbcfd39186b8161fb497b72ddb070fbfb7471
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580444"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="d7bec-103">Förhindra dataförlust med DLP</span><span class="sxs-lookup"><span data-stu-id="d7bec-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="d7bec-104">Principer för dataförlustskydd hjälper till att identifiera och skydda känslig information inom företaget, t.ex. personnummer eller journaler.</span><span class="sxs-lookup"><span data-stu-id="d7bec-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="d7bec-105">Prova själv!</span><span class="sxs-lookup"><span data-stu-id="d7bec-105">Try it!</span></span>

1. <span data-ttu-id="d7bec-106">Kom igång genom att gå till [administrationscentret](https://admin.microsoft.com)och välja **Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="d7bec-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="d7bec-107">Rulla ned till **Konfigurera skydd mot dataförlust** och välj sedan **Visa** och **hantera**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="d7bec-108">Om du vill redigera en princip markerar du den, **väljer Redigera princip** och väljer sedan vad du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="d7bec-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="d7bec-109">Välj till exempel **Platser om du vill** ändra vad som genomsöks.</span><span class="sxs-lookup"><span data-stu-id="d7bec-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="d7bec-110">Om du vill aktivera genomsökning av Microsoft Teams för innehållet i Microsoft Teams ändrar du växlingsknappen till **läget** På och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="d7bec-111">Om du vill redigera principinställningarna väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="d7bec-112">Du måste ange separata regler som gäller för små och stora mängder känsligt innehåll som upptäckts.</span><span class="sxs-lookup"><span data-stu-id="d7bec-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="d7bec-113">Utöka regeln för låg volym.</span><span class="sxs-lookup"><span data-stu-id="d7bec-113">Expand your low volume rule.</span></span> <span data-ttu-id="d7bec-114">Välj **Redigera regel.**</span><span class="sxs-lookup"><span data-stu-id="d7bec-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="d7bec-115">Granska inställningarna och justera dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="d7bec-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="d7bec-116">Du kan till exempel välja att Anpassa **e-posttexten** **och Anpassa texten med principtips.**</span><span class="sxs-lookup"><span data-stu-id="d7bec-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="d7bec-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-117">Select **Save**.</span></span>
1. <span data-ttu-id="d7bec-118">Upprepa för regeln om hög volym.</span><span class="sxs-lookup"><span data-stu-id="d7bec-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="d7bec-119">Välj **Spara** och sedan **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="d7bec-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="d7bec-120">Om du vill skapa en ny princip väljer **du Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="d7bec-121">Du kan skapa en anpassad princip eller utgå från en mall.</span><span class="sxs-lookup"><span data-stu-id="d7bec-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="d7bec-122">Om du till exempel vill skapa en HIPAA-policy väljer du mallen Medical **and health** och sedan **U.S. Health Insurance Act (HIPAA).**</span><span class="sxs-lookup"><span data-stu-id="d7bec-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="d7bec-123">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-123">Select **Next**.</span></span>
1. <span data-ttu-id="d7bec-124">Ange ett namn och en beskrivning för principen.</span><span class="sxs-lookup"><span data-stu-id="d7bec-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="d7bec-125">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-125">Select **Next**.</span></span>
1. <span data-ttu-id="d7bec-126">Välj platser att söka igenom.</span><span class="sxs-lookup"><span data-stu-id="d7bec-126">Choose the locations to scan.</span></span> <span data-ttu-id="d7bec-127">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-127">Select **Next**.</span></span>
1. <span data-ttu-id="d7bec-128">Välj den typ av innehåll som du vill skydda.</span><span class="sxs-lookup"><span data-stu-id="d7bec-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="d7bec-129">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-129">Select **Next**.</span></span>
1. <span data-ttu-id="d7bec-130">Välj vad du vill ska hända om känslig information identifieras.</span><span class="sxs-lookup"><span data-stu-id="d7bec-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="d7bec-131">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-131">Select **Next**.</span></span>
1. <span data-ttu-id="d7bec-132">Anpassa åtkomst och åsidosätta behörigheter.</span><span class="sxs-lookup"><span data-stu-id="d7bec-132">Customize your access and override permissions.</span></span> <span data-ttu-id="d7bec-133">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-133">Select **Next**.</span></span>
1. <span data-ttu-id="d7bec-134">Välj när du vill att principen ska gälla.</span><span class="sxs-lookup"><span data-stu-id="d7bec-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="d7bec-135">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-135">Select **Next**.</span></span>
1. <span data-ttu-id="d7bec-136">Granska inställningarna och välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d7bec-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="d7bec-137">När principen börjar gälla kommer e-post som innehåller den beskrivna känsliga informationen att blockeras och avsändaren som försökte skicka informationen ser ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="d7bec-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>