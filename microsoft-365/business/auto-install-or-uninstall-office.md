---
title: Installera och avinstallera Office automatiskt på Windows 10-enheter
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Installera eller avinstallera Office på Windows 10-enheter från Microsoft 365 Business Admin Center. '
ms.openlocfilehash: d82ab8292211d1adacba732922bf693dd2157ad6
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287544"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="451da-103">Installera och avinstallera Office automatiskt på Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="451da-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="451da-104">[![Etiketten så att du vet att Admin Center förändras och du kan hitta mer information på aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="451da-104">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="451da-105">Du kan snabbt och enkelt installera Office på datorer med Windows 10 från Microsoft 365 Business Administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="451da-105">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="451da-106">Om du vill veta mer om hur det fungerar med tidigare installerade Office-program kan du läsa [Förbered för installation av Office-klienten](prepare-for-office-client-deployment.md) innan du sätter igång.</span><span class="sxs-lookup"><span data-stu-id="451da-106">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="451da-107">Hantera Office-distribution</span><span class="sxs-lookup"><span data-stu-id="451da-107">Manage Office deployments</span></span>

1. <span data-ttu-id="451da-108">Logga in på [Administrationscenter](https://aka.ms/bcsportal) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="451da-108">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="451da-109">På kortet **Enheter** väljer du **Hantera Office-distribution**.</span><span class="sxs-lookup"><span data-stu-id="451da-109">On the **Devices** card, choose **Manage Office Deployment**.</span></span>
      <span data-ttu-id="451da-110">Om **enhets åtgärds** kortet inte visas klickar du på **Lägg** till (+) på **Start** sidan för administratörscenter för att lägga till det i administratörs hemmet.</span><span class="sxs-lookup"><span data-stu-id="451da-110">If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="451da-112">I fönstret **Hantera Office distribution** som öppnas väljer du **Lägg till en grupp** och markerar de grupper som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="451da-112">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="451da-113">När du har lagt till den eller de grupper som du vill använda väljer du antingen **Installera Office så snart som möjligt** eller **Avinstallera Office** i listrutan **Distributionsåtgärd**.</span><span class="sxs-lookup"><span data-stu-id="451da-113">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="451da-115">Välj **Nästa** \> granska inställningarna och välj sedan **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="451da-115">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="451da-116">32-bitarsversionen av Office installeras/avinstalleras automatiskt på de enheter som ägs av användare som ingår i gruppen eller grupperna du valde.</span><span class="sxs-lookup"><span data-stu-id="451da-116">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="451da-117">För att bekräfta åtgärden kan du öppna Aktivitetshanteraren på en dator som har angivits för Office-installation och leta processen Microsoft Office Klicka-och-kör.</span><span class="sxs-lookup"><span data-stu-id="451da-117">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


