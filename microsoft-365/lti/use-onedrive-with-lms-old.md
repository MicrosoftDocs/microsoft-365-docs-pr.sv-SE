---
title: Användning OneDrive Learning verktygskompatibilitet
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Skapa och betygs gradera uppgifter, skapa och hantera kursinnehåll och samarbeta i filer i realtid med den nya appen OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257050"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="109a4-103">Använda Microsoft OneDrive LTI med Canvas</span><span class="sxs-lookup"><span data-stu-id="109a4-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="109a4-104">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="109a4-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="109a4-105">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="109a4-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="109a4-106">Integrera med Canvas</span><span class="sxs-lookup"><span data-stu-id="109a4-106">Integrate with Canvas</span></span>

<span data-ttu-id="109a4-107">Den person som utför den här integrationen bör vara administratör för Canvas och administratör för Microsoft 365 klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="109a4-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="109a4-108">Logga in på Microsoft Azure med klientorganisationens administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="109a4-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="109a4-109">Azure-innehavaradministratören bör också ha rollen Gruppadministratör.</span><span class="sxs-lookup"><span data-stu-id="109a4-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![gruppadministratör markerad](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="109a4-111">Logga in på Microsoft [OneDrive LTI-portalen](https://odltiappnl.azurewebsites.net/admin).</span><span class="sxs-lookup"><span data-stu-id="109a4-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="109a4-112">Godkänn behörigheterna för att slutföra inloggningen.</span><span class="sxs-lookup"><span data-stu-id="109a4-112">Accept the permissions to complete the sign-in.</span></span>

    ![acceptera behörigheter](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="109a4-114">Välj **Lägg till LTI-klient.**</span><span class="sxs-lookup"><span data-stu-id="109a4-114">Select **Add LTI Tenant**.</span></span>

     ![lägg till LTI-klient](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="109a4-116">Välj **LTI Consumer Platform** som **Canvas** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="109a4-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="109a4-117">Välj **Arbetsytebas-URL** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="109a4-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![välj Arbetsyta och lägg till bas-URL](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="109a4-119">På nästa skärm visas fält som är konfidentiella.</span><span class="sxs-lookup"><span data-stu-id="109a4-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="109a4-120">Välj **Nästa** från ??</span><span class="sxs-lookup"><span data-stu-id="109a4-120">Select **Next** from ??</span></span> <span data-ttu-id="109a4-121">.</span><span class="sxs-lookup"><span data-stu-id="109a4-121">page.</span></span> <span data-ttu-id="109a4-122">KAN GRANSKARE FYLLA I DET TOMMA HÄR?</span><span class="sxs-lookup"><span data-stu-id="109a4-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="109a4-123">Välj **Nästa** på skärmen som visar information som är konfidentiell.</span><span class="sxs-lookup"><span data-stu-id="109a4-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="109a4-124">Den sista skärmen i Azure-portalen visar nästa steg för att lägga till din Canvas-instans.</span><span class="sxs-lookup"><span data-stu-id="109a4-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="109a4-125">Kopiera utvecklarnycklarna från den här skärmen.</span><span class="sxs-lookup"><span data-stu-id="109a4-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="109a4-126">Du kommer att använda när du skapar Canvas-instansen.</span><span class="sxs-lookup"><span data-stu-id="109a4-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="109a4-127">Lägga till Canvas-instansen</span><span class="sxs-lookup"><span data-stu-id="109a4-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="109a4-128">Avmarkera Administratörsutvecklarenycklar i  >  **Canvas-instansen.**</span><span class="sxs-lookup"><span data-stu-id="109a4-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="109a4-129">Välj **LTI-nyckel** i listrutan på **Utvecklarnyckel**.</span><span class="sxs-lookup"><span data-stu-id="109a4-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![Hämta LTI-utvecklarnycklarna](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="109a4-131">Klistra in utvecklarnycklarna här.</span><span class="sxs-lookup"><span data-stu-id="109a4-131">Paste the developer keys here.</span></span>

     ![Klistra in utvecklarnycklarna](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="109a4-133">Nyckeln skapas i **AV-läge**</span><span class="sxs-lookup"><span data-stu-id="109a4-133">The key gets created in **OFF** mode</span></span>

   ![Utvecklarnycklarna som skapats i läget Av](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="109a4-135">Kopiera den markerade texten.</span><span class="sxs-lookup"><span data-stu-id="109a4-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="109a4-136">Det här fungerar som klient-ID Microsoft OneDrive LTI-portalen.</span><span class="sxs-lookup"><span data-stu-id="109a4-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="109a4-137">Klistra in texten i fältet **Klient-ID** i Microsoft OneDrive LTI-portalen och välj **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="109a4-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="109a4-138">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="109a4-138">Select **Save**.</span></span>

7. <span data-ttu-id="109a4-139">Visa inställningarna genom att välja **Visa LTI-klientorganisation.**</span><span class="sxs-lookup"><span data-stu-id="109a4-139">View the settings by selecting **View LTI Tenants**.</span></span>
