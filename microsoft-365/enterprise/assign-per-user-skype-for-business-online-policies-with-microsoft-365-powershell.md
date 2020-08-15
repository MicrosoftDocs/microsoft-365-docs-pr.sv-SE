---
title: Tilldela principer för Skype för företag – Online med PowerShell för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 'Sammanfattning: Använd PowerShell för Microsoft 365 för att tilldela inställningar för kommunikation per användare med principer för Skype för företag – online.'
ms.openlocfilehash: 6ff9fce3e0287313f6725b370b6ba89cb939eb3a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694563"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="b40dd-103">Tilldela principer för Skype för företag – Online med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b40dd-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="b40dd-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b40dd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b40dd-105">Att använda PowerShell för Microsoft 365 är ett effektivt sätt att tilldela användar inställningar för enskilda användare med principer för Skype för företag – online.</span><span class="sxs-lookup"><span data-stu-id="b40dd-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="b40dd-106">Förbereda för att köra PowerShell-kommandon</span><span class="sxs-lookup"><span data-stu-id="b40dd-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="b40dd-107">Använd dessa instruktioner för att komma igång med kommandona (hoppa över stegen som du redan har slutfört):</span><span class="sxs-lookup"><span data-stu-id="b40dd-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
1. <span data-ttu-id="b40dd-108">Ladda ned och installera [kopplingen för Skype för företag – Online](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="b40dd-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
    
2. <span data-ttu-id="b40dd-109">Öppna en Windows PowerShell-kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="b40dd-109">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
```powershell
Import-Module LyncOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

<span data-ttu-id="b40dd-110">Skriv in namnet och lösen ordet för Skype för företag – Online när du uppmanas till det.</span><span class="sxs-lookup"><span data-stu-id="b40dd-110">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="b40dd-111">Uppdatera inställningar för extern kommunikation för ett användar konto</span><span class="sxs-lookup"><span data-stu-id="b40dd-111">Updating external communication settings for a user account</span></span>

<span data-ttu-id="b40dd-112">Anta att du vill ändra inställningar för extern kommunikation för ett användar konto.</span><span class="sxs-lookup"><span data-stu-id="b40dd-112">Suppose you want to change external communication settings on a user account.</span></span> <span data-ttu-id="b40dd-113">Du vill till exempel tillåta att Alex kommunicerar med externa användare (EnableFederationAccess är lika med sant) men inte med Windows Live-användare (EnablePublicCloudAccess är lika med falskt).</span><span class="sxs-lookup"><span data-stu-id="b40dd-113">For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False).</span></span> <span data-ttu-id="b40dd-114">För att göra det måste du göra två saker:</span><span class="sxs-lookup"><span data-stu-id="b40dd-114">To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="b40dd-115">Hitta en extern åtkomst policy som uppfyller våra villkor.</span><span class="sxs-lookup"><span data-stu-id="b40dd-115">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="b40dd-116">Tilldela den externa åtkomst principen till Alex.</span><span class="sxs-lookup"><span data-stu-id="b40dd-116">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="b40dd-117">Hur avgör du vilken extern åtkomst princip som ska tilldelas Alex?</span><span class="sxs-lookup"><span data-stu-id="b40dd-117">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="b40dd-118">Följande kommando returnerar alla externa åtkomst principer där EnableFederationAccess är inställt på True och EnablePublicCloudAccess är inställt på false:</span><span class="sxs-lookup"><span data-stu-id="b40dd-118">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="b40dd-119">Om du inte har skapat några anpassade instanser av ExternalAccessPolicy returnerar det en princip som uppfyller våra villkor (FederationOnly).</span><span class="sxs-lookup"><span data-stu-id="b40dd-119">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="b40dd-120">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="b40dd-120">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="b40dd-121">Nu när du vet vilken princip som ska tilldelas Alex kan vi tilldela principen genom att använda cmdleten [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) .</span><span class="sxs-lookup"><span data-stu-id="b40dd-121">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) cmdlet.</span></span> <span data-ttu-id="b40dd-122">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="b40dd-122">Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="b40dd-123">Det är ganska enkelt att tilldela en policy: du anger bara användarens identitet och namnet på den princip som ska tilldelas.</span><span class="sxs-lookup"><span data-stu-id="b40dd-123">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="b40dd-124">Och när det gäller principer och policy tilldelningar är du inte begränsad till att arbeta med användar konton en gång.</span><span class="sxs-lookup"><span data-stu-id="b40dd-124">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time.</span></span> <span data-ttu-id="b40dd-125">Anta till exempel att du behöver en lista över alla användare som får kommunicera med federerade partners och med Windows Live-användare.</span><span class="sxs-lookup"><span data-stu-id="b40dd-125">For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users.</span></span> <span data-ttu-id="b40dd-126">Vi vet redan att dessa användare har tilldelats FederationAndPICDefault för principer för extern användar åtkomst.</span><span class="sxs-lookup"><span data-stu-id="b40dd-126">We already know that those users have been assigned the external user access policy FederationAndPICDefault.</span></span> <span data-ttu-id="b40dd-127">Eftersom vi vet att du kan visa en lista över alla dessa användare genom att köra ett enkelt kommando.</span><span class="sxs-lookup"><span data-stu-id="b40dd-127">Because we know that, you can display a list of all those users by running one simple command.</span></span> <span data-ttu-id="b40dd-128">Här är kommandot:</span><span class="sxs-lookup"><span data-stu-id="b40dd-128">Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="b40dd-129">Visa alla användare där egenskapen ExternalAccessPolicy är inställd på FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="b40dd-129">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault.</span></span> <span data-ttu-id="b40dd-130">(Om du vill begränsa hur mycket information som visas på skärmen kan du använda cmdleten Select-Object för att visa endast Visa amerikansk användares visnings namn.)</span><span class="sxs-lookup"><span data-stu-id="b40dd-130">(And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="b40dd-131">Använd det här kommandot för att konfigurera alla våra användar konton så att de använder samma princip:</span><span class="sxs-lookup"><span data-stu-id="b40dd-131">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="b40dd-132">Det här kommandot använder Get-CsOnlineUser för att returnera en samling med alla användare som har Aktiver ATS för Lync och skickar sedan all den informationen till Grant-CsExternalAccessPolicy, som tilldelar alla användare i samlingen en FederationAndPICDefault-princip.</span><span class="sxs-lookup"><span data-stu-id="b40dd-132">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="b40dd-133">Anta att du tidigare har tilldelat Alex FederationAndPICDefault policy och nu har ändrat dig och vill att han ska hanteras av den globala principen för extern åtkomst.</span><span class="sxs-lookup"><span data-stu-id="b40dd-133">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="b40dd-134">Du kan inte uttryckligen koppla den globala principen till vem som helst.</span><span class="sxs-lookup"><span data-stu-id="b40dd-134">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="b40dd-135">Istället används den globala principen för en viss användare om ingen princip för användare har tilldelats till användaren.</span><span class="sxs-lookup"><span data-stu-id="b40dd-135">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="b40dd-136">Om vi vill att Alex ska hanteras av den globala policyn måste du därför  *ta bort tilldelningen*  för alla användare som tidigare tilldelats till honom.</span><span class="sxs-lookup"><span data-stu-id="b40dd-136">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="b40dd-137">Här är ett exempel kommando:</span><span class="sxs-lookup"><span data-stu-id="b40dd-137">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="b40dd-138">Det här kommandot anger namnet på den externa åtkomst principen som tilldelats till Alex till ett null-värde ($Null).</span><span class="sxs-lookup"><span data-stu-id="b40dd-138">This command sets the name of the external access policy assigned to Alex to a null value ($Null).</span></span> <span data-ttu-id="b40dd-139">Null betyder "inget".</span><span class="sxs-lookup"><span data-stu-id="b40dd-139">Null means "nothing".</span></span> <span data-ttu-id="b40dd-140">Ingen extern åtkomst policy är kopplad till Alex.</span><span class="sxs-lookup"><span data-stu-id="b40dd-140">In other words, no external access policy is assigned to Alex.</span></span> <span data-ttu-id="b40dd-141">När ingen extern åtkomst policy har tilldelats till en användare hanteras den av den globala principen.</span><span class="sxs-lookup"><span data-stu-id="b40dd-141">When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>
  

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="b40dd-142">Hantera många användare</span><span class="sxs-lookup"><span data-stu-id="b40dd-142">Managing large numbers of users</span></span>

<span data-ttu-id="b40dd-143">Om du vill hantera många användare (1000 eller mer) måste du först gruppera kommandona via ett skript block med cmdleten [Invoke-kommando](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) .</span><span class="sxs-lookup"><span data-stu-id="b40dd-143">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) cmdlet.</span></span>  <span data-ttu-id="b40dd-144">I tidigare exempel körs en cmdlet för att aktivera samtalet och sedan vänta tills det blir tillbaka.</span><span class="sxs-lookup"><span data-stu-id="b40dd-144">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="b40dd-145">När du använder ett skript block kan du använda cmdlets för fjärr anslutning och när det är slutfört skicka data tillbaka.</span><span class="sxs-lookup"><span data-stu-id="b40dd-145">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span> 

```powershell
Import-Module LyncOnlineConnector
$sfbSession = New-CsOnlineSession
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

<span data-ttu-id="b40dd-146">Detta hittar 500-användare åt gången som inte har någon klient policy.</span><span class="sxs-lookup"><span data-stu-id="b40dd-146">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="b40dd-147">Den får klient principen "ClientPolicyNoIMURL" och den externa åtkomst principen "FederationAndPicDefault".</span><span class="sxs-lookup"><span data-stu-id="b40dd-147">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="b40dd-148">Resultaten grupperas i 50 och varje sats i 50 skickas till fjärrdatorn.</span><span class="sxs-lookup"><span data-stu-id="b40dd-148">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b40dd-149">Se även</span><span class="sxs-lookup"><span data-stu-id="b40dd-149">See also</span></span>

[<span data-ttu-id="b40dd-150">Hantera Skype för företag – Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="b40dd-150">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b40dd-151">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="b40dd-151">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b40dd-152">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b40dd-152">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
