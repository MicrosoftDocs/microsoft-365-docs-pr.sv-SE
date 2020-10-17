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
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Hantera Skype för företag – Onlineprinciper med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

För att hantera många egenskaper för användar konto för Skype för företag – Online måste du ange dem som egenskaper för principer med PowerShell för Microsoft 365.
  
## <a name="before-you-begin"></a>Innan du börjar

Använd dessa instruktioner för att komma igång med kommandona (hoppa över stegen som du redan har slutfört):

  > [!Note]
  > Connector för Skype för företag – Online är nu en del av den senaste Teams PowerShell-modulen. Om du använder den senaste Teams-versionen för att använda det här alternativet behöver du inte installera Skype för företag – Online-anslutaren.

1. Installera [modulen för moduler i PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Öppna en Windows PowerShell kommandotolk och kör följande kommandon: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

   Skriv in namnet och lösen ordet för Skype för företag – Online när du uppmanas till det.
    
## <a name="manage-user-account-policies"></a>Hantera principer för användar konton

Många användar konto egenskaper för Skype för företag – Online konfigureras med hjälp av principer. Principer är helt enkelt samlingar av inställningar som kan tillämpas på en eller flera användare. Om du vill ta en titt på hur en princip har kon figurer ATS kan du köra det här exemplet på FederationAndPICDefault princip:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

I sin tur bör du få tillbaka något liknande det här:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

I det här exemplet bestämmer värdena i den här principen vad en användning kan eller inte kan göra när det gäller kommunikation med externa användare. Till exempel måste egenskapen EnableOutsideAccess vara angiven till true för att en användare ska kunna kommunicera med personer utanför organisationen. Observera att den här egenskapen inte visas i administrations centret för Microsoft 365. I stället anges egenskapen automatiskt till true eller false utifrån de andra val du gör. De andra två intresse egenskaperna är:
  
- **EnableFederationAccess** anger om användaren kan kommunicera med personer från federerade domäner.
    
- **EnablePublicCloudAccess** anger om användaren kan kommunicera med Windows Live-användare.
    
Därför behöver du inte direkt ändra egenskaperna för ett närstående konto för användar konton (till exempel **set-CsUser-EnableFederationAccess $True**). Istället tilldelar du ett konto en extern åtkomst princip med de önskade egenskaps värdena förkonfigurerade. Om vi vill att en användare ska kunna kommunicera med externa användare och med Windows Live-användare måste användar kontot ha tilldelats en princip som tillåter dessa typer av kommunikation.
  
Om du vill veta om någon kan kommunicera med användare utanför organisationen måste du:
  
- Avgöra vilken extern åtkomst policy som har tilldelats till användaren.
    
- Avgöra vilka funktioner som är tillåtna eller inte av den policyn.
    
Du kan till exempel göra det genom att använda det här kommandot:
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Det här kommandot hittar den princip som är tilldelad användaren och hittar sedan funktionerna aktiverade eller inaktiverade i principen.
  
Information om hur du hanterar principer för Skype för företag – Online med PowerShell finns i cmdletar för:

- [Klient princip](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [Konferens policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [Mobil policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Sekretess policy online](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [Policy för Röstträning](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> Ett uppringnings abonnemang för Skype för företag – Online är en policy i alla avseenden förutom namnet. Namnet "uppringnings plan" valdes i stället för "uppringnings princip" för att ge bakåtkompatibilitet med Office Communications Server och med Exchange. 
  
Om du till exempel vill visa alla tillgängliga röst principer för användning kör du det här kommandot:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Det returnerar en lista över alla tillgängliga röst principer. Kom ihåg att alla användare inte kan kopplas till alla principer. Detta beror på olika begränsningar avseende licensiering och geografisk plats. (Den s.k. "[användnings plats](https://msdn.microsoft.com/library/azure/dn194136.aspx).") Om du vill veta vilka externa åtkomst principer och konferens principer som kan kopplas till en viss användare använder du kommandon som liknar dessa: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

Parametern ApplicableTo begränsar den returnerade informationen till principer som kan tilldelas till den angivna användaren (till exempel Alex Darrow). Beroende på plats begränsningar för licenser och användnings områden kan det representera en delmängd av alla tillgängliga principer. 
  
I vissa fall används inte egenskaper för principer med Microsoft 365, medan andra endast kan hanteras av Microsofts support personal. 
  
Med Skype för företag – Online måste användarna hanteras av en princip av något slag. Om en giltig principbaserad egenskap är tom innebär det att användaren hanteras av en global princip, vilket är en princip som automatiskt tillämpas på en användare såvida inte han eller hon tilldelats en princip per användare. Eftersom en klient princip inte visas för ett användar konto hanteras den av den globala principen. Du kan bestämma den globala klient principen med det här kommandot:
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>Se även

[Hantera Skype för företag – Online med PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)

