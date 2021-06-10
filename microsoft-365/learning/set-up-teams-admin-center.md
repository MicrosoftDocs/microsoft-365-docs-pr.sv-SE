---
title: Konfigurera Microsoft Viva Learning (förhandsversion) i Teams administrationscenter
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
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
ms.openlocfilehash: 860f16bee7d93f2212072c5d738263402704272f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789237"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="a6157-103">Konfigurera Microsoft Viva Learning (förhandsversion) i Teams administrationscenter</span><span class="sxs-lookup"><span data-stu-id="a6157-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="a6157-104">Informationen i den här artikeln gäller en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="a6157-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="a6157-105">Administratören Teams utföra vissa steg för att aktivera Viva Learning (förhandsversion) för sina användare i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="a6157-105">The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant.</span></span> <span data-ttu-id="a6157-106">De här stegen varierar beroende på hur klientorganisationen är aktiverad: [*Offentlig förhandsversion*](set-up-teams-admin-center.md#public-preview-tenants) eller [ *Privat förhandsversion* (eller betaversion).](set-up-teams-admin-center.md#private-preview-tenants)</span><span class="sxs-lookup"><span data-stu-id="a6157-106">These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center.md#private-preview-tenants).</span></span>

## <a name="public-preview-tenants"></a><span data-ttu-id="a6157-107">Offentliga förhandsversionsklienter</span><span class="sxs-lookup"><span data-stu-id="a6157-107">Public Preview tenants</span></span>

### <a name="administrator-steps-for-public-preview-tenants"></a><span data-ttu-id="a6157-108">Administratörssteg för offentliga förhandsversionsklienter</span><span class="sxs-lookup"><span data-stu-id="a6157-108">Administrator steps for Public Preview tenants</span></span>

<span data-ttu-id="a6157-109">Eftersom Viva Learning (förhandsversion) ännu inte är tillgängligt i allmänhet krävs vissa steg för att aktivera funktionerna och ange behörigheter för specifika användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="a6157-109">Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.</span></span> 

1. <span data-ttu-id="a6157-110">Aktivera funktioner för offentlig förhandsversion för Viva Learning -användare (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="a6157-110">Enable Public Preview features for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="a6157-111">a.</span><span class="sxs-lookup"><span data-stu-id="a6157-111">a.</span></span> <span data-ttu-id="a6157-112">Ändra Teams för att aktivera funktioner för offentlig förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="a6157-112">Modify Teams update policy to enable Public Preview features.</span></span> <span data-ttu-id="a6157-113">Se [Microsoft Teams offentlig förhandsversion](/microsoftteams/public-preview-doc-updates).</span><span class="sxs-lookup"><span data-stu-id="a6157-113">See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span></span>

    <span data-ttu-id="a6157-114">b.</span><span class="sxs-lookup"><span data-stu-id="a6157-114">b.</span></span> <span data-ttu-id="a6157-115">Aktivera uppdateringsprincipen för användare eller grupper som ska testa Viva Learning (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="a6157-115">Enable the update policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="a6157-116">Se [Tilldela principer till användare och grupper.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="a6157-116">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

2. <span data-ttu-id="a6157-117">Ändra appbehörighetsprincipen för Viva Learning-användare (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="a6157-117">Modify the app permission policy for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="a6157-118">a.</span><span class="sxs-lookup"><span data-stu-id="a6157-118">a.</span></span> <span data-ttu-id="a6157-119">Såvida den inte ingår i den globala principen ska du tillåta alla Microsoft-appar i appens behörighetsprincip.</span><span class="sxs-lookup"><span data-stu-id="a6157-119">Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy.</span></span> <span data-ttu-id="a6157-120">Se [Hantera appbehörighetsprinciper i Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="a6157-120">See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span> 

    <span data-ttu-id="a6157-121">b.</span><span class="sxs-lookup"><span data-stu-id="a6157-121">b.</span></span> <span data-ttu-id="a6157-122">Aktivera appens behörighetsprincip för användare eller grupper som ska utföra Viva Learning-testning (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="a6157-122">Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="a6157-123">Se [Tilldela principer till användare och grupper.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="a6157-123">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

3.  <span data-ttu-id="a6157-124">Meddela användare som kommer att testa Viva Learning (förhandsversion) för att [byta sin build-klient till offentlig förhandsversion för Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span><span class="sxs-lookup"><span data-stu-id="a6157-124">Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6157-125">För offentliga förhandsversionsklienter visas Viva Learning (förhandsversion) inte i Hanterade appar i Teams förrän den slutgiltiga produktlansen. </span><span class="sxs-lookup"><span data-stu-id="a6157-125">For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release.</span></span> <span data-ttu-id="a6157-126">Aktiverade användare av offentlig förhandsversion kan hitta Viva Learning (förhandsversion) i appbutiken Teams och använda den, när rätt principer och behörigheter har angetts.</span><span class="sxs-lookup"><span data-stu-id="a6157-126">However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.</span></span>

### <a name="user-steps-for-public-preview-tenants"></a><span data-ttu-id="a6157-127">Användarsteg för offentliga förhandsversionsklienter</span><span class="sxs-lookup"><span data-stu-id="a6157-127">User steps for Public Preview tenants</span></span>

<span data-ttu-id="a6157-128">Användare som har aktiverats för test av den offentliga förhandsversionen – genom att aktivera de principer som tidigare beskrivits [–](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) måste växla till offentlig förhandsgranskning i Teams klient. [](/microsoftteams/public-preview-doc-updates#enable-public-preview)</span><span class="sxs-lookup"><span data-stu-id="a6157-128">Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.</span></span>

1. <span data-ttu-id="a6157-129">Användarna måste välja sin profilbild > **om**  >  **offentlig förhandsversion**.</span><span class="sxs-lookup"><span data-stu-id="a6157-129">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
    ![Övre navigeringsfältet i Teams visar användarens profil](../media/learning/learning-app-select-profile-teams.png)
    
2. <span data-ttu-id="a6157-131">Användarna måste godkänna villkoren för den offentliga förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="a6157-131">Users must accept the Public Preview terms and conditions.</span></span>

    ![Växla till offentlig förhandsversion](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="a6157-133">Användare kan nu hitta Viva Learning (förhandsversion) i Teams app store och börja använda den.</span><span class="sxs-lookup"><span data-stu-id="a6157-133">Users can now find Viva Learning (Preview) in the Teams app store and start using it.</span></span>

## <a name="private-preview-tenants"></a><span data-ttu-id="a6157-134">Privata förhandsversionsklienter</span><span class="sxs-lookup"><span data-stu-id="a6157-134">Private Preview tenants</span></span>

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a><span data-ttu-id="a6157-135">Administratörssteg för privata förhandsversionsklienter (eller betaklienter)</span><span class="sxs-lookup"><span data-stu-id="a6157-135">Administrator steps for Private Preview (or Beta) tenants</span></span>

<span data-ttu-id="a6157-136">Det finns inga ytterligare principer som behöver aktiveras för klientorganisationen av den privata förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="a6157-136">For Private Preview tenants, there are no additional policies that need to be enabled.</span></span> <span data-ttu-id="a6157-137">Viva Learning (förhandsversion) måste emellertid göras tillgängligt för användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a6157-137">However, Viva Learning (Preview) must be made available for users in your organization.</span></span>

1. <span data-ttu-id="a6157-138">I det vänstra navigeringsfältet i Teams administrationscenter går du till Teams   >  **Hantera appar**.</span><span class="sxs-lookup"><span data-stu-id="a6157-138">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Vänster navigering i Teams administrationscenter som visar Teams program och avsnittet Hantera appar.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="a6157-140">På sidan **Hantera appar** skriver du *Viva Learning* i sökrutan och väljer sedan **Viva Learning (förhandsversion).**</span><span class="sxs-lookup"><span data-stu-id="a6157-140">On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Sidan Hantera appar i Teams administrationscenter som visar sökrutan.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="a6157-142">På sidan **Viva Learning (förhandsversion)** under **Status** väljer du **Tillåts** att aktivera Viva Learning (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="a6157-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   ![Sidan Utbildning i Teams visar avsnittet Status och Appinställningar.](../media/learning/learning-app-teams-learning-page.png)


<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a><span data-ttu-id="a6157-144">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a6157-144">Next step</span></span>

[<span data-ttu-id="a6157-145">Konfigurera utbildningsinnehållskällor för Viva Learning (förhandsversion) Microsoft 365 administrationscentret</span><span class="sxs-lookup"><span data-stu-id="a6157-145">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
