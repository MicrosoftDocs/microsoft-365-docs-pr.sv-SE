---
title: Hantera principer för Skype för företag – Online med PowerShell
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
ms.openlocfilehash: 7657dae6fa1b27299e4cbc0cf6a311380cb90e9e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694774"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="1dd9e-103">Hantera principer för Skype för företag – Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1dd9e-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="1dd9e-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1dd9e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1dd9e-105">För att hantera många egenskaper för användar konto för Skype för företag – Online måste du ange dem som egenskaper för principer med PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="1dd9e-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="1dd9e-106">Before you begin</span></span>

<span data-ttu-id="1dd9e-107">Använd dessa instruktioner för att komma igång med kommandona (hoppa över stegen som du redan har slutfört):</span><span class="sxs-lookup"><span data-stu-id="1dd9e-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
1. <span data-ttu-id="1dd9e-108">Ladda ned och installera [kopplingen för Skype för företag – Online](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="1dd9e-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
    
2. <span data-ttu-id="1dd9e-109">Öppna en Windows PowerShell-kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="1dd9e-109">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
  ```

<span data-ttu-id="1dd9e-110">Skriv in namnet och lösen ordet för Skype för företag – Online när du uppmanas till det.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-110">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="1dd9e-111">Hantera principer för användar konton</span><span class="sxs-lookup"><span data-stu-id="1dd9e-111">Manage user account policies</span></span>

<span data-ttu-id="1dd9e-112">Många användar konto egenskaper för Skype för företag – Online konfigureras med hjälp av principer.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-112">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="1dd9e-113">Principer är helt enkelt samlingar av inställningar som kan tillämpas på en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-113">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="1dd9e-114">Om du vill ta en titt på hur en princip har kon figurer ATS kan du köra det här exemplet på FederationAndPICDefault princip:</span><span class="sxs-lookup"><span data-stu-id="1dd9e-114">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="1dd9e-115">I sin tur bör du få tillbaka något liknande det här:</span><span class="sxs-lookup"><span data-stu-id="1dd9e-115">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="1dd9e-116">I det här exemplet bestämmer värdena i den här principen vad en användning kan eller inte kan göra när det gäller kommunikation med externa användare.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-116">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="1dd9e-117">Till exempel måste egenskapen EnableOutsideAccess vara angiven till true för att en användare ska kunna kommunicera med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-117">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="1dd9e-118">Observera att den här egenskapen inte visas i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-118">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1dd9e-119">I stället anges egenskapen automatiskt till true eller false utifrån de andra val du gör.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-119">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="1dd9e-120">De andra två intresse egenskaperna är:</span><span class="sxs-lookup"><span data-stu-id="1dd9e-120">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="1dd9e-121">**EnableFederationAccess** anger om användaren kan kommunicera med personer från federerade domäner.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-121">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="1dd9e-122">**EnablePublicCloudAccess** anger om användaren kan kommunicera med Windows Live-användare.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-122">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="1dd9e-123">Därför behöver du inte direkt ändra egenskaperna för ett närstående konto för användar konton (till exempel **set-CsUser-EnableFederationAccess $True**).</span><span class="sxs-lookup"><span data-stu-id="1dd9e-123">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="1dd9e-124">Istället tilldelar du ett konto en extern åtkomst princip med de önskade egenskaps värdena förkonfigurerade.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-124">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="1dd9e-125">Om vi vill att en användare ska kunna kommunicera med externa användare och med Windows Live-användare måste användar kontot ha tilldelats en princip som tillåter dessa typer av kommunikation.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-125">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="1dd9e-126">Om du vill veta om någon kan kommunicera med användare utanför organisationen måste du:</span><span class="sxs-lookup"><span data-stu-id="1dd9e-126">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="1dd9e-127">Avgöra vilken extern åtkomst policy som har tilldelats till användaren.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-127">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="1dd9e-128">Avgöra vilka funktioner som är tillåtna eller inte av den policyn.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-128">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="1dd9e-129">Du kan till exempel göra det genom att använda det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="1dd9e-129">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="1dd9e-130">Det här kommandot hittar den princip som är tilldelad användaren och hittar sedan funktionerna aktiverade eller inaktiverade i principen.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-130">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="1dd9e-131">Information om hur du hanterar principer för Skype för företag – Online med PowerShell finns i cmdletar för:</span><span class="sxs-lookup"><span data-stu-id="1dd9e-131">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="1dd9e-132">[Klient princip](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="1dd9e-132">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="1dd9e-133">[Konferens policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="1dd9e-133">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="1dd9e-134">[Mobil policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="1dd9e-134">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="1dd9e-135">[Sekretess policy online](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="1dd9e-135">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="1dd9e-136">[Policy för Röstträning](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="1dd9e-136">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="1dd9e-137">Ett uppringnings abonnemang för Skype för företag – Online är en policy i alla avseenden förutom namnet.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-137">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="1dd9e-138">Namnet "uppringnings plan" valdes i stället för "uppringnings princip" för att ge bakåtkompatibilitet med Office Communications Server och med Exchange.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-138">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="1dd9e-139">Om du till exempel vill visa alla tillgängliga röst principer för användning kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="1dd9e-139">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="1dd9e-140">Det returnerar en lista över alla tillgängliga röst principer.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-140">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="1dd9e-141">Kom ihåg att alla användare inte kan kopplas till alla principer.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-141">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="1dd9e-142">Detta beror på olika begränsningar avseende licensiering och geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-142">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="1dd9e-143">(Den s.k. "[användnings plats](https://msdn.microsoft.com/library/azure/dn194136.aspx).") Om du vill veta vilka externa åtkomst principer och konferens principer som kan kopplas till en viss användare använder du kommandon som liknar dessa:</span><span class="sxs-lookup"><span data-stu-id="1dd9e-143">(The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="1dd9e-144">Parametern ApplicableTo begränsar den returnerade informationen till principer som kan tilldelas till den angivna användaren (till exempel Alex Darrow).</span><span class="sxs-lookup"><span data-stu-id="1dd9e-144">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow).</span></span> <span data-ttu-id="1dd9e-145">Beroende på plats begränsningar för licenser och användnings områden kan det representera en delmängd av alla tillgängliga principer.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-145">Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="1dd9e-146">I vissa fall används inte egenskaper för principer med Microsoft 365, medan andra endast kan hanteras av Microsofts support personal.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-146">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="1dd9e-147">Med Skype för företag – Online måste användarna hanteras av en princip av något slag.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-147">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="1dd9e-148">Om en giltig principbaserad egenskap är tom innebär det att användaren hanteras av en global princip, vilket är en princip som automatiskt tillämpas på en användare såvida inte han eller hon tilldelats en princip per användare.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-148">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="1dd9e-149">Eftersom en klient princip inte visas för ett användar konto hanteras den av den globala principen.</span><span class="sxs-lookup"><span data-stu-id="1dd9e-149">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="1dd9e-150">Du kan bestämma den globala klient principen med det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="1dd9e-150">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="1dd9e-151">Se även</span><span class="sxs-lookup"><span data-stu-id="1dd9e-151">See also</span></span>

[<span data-ttu-id="1dd9e-152">Hantera Skype för företag – Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1dd9e-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1dd9e-153">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1dd9e-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1dd9e-154">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1dd9e-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

