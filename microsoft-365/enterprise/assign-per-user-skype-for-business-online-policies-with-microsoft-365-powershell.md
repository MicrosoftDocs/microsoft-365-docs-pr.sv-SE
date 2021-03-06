---
title: Tilldela principer för Skype för företag – Online per användare med PowerShell för Microsoft 365
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
description: 'Sammanfattning: Använd PowerShell för Microsoft 365 för att tilldela kommunikationsinställningar per användare med principer för Skype för företag – Online.'
ms.openlocfilehash: 6ee237e5d2ee0c9f472f372a6aa66c9612336265
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514986"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>Tilldela principer för Skype för företag – Online per användare med PowerShell för Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Att använda PowerShell för Microsoft 365 är ett effektivt sätt att tilldela kommunikationsinställningar per användare med principer för Skype för företag – Online.
  
## <a name="prepare-to-run-the-powershell-commands"></a>Förbereda för att köra PowerShell-kommandon

Använd de här anvisningarna för att konfigurera att köra kommandona (hoppa över stegen som du redan har slutfört):
  
  > [!Note]
   > Skype för företag – Online-Connector är för närvarande en del av den senaste versionen av Teams PowerShell-modul. Om du använder den senaste versionen av Teams PowerShell, behöver du inte installera Skype för företag – Online-Connector.

1. Installera [Teams PowerShell-modulen.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Öppna en Windows PowerShell kommandotolk och kör följande kommandon: 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   När du uppmanas till det anger du ditt administratörskonto och lösenord för Skype för företag – Online.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>Uppdatera inställningar för extern kommunikation för ett användarkonto

Anta att du vill ändra inställningarna för extern kommunikation för ett användarkonto. Du vill till exempel tillåta att Alex kommunicerar med externa användare (EnableFederationAccess är lika med True) men inte med Windows Live-användare (EnablePublicCloudAccess är lika med False). För att göra det måste du göra två saker:
  
1. Hitta en princip för extern åtkomst som uppfyller våra villkor.
    
2. Tilldela den externa åtkomstprincipen till Alex.
    
Hur avgör du vilken extern åtkomstprincip som ska tilldela Alex? Följande kommando returnerar alla principer för extern åtkomst där EnableFederationAccess är inställt på Sant och EnablePublicCloudAccess är inställt på Falskt:
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

Om du inte har skapat anpassade instanser av ExternalAccessPolicy, returnerar det kommandot en princip som uppfyller våra villkor (FederationOnly). Här är ett exempel:
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Nu när du vet vilken princip som ska tilldelas till Alex kan vi tilldela den principen med hjälp av cmdleten [Grant-CsExternalAccessPolicy.](https://go.microsoft.com/fwlink/?LinkId=523974) Här är ett exempel:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

Det är ganska enkelt att tilldela en princip: du anger bara identiteten för användaren och namnet på principen som ska tilldelas. 
  
När det gäller principer och principtilldelningar är du inte begränsad till att arbeta med användarkonton en i taget. Anta till exempel att du behöver en lista över alla användare som tillåts kommunicera med externa partner och med Windows Live-användare. Vi vet redan att dessa användare har tilldelats behörighetsprincipen externa användare FederationAndPICDefault. Eftersom vi vet det kan du visa en lista över alla användare genom att köra ett enkelt kommando. Här är kommandot:
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

Med andra ord, visa oss alla användare där egenskapen ExternalAccessPolicy är inställd på FederationAndPICDefault. (Om du vill begränsa hur mycket information som visas på skärmen kan du använda cmdleten Select-Object för att bara visa varje användares visningsnamn.) 
  
Använd det här kommandot om du vill konfigurera alla användarkonton till att använda samma princip:
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

Det här kommandot använder Get-CsOnlineUser för att returnera en samling av alla användare som har aktiverats för Lync. Sedan skickas all den informationen till Grant-CsExternalAccessPolicy, som tilldelar principen FederationAndPICDefault till varje användare i samlingen.
  
Anta att du tidigare har tilldelat FederationAndPICDefault-principen till ett annat exempel, och nu har du ändrat dig och vill att han ska hanteras av den globala policyn för extern åtkomst. Du kan inte uttryckligen tilldela den globala principen till någon annan. Den globala principen används i stället för en viss användare om ingen princip per användare tilldelas till den användaren. Om vi vill att Alex ska hanteras av den globala principen måste du därför ta bort  *alla*  policyer per användare som tidigare tilldelats honom. Här är ett exempelkommando:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

Det här kommandot anger namnet på den princip för extern åtkomst som Alex tilldelats till ett nullvärde ($Null). Null betyder "inget". Med andra ord tilldelas ingen princip för extern åtkomst till Alex. När ingen princip för extern åtkomst tilldelas till en användare hanteras den användaren av den globala principen.
  

## <a name="managing-large-numbers-of-users"></a>Hantera stora mängder användare

Om du vill hantera stora antal användare (1 000 eller fler) måste du batcha kommandona via ett skriptblock med cmdleten [Invoke-Command.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7)  I tidigare exempel måste det konfigurera samtalet varje gång en cmdlet körs och sedan vänta på resultatet innan det skickas tillbaka.  När du använder ett skriptblock kan cmdlets köras på distans och när de har slutförts kan du skicka tillbaka data. 

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

Då hittar du 500 användare i taget som inte har en klientprincip. Det ger dem klientprincipen "ClientPolicyNoIMURL" och principen för extern åtkomst "FederationAndPicDefault". Resultatet grupperas i grupper om 50 och varje batch med 50 skickas sedan till fjärrdatorn.
  
## <a name="see-also"></a>Se även

[Hantera Skype för företag – Online med PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
