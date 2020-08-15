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
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>Tilldela principer för Skype för företag – Online med PowerShell för Microsoft 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Att använda PowerShell för Microsoft 365 är ett effektivt sätt att tilldela användar inställningar för enskilda användare med principer för Skype för företag – online.
  
## <a name="prepare-to-run-the-powershell-commands"></a>Förbereda för att köra PowerShell-kommandon

Använd dessa instruktioner för att komma igång med kommandona (hoppa över stegen som du redan har slutfört):
  
1. Ladda ned och installera [kopplingen för Skype för företag – Online](https://www.microsoft.com/download/details.aspx?id=39366).
    
2. Öppna en Windows PowerShell-kommandotolk och kör följande kommandon: 
    
```powershell
Import-Module LyncOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

Skriv in namnet och lösen ordet för Skype för företag – Online när du uppmanas till det.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>Uppdatera inställningar för extern kommunikation för ett användar konto

Anta att du vill ändra inställningar för extern kommunikation för ett användar konto. Du vill till exempel tillåta att Alex kommunicerar med externa användare (EnableFederationAccess är lika med sant) men inte med Windows Live-användare (EnablePublicCloudAccess är lika med falskt). För att göra det måste du göra två saker:
  
1. Hitta en extern åtkomst policy som uppfyller våra villkor.
    
2. Tilldela den externa åtkomst principen till Alex.
    
Hur avgör du vilken extern åtkomst princip som ska tilldelas Alex? Följande kommando returnerar alla externa åtkomst principer där EnableFederationAccess är inställt på True och EnablePublicCloudAccess är inställt på false:
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

Om du inte har skapat några anpassade instanser av ExternalAccessPolicy returnerar det en princip som uppfyller våra villkor (FederationOnly). Här är ett exempel:
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Nu när du vet vilken princip som ska tilldelas Alex kan vi tilldela principen genom att använda cmdleten [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) . Här är ett exempel:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

Det är ganska enkelt att tilldela en policy: du anger bara användarens identitet och namnet på den princip som ska tilldelas. 
  
Och när det gäller principer och policy tilldelningar är du inte begränsad till att arbeta med användar konton en gång. Anta till exempel att du behöver en lista över alla användare som får kommunicera med federerade partners och med Windows Live-användare. Vi vet redan att dessa användare har tilldelats FederationAndPICDefault för principer för extern användar åtkomst. Eftersom vi vet att du kan visa en lista över alla dessa användare genom att köra ett enkelt kommando. Här är kommandot:
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

Visa alla användare där egenskapen ExternalAccessPolicy är inställd på FederationAndPICDefault. (Om du vill begränsa hur mycket information som visas på skärmen kan du använda cmdleten Select-Object för att visa endast Visa amerikansk användares visnings namn.) 
  
Använd det här kommandot för att konfigurera alla våra användar konton så att de använder samma princip:
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

Det här kommandot använder Get-CsOnlineUser för att returnera en samling med alla användare som har Aktiver ATS för Lync och skickar sedan all den informationen till Grant-CsExternalAccessPolicy, som tilldelar alla användare i samlingen en FederationAndPICDefault-princip.
  
Anta att du tidigare har tilldelat Alex FederationAndPICDefault policy och nu har ändrat dig och vill att han ska hanteras av den globala principen för extern åtkomst. Du kan inte uttryckligen koppla den globala principen till vem som helst. Istället används den globala principen för en viss användare om ingen princip för användare har tilldelats till användaren. Om vi vill att Alex ska hanteras av den globala policyn måste du därför  *ta bort tilldelningen*  för alla användare som tidigare tilldelats till honom. Här är ett exempel kommando:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

Det här kommandot anger namnet på den externa åtkomst principen som tilldelats till Alex till ett null-värde ($Null). Null betyder "inget". Ingen extern åtkomst policy är kopplad till Alex. När ingen extern åtkomst policy har tilldelats till en användare hanteras den av den globala principen.
  

## <a name="managing-large-numbers-of-users"></a>Hantera många användare

Om du vill hantera många användare (1000 eller mer) måste du först gruppera kommandona via ett skript block med cmdleten [Invoke-kommando](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) .  I tidigare exempel körs en cmdlet för att aktivera samtalet och sedan vänta tills det blir tillbaka.  När du använder ett skript block kan du använda cmdlets för fjärr anslutning och när det är slutfört skicka data tillbaka. 

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

Detta hittar 500-användare åt gången som inte har någon klient policy. Den får klient principen "ClientPolicyNoIMURL" och den externa åtkomst principen "FederationAndPicDefault". Resultaten grupperas i 50 och varje sats i 50 skickas till fjärrdatorn.
  
## <a name="see-also"></a>Se även

[Hantera Skype för företag – Online med PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
