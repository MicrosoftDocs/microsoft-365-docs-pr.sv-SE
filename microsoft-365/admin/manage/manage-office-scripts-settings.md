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
description: Lär dig hur du hanterar inställningar för Office-skript för användare i organisationen.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058429"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="6b763-103">Hantera inställningar för Office-skript</span><span class="sxs-lookup"><span data-stu-id="6b763-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="6b763-104">Med Office-skript kan användare automatisera uppgifter genom att spela in, redigera och köra skript i Excel på webben.</span><span class="sxs-lookup"><span data-stu-id="6b763-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="6b763-105">Office-skript fungerar med Power Automate och användare kör skript på arbetsböcker med hjälp av Excel Online-kopplingen (företag).</span><span class="sxs-lookup"><span data-stu-id="6b763-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="6b763-106">Microsoft 365-administratörer kan hantera inställningar för Office-skript från administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6b763-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6b763-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="6b763-107">Before you begin</span></span>

- <span data-ttu-id="6b763-108">Du måste vara global administratör för att kunna hantera inställningar för Office-skript. Mer information finns i Om [administratörsroller.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6b763-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="6b763-109">Se till att användarna i organisationen har en giltig licens för kommersiella Microsoft 365- eller Office 365-abonnemang eller EDU-abonnemang som omfattar åtkomst till Office-skrivbordsprogram, till exempel något av följande abonnemang:</span><span class="sxs-lookup"><span data-stu-id="6b763-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="6b763-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="6b763-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="6b763-111">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="6b763-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="6b763-112"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="6b763-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="6b763-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="6b763-113">Office 365 E3</span></span>
    - <span data-ttu-id="6b763-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="6b763-114">Office 365 E5</span></span>
    - <span data-ttu-id="6b763-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="6b763-115">Office 365 A3</span></span>
    - <span data-ttu-id="6b763-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="6b763-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="6b763-117">Hantera tillgängligheten för Office-skript och delning av skript</span><span class="sxs-lookup"><span data-stu-id="6b763-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="6b763-118">Gå till fliken Inställningar för organisationsinställningar  i administrationscentret för Microsoft 365. \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="6b763-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="6b763-119">Välj **Office-skript.**</span><span class="sxs-lookup"><span data-stu-id="6b763-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="6b763-120">Office-skript är aktiverat som standard och alla i organisationen kan komma åt och använda funktionen och dela skript.</span><span class="sxs-lookup"><span data-stu-id="6b763-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="6b763-121">Om du vill inaktivera Office-skript för organisationen avmarkerar du kryssrutan Låt användare **automatisera sina uppgifter i Excel på** webben.</span><span class="sxs-lookup"><span data-stu-id="6b763-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="6b763-122">Om du tidigare har inaktiverat Office-skript för organisationen och du vill aktivera det igen väljer du Låt användare automatisera sina uppgifter i **Excel** på webben och anger sedan vem som kan komma åt och använda funktionen:</span><span class="sxs-lookup"><span data-stu-id="6b763-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="6b763-123">Om du vill ge alla användare i organisationen åtkomst till och använda Office-skript lämnar du **Alla** (standardinställningen) markerad.</span><span class="sxs-lookup"><span data-stu-id="6b763-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="6b763-124">Om du bara vill ge medlemmar i en viss grupp åtkomst till och använda Office-skript väljer du Specifik grupp och anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan över tillåtna grupper.</span><span class="sxs-lookup"><span data-stu-id="6b763-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="6b763-125">Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:</span><span class="sxs-lookup"><span data-stu-id="6b763-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="6b763-126">Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="6b763-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="6b763-127">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="6b763-127">Distribution group</span></span>
        - <span data-ttu-id="6b763-128">Säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="6b763-128">Security group</span></span>
        - <span data-ttu-id="6b763-129">E-postaktiverad säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="6b763-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="6b763-130">Mer information om de olika typerna av grupper finns i [Jämför grupper.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="6b763-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="6b763-131">Om du vill låta användare med åtkomst till Office-skript dela sina skript med andra i organisationen väljer du Låt användare med åtkomst till **Office-skript** dela sina skript med andra i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6b763-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="6b763-132">Det går inte att dela skript utanför en organisation.</span><span class="sxs-lookup"><span data-stu-id="6b763-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="6b763-133">Om du senare inaktiverar skriptdelning för organisationen kan användarna fortfarande köra skript som delats tidigare.</span><span class="sxs-lookup"><span data-stu-id="6b763-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="6b763-134">Ange vilka användare som har åtkomst till Office-skript kan dela sina skript:</span><span class="sxs-lookup"><span data-stu-id="6b763-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="6b763-135">Om du vill tillåta att alla användare med åtkomst till Office-skript kan dela sina skript lämnar du **Alla** (standardinställningen) markerad.</span><span class="sxs-lookup"><span data-stu-id="6b763-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="6b763-136">Om du bara vill låta medlemmar i en viss grupp med åtkomst till Office-skript dela sina skript väljer du Specifik grupp och anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan över tillåtna.</span><span class="sxs-lookup"><span data-stu-id="6b763-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="6b763-137">Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:</span><span class="sxs-lookup"><span data-stu-id="6b763-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="6b763-138">Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="6b763-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="6b763-139">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="6b763-139">Distribution group</span></span>
        - <span data-ttu-id="6b763-140">Säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="6b763-140">Security group</span></span>
        - <span data-ttu-id="6b763-141">E-postaktiverad säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="6b763-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="6b763-142">Mer information om de olika typerna av grupper finns i [Jämför grupper.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="6b763-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="6b763-143">Om du vill tillåta användare att köra Office-skript i Power Automate-flöden väljer du Låt användare med åtkomst till Office-skript köra sina skript **med Power Automate.**</span><span class="sxs-lookup"><span data-stu-id="6b763-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="6b763-144">På så sätt kan användarna lägga till flödessteg med [körskriptalternativet för Excel Online (företag).](/connectors/excelonlinebusiness) </span><span class="sxs-lookup"><span data-stu-id="6b763-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="6b763-145">Om du vill tillåta alla användare med åtkomst till Office-skript att använda sina skript i flöden lämnar du **Alla** (standardinställningen) markerad.</span><span class="sxs-lookup"><span data-stu-id="6b763-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="6b763-146">Om du bara vill låta medlemmar i en viss grupp med åtkomst till Office-skript använda sina skript i flöden väljer du Specifik grupp och anger sedan namnet eller e-postaliaset för gruppen för att lägga till den i listan över tillåtna.</span><span class="sxs-lookup"><span data-stu-id="6b763-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="6b763-147">Du kan bara lägga till en grupp i listan över tillåtna grupper och det måste vara någon av följande typer:</span><span class="sxs-lookup"><span data-stu-id="6b763-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="6b763-148">Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="6b763-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="6b763-149">Distributionsgrupp</span><span class="sxs-lookup"><span data-stu-id="6b763-149">Distribution group</span></span>
        - <span data-ttu-id="6b763-150">Säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="6b763-150">Security group</span></span>
        - <span data-ttu-id="6b763-151">E-postaktiverad säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="6b763-151">Mail-enabled security group</span></span>

        <span data-ttu-id="6b763-152">Mer information om de olika typerna av grupper finns i [Jämför grupper.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="6b763-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="6b763-153">Mer information om hur du använder Office-skript med Power Automate, inklusive hur principer för skydd mot dataförlust kan påverkas, finns i Köra Office-skript med [Power Automate.](/office/dev/scripts/develop/power-automate-integration)</span><span class="sxs-lookup"><span data-stu-id="6b763-153">To learn more about using Office Scripts with Power Automate, including how your data loss prevention policies may be impacted, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="6b763-154">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6b763-154">Select **Save**.</span></span>

    <span data-ttu-id="6b763-155">Det kan ta upp till 48 timmar innan ändringarna av inställningarna för Office-skript verkställs.</span><span class="sxs-lookup"><span data-stu-id="6b763-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6b763-156">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6b763-156">Next steps</span></span>

<span data-ttu-id="6b763-157">Eftersom Office Scripts fungerar med Power Automate rekommenderar vi att du granskar befintliga DLP-principer (dataförlustskydd) för att säkerställa att organisationens data skyddas när användarna använder Office-skript.</span><span class="sxs-lookup"><span data-stu-id="6b763-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="6b763-158">Mer information finns i [DLP-principer (Data Loss Prevention).](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="6b763-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="6b763-159">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="6b763-159">Related content</span></span>

<span data-ttu-id="6b763-160">[Teknisk dokumentation för Office Scripts](/office/dev/scripts/) (länksida)</span><span class="sxs-lookup"><span data-stu-id="6b763-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="6b763-161">[Introduktion till Office-skript i Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)</span><span class="sxs-lookup"><span data-stu-id="6b763-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="6b763-162">[Dela Office-skript i Excel för webben](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikeln)</span><span class="sxs-lookup"><span data-stu-id="6b763-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="6b763-163">[Spela in, redigera och skapa Office-skript i Excel på webben](/office/dev/scripts/tutorials/excel-tutorial) (artikel)</span><span class="sxs-lookup"><span data-stu-id="6b763-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
