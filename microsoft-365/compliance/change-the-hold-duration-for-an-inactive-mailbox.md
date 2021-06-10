---
title: Ändra kvarhållningstiden för en inaktiv postlåda
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: När en Office 365 postlåda har gjorts inaktiv ändrar du varaktigheten för bevarandet Office 365 bevarandeprincip som tilldelas till den inaktiva postlådan.
ms.openlocfilehash: 49d133c64763cee12cb26e27d372a16ba4ad7e94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162019"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Ändra kvarhållningstiden för en inaktiv postlåda

En inaktiv postlåda används för att behålla en tidigare anställds e-post när han eller hon lämnar organisationen. En postlåda blir inaktiv när ett bevarande av juridiska skäl, ett In-Place-bevarande, en Microsoft 365-bevarandeprincip eller ett bevarande som är kopplat till ett eDiscovery-ärende placeras i postlådan och motsvarande användarkonto tas bort. Innehållet i en inaktiv postlåda behålls under det kvarhållna antalet som gjordes för postlådan innan den gjordes inaktiv. Varaktigheten för håll definierar hur länge objekten i mappen för återställningsbara objekt behålls. När varaktigheten för undantaget för ett objekt i mappen återställningsbara objekt upphör att gälla tas objektet bort permanent från den inaktiva postlådan. När en postlåda har gjorts inaktiv kan du ändra varaktigheten för bevarandet Microsoft 365 bevarandeprincip som tilldelas till den inaktiva postlådan.
  
> [!IMPORTANT]
> Medan vi fortsätter att investera på olika sätt för att bevara postlådeinnehållet presenterar vi att innehållet i In-Place Holds har Exchange i administrationscentret. Det innebär att du bör använda bevarandeprinciper för Microsoft 365 och bevarandeprinciper för att skapa en inaktiv postlåda. Från och med den 1 april 2020 kan du inte skapa nya In-Place i Exchange Online. Men du kan fortfarande ändra varaktigheten för ett aktivt In-Place som gjorts på en inaktiv postlåda. Men från och med den 1 juli 2020 kan du inte ändra varaktigheten för varaktigheten. Du kan bara ta bort en inaktiv postlåda genom att ta bort In-Place inaktiv. Befintliga inaktiva postlådor som finns på In-Place behålls fortfarande tills brytningen tas bort. Mer information om hur du tar In-Place [eDiscovery-verktyg finns i Slutet av äldre eDiscovery-verktyg.](legacy-ediscovery-retirement.md)
  
## <a name="connect-to-powershell"></a>Anslut till PowerShell

- Du måste använda Exchange Online PowerShell för att ändra varaktigheten för bevarande av juridiska skäl för en inaktiv postlåda. Du kan inte använda Exchange (EAC). Men du kan använda Exchange Online PowerShell eller EAC om du vill ändra varaktigheten för ett In-Place. Du kan använda Säkerhets- och efterlevnadscenter eller Säkerhets- och & PowerShell för att ändra varaktigheten för en bevarandeprincip Microsoft 365 bevarandeprincip.
    
- Information om hur du Exchange Online ett PowerShell- & Säkerhetscenter för efterlevnadscenter finns i följande avsnitt:
    
  - [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [Anslut till Säkerhets- och efterlevnadscenter i PowerShell](/powershell/exchange/connect-to-scc-powershell).
    
- Håll som är kopplade till eDiscovery-ärenden är oändligt antal kvar, vilket innebär att ingen varaktighet kan ändras. Objekten hålls kvar för alltid eller tills du tar bort det inaktiva postlådan.
    
- Mer information om inaktiva postlådor finns i [Inaktiva postlådor i Microsoft 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Steg 1: Identifiera eventuella spärrade e-postlådor i inaktiva postlådor

Eftersom olika typer av kvarhållning eller en eller flera Microsoft 365 bevarandeprinciper kan placeras i en inaktiv postlåda är det första steget att identifiera spärrade objekt i en inaktiv postlåda.
  
Kör följande kommando i Exchange Online PowerShell för att visa information om väntande åtgärder för alla inaktiva postlådor i organisationen.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

Värdet för **True för** egenskapen **LitigationHoldEnabled** anger att den inaktiva postlådan finns på Bevarande av juridiska skäl. Om en bevarandeprincip för In-Place, ett eDiscovery-bevarande eller en Microsoft 365-bevarandeprincip placeras i en inaktiv postlåda visas ett GUID för bevarande- eller kvarhållningsprincipen som värde för egenskapen **InPlaceHolds.** Följande visar till exempel resultat för fem inaktiva postlådor. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

I följande tabell identifieras de fem olika typerna av håll som användes för att göra varje postlåda inaktiv.
  
|**Inaktiv postlåda**|**Typ av håll**|**Så här identifierar du holden för den inaktiva postlådan**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Bevarande av juridiska skäl  <br/> |Egenskapen  *LitigationHoldEnabled*  är inställd på  `True` .  <br/> |
|Pilar Pinilla  <br/> |In-Place på  <br/> |Egenskapen  *InPlaceHolds*  innehåller GUID för det In-Place håll som är placerat på den inaktiva postlådan. Det här är ett bra In-Place på grund av att ID:t inte börjar med ett prefix.  <br/> Du kan använda kommandot i Exchange Online PowerShell för att få information om `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` In-Place på den inaktiva postlådan.  <br/> |
|Mario Necaise  <br/> |Organisationens Microsoft 365 bevarandeprincip i Säkerhets- & Efterlevnadscenter  <br/> |Egenskapen  *InPlaceHolds*  är tom. Det här anger att en eller Exchange hela organisationen Microsoft 365 den inaktiva postlådan. I det här fallet kan du köra kommandot i Exchange Online PowerShell för att få en lista över `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` GUID:er för organisationens Microsoft 365 bevarandeprinciper. GUID för organisationsomfattande bevarandeprinciper som tillämpas på Exchange börjar med `mbx` prefixet, till exempel `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> <br/>Om du vill Microsoft 365 bevarandeprincip som tillämpas på den inaktiva postlådan kör du följande kommando i Security & Compliance Center PowerShell.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Microsoft 365-bevarandeprincip i Säkerhets- & säkerhets- och efterlevnadscenter som används för specifika postlådor  <br/> |Egenskapen *InPlaceHolds* innehåller GUID för den Microsoft 365 bevarandeprincip som används för den inaktiva postlådan. Det här är en bevarandeprincip som tillämpas på specifika postlådor eftersom GUID startar med  `mbx` prefixet. Om GUID för bevarandeprincipen som tillämpats på den inaktiva postlådan började med prefixet, indikerar det att bevarandeprincipen används i `skp` Skype för företag konversationer.  <br/><br/> Om du vill Microsoft 365 bevarandeprincip som tillämpas på den inaktiva postlådan kör du följande kommando i Security & Compliance Center PowerShell.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Se till att ta bort  `mbx`  `skp` prefixet eller när du kör det här kommandot.  <br/> |
|Abraham McMahon  <br/> |eDiscovery case hold in the Security & Compliance Center  <br/> |Egenskapen  *InPlaceHolds*  innehåller GUID för det eDiscovery-ärende som är placerat för den inaktiva postlådan. Du ser att detta är ett eDiscovery-ärende som kan innehållas eftersom GUID börjar med  `UniH` prefixet.  <br/> Du kan använda cmdleten i Security & Compliance Center PowerShell för att få information om eDiscovery-ärendet som är kopplat till en  `Get-CaseHoldPolicy` inaktiv postlåda. Du kan till exempel köra kommandot för  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` att visa namnet på det ärende som finns på den inaktiva postlådan. Se till att ta bort  `UniH` prefixet när du kör det här kommandot.  <br/><br/> Kör följande kommandon för att identiteten för eDiscovery-ärendet som håller i den inaktiva postlådan är kopplat till.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Obs!** Vi rekommenderar inte att du använder eDiscovery-innehåller för inaktiva postlådor. Det beror på att eDiscovery-ärenden är avsedda för specifika, tidsbundna ärenden relaterade till ett juridiskt ärende. Förr eller senare avslutas förmodligen ett juridiskt ärende och det som är kopplat till ärendet kommer att tas bort och eDiscovery-ärendet kommer att stängas (eller tas bort). Om ett ärende som sätts i en inaktiv postlåda kopplas till ett eDiscovery-ärende och det frisläpps eller eDiscovery-ärendet stängs eller tas bort, tas den inaktiva postlådan bort permanent. 

Mer information om hur du Microsoft 365 bevarandeprinciper finns i [Läs mer om bevarandeprinciper och bevarandeetiketter.](retention.md)
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Steg 2: Ändra varaktigheten för varaktigheten för en inaktiv postlåda

När du har identifierat vilken typ av spärrade objekt som ska spärras för den inaktiva postlådan (och om det finns flera spärrade objekt) är nästa steg att ändra varaktigheten för det spärrade företaget. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Ändra varaktigheten för bevarande av juridiska skäl

Gör så här för att använda Exchange Online PowerShell för att ändra varaktigheten för bevarande av juridiska skäl som placeras för en inaktiv postlåda. Du kan inte använda EAC. Kör följande kommando för att ändra varaktigheten för att hålla kvar. I det här exemplet ändras varaktigheten för varaktigheten för varaktigheten till en obegränsad tid.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

Resultatet är att objekten i den inaktiva postlådan behålls ett obestämt år eller tills hålltiden tas bort eller då varaktigheten för hålltiden ändras till ett annat värde.
  
> [!TIP]
> Det bästa sättet att identifiera en inaktiv postlåda är att använda det unika **namnet** **eller det unika Exchange GUID-värdet.** Om du använder något av dessa värden undviker du att ange fel postlåda av misstag. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Ändra varaktigheten för ett In-Place håll

 In-Place innehåller har dragits tillbaka och kan inte längre ändras. Om en inaktiv postlåda har In-Place tillämpas på den kan du inte ändra varaktigheten för att hålla. Du kan bara ta bort In-Place, vilket innebär att den inaktiva postlådan tas bort. Mer information finns i Ta [bort en inaktiv postlåda](delete-an-inactive-mailbox.md#remove-in-place-holds).
  
## <a name="more-information"></a>Mer information

- **Hur beräknas varaktigheten för varaktigheten för ett objekt i en inaktiv postlåda?** Varaktigheten beräknas från det ursprungliga datumet då ett postlådeobjekt togs emot eller skapades. 
    
- **Vad händer när undantagets varaktighet går ut?** När varaktigheten för undantaget för ett postlådeobjekt i mappen Återställningsbara objekt upphör att gälla tas objektet bort permanent från den inaktiva postlådan. Om ingen varaktighet anges för det inaktiva postlådan rensas aldrig objekten i mappen Återställningsbara objekt bort (såvida inte varaktigheten för den inaktiva postlådan ändras). 
    
- **Bearbetas Exchange bevarandeprincip på inaktiva postlådor?** Om en Exchange-bevarandeprincip (hantering av meddelandeposter, eller MRM, funktion i Exchange Online) tillämpats på en postlåda när den gjordes inaktiv  kommer borttagningsprinciperna (som är bevarandetaggar som konfigurerats med åtgärden Ta bort bevarande) att fortsätta att bearbetas i den inaktiva postlådan. Det innebär att objekt som är märkta med en borttagningsprincip flyttas till mappen Återställningsbara objekt när bevarandetiden löper ut. De objekten rensas sedan från den inaktiva postlådan när varaktigheten för ett objekt upphör att gälla. 
    
    Och alla arkiveringsprinciper (som är bevarandetaggar som konfigurerats med bevarandeåtgärden **FlyttaTillArkiv)** som ingår i den bevarandeprincip som tilldelats en inaktiv postlåda ignoreras. Det innebär att objekt i en inaktiv postlåda som är märkta med en arkiveringsprincip finns kvar i den primära postlådan när lagringsperioden går ut. De flyttas inte till arkivpostlådan eller till mappen Återställningsbara objekt i arkivpostlådan. Eftersom en användare inte kan logga in på en inaktiv postlåda finns det ingen anledning att använda datacenterresurser för att bearbeta arkiveringsprinciper. 

- **Om du vill kontrollera den nya varaktigheten för bevarande av juridiska skäl kör du följande kommandon** 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- **Precis som vanliga postlådor bearbetar assistenten för hanterade mappar (MFA) även inaktiva postlådor.** I Exchange Online bearbetar MFA postlådor ungefär var sjunde dag. När du har ändrat varaktigheten för väntande ändringar för en inaktiv postlåda kan du använda cmdleten **Start-ManagedFolderAssistant** för att direkt börja bearbeta den nya varaktigheten för den inaktiva postlådan. Kör följande kommando. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Om många spärrade objekt placeras i en inaktiv postlåda visas inte alla GUID:er för håll.** Du kan köra följande kommando för att visa GUID:er för alla undantag från juridiska skäl som placeras i en inaktiv postlåda. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```