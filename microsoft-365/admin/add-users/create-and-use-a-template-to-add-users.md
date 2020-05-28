---
title: Skapa och använda en mall för att lägga till användare
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Du kan skapa och använda en mall för att spara tid och standardisera inställningar när du lägger till flera användare.
ms.openlocfilehash: 3173d28f27acdf1a084137d36cd71894e94e9547
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387231"
---
# <a name="create-and-use-a-template-to-add-users"></a><span data-ttu-id="9aab5-103">Skapa och använda en mall för att lägga till användare</span><span class="sxs-lookup"><span data-stu-id="9aab5-103">Create and use a template to add users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9aab5-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="9aab5-104">The admin center is changing.</span></span> <span data-ttu-id="9aab5-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="9aab5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="9aab5-106">Du kan skapa och använda en mall för att spara tid och standardisera inställningar när du lägger till flera användare.</span><span class="sxs-lookup"><span data-stu-id="9aab5-106">You can create and use a template to save time and standardize settings when you are adding multiple users.</span></span> <span data-ttu-id="9aab5-107">Mallar är särskilt användbara om du har användare som delar många vanliga egenskaper, som de som har samma roll och arbetar på samma plats och de som behöver samma programvara.</span><span class="sxs-lookup"><span data-stu-id="9aab5-107">Templates are particularly useful if you have users who share many common properties, like those who have the same role and work at the same location and those who require the same software.</span></span> <span data-ttu-id="9aab5-108">Du kan till exempel ha ett team med supporttekniker som arbetar på samma kontor.</span><span class="sxs-lookup"><span data-stu-id="9aab5-108">For example, you might have a team of support engineers who work in the same office.</span></span>  

## <a name="create-a-template"></a><span data-ttu-id="9aab5-109">Skapa en mall</span><span class="sxs-lookup"><span data-stu-id="9aab5-109">Create a template</span></span>

<span data-ttu-id="9aab5-110">Mallar är enkla att &mdash; skapa, du kan välja **Användare**  >  **Aktiva användare**  >  **Användarmallar**, och välj sedan Lägg till en **mall** i listrutan, eller så kan du lägga till en ny användare och när du är klar har du möjlighet att spara posten som en mall.</span><span class="sxs-lookup"><span data-stu-id="9aab5-110">Templates are easy to create&mdash;you can select **Users** > **Active users** > **User templates**, and then select **Add a template** from the drop-down list, or you can add a new user and when you are finished, you will have the option of saving the entry as a template.</span></span>

<span data-ttu-id="9aab5-111">När du skapar en mall när du har lagt till en användare sparas de värden du väljer för följande inställningar i mallen:</span><span class="sxs-lookup"><span data-stu-id="9aab5-111">When you create a template after adding a user, the values you choose for the following settings are saved in the template:</span></span>

- <span data-ttu-id="9aab5-112">Domännamn</span><span class="sxs-lookup"><span data-stu-id="9aab5-112">Domain name</span></span>
- <span data-ttu-id="9aab5-113">Val av lösenordsinställningar: du kan välja att skapa lösenord eller låta dem genereras automatiskt</span><span class="sxs-lookup"><span data-stu-id="9aab5-113">Password settings choice: you can choose to create passwords or have them auto-generated</span></span>
- <span data-ttu-id="9aab5-114">Engångslösenord: du kan kräva att användaren skapar ett nytt lösenord efter första inloggningen</span><span class="sxs-lookup"><span data-stu-id="9aab5-114">One-time password choice: you can require the user to create a new password after first sign in</span></span>
- <span data-ttu-id="9aab5-115">Licensplats</span><span class="sxs-lookup"><span data-stu-id="9aab5-115">License location</span></span>
- <span data-ttu-id="9aab5-116">Licensval</span><span class="sxs-lookup"><span data-stu-id="9aab5-116">License choices</span></span>
- <span data-ttu-id="9aab5-117">Val av program</span><span class="sxs-lookup"><span data-stu-id="9aab5-117">Application choices</span></span>
- <span data-ttu-id="9aab5-118">Roll</span><span class="sxs-lookup"><span data-stu-id="9aab5-118">Role</span></span>
- <span data-ttu-id="9aab5-119">Mest profilinformation, till exempel **Jobbprofil,** **Avdelning,** **Office,** **Office-telefon**och **Gatuadress**</span><span class="sxs-lookup"><span data-stu-id="9aab5-119">Most profile information, such as **Job profile**, **Department**, **Office**, **Office phone**, and **Street address**</span></span> 

<span data-ttu-id="9aab5-120">Följande information är användarspecifik och sparas inte i mallen:</span><span class="sxs-lookup"><span data-stu-id="9aab5-120">The following information is user-specific and isn't saved in the template:</span></span>

- <span data-ttu-id="9aab5-121">För- och efternamn</span><span class="sxs-lookup"><span data-stu-id="9aab5-121">First and last name</span></span>
- <span data-ttu-id="9aab5-122">Visningsnamn</span><span class="sxs-lookup"><span data-stu-id="9aab5-122">Display name</span></span>
- <span data-ttu-id="9aab5-123">Användarnamn</span><span class="sxs-lookup"><span data-stu-id="9aab5-123">User name</span></span>
- <span data-ttu-id="9aab5-124">Val att skicka lösenordet via e-post och vem lösenordet e-postmeddelandet skickas till</span><span class="sxs-lookup"><span data-stu-id="9aab5-124">Choice to send the password in email and who the password email is sent to</span></span>
- <span data-ttu-id="9aab5-125">Mobiltelefonnummer</span><span class="sxs-lookup"><span data-stu-id="9aab5-125">Mobile phone number</span></span>

<span data-ttu-id="9aab5-126">Om du väljer att inte ange information för en inställning i ett avsnitt är det värdet tomt och den inställningen visas inte i mallen.</span><span class="sxs-lookup"><span data-stu-id="9aab5-126">If you choose not to enter information for a setting within a section, that value will be blank and that setting will not display in the template.</span></span> <span data-ttu-id="9aab5-127">Om du till exempel lämnar **befattningen** tom visas inte **befattningen jobbtitel** alls när du granskar mallen och när du använder mallen.</span><span class="sxs-lookup"><span data-stu-id="9aab5-127">For example, if you leave **Job title** blank, when you review your template and when you use your template, **Job title** will not appear at all.</span></span> <span data-ttu-id="9aab5-128">Om du lämnar alla inställningar för **profilavsnittet** tomma visas **Ingen** i den slutliga mallen i avsnittet **Profil.**</span><span class="sxs-lookup"><span data-stu-id="9aab5-128">If you leave all the **Profile** section settings blank, the **Profile** section will display **None provided** in your final template.</span></span>

<span data-ttu-id="9aab5-129">När du skapar en mall genom att välja alternativet **Lägg till en mall** kan du välja vilka värden som ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="9aab5-129">When you create a template by selecting the **Add a template** option, you can choose which values to complete.</span></span> <span data-ttu-id="9aab5-130">Allt som lämnas tomt visas som **Ingen i** mallen.</span><span class="sxs-lookup"><span data-stu-id="9aab5-130">Anything that is left blank will appear as **None provided** in the template.</span></span>

## <a name="use-a-template-to-add-a-user"></a><span data-ttu-id="9aab5-131">Använda en mall för att lägga till en användare</span><span class="sxs-lookup"><span data-stu-id="9aab5-131">Use a template to add a user</span></span>

<span data-ttu-id="9aab5-132">Så här använder du en befintlig mall för att lägga till en användare:</span><span class="sxs-lookup"><span data-stu-id="9aab5-132">To use an existing template to add a user:</span></span>

1. <span data-ttu-id="9aab5-133">I administrationscentret väljer du **Aktiva**  >  **användare**.</span><span class="sxs-lookup"><span data-stu-id="9aab5-133">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="9aab5-134">Välj **Användarmallar**och välj sedan en mall i listrutan.</span><span class="sxs-lookup"><span data-stu-id="9aab5-134">Select **User templates**, and then select a template from the drop-down list.</span></span> <span data-ttu-id="9aab5-135">(Listan innehåller bara de mallar som du har skapat, inte de som skapats av andra administratörer.)</span><span class="sxs-lookup"><span data-stu-id="9aab5-135">(The list will contain only the templates that you created, not those created by other admins.)</span></span>

 > [!NOTE]
 > <span data-ttu-id="9aab5-136">Du kan också använda en mall för att lägga till en användare genom att välja **Användarmallar**  >  **Hantera mallar,** välja en mall och sedan välja **Använd mall**.</span><span class="sxs-lookup"><span data-stu-id="9aab5-136">You can also use a template to add a user by selecting **User templates** > **Manage templates**, selecting a template, and then selecting **Use template**.</span></span>

3. <span data-ttu-id="9aab5-137">Följ stegen för att skapa en användare från den mall du valde.</span><span class="sxs-lookup"><span data-stu-id="9aab5-137">Follow the steps to create a user from the template you selected.</span></span>

> [!NOTE]
> <span data-ttu-id="9aab5-138">Om du inte har tillräckliga licenser tillgängliga för en användare som du lägger till och din betalningsinformation är tillgänglig försöker vi köpa en annan licens med din befintliga betalningsinformation.</span><span class="sxs-lookup"><span data-stu-id="9aab5-138">If you have insufficient licenses available for a user that you add, and your payment information is available, we will attempt to purchase another license using your existing payment information.</span></span> <span data-ttu-id="9aab5-139">Om din betalningsinformation inte är tillgänglig skapas användaren som en olicensierad användare.</span><span class="sxs-lookup"><span data-stu-id="9aab5-139">If your payment information is unavailable, the user will be created as an unlicensed user.</span></span>

## <a name="manage-templates"></a><span data-ttu-id="9aab5-140">Hantera mallar</span><span class="sxs-lookup"><span data-stu-id="9aab5-140">Manage templates</span></span>

<span data-ttu-id="9aab5-141">Du kan enkelt ta bort mallar som du inte längre behöver och lägga till nya.</span><span class="sxs-lookup"><span data-stu-id="9aab5-141">You can easily delete templates you no longer need and add new ones.</span></span> <span data-ttu-id="9aab5-142">Så här tar du bort en mall:</span><span class="sxs-lookup"><span data-stu-id="9aab5-142">To delete a template:</span></span>

1. <span data-ttu-id="9aab5-143">I administrationscentret väljer du **Aktiva**  >  **användare**.</span><span class="sxs-lookup"><span data-stu-id="9aab5-143">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="9aab5-144">Välj **Mallar**och välj sedan **Hantera mallar** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="9aab5-144">Select **Templates**, and then select **Manage templates** from the drop-down list.</span></span>

3. <span data-ttu-id="9aab5-145">En lista med mallar visas.</span><span class="sxs-lookup"><span data-stu-id="9aab5-145">A list of templates will appear.</span></span> <span data-ttu-id="9aab5-146">Du kan ta bort en mall genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="9aab5-146">You can delete a template by doing any of the following:</span></span>
    - <span data-ttu-id="9aab5-147">Markera en eller flera mallar och välj sedan **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="9aab5-147">Select one or more templates, and then select **Delete**.</span></span> 
    - <span data-ttu-id="9aab5-148">Markera de tre punkterna till höger om mallnamnet och välj sedan **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="9aab5-148">Select the three dots to the right of the template name, and then select **Delete**.</span></span>
    - <span data-ttu-id="9aab5-149">Välj mallnamnet.</span><span class="sxs-lookup"><span data-stu-id="9aab5-149">Select the template name.</span></span> <span data-ttu-id="9aab5-150">När mallinformationen visas till höger på skärmen väljer du **Ta bort mall**.</span><span class="sxs-lookup"><span data-stu-id="9aab5-150">When the template details appear on the right side of your screen, select **Delete template**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9aab5-151">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="9aab5-151">Related articles</span></span>

[<span data-ttu-id="9aab5-152">Lägga till användare individuellt eller i grupp i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9aab5-152">Add users individually or in bulk to Microsoft 365</span></span>](add-users.md)

[<span data-ttu-id="9aab5-153">Ta bort en tidigare anställd från Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9aab5-153">Remove a former employee from Microsoft 365</span></span>](remove-former-employee.md)
  
