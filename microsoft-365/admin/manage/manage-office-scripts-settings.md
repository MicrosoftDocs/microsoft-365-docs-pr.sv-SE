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
description: Lär dig hur du Office skriptinställningar för användare i organisationen.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572315"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="147fc-103">Hantera inställningar för Office-skript</span><span class="sxs-lookup"><span data-stu-id="147fc-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="147fc-104">[Office med skript](/office/dev/scripts)kan användare automatisera uppgifter genom att spela in, redigera och köra skript i Excel på webben.</span><span class="sxs-lookup"><span data-stu-id="147fc-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="147fc-105">Office Skript fungerar med Power Automate och användare kör skript i arbetsböcker med hjälp av kopplingen Excel Online (Företag).</span><span class="sxs-lookup"><span data-stu-id="147fc-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="147fc-106">Microsoft 365 administratörer kan hantera Office skriptinställningar från Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="147fc-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="147fc-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="147fc-107">Before you begin</span></span>

- <span data-ttu-id="147fc-108">Du måste Office global administratör för att kunna hantera skriptinställningar. Mer information finns i Om [administratörsroller.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="147fc-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="147fc-109">Se till att användarna i organisationen har en giltig licens för ett Microsoft 365- eller Office 365-kommersiellt abonnemang eller EDU-abonnemang som omfattar åtkomst till Office-skrivbordsprogram, till exempel ett av följande abonnemang:</span><span class="sxs-lookup"><span data-stu-id="147fc-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="147fc-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="147fc-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="147fc-111">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="147fc-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="147fc-112"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="147fc-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="147fc-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="147fc-113">Office 365 E3</span></span>
    - <span data-ttu-id="147fc-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="147fc-114">Office 365 E5</span></span>
    - <span data-ttu-id="147fc-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="147fc-115">Office 365 A3</span></span>
    - <span data-ttu-id="147fc-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="147fc-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="147fc-117">Hantera tillgänglighet Office skript och delning av skript</span><span class="sxs-lookup"><span data-stu-id="147fc-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="147fc-118">I administrationscentret Microsoft 365 du på fliken Tjänster **Inställningar** \> **Organisationsinställningar.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="147fc-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="147fc-119">Välj **Office skript**.</span><span class="sxs-lookup"><span data-stu-id="147fc-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="147fc-120">Office Skript är aktiverat som standard och alla i organisationen kan komma åt och använda funktionen och dela skript.</span><span class="sxs-lookup"><span data-stu-id="147fc-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="147fc-121">Om du Office inaktivera skript för organisationen avmarkerar du kryssrutan Låt användare automatisera sina **uppgifter Excel på webben** skript.</span><span class="sxs-lookup"><span data-stu-id="147fc-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="147fc-122">Om du tidigare har inaktiverat Office-skript för din organisation och du vill aktivera det igen väljer du Låt användare automatisera sina uppgifter i **Excel på webben** och anger sedan vem som kan komma åt och använda funktionen:</span><span class="sxs-lookup"><span data-stu-id="147fc-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="147fc-123">Om du vill tillåta alla användare i organisationen att komma åt Office och använda skript lämnar du **Alla** (standard) markerat.</span><span class="sxs-lookup"><span data-stu-id="147fc-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="147fc-124">Om du bara vill tillåta medlemmar i en viss grupp att komma åt och använda Office Scripts väljer du Specifik grupp och anger sedan gruppens namn eller e-postalias för att lägga till den i listan över tillåtna.</span><span class="sxs-lookup"><span data-stu-id="147fc-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="147fc-125">Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:</span><span class="sxs-lookup"><span data-stu-id="147fc-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="147fc-126">Microsoft 365 grupp</span><span class="sxs-lookup"><span data-stu-id="147fc-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="147fc-127">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="147fc-127">Distribution group</span></span>
        - <span data-ttu-id="147fc-128">Säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="147fc-128">Security group</span></span>
        - <span data-ttu-id="147fc-129">E-postaktiverad säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="147fc-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="147fc-130">Mer information om olika typer av grupper finns i [Jämföra grupper.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="147fc-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="147fc-131">Om du vill ge användare med åtkomst till Office-skript att dela sina skript med andra i organisationen väljer du Låt användare med åtkomst till **Office-skript** dela sina skript med andra i organisationen.</span><span class="sxs-lookup"><span data-stu-id="147fc-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="147fc-132">Det är inte tillåtet att dela skript utanför en organisation.</span><span class="sxs-lookup"><span data-stu-id="147fc-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="147fc-133">Om du senare inaktiverar skriptdelning för organisationen kan användarna fortfarande köra skript som har delats tidigare.</span><span class="sxs-lookup"><span data-stu-id="147fc-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="147fc-134">Ange vilka användare som har åtkomst Office skript kan dela sina skript:</span><span class="sxs-lookup"><span data-stu-id="147fc-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="147fc-135">Om du vill tillåta alla användare som har Office att dela sina skript låter du **Alla** (standard) vara markerat.</span><span class="sxs-lookup"><span data-stu-id="147fc-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="147fc-136">Om du bara vill tillåta medlemmar i en viss grupp med åtkomst till Office Scripts att dela sina skript väljer du Specifik grupp **och** anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan över tillåtna.</span><span class="sxs-lookup"><span data-stu-id="147fc-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="147fc-137">Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:</span><span class="sxs-lookup"><span data-stu-id="147fc-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="147fc-138">Microsoft 365 grupp</span><span class="sxs-lookup"><span data-stu-id="147fc-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="147fc-139">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="147fc-139">Distribution group</span></span>
        - <span data-ttu-id="147fc-140">Säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="147fc-140">Security group</span></span>
        - <span data-ttu-id="147fc-141">E-postaktiverad säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="147fc-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="147fc-142">Mer information om olika typer av grupper finns i [Jämföra grupper.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="147fc-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="147fc-143">Om du vill tillåta att användare kör sina Office-skript i Power Automate-flöden väljer du Låt användare med åtkomst till **Office-skript** köra sina skript med Power Automate .</span><span class="sxs-lookup"><span data-stu-id="147fc-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="147fc-144">Det gör att användarna kan lägga till flödessteg [med hjälp Excel för Online (Företag) Connectors](/connectors/excelonlinebusiness) **Kör-skriptalternativ.**</span><span class="sxs-lookup"><span data-stu-id="147fc-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="147fc-145">Om du vill tillåta alla användare som har Office att använda sina skript i flöden lämnar du **Alla** (standard) markerat.</span><span class="sxs-lookup"><span data-stu-id="147fc-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="147fc-146">Om du bara vill tillåta medlemmar i en viss grupp med åtkomst till Office Scripts att använda sina skript i flöden väljer du Specifik grupp **och** anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan över tillåtna.</span><span class="sxs-lookup"><span data-stu-id="147fc-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="147fc-147">Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:</span><span class="sxs-lookup"><span data-stu-id="147fc-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="147fc-148">Microsoft 365 grupp</span><span class="sxs-lookup"><span data-stu-id="147fc-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="147fc-149">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="147fc-149">Distribution group</span></span>
        - <span data-ttu-id="147fc-150">Säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="147fc-150">Security group</span></span>
        - <span data-ttu-id="147fc-151">E-postaktiverad säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="147fc-151">Mail-enabled security group</span></span>

        <span data-ttu-id="147fc-152">Mer information om olika typer av grupper finns i [Jämföra grupper.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="147fc-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="147fc-153">Mer information om hur du Office skript med Power Automate finns i [Köra Office-skript med Power Automate](/office/dev/scripts/develop/power-automate-integration).</span><span class="sxs-lookup"><span data-stu-id="147fc-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="147fc-154">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="147fc-154">Select **Save**.</span></span>

    <span data-ttu-id="147fc-155">Det kan ta upp till 48 timmar innan ändringar Office inställningarna för skript ska gå i kraft.</span><span class="sxs-lookup"><span data-stu-id="147fc-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="147fc-156">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="147fc-156">Next steps</span></span>

<span data-ttu-id="147fc-157">Eftersom Office-skript fungerar med Power Automate rekommenderar vi att du granskar dina befintliga DLP-principer (Data Loss Prevention) för att säkerställa att organisationens data förblir skyddade medan användare använder Office-skript.</span><span class="sxs-lookup"><span data-stu-id="147fc-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="147fc-158">Mer information finns i [Principer för skydd mot dataförlust (DLP).](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="147fc-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="147fc-159">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="147fc-159">Related content</span></span>

<span data-ttu-id="147fc-160">[Office den tekniska dokumentationen för skript](/office/dev/scripts/) (länksida)</span><span class="sxs-lookup"><span data-stu-id="147fc-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="147fc-161">[Introduktion till Office skript i Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)</span><span class="sxs-lookup"><span data-stu-id="147fc-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="147fc-162">[Delning Office skript i Excel för webben](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel)</span><span class="sxs-lookup"><span data-stu-id="147fc-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="147fc-163">[Spela in, redigera och skapa Office skript i Excel på webben](/office/dev/scripts/tutorials/excel-tutorial) (artikel)</span><span class="sxs-lookup"><span data-stu-id="147fc-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
