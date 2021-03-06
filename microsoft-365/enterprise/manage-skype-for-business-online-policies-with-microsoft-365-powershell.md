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
description: 'Sammanfattning: Använd PowerShell för att hantera användarkontoegenskaper för Skype för företag – Online med principer.'
ms.openlocfilehash: ca945bc05e76525b4b2df6fb0b982a8468d87810
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515058"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="d77c2-103">Hantera Skype för företag – Onlineprinciper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="d77c2-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="d77c2-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d77c2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d77c2-105">Om du vill hantera många egenskaper för användarkonton för Skype för företag – Online måste du ange dem som egenskaper för principer med PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d77c2-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="d77c2-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="d77c2-106">Before you begin</span></span>

<span data-ttu-id="d77c2-107">Använd de här anvisningarna för att konfigurera att köra kommandona (hoppa över stegen som du redan har slutfört):</span><span class="sxs-lookup"><span data-stu-id="d77c2-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="d77c2-108">Skype för företag – Online-Connector är för närvarande en del av den senaste versionen av Teams PowerShell-modul.</span><span class="sxs-lookup"><span data-stu-id="d77c2-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="d77c2-109">Om du använder den senaste versionen av Teams PowerShell, behöver du inte installera Skype för företag – Online-Connector.</span><span class="sxs-lookup"><span data-stu-id="d77c2-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="d77c2-110">Installera [Teams PowerShell-modulen.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="d77c2-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="d77c2-111">Öppna en Windows PowerShell kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="d77c2-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   <span data-ttu-id="d77c2-112">När du uppmanas till det anger du ditt administratörskonto och lösenord för Skype för företag – Online.</span><span class="sxs-lookup"><span data-stu-id="d77c2-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="d77c2-113">Hantera principer för användarkonton</span><span class="sxs-lookup"><span data-stu-id="d77c2-113">Manage user account policies</span></span>

<span data-ttu-id="d77c2-114">Många användarkontoegenskaper för Skype för företag – Online konfigureras med hjälp av principer.</span><span class="sxs-lookup"><span data-stu-id="d77c2-114">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="d77c2-115">Principer är helt enkelt samlingar av inställningar som kan tillämpas på en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="d77c2-115">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="d77c2-116">Om du vill ta en titt på hur en princip har konfigurerats kan du köra det här exempelkommandot för FederationAndPICDefault-principen:</span><span class="sxs-lookup"><span data-stu-id="d77c2-116">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="d77c2-117">Du bör i sin tur få tillbaka något som liknar det här:</span><span class="sxs-lookup"><span data-stu-id="d77c2-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="d77c2-118">I det här exemplet avgör värdena i den här principen vad en användning kan eller inte göra när det gäller kommunikation med externa användare.</span><span class="sxs-lookup"><span data-stu-id="d77c2-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="d77c2-119">Egenskapen EnableOutsideAccess måste till exempel vara inställd på Sant för att en användare ska kunna kommunicera med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="d77c2-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="d77c2-120">Observera att den här egenskapen inte visas i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d77c2-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d77c2-121">I stället sätts egenskapen automatiskt till Sant eller Falskt baserat på andra val som du gör.</span><span class="sxs-lookup"><span data-stu-id="d77c2-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="d77c2-122">De andra två intressanta egenskaperna är:</span><span class="sxs-lookup"><span data-stu-id="d77c2-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="d77c2-123">**EnableFederationAccess** anger om användaren kan kommunicera med personer från federerade domäner.</span><span class="sxs-lookup"><span data-stu-id="d77c2-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="d77c2-124">**EnablePublicCloudAccess** anger om användaren kan kommunicera med Windows Live-användare.</span><span class="sxs-lookup"><span data-stu-id="d77c2-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="d77c2-125">Därför ändrar du inte direkt federationsrelaterade egenskaper på användarkonton (till exempel **Set-CsUser -EnableFederationAccess $True).**</span><span class="sxs-lookup"><span data-stu-id="d77c2-125">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="d77c2-126">I stället tilldelar du ett konto en princip för extern åtkomst som har förkonfigurerade önskade egenskapsvärden.</span><span class="sxs-lookup"><span data-stu-id="d77c2-126">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="d77c2-127">Om vi vill att en användare ska kunna kommunicera med externa användare och med Windows Live-användare måste det användarkontot tilldelas en princip som tillåter de typerna av kommunikation.</span><span class="sxs-lookup"><span data-stu-id="d77c2-127">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="d77c2-128">Om du vill veta om någon kan kommunicera med användare utanför organisationen måste du:</span><span class="sxs-lookup"><span data-stu-id="d77c2-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="d77c2-129">Avgör vilken extern åtkomstprincip som har tilldelats till den användaren.</span><span class="sxs-lookup"><span data-stu-id="d77c2-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="d77c2-130">Avgör vilka funktioner som tillåts eller inte tillåts av den principen.</span><span class="sxs-lookup"><span data-stu-id="d77c2-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="d77c2-131">Det kan du till exempel göra genom att använda det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="d77c2-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="d77c2-132">Det här kommandot hittar principen som tilldelats användaren och hittar sedan de funktioner som är aktiverade eller inaktiverade i den principen.</span><span class="sxs-lookup"><span data-stu-id="d77c2-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="d77c2-133">Mer information om hur du hanterar principer för Skype för företag – Online med PowerShell finns i cmdlet:arna för:</span><span class="sxs-lookup"><span data-stu-id="d77c2-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="d77c2-134">[Klientprincip](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="d77c2-134">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="d77c2-135">[Konferensprincip](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="d77c2-135">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="d77c2-136">[Mobilpolicy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="d77c2-136">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="d77c2-137">[Policy för röstbrevlåda online](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="d77c2-137">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="d77c2-138">[Princip för röstdirigering](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="d77c2-138">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="d77c2-139">En uppringningsplan för Skype för företag – Online är en princip i alla sammanhang utom namnet.</span><span class="sxs-lookup"><span data-stu-id="d77c2-139">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="d77c2-140">Namnet "uppringningsplan" har valts istället för "uppringningsprincip" för att ge bakåtkompatibilitet med Office Communications Server och Exchange.</span><span class="sxs-lookup"><span data-stu-id="d77c2-140">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="d77c2-141">Om du till exempel vill titta på alla tillgängliga röstprinciper för ditt bruk kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="d77c2-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="d77c2-142">Då visas en lista över alla tillgängliga röstprinciper.</span><span class="sxs-lookup"><span data-stu-id="d77c2-142">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="d77c2-143">Kom dock ihåg att alla principer inte kan tilldelas till alla användare.</span><span class="sxs-lookup"><span data-stu-id="d77c2-143">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="d77c2-144">Detta beror på olika begränsningar som innefattar licensiering och geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="d77c2-144">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="d77c2-145">(Den s.k.[användningsplatsen](https://msdn.microsoft.com/library/azure/dn194136.aspx).") Om du vill veta vilka principer för extern åtkomst och konferensprinciper som kan tilldelas en viss användare kan du använda kommandon som liknar dessa:</span><span class="sxs-lookup"><span data-stu-id="d77c2-145">(The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="d77c2-146">Parametern ApplicableTo begränsar returnerade data till principer som kan tilldelas till den angivna användaren (till exempel Alex Darrow).</span><span class="sxs-lookup"><span data-stu-id="d77c2-146">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow).</span></span> <span data-ttu-id="d77c2-147">Beroende på begränsningar för licensiering och användningsplats kan det representera en delmängd av alla tillgängliga principer.</span><span class="sxs-lookup"><span data-stu-id="d77c2-147">Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="d77c2-148">I vissa fall används inte principers egenskaper tillsammans med Microsoft 365, medan andra endast kan hanteras av Microsofts supportpersonal.</span><span class="sxs-lookup"><span data-stu-id="d77c2-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="d77c2-149">Med Skype för företag – Online måste användarna hanteras med någon sorts policy.</span><span class="sxs-lookup"><span data-stu-id="d77c2-149">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="d77c2-150">Om en giltig principrelaterad egenskap är tom innebär det att användaren i fråga hanteras av en global princip, vilket är en princip som tillämpas automatiskt på en användare såvida han eller hon inte specifikt har tilldelats en princip per användare.</span><span class="sxs-lookup"><span data-stu-id="d77c2-150">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="d77c2-151">Eftersom det inte finns en klientprincip för ett användarkonto hanteras den av den globala principen.</span><span class="sxs-lookup"><span data-stu-id="d77c2-151">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="d77c2-152">Du kan fastställa den globala klientprincipen med det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="d77c2-152">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="d77c2-153">Se även</span><span class="sxs-lookup"><span data-stu-id="d77c2-153">See also</span></span>

[<span data-ttu-id="d77c2-154">Hantera Skype för företag – Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="d77c2-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d77c2-155">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="d77c2-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d77c2-156">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d77c2-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

