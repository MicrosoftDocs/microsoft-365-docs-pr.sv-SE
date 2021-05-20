---
title: Hantera inställningar för Office-skript
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Läs om hur du Office skriptinställningar för användare i organisationen.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572315"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="9bc33-103">Hantera inställningar för Office-skript</span><span class="sxs-lookup"><span data-stu-id="9bc33-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="9bc33-104">[Office skript gör](/office/dev/scripts)det möjligt för användare att automatisera uppgifter genom att spela in, redigera och köra skript i Excel på webben.</span><span class="sxs-lookup"><span data-stu-id="9bc33-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="9bc33-105">Office Skript fungerar med Power Automate och användare kör skript på arbetsböcker med hjälp av Excel Online (Business) -anslutningen.</span><span class="sxs-lookup"><span data-stu-id="9bc33-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="9bc33-106">Microsoft 365 administratörer kan hantera Office skriptinställningar från Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="9bc33-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9bc33-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="9bc33-107">Before you begin</span></span>

- <span data-ttu-id="9bc33-108">Om du Office skriptinställningar måste du vara global administratör. Mer information finns i [Om administratörsroller](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9bc33-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="9bc33-109">Se till att användare i organisationen har en giltig licens för en Microsoft 365- eller Office 365-abonnemang eller EDU-plan som innehåller åtkomst till Office-skrivbordsappar, till exempel något av följande planer:</span><span class="sxs-lookup"><span data-stu-id="9bc33-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="9bc33-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="9bc33-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="9bc33-111">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="9bc33-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="9bc33-112">Microsoft 365-applikationer för företag</span><span class="sxs-lookup"><span data-stu-id="9bc33-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="9bc33-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="9bc33-113">Office 365 E3</span></span>
    - <span data-ttu-id="9bc33-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="9bc33-114">Office 365 E5</span></span>
    - <span data-ttu-id="9bc33-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="9bc33-115">Office 365 A3</span></span>
    - <span data-ttu-id="9bc33-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="9bc33-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="9bc33-117">Hantera tillgänglighet Office skript och delning av skript</span><span class="sxs-lookup"><span data-stu-id="9bc33-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="9bc33-118">Gå Microsoft 365 administrationscentret i Inställningar  \> **fliken** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Organisationsinställningar.</a></span><span class="sxs-lookup"><span data-stu-id="9bc33-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="9bc33-119">Välj **Office skript**.</span><span class="sxs-lookup"><span data-stu-id="9bc33-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="9bc33-120">Office Skript är aktiverat som standard och alla i organisationen kan komma åt och använda funktionen och dela skript.</span><span class="sxs-lookup"><span data-stu-id="9bc33-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="9bc33-121">Om du vill Office skript för din organisation **avmarkera** du kryssrutan Låt användarna automatisera sina uppgifter Excel på webben skript.</span><span class="sxs-lookup"><span data-stu-id="9bc33-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="9bc33-122">Om du tidigare har inaktiverat Office Scripts för din organisation och vill aktivera den igen väljer **du Låt användarna automatisera sina uppgifter i Excel på webben** och anger sedan vem som kan komma åt och använda funktionen:</span><span class="sxs-lookup"><span data-stu-id="9bc33-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="9bc33-123">Om du vill att alla användare i organisationen ska kunna komma åt och Office skript lämnar **du** Alla (standard) markerade.</span><span class="sxs-lookup"><span data-stu-id="9bc33-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="9bc33-124">Om du bara vill att medlemmar i en viss grupp ska kunna komma åt och använda Office Scripts väljer **du Specifik grupp** och anger sedan gruppens namn eller e-postalias för att lägga till den i listan över tillåtna.</span><span class="sxs-lookup"><span data-stu-id="9bc33-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="9bc33-125">Du kan bara lägga till en grupp i listan över tillåtna och det måste vara en av följande typer:</span><span class="sxs-lookup"><span data-stu-id="9bc33-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="9bc33-126">Microsoft 365 grupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="9bc33-127">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-127">Distribution group</span></span>
        - <span data-ttu-id="9bc33-128">Säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-128">Security group</span></span>
        - <span data-ttu-id="9bc33-129">E-postaktiverad säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="9bc33-130">Mer information om de olika typerna av grupper finns i [Jämföra grupper](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9bc33-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="9bc33-131">Om du vill att användare med åtkomst till Office Scripts ska kunna dela sina skript med andra i organisationen väljer **du Låt användare med åtkomst till Office Scripts dela sina skript med andra i organisationen**.</span><span class="sxs-lookup"><span data-stu-id="9bc33-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="9bc33-132">Det är inte tillåtet att dela skript utanför en organisation.</span><span class="sxs-lookup"><span data-stu-id="9bc33-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="9bc33-133">Om du senare inaktiverar skriptdelning för din organisation kan användarna fortfarande köra tidigare delade skript.</span><span class="sxs-lookup"><span data-stu-id="9bc33-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="9bc33-134">Ange vilka användare med åtkomst till Office skript som kan dela sina skript:</span><span class="sxs-lookup"><span data-stu-id="9bc33-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="9bc33-135">Om du vill att alla användare med Office skript ska kunna dela sina skript **lämnar du** Alla (standard) markerade.</span><span class="sxs-lookup"><span data-stu-id="9bc33-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="9bc33-136">Om du bara vill att medlemmar i en viss grupp med åtkomst till Office Scripts ska kunna dela sina skript väljer du **Specifik grupp** och anger sedan gruppens namn eller e-postalias för att lägga till det i listan över tillåtna.</span><span class="sxs-lookup"><span data-stu-id="9bc33-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="9bc33-137">Du kan bara lägga till en grupp i listan över tillåtna och det måste vara en av följande typer:</span><span class="sxs-lookup"><span data-stu-id="9bc33-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="9bc33-138">Microsoft 365 grupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="9bc33-139">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-139">Distribution group</span></span>
        - <span data-ttu-id="9bc33-140">Säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-140">Security group</span></span>
        - <span data-ttu-id="9bc33-141">E-postaktiverad säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="9bc33-142">Mer information om de olika typerna av grupper finns i [Jämföra grupper](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9bc33-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="9bc33-143">Om du vill tillåta användare att köra sina Office-skript i Power Automate-flöden väljer **du Låt användare med åtkomst till Office Scripts köra sina skript med Power Automate**.</span><span class="sxs-lookup"><span data-stu-id="9bc33-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="9bc33-144">Detta gör det möjligt för användare att lägga [till flödessteg Excel skriptalternativet Business( Business) Connector's](/connectors/excelonlinebusiness) **Run.**</span><span class="sxs-lookup"><span data-stu-id="9bc33-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="9bc33-145">Om du vill att alla användare med Office skript ska kunna använda sina skript i flöden **lämnar du** Alla (standard) markerade.</span><span class="sxs-lookup"><span data-stu-id="9bc33-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="9bc33-146">Om du bara vill att medlemmar i en viss grupp med åtkomst till Office Scripts ska kunna använda sina skript i flöden väljer **du Specifik grupp** och anger sedan gruppens namn eller e-postalias för att lägga till det i listan över tillåtna.</span><span class="sxs-lookup"><span data-stu-id="9bc33-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="9bc33-147">Du kan bara lägga till en grupp i listan över tillåtna och det måste vara en av följande typer:</span><span class="sxs-lookup"><span data-stu-id="9bc33-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="9bc33-148">Microsoft 365 grupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="9bc33-149">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-149">Distribution group</span></span>
        - <span data-ttu-id="9bc33-150">Säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-150">Security group</span></span>
        - <span data-ttu-id="9bc33-151">E-postaktiverad säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="9bc33-151">Mail-enabled security group</span></span>

        <span data-ttu-id="9bc33-152">Mer information om de olika typerna av grupper finns i [Jämföra grupper](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9bc33-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="9bc33-153">Mer information om hur du Office använda Power Automate med Office [skript med Power Automate](/office/dev/scripts/develop/power-automate-integration).</span><span class="sxs-lookup"><span data-stu-id="9bc33-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="9bc33-154">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9bc33-154">Select **Save**.</span></span>

    <span data-ttu-id="9bc33-155">Det kan ta upp till 48 timmar innan ändringar Office skriptinställningarna träder i kraft.</span><span class="sxs-lookup"><span data-stu-id="9bc33-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9bc33-156">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9bc33-156">Next steps</span></span>

<span data-ttu-id="9bc33-157">Eftersom Office-skript fungerar med Power Automate rekommenderar vi att du granskar dina befintliga DLP-principer (Data Loss Prevention) för att säkerställa att organisationens data förblir skyddade medan användarna använder Office skript.</span><span class="sxs-lookup"><span data-stu-id="9bc33-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="9bc33-158">Mer information finns i [DLP-principer (Data Loss Prevention).](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="9bc33-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="9bc33-159">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="9bc33-159">Related content</span></span>

<span data-ttu-id="9bc33-160">[Office teknisk dokumentation för skript](/office/dev/scripts/) (länksida)</span><span class="sxs-lookup"><span data-stu-id="9bc33-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="9bc33-161">[Introduktion till Office skript i Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)</span><span class="sxs-lookup"><span data-stu-id="9bc33-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="9bc33-162">[Dela Office skript Excel för webben](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel)</span><span class="sxs-lookup"><span data-stu-id="9bc33-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="9bc33-163">[Spela in, redigera och Office skript i Excel på webben](/office/dev/scripts/tutorials/excel-tutorial) (artikel)</span><span class="sxs-lookup"><span data-stu-id="9bc33-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
