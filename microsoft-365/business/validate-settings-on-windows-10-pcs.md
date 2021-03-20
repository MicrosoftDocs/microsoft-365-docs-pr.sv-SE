---
title: Bekräfta programskyddsinställningar på PC-datorer med Windows 10
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Läs om hur du kontrollerar att programskyddsinställningarna för Microsoft 365 för företag verkställde på användarnas Windows 10-enheter.
ms.openlocfilehash: ff99b3a4fce49aebdb5c72f51e46678a7821e186
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912423"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="5f31f-103">Validera inställningar för enhetsskydd på PC-datorer med Windows 10</span><span class="sxs-lookup"><span data-stu-id="5f31f-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="5f31f-104">Kontrollera att principer för Windows 10-enheter har angetts</span><span class="sxs-lookup"><span data-stu-id="5f31f-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="5f31f-105">När du [konfigurerat principer för enheter](protection-settings-for-windows-10-pcs.md) kan det ta några timmar innan principen börjar gälla på användarnas enheter.</span><span class="sxs-lookup"><span data-stu-id="5f31f-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="5f31f-106">Du kan bekräfta att principerna har verkställts genom att titta på olika skärmar för Windows-inställningar på användarnas enheter.</span><span class="sxs-lookup"><span data-stu-id="5f31f-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="5f31f-107">Eftersom användarna inte kan ändra inställningarna för Windows Update och Windows Defender Antivirus på sina Windows 10-enheter är många alternativ nedtonade.</span><span class="sxs-lookup"><span data-stu-id="5f31f-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="5f31f-108">Gå till **Inställningar Uppdatera** \> **säkerhet &amp; vid** \> **omstart** av Windows Update \>  och kontrollera att alla inställningar är nedtonade.</span><span class="sxs-lookup"><span data-stu-id="5f31f-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Alla alternativ för omstart är nedtonade.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="5f31f-110">Gå till **Inställningar** \> **Uppdatera &amp; säkerhetsinställningar** \> **i Windows Update** \> **–** avancerade alternativ och kontrollera att alla inställningar är nedtonade.</span><span class="sxs-lookup"><span data-stu-id="5f31f-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Alternativen för Avancerade uppdateringar i Windows är nedtonade.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="5f31f-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="5f31f-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="5f31f-113">Bekräfta att du kan se meddelandet (i rött) om att vissa inställningar är dolda eller hanteras av din organisation och att alla alternativ är nedtonade.</span><span class="sxs-lookup"><span data-stu-id="5f31f-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="5f31f-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="5f31f-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="5f31f-116">Kontrollera att alla alternativ är nedtonade.</span><span class="sxs-lookup"><span data-stu-id="5f31f-116">Verify that all options are grayed out.</span></span> 
    
    ![Inställningarna för skydd mot virus och hot är nedtonade.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="5f31f-118">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="5f31f-118">Related Topics</span></span>

[<span data-ttu-id="5f31f-119">Dokumentation och resurser för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="5f31f-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="5f31f-120">Komma igång med Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="5f31f-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="5f31f-121">Hantera Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="5f31f-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="5f31f-122">Ange enhetskonfigurationer för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="5f31f-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
