---
title: Bekräfta programskyddsinställningar på PC-datorer med Windows 10
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
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Lär dig hur du validerar Microsoft 365 Business app inställningar i Windows 10 enheter.
ms.openlocfilehash: 15c2d54c6281369875d15985c9d4ed16f0114176
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072249"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="345ed-103">Validera inställningar för enhetsskydd på PC-datorer med Windows 10</span><span class="sxs-lookup"><span data-stu-id="345ed-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="345ed-104">Kontrollera att principer för Windows 10-enheter har angetts</span><span class="sxs-lookup"><span data-stu-id="345ed-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="345ed-p101">När du [konfigurerat principer för enheter](protection-settings-for-windows-10-pcs.md) kan det ta några timmar innan principen börjar gälla på användarnas enheter. Du kan bekräfta att principerna har verkställts genom att titta på olika skärmar för Windows-inställningar på användarnas enheter. Eftersom användarna inte kan ändra inställningarna för Windows Update och Windows Defender Antivirus på sina Windows 10-enheter kommer många av de här alternativen vara nedtonade.</span><span class="sxs-lookup"><span data-stu-id="345ed-p101">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices. You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices. Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, a lot of those options will be greyed out.</span></span>
  
1. <span data-ttu-id="345ed-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span><span class="sxs-lookup"><span data-stu-id="345ed-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span></span> 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="345ed-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span><span class="sxs-lookup"><span data-stu-id="345ed-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span></span> 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="345ed-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="345ed-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="345ed-113">Bekräfta att du kan se meddelandet (i rött) om att vissa inställningar är dolda eller hanteras av din organisation och att alla alternativ är nedtonade.</span><span class="sxs-lookup"><span data-stu-id="345ed-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are greyed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="345ed-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="345ed-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="345ed-116">Kontrollera att alla alternativ är nedtonade.</span><span class="sxs-lookup"><span data-stu-id="345ed-116">Verify that all options are greyed out.</span></span> 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="345ed-118">Närliggande information</span><span class="sxs-lookup"><span data-stu-id="345ed-118">Related Topics</span></span>

[<span data-ttu-id="345ed-119">Dokumentation och resurser för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="345ed-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="345ed-120">Komma igång med Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="345ed-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="345ed-121">Hantera Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="345ed-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="345ed-122">Ange enhetskonfigurationer för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="345ed-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

