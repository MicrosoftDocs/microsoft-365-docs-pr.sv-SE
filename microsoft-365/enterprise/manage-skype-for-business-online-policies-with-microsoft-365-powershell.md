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
description: Sammanfattning Använd PowerShell för att hantera egenskaperna Skype för företag Online-användarkonton med principer.
ms.openlocfilehash: a10929bbdce499ad26f9714127f675beeef58765
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916708"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Hantera Skype för företag – Onlineprinciper med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Om du vill hantera många egenskaper för användarkonton för Skype för företag Online måste du ange dem som egenskaper för principer med PowerShell för Microsoft 365.
  
## <a name="before-you-begin"></a>Innan du börjar

Använd de här anvisningarna för att konfigurera om du vill köra kommandona (hoppa över de steg som redan är slutförda):

  > [!Note]
  > Skype för företag – Online-Connector är för närvarande en del av den senaste versionen av Teams PowerShell-modul. Om du använder den senaste versionen av Teams PowerShell, behöver du inte installera Skype för företag – Online-Connector.

1. Installera [Teams PowerShell-modul](/microsoftteams/teams-powershell-install).
    
2. Öppna en Windows PowerShell kommandotolk och kör följande kommandon: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   När du uppmanas till det anger Skype för företag onlineadministratörens kontonamn och lösenord.
    
## <a name="manage-user-account-policies"></a>Hantera principer för användarkonton

Många Skype för företag Online-användarkontoegenskaper konfigureras med hjälp av principer. Principer är helt enkelt samlingar av inställningar som kan tillämpas på en eller flera användare. Om du vill ta en titt på hur en princip har konfigurerats kan du köra det här exempelkommandot för principen FederationAndPICDefault:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

Du bör i sin tur få tillbaka något som liknar det här:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

I det här exemplet avgör värdena i den här principen vad en användning kan eller inte kan göra när det gäller kommunikation med externa användare. Egenskapen EnableOutsideAccess måste till exempel vara inställd på Sant för att en användare ska kunna kommunicera med personer utanför organisationen. Observera att den här egenskapen inte visas Microsoft 365 administrationscentret. I stället sätts egenskapen automatiskt till Sant eller Falskt baserat på andra val som du gör. De andra två intressanta egenskaperna är:
  
- **EnableFederationAccess** anger om användaren kan kommunicera med personer från federerade domäner.
    
- **EnablePublicCloudAccess** anger om användaren kan kommunicera med Windows Live-användare.
    
Därför ändrar du inte federationsrelaterade egenskaper direkt på användarkonton (till exempel **Set-CsUser -EnableFederationAccess $True**). I stället tilldelar du ett konto en princip för extern åtkomst som har önskade egenskapsvärden förkonfigurerade. Om vi vill att en användare ska kunna kommunicera med externa användare och med Windows Live-användare måste det användarkontot tilldelas en princip som tillåter de typerna av kommunikation.
  
Om du vill veta om någon kan kommunicera med användare utanför organisationen måste du:
  
- Avgör vilken princip för extern åtkomst som har tilldelats den användaren.
    
- Avgör vilka funktioner som tillåts eller inte tillåts av den principen.
    
Du kan till exempel göra det med hjälp av det här kommandot:
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Det här kommandot hittar den princip som tilldelats användaren och söker sedan efter aktiverade eller inaktiverade funktioner i principen.
  
Information om Skype för företag onlineprinciper med PowerShell finns i cmdlets för:

- [Klientprincip](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [Konferensprincip](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [Mobilpolicy](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Policy för röstbrevlåda online](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [Princip för röstdirigering](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> En Skype för företag Online-uppringningsplan är en princip i alla sammanhang utom namnet. Namnet "uppringningsplan" valdes i stället för t.ex. "uppringningsprincip" för att ge bakåtkompatibilitet med Office Communications Server och med Exchange. 
  
Om du till exempel vill titta på alla röstprinciper som är tillgängliga för din användning, kör du det här kommandot:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Då returneras en lista över alla tillgängliga röstprinciper. Kom dock ihåg att alla principer inte kan tilldelas till alla användare. Detta beror på olika begränsningar som innefattar licensiering och geografisk plats. (Den s.k.[användningsplatsen](/previous-versions/azure/dn194136(v=azure.100)).") Om du vill veta vilka principer för extern åtkomst och konferensprinciper som kan tilldelas en viss användare kan du använda kommandon som liknar dessa: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

Parametern ApplicableTo begränsar returnerade data till principer som kan tilldelas till den angivna användaren (till exempel Alex Darrow). Beroende på begränsningar för licensiering och användningsplats kan det representera en delmängd av alla tillgängliga principer. 
  
I vissa fall används inte principers egenskaper tillsammans med Microsoft 365, medan andra endast kan hanteras av Microsofts supportpersonal. 
  
Med Skype för företag Online måste användarna hanteras av någon typ av princip. Om en giltig principrelaterad egenskap är tom innebär det att användaren hanteras av en global princip, vilket är en princip som automatiskt används för en användare såvida han eller hon inte specifikt tilldelas en princip per användare. Eftersom det inte visas någon klientprincip för ett användarkonto hanteras den av den globala principen. Du kan fastställa den globala klientprincipen med det här kommandot:
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>Se även

[Hantera Skype för företag – Online med PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)