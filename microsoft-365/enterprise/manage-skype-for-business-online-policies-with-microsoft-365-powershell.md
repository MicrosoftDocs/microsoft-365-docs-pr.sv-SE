---
title: Hantera Skype för företag – Onlineprinciper med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 'Sammanfattning: Använd PowerShell för att hantera dina användar konto egenskaper för Skype för företag – Online med principer.'
ms.openlocfilehash: 20a75fa1c131f693fcf30d20477af5c9ee7aed35
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477047"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="e2a21-103">Hantera Skype för företag – Onlineprinciper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2a21-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="e2a21-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e2a21-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e2a21-105">För att hantera många egenskaper för användar konto för Skype för företag – Online måste du ange dem som egenskaper för principer med PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2a21-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="e2a21-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="e2a21-106">Before you begin</span></span>

<span data-ttu-id="e2a21-107">Använd dessa instruktioner för att komma igång med kommandona (hoppa över stegen som du redan har slutfört):</span><span class="sxs-lookup"><span data-stu-id="e2a21-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="e2a21-108">Connector för Skype för företag – Online är nu en del av den senaste Teams PowerShell-modulen.</span><span class="sxs-lookup"><span data-stu-id="e2a21-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="e2a21-109">Om du använder den senaste Teams-versionen för att använda det här alternativet behöver du inte installera Skype för företag – Online-anslutaren.</span><span class="sxs-lookup"><span data-stu-id="e2a21-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="e2a21-110">Installera [modulen för moduler i PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="e2a21-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="e2a21-111">Öppna en Windows PowerShell kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="e2a21-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

   <span data-ttu-id="e2a21-112">Skriv in namnet och lösen ordet för Skype för företag – Online när du uppmanas till det.</span><span class="sxs-lookup"><span data-stu-id="e2a21-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="e2a21-113">Hantera principer för användar konton</span><span class="sxs-lookup"><span data-stu-id="e2a21-113">Manage user account policies</span></span>

<span data-ttu-id="e2a21-114">Många användar konto egenskaper för Skype för företag – Online konfigureras med hjälp av principer.</span><span class="sxs-lookup"><span data-stu-id="e2a21-114">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="e2a21-115">Principer är helt enkelt samlingar av inställningar som kan tillämpas på en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="e2a21-115">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="e2a21-116">Om du vill ta en titt på hur en princip har kon figurer ATS kan du köra det här exemplet på FederationAndPICDefault princip:</span><span class="sxs-lookup"><span data-stu-id="e2a21-116">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="e2a21-117">I sin tur bör du få tillbaka något liknande det här:</span><span class="sxs-lookup"><span data-stu-id="e2a21-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="e2a21-118">I det här exemplet bestämmer värdena i den här principen vad en användning kan eller inte kan göra när det gäller kommunikation med externa användare.</span><span class="sxs-lookup"><span data-stu-id="e2a21-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="e2a21-119">Till exempel måste egenskapen EnableOutsideAccess vara angiven till true för att en användare ska kunna kommunicera med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="e2a21-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="e2a21-120">Observera att den här egenskapen inte visas i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2a21-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e2a21-121">I stället anges egenskapen automatiskt till true eller false utifrån de andra val du gör.</span><span class="sxs-lookup"><span data-stu-id="e2a21-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="e2a21-122">De andra två intresse egenskaperna är:</span><span class="sxs-lookup"><span data-stu-id="e2a21-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="e2a21-123">**EnableFederationAccess** anger om användaren kan kommunicera med personer från federerade domäner.</span><span class="sxs-lookup"><span data-stu-id="e2a21-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="e2a21-124">**EnablePublicCloudAccess** anger om användaren kan kommunicera med Windows Live-användare.</span><span class="sxs-lookup"><span data-stu-id="e2a21-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="e2a21-125">Därför behöver du inte direkt ändra egenskaperna för ett närstående konto för användar konton (till exempel **set-CsUser-EnableFederationAccess $True**).</span><span class="sxs-lookup"><span data-stu-id="e2a21-125">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="e2a21-126">Istället tilldelar du ett konto en extern åtkomst princip med de önskade egenskaps värdena förkonfigurerade.</span><span class="sxs-lookup"><span data-stu-id="e2a21-126">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="e2a21-127">Om vi vill att en användare ska kunna kommunicera med externa användare och med Windows Live-användare måste användar kontot ha tilldelats en princip som tillåter dessa typer av kommunikation.</span><span class="sxs-lookup"><span data-stu-id="e2a21-127">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="e2a21-128">Om du vill veta om någon kan kommunicera med användare utanför organisationen måste du:</span><span class="sxs-lookup"><span data-stu-id="e2a21-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="e2a21-129">Avgöra vilken extern åtkomst policy som har tilldelats till användaren.</span><span class="sxs-lookup"><span data-stu-id="e2a21-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="e2a21-130">Avgöra vilka funktioner som är tillåtna eller inte av den policyn.</span><span class="sxs-lookup"><span data-stu-id="e2a21-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="e2a21-131">Du kan till exempel göra det genom att använda det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="e2a21-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="e2a21-132">Det här kommandot hittar den princip som är tilldelad användaren och hittar sedan funktionerna aktiverade eller inaktiverade i principen.</span><span class="sxs-lookup"><span data-stu-id="e2a21-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="e2a21-133">Information om hur du hanterar principer för Skype för företag – Online med PowerShell finns i cmdletar för:</span><span class="sxs-lookup"><span data-stu-id="e2a21-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="e2a21-134">[Klient princip](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="e2a21-134">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="e2a21-135">[Konferens policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="e2a21-135">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="e2a21-136">[Mobil policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="e2a21-136">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="e2a21-137">[Sekretess policy online](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="e2a21-137">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="e2a21-138">[Policy för Röstträning](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="e2a21-138">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="e2a21-139">Ett uppringnings abonnemang för Skype för företag – Online är en policy i alla avseenden förutom namnet.</span><span class="sxs-lookup"><span data-stu-id="e2a21-139">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="e2a21-140">Namnet "uppringnings plan" valdes i stället för "uppringnings princip" för att ge bakåtkompatibilitet med Office Communications Server och med Exchange.</span><span class="sxs-lookup"><span data-stu-id="e2a21-140">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="e2a21-141">Om du till exempel vill visa alla tillgängliga röst principer för användning kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="e2a21-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="e2a21-142">Det returnerar en lista över alla tillgängliga röst principer.</span><span class="sxs-lookup"><span data-stu-id="e2a21-142">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="e2a21-143">Kom ihåg att alla användare inte kan kopplas till alla principer.</span><span class="sxs-lookup"><span data-stu-id="e2a21-143">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="e2a21-144">Detta beror på olika begränsningar avseende licensiering och geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="e2a21-144">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="e2a21-145">(Den s.k. "[användnings plats](https://msdn.microsoft.com/library/azure/dn194136.aspx).") Om du vill veta vilka externa åtkomst principer och konferens principer som kan kopplas till en viss användare använder du kommandon som liknar dessa:</span><span class="sxs-lookup"><span data-stu-id="e2a21-145">(The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="e2a21-146">Parametern ApplicableTo begränsar den returnerade informationen till principer som kan tilldelas till den angivna användaren (till exempel Alex Darrow).</span><span class="sxs-lookup"><span data-stu-id="e2a21-146">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow).</span></span> <span data-ttu-id="e2a21-147">Beroende på plats begränsningar för licenser och användnings områden kan det representera en delmängd av alla tillgängliga principer.</span><span class="sxs-lookup"><span data-stu-id="e2a21-147">Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="e2a21-148">I vissa fall används inte egenskaper för principer med Microsoft 365, medan andra endast kan hanteras av Microsofts support personal.</span><span class="sxs-lookup"><span data-stu-id="e2a21-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="e2a21-149">Med Skype för företag – Online måste användarna hanteras av en princip av något slag.</span><span class="sxs-lookup"><span data-stu-id="e2a21-149">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="e2a21-150">Om en giltig principbaserad egenskap är tom innebär det att användaren hanteras av en global princip, vilket är en princip som automatiskt tillämpas på en användare såvida inte han eller hon tilldelats en princip per användare.</span><span class="sxs-lookup"><span data-stu-id="e2a21-150">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="e2a21-151">Eftersom en klient princip inte visas för ett användar konto hanteras den av den globala principen.</span><span class="sxs-lookup"><span data-stu-id="e2a21-151">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="e2a21-152">Du kan bestämma den globala klient principen med det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="e2a21-152">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="e2a21-153">Se även</span><span class="sxs-lookup"><span data-stu-id="e2a21-153">See also</span></span>

[<span data-ttu-id="e2a21-154">Hantera Skype för företag – Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2a21-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e2a21-155">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2a21-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e2a21-156">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e2a21-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

