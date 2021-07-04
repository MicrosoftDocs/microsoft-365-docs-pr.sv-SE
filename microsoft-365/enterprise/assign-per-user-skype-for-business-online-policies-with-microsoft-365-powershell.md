---
title: Tilldela principer per användare Skype för företag Online-principer med PowerShell för Microsoft 365
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
description: Sammanfattning Använd PowerShell för att Microsoft 365 tilldela kommunikationsinställningar per användare med hjälp Skype för företag onlineprinciper.
ms.openlocfilehash: d7f369e96f3db95c741e6d4f2178eaf9032ab0bb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288089"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="a1ff4-103">Tilldela principer per användare Skype för företag Online-principer med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1ff4-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="a1ff4-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a1ff4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a1ff4-105">Att använda PowerShell för Microsoft 365 är ett effektivt sätt att tilldela kommunikationsinställningar per användare med Skype för företag Online-principer.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="a1ff4-106">Förbereda för att köra PowerShell-kommandon</span><span class="sxs-lookup"><span data-stu-id="a1ff4-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="a1ff4-107">Använd de här anvisningarna för att konfigurera om du vill köra kommandona (hoppa över de steg som redan är slutförda):</span><span class="sxs-lookup"><span data-stu-id="a1ff4-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
  > [!Note]
   > <span data-ttu-id="a1ff4-108">Skype för företag – Online-Connector är för närvarande en del av den senaste versionen av Teams PowerShell-modul.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="a1ff4-109">Om du använder den senaste versionen av Teams PowerShell, behöver du inte installera Skype för företag – Online-Connector.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="a1ff4-110">Installera [Teams PowerShell-modul](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="a1ff4-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="a1ff4-111">Öppna en Windows PowerShell kommandotolk och kör följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="a1ff4-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   <span data-ttu-id="a1ff4-112">När du uppmanas till det anger Skype för företag onlineadministratörens kontonamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="a1ff4-113">Uppdatera inställningar för extern kommunikation för ett användarkonto</span><span class="sxs-lookup"><span data-stu-id="a1ff4-113">Updating external communication settings for a user account</span></span>

<span data-ttu-id="a1ff4-114">Anta att du vill ändra inställningarna för extern kommunikation för ett användarkonto.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-114">Suppose you want to change external communication settings on a user account.</span></span> <span data-ttu-id="a1ff4-115">Du vill till exempel tillåta att Alex kommunicerar med externa användare (EnableFederationAccess är lika med Sant) men inte med Windows Live-användare (EnablePublicCloudAccess är lika med False).</span><span class="sxs-lookup"><span data-stu-id="a1ff4-115">For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False).</span></span> <span data-ttu-id="a1ff4-116">För att göra det måste du göra två saker:</span><span class="sxs-lookup"><span data-stu-id="a1ff4-116">To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="a1ff4-117">Hitta en princip för extern åtkomst som uppfyller våra villkor.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-117">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="a1ff4-118">Tilldela den externa åtkomstprincipen till Alex.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-118">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="a1ff4-119">Hur tar du reda på vilken princip för extern åtkomst som ska tilldela Alex?</span><span class="sxs-lookup"><span data-stu-id="a1ff4-119">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="a1ff4-120">Följande kommando returnerar alla principer för extern åtkomst där EnableFederationAccess är inställd på Sant och EnablePublicCloudAccess är inställt på False:</span><span class="sxs-lookup"><span data-stu-id="a1ff4-120">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="a1ff4-121">Om du inte har skapat några anpassade instanser av ExternalAccessPolicy, returnerar det kommandot en princip som uppfyller våra villkor (FederationOnly).</span><span class="sxs-lookup"><span data-stu-id="a1ff4-121">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="a1ff4-122">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="a1ff4-122">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="a1ff4-123">Nu när du vet vilken princip som ska tilldelas till Alex kan vi tilldela den principen med hjälp av cmdleten [Grant-CsExternalAccessPolicy.](/powershell/module/skype/Get-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="a1ff4-123">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) cmdlet.</span></span> <span data-ttu-id="a1ff4-124">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="a1ff4-124">Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="a1ff4-125">Det är ganska enkelt att tilldela en princip: du anger bara identiteten för användaren och namnet på principen som ska tilldelas.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-125">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="a1ff4-126">När det gäller principer och policytilldelningar är du inte begränsad till att arbeta med användarkonton en i taget.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-126">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time.</span></span> <span data-ttu-id="a1ff4-127">Anta till exempel att du behöver en lista över alla användare som tillåts kommunicera med externa partner och med Windows Live-användare.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-127">For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users.</span></span> <span data-ttu-id="a1ff4-128">Vi vet redan att dessa användare har tilldelats policyn FederationAndPICDefault för externa användare.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-128">We already know that those users have been assigned the external user access policy FederationAndPICDefault.</span></span> <span data-ttu-id="a1ff4-129">Eftersom vi vet det kan du visa en lista över alla dessa användare genom att köra ett enkelt kommando.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-129">Because we know that, you can display a list of all those users by running one simple command.</span></span> <span data-ttu-id="a1ff4-130">Här är kommandot:</span><span class="sxs-lookup"><span data-stu-id="a1ff4-130">Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="a1ff4-131">Med andra ord, visa oss alla användare där egenskapen ExternalAccessPolicy är inställd på FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-131">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault.</span></span> <span data-ttu-id="a1ff4-132">(För att begränsa mängden information som visas på skärmen kan du använda cmdleten Select-Object för att visa endast användarnas visningsnamn.)</span><span class="sxs-lookup"><span data-stu-id="a1ff4-132">(And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="a1ff4-133">Använd det här kommandot om du vill konfigurera alla våra användarkonton att använda samma princip:</span><span class="sxs-lookup"><span data-stu-id="a1ff4-133">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="a1ff4-134">Det här kommandot använder Get-CsOnlineUser för att returnera en samling av alla användare som har aktiverats för Lync. Sedan skickas all den informationen till Grant-CsExternalAccessPolicy, som tilldelar principen FederationAndPICDefault till varje användare i samlingen.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-134">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="a1ff4-135">Anta att du tidigare har tilldelat Alex policyn FederationAndPICDefault och nu har du ändrat dig och vill att han ska hanteras av den globala policyn för extern åtkomst.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-135">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="a1ff4-136">Du kan inte uttryckligen tilldela global princip till någon.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-136">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="a1ff4-137">Den globala principen används istället för en viss användare om ingen princip per användare tilldelas till den användaren.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-137">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="a1ff4-138">Om vi därför vill att Alex ska hanteras av  den globala principen måste du ta bort alla policyer per användare som tidigare tilldelats till honom.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-138">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="a1ff4-139">Här är ett exempelkommando:</span><span class="sxs-lookup"><span data-stu-id="a1ff4-139">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="a1ff4-140">Det här kommandot anger namnet på principen för extern åtkomst som tilldelats Alex till ett nullvärde ($Null).</span><span class="sxs-lookup"><span data-stu-id="a1ff4-140">This command sets the name of the external access policy assigned to Alex to a null value ($Null).</span></span> <span data-ttu-id="a1ff4-141">Null innebär "inget".</span><span class="sxs-lookup"><span data-stu-id="a1ff4-141">Null means "nothing".</span></span> <span data-ttu-id="a1ff4-142">Med andra ord har ingen policy för extern åtkomst tilldelats till Alex.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-142">In other words, no external access policy is assigned to Alex.</span></span> <span data-ttu-id="a1ff4-143">När ingen princip för extern åtkomst är tilldelad till en användare hanteras den användaren av den globala principen.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-143">When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="a1ff4-144">Hantera stora antal användare</span><span class="sxs-lookup"><span data-stu-id="a1ff4-144">Managing large numbers of users</span></span>

<span data-ttu-id="a1ff4-145">Om du vill hantera stora antal användare (1 000 eller fler) måste du batcha kommandona via ett skriptblock med cmdleten [Invoke-Command.](/powershell/module/microsoft.powershell.core/invoke-command)</span><span class="sxs-lookup"><span data-stu-id="a1ff4-145">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>  <span data-ttu-id="a1ff4-146">I tidigare exempel måste samtalet konfigureras varje gång en cmdlet körs och sedan vänta på resultatet innan det skickas tillbaka.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-146">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="a1ff4-147">När du använder ett skriptblock gör detta att cmdlet:arna kan köras på distans och när de har slutförts kan du skicka tillbaka data.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-147">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span>

```powershell
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

<span data-ttu-id="a1ff4-148">Då hittar du 500 användare i taget som inte har någon klientprincip.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-148">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="a1ff4-149">Det ger dem klientprincipen "ClientPolicyNoIMURL" och principen för extern åtkomst "FederationAndPicDefault".</span><span class="sxs-lookup"><span data-stu-id="a1ff4-149">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="a1ff4-150">Resultatet grupperas i grupper om 50 och varje batch på 50 skickas sedan till fjärrdatorn.</span><span class="sxs-lookup"><span data-stu-id="a1ff4-150">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a1ff4-151">Se även</span><span class="sxs-lookup"><span data-stu-id="a1ff4-151">See also</span></span>

[<span data-ttu-id="a1ff4-152">Hantera Skype för företag – Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1ff4-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a1ff4-153">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1ff4-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a1ff4-154">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1ff4-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)