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
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>Tilldela principer per användare Skype för företag Online-principer med PowerShell för Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Att använda PowerShell för Microsoft 365 är ett effektivt sätt att tilldela kommunikationsinställningar per användare med Skype för företag Online-principer.
  
## <a name="prepare-to-run-the-powershell-commands"></a>Förbereda för att köra PowerShell-kommandon

Använd de här anvisningarna för att konfigurera om du vill köra kommandona (hoppa över de steg som redan är slutförda):
  
  > [!Note]
   > Skype för företag – Online-Connector är för närvarande en del av den senaste versionen av Teams PowerShell-modul. Om du använder den senaste versionen av Teams PowerShell, behöver du inte installera Skype för företag – Online-Connector.

1. Installera [Teams PowerShell-modul](/microsoftteams/teams-powershell-install).
    
2. Öppna en Windows PowerShell kommandotolk och kör följande kommandon: 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   När du uppmanas till det anger Skype för företag onlineadministratörens kontonamn och lösenord.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>Uppdatera inställningar för extern kommunikation för ett användarkonto

Anta att du vill ändra inställningarna för extern kommunikation för ett användarkonto. Du vill till exempel tillåta att Alex kommunicerar med externa användare (EnableFederationAccess är lika med Sant) men inte med Windows Live-användare (EnablePublicCloudAccess är lika med False). För att göra det måste du göra två saker:
  
1. Hitta en princip för extern åtkomst som uppfyller våra villkor.
    
2. Tilldela den externa åtkomstprincipen till Alex.
    
Hur tar du reda på vilken princip för extern åtkomst som ska tilldela Alex? Följande kommando returnerar alla principer för extern åtkomst där EnableFederationAccess är inställd på Sant och EnablePublicCloudAccess är inställt på False:
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

Om du inte har skapat några anpassade instanser av ExternalAccessPolicy, returnerar det kommandot en princip som uppfyller våra villkor (FederationOnly). Här är ett exempel:
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Nu när du vet vilken princip som ska tilldelas till Alex kan vi tilldela den principen med hjälp av cmdleten [Grant-CsExternalAccessPolicy.](/powershell/module/skype/Get-CsExternalAccessPolicy) Här är ett exempel:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

Det är ganska enkelt att tilldela en princip: du anger bara identiteten för användaren och namnet på principen som ska tilldelas. 
  
När det gäller principer och policytilldelningar är du inte begränsad till att arbeta med användarkonton en i taget. Anta till exempel att du behöver en lista över alla användare som tillåts kommunicera med externa partner och med Windows Live-användare. Vi vet redan att dessa användare har tilldelats policyn FederationAndPICDefault för externa användare. Eftersom vi vet det kan du visa en lista över alla dessa användare genom att köra ett enkelt kommando. Här är kommandot:
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

Med andra ord, visa oss alla användare där egenskapen ExternalAccessPolicy är inställd på FederationAndPICDefault. (För att begränsa mängden information som visas på skärmen kan du använda cmdleten Select-Object för att visa endast användarnas visningsnamn.) 
  
Använd det här kommandot om du vill konfigurera alla våra användarkonton att använda samma princip:
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

Det här kommandot använder Get-CsOnlineUser för att returnera en samling av alla användare som har aktiverats för Lync. Sedan skickas all den informationen till Grant-CsExternalAccessPolicy, som tilldelar principen FederationAndPICDefault till varje användare i samlingen.
  
Anta att du tidigare har tilldelat Alex policyn FederationAndPICDefault och nu har du ändrat dig och vill att han ska hanteras av den globala policyn för extern åtkomst. Du kan inte uttryckligen tilldela global princip till någon. Den globala principen används istället för en viss användare om ingen princip per användare tilldelas till den användaren. Om vi därför vill att Alex ska hanteras av  den globala principen måste du ta bort alla policyer per användare som tidigare tilldelats till honom. Här är ett exempelkommando:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

Det här kommandot anger namnet på principen för extern åtkomst som tilldelats Alex till ett nullvärde ($Null). Null innebär "inget". Med andra ord har ingen policy för extern åtkomst tilldelats till Alex. När ingen princip för extern åtkomst är tilldelad till en användare hanteras den användaren av den globala principen.

## <a name="managing-large-numbers-of-users"></a>Hantera stora antal användare

Om du vill hantera stora antal användare (1 000 eller fler) måste du batcha kommandona via ett skriptblock med cmdleten [Invoke-Command.](/powershell/module/microsoft.powershell.core/invoke-command)  I tidigare exempel måste samtalet konfigureras varje gång en cmdlet körs och sedan vänta på resultatet innan det skickas tillbaka.  När du använder ett skriptblock gör detta att cmdlet:arna kan köras på distans och när de har slutförts kan du skicka tillbaka data.

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

Då hittar du 500 användare i taget som inte har någon klientprincip. Det ger dem klientprincipen "ClientPolicyNoIMURL" och principen för extern åtkomst "FederationAndPicDefault". Resultatet grupperas i grupper om 50 och varje batch på 50 skickas sedan till fjärrdatorn.
  
## <a name="see-also"></a>Se även

[Hantera Skype för företag – Online med PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)