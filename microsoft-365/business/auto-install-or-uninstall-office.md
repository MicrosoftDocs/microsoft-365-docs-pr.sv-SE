---
title: Installera och avinstallera Office automatiskt på Windows 10-enheter
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Installera eller avinstallera Office på Windows 10 enheter från Microsoft 365 Business administratörscenter. '
ms.openlocfilehash: fef4a543aed489202bf05dfb1e8cafbb784ca819
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277309"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="af44d-103">Installera och avinstallera Office automatiskt på Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="af44d-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="af44d-104">Du kan snabbt och enkelt installera Office på datorer med Windows 10 från Microsoft 365 Business Administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="af44d-104">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="af44d-105">Om du vill veta mer om hur det fungerar med tidigare installerade Office-program kan du läsa [Förbered för installation av Office-klienten](prepare-for-office-client-deployment.md) innan du sätter igång.</span><span class="sxs-lookup"><span data-stu-id="af44d-105">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="af44d-106">Hantera Office-distribution</span><span class="sxs-lookup"><span data-stu-id="af44d-106">Manage Office deployments</span></span>

1. <span data-ttu-id="af44d-107">Logga in på [Administrationscenter](https://aka.ms/bcsportal) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="af44d-107">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="af44d-108">På kortet **Enheter** väljer du **Hantera Office-distribution**.</span><span class="sxs-lookup"><span data-stu-id="af44d-108">On the **Devices** card, choose **Manage Office Deployment**.</span></span>
      <span data-ttu-id="af44d-109">Om du inte ser **enheten åtgärder** -kort klickar du på **Lägg till** (+) om du vill lägga till den i hemmet admin admin center **Hem** på sidan.</span><span class="sxs-lookup"><span data-stu-id="af44d-109">If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="af44d-111">I fönstret **Hantera Office distribution** som öppnas väljer du **Lägg till en grupp** och markerar de grupper som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="af44d-111">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="af44d-112">När du har lagt till den eller de grupper som du vill använda väljer du antingen **Installera Office så snart som möjligt** eller **Avinstallera Office** i listrutan **Distributionsåtgärd**.</span><span class="sxs-lookup"><span data-stu-id="af44d-112">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="af44d-114">Välj **Nästa** \> granska inställningarna och välj sedan **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="af44d-114">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="af44d-115">32-bitarsversionen av Office installeras/avinstalleras automatiskt på de enheter som ägs av användare som ingår i gruppen eller grupperna du valde.</span><span class="sxs-lookup"><span data-stu-id="af44d-115">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="af44d-116">För att bekräfta åtgärden kan du öppna Aktivitetshanteraren på en dator som har angivits för Office-installation och leta processen Microsoft Office Klicka-och-kör.</span><span class="sxs-lookup"><span data-stu-id="af44d-116">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


