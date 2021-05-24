---
title: Konfigurera Microsoft Viva Learning (förhandsversion) i Teams administrationscenter
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/24/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Lär dig hur du konfigurerar Microsoft Viva Learning (förhandsversion) Teams administrationscentret.
ms.openlocfilehash: a96a2f3ecf7d4e1ee0c136ae155868218f08aaf4
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636140"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="becf2-103">Konfigurera Microsoft Viva Learning (förhandsversion) i Teams administrationscenter</span><span class="sxs-lookup"><span data-stu-id="becf2-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="becf2-104">Informationen i den här artikeln gäller en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="becf2-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="becf2-105">Administratören Teams viva Learning (förhandsversion) och tillämpar behörighetsprinciper via Teams administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="becf2-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

1. <span data-ttu-id="becf2-106">För Viva Learning (förhandsversion) måste du först ställa in uppdateringsprincipen i Teams.</span><span class="sxs-lookup"><span data-stu-id="becf2-106">For Viva Learning (Preview), you must first set the Update policy in Teams.</span></span> <span data-ttu-id="becf2-107">Mer information finns i Microsoft Teams [förhandsgranskning.](/MicrosoftTeams/public-preview-doc-updates)</span><span class="sxs-lookup"><span data-stu-id="becf2-107">For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span></span>

    1. <span data-ttu-id="becf2-108">Logga in Teams administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="becf2-108">Sign in to the Teams admin center.</span></span>

    2. <span data-ttu-id="becf2-109">Välj **Teams**  >  **Uppdatera principer**.</span><span class="sxs-lookup"><span data-stu-id="becf2-109">Select **Teams** > **Update policies**.</span></span>

    3. <span data-ttu-id="becf2-110">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="becf2-110">Select **Add**.</span></span> 

    4. <span data-ttu-id="becf2-111">Namnge uppdateringsprincipen, lägg till en princip och aktivera Visa **förhandsgranskningsfunktioner.**</span><span class="sxs-lookup"><span data-stu-id="becf2-111">Name the update policy, add a policy, and turn on **Show preview features**.</span></span>

2. <span data-ttu-id="becf2-112">Administratören måste meddela användarna om principuppdateringen så att de flyttar sin version till den offentliga förhandsversionen för Teams.</span><span class="sxs-lookup"><span data-stu-id="becf2-112">The admin must notify users of the policy update so that they move their build into the Public Preview for Teams.</span></span> 

    1. <span data-ttu-id="becf2-113">Användarna måste välja sin profilbild > **om**  >  **offentlig förhandsversion**.</span><span class="sxs-lookup"><span data-stu-id="becf2-113">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
        ![Övre navigeringsfältet i Teams visar användarens profil](../media/learning/learning-app-select-profile-teams.png)
    
    2. <span data-ttu-id="becf2-115">Användarna måste godkänna **villkoren för** den offentliga förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="becf2-115">Users must accept the **Public preview** terms and conditions.</span></span>

        ![Växla till offentlig förhandsversion](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="becf2-117">För organisationer som har restriktiva principer och behöver aktivera Viva Learning (förhandsversion) följer du processen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="becf2-117">For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="becf2-118">Hantera inställningar för Viva Learning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="becf2-118">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="becf2-119">Du måste vara administratör i administrationscentret Teams utföra de här uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="becf2-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="becf2-120">Gör Viva Learning (förhandsversion) tillgängligt för användare i organisationen genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="becf2-120">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="becf2-121">I det vänstra navigeringsfältet i Teams administrationscenter går du till Teams   >  **Hantera appar**.</span><span class="sxs-lookup"><span data-stu-id="becf2-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Vänster navigering i Teams administrationscenter som visar Teams program och avsnittet Hantera appar.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="becf2-123">På sidan **Hantera appar** skriver du *Viva learning* i sökrutan och väljer sedan **Viva Learning (förhandsversion).**</span><span class="sxs-lookup"><span data-stu-id="becf2-123">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Sidan Hantera appar i Teams administrationscenter som visar sökrutan.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="becf2-125">På **sidan Viva Learning (förhandsversion):**</span><span class="sxs-lookup"><span data-stu-id="becf2-125">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="becf2-126">Under **Status** väljer du **Tillåts** att aktivera Viva Learning (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="becf2-126">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="becf2-127">På fliken **Inställningar,** under **Appinställningar,** går du till administrationscentret för Microsoft 365 för [att konfigurera källor för utbildningsinnehåll.](content-sources-365-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="becf2-127">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![Sidan Utbildning i Teams visar avsnittet Status och Appinställningar.](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="becf2-129">När **du har hanterat appinställningarna** går du till Behörighetsprinciper och Konfigurationsprinciper för att ge behörighet till anställda som bör ha tillgång till Viva Learning (förhandsversion) som en del av organisationens deltagande i förhandsgranskningen.  </span><span class="sxs-lookup"><span data-stu-id="becf2-129">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="becf2-130">Om din organisation har Ring 4.0 som en del av Teams TAP100-programmet kan du behöva aktivera godkända användare i Ring 3.0 för att få åtkomst till Viva Learning (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="becf2-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="becf2-131">Som en del av förhandsversionen släpps Viva Learning (förhandsversion) i Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="becf2-131">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="becf2-132">Om din organisation har Ring 4.0 ser du inte Viva Learning (förhandsversion) på **sidan Hantera** appar.</span><span class="sxs-lookup"><span data-stu-id="becf2-132">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="becf2-133">Om du vill testa appen måste du skapa en behörighetsprincip för anpassade appar, ange Tillåt alla appar och tilldela den till Ring 3.0-godkända användare.</span><span class="sxs-lookup"><span data-stu-id="becf2-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="becf2-134">![TAP-AppsPermission-Plcy-sidan med Tillåt alla appar markerade.](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="becf2-134">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="becf2-135">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="becf2-135">Next step</span></span>

[<span data-ttu-id="becf2-136">Konfigurera utbildningsinnehållskällor för Viva Learning (förhandsversion) Microsoft 365 administrationscentret</span><span class="sxs-lookup"><span data-stu-id="becf2-136">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
