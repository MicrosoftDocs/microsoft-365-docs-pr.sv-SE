---
title: Visa Microsoft 365-licenser och-tjänster med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Förklarar hur du använder PowerShell för att visa information om licens planer, tjänster och licenser som är tillgängliga i din Microsoft 365-organisation.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694560"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Visa Microsoft 365-licenser och-tjänster med PowerShell

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Alla Microsoft 365-prenumerationer består av följande element:

- **Licens planer** Dessa kallas även licens planer eller Microsoft 365-abonnemang. Licens planer definierar vilka Microsoft 365-tjänster som är tillgängliga för användarna. Ditt Microsoft 365-abonnemang kan innehålla flera licens planer. Ett exempel på en licens plan är Microsoft 365 E3.
    
- **Tjänster** De här kallas även för tjänste abonnemang. Tjänster är Microsoft 365-produkter,-funktioner och-funktioner som är tillgängliga i varje licens plan, till exempel Exchange Online och Microsoft 365-appar för företag (tidigare kallat Office 365 ProPlus). Användare kan ha flera licenser tilldelade till dem från olika licens planer som beviljar åtkomst till olika tjänster.
    
- **Licenser** Varje licens plan innehåller antalet licenser som du har köpt. Du tilldelar licenser till användarna så att de kan använda Microsoft 365-tjänsterna som definieras av licens planen. För varje användar konto krävs minst en licens från ett licens abonnemang så att de kan logga in på Microsoft 365 och använda tjänsterna.
    
Du kan använda PowerShell för Microsoft 365 för att visa information om tillgängliga licens planer, licenser och tjänster i din Microsoft 365-organisation. Mer information om produkter, funktioner och tjänster som är tillgängliga i olika Office 365-abonnemang finns i alternativ för [office 365-abonnemang](https://go.microsoft.com/fwlink/p/?LinkId=691147).


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Om du vill visa sammanfattnings information om dina aktuella licens planer och tillgängliga licenser för varje abonnemang kör du det här kommandot:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

Resultatet innehåller:
  
- **SkuPartNumber:** Visar tillgängliga licens planer för organisationen. Till exempel `ENTERPRISEPACK` är licens Plans namnet för Office 365 Enterprise E3.
    
- **Aktive rad:** Antalet licenser som du har köpt för ett specifikt licens abonnemang.
    
- **ConsumedUnits:** Antalet licenser som du har tilldelat användarna från en viss licens plan.
    
Om du vill visa information om de Microsoft 365-tjänster som är tillgängliga i alla dina licens planer måste du först Visa en lista över dina licens planer.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Sedan lagrar du information om licens planer i en variabel.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Nästa steg är att Visa tjänsterna i en specifik licens plan.

```powershell
$licenses[<index>].ServicePlans
```

\<index> är ett heltal som anger rad numret för licens planen från visningen av `Get-AzureADSubscribedSku | Select SkuPartNumber` kommandot, minus 1.

Till exempel om visningen av `Get-AzureADSubscribedSku | Select SkuPartNumber` kommandot är det här:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Då är kommandot för att Visa tjänsterna för ENTERPRISEPREMIUM-licens planen det här:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM är den tredje raden. Därför är indexvärdet (3-1) eller 2.

En fullständig lista över licens planer (kallas även produkt namn), deras inkluderade tjänste abonnemang och deras motsvarande namn finns i [produkt namn och service plan-ID: n för licensiering](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

>[!Note]
>Det finns ett PowerShell-skript som automatiserar procedurerna som beskrivs i det här avsnittet. Du kan också använda skript för att visa och inaktivera tjänster i Microsoft 365-organisationen, inklusive Sway. Mer information finns i [inaktivera åtkomst till Sway med PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
>
    
Om du vill visa sammanfattnings information om dina aktuella licens planer och tillgängliga licenser för varje abonnemang kör du följande kommando:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
>

Resultatet innehåller följande information:
  
- **AccountSkuId:** Visa tillgängliga licens planer för organisationen med hjälp av syntaxen `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ är värdet som du angav när du registrerade dig i Microsoft 365 och är unikt för din organisation. _\<LicensingPlan>_ Värdet är detsamma för alla. Till exempel, i värdet `litwareinc:ENTERPRISEPACK` , företags namnet  `litwareinc` och namnet på licens planen  `ENTERPRISEPACK` , som är system namnet för Office 365 Enterprise E3.
    
- **ActiveUnits:** Antalet licenser som du har köpt för ett specifikt licens abonnemang.
    
- **WarningUnits:** Antalet licenser i en licens plan som du inte har förnyat och som upphör att gälla efter 30 dagar.
    
- **ConsumedUnits:** Antalet licenser som du har tilldelat användarna från en viss licens plan.
    
Om du vill visa information om de Microsoft 365-tjänster som är tillgängliga i alla dina licens planer kör du följande kommando:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

I följande tabell visas Microsoft 365-tjänstens abonnemang och deras egna namn för de vanligaste tjänsterna. Din lista över tjänste abonnemang kan skilja sig från varandra. 
  
|**Service plan**|**Beskrivning**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365-appar för företag *(tidigare kallat Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype för företag – Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online-abonnemang 2  <br/> |
   
En fullständig lista över licens planer (kallas även produkt namn), deras inkluderade tjänste abonnemang och deras motsvarande namn finns i [produkt namn och service plan-ID: n för licensiering](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Om du vill visa information om de Microsoft 365-tjänster som är tillgängliga i ett specifikt licens abonnemang använder du följande syntax.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

I det här exemplet visas de tjänster som är tillgängliga i licens planen litwareinc: ENTERPRISEPACK (Office 365 Enterprise E3).
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
