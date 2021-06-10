---
title: Visa Microsoft 365 licenser och tjänster med PowerShell
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
description: Förklarar hur du använder PowerShell för att visa information om licensplaner, tjänster och licenser som är tillgängliga i din Microsoft 365 organisation.
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924642"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Visa Microsoft 365 licenser och tjänster med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Varje Microsoft 365-prenumeration består av följande element:

- **Licensplaner** Dessa kallas även licensplaner eller Microsoft 365 abonnemang. Licensieringsplaner definierar Microsoft 365 tjänster som är tillgängliga för användare. Din Microsoft 365-prenumeration kan innehålla flera licensplaner. Ett exempel på en licensieringsplan är Microsoft 365 E3.
    
- **Tjänster** De kallas även tjänstplaner. Tjänster är de Microsoft 365 produkter, funktioner och funktioner som är tillgängliga i varje licensplan, till exempel Exchange Online och Microsoft 365-appar för företag (kallades tidigare Office 365 ProPlus). Användare kan ha flera licenser tilldelade till sig från olika licensplaner som beviljar åtkomst till olika tjänster.
    
- **Licenser** Varje licensplan innehåller antalet licenser som du har köpt. Du tilldelar användare licenser så att de kan Microsoft 365 tjänster som definieras av licensplanen. Varje användarkonto kräver minst en licens från en licensplan så att de kan logga in på Microsoft 365 och använda tjänsterna.
    
Du kan använda PowerShell för Microsoft 365 för att visa information om tillgängliga licensplaner, licenser och tjänster i din Microsoft 365 organisation. Mer information om de produkter, funktioner och tjänster som är tillgängliga i olika Office 365-prenumerationer finns [i Office 365 Alternativ för abonnemang.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph modul

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Om du vill visa sammanfattningsinformation om dina aktuella licensabonnemang och tillgängliga licenser för varje abonnemang kör du det här kommandot:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

Resultatet innehåller:
  
- **SkuPartNumber:** Visar organisationens tillgängliga licensplaner. `ENTERPRISEPACK`Licensplanens namn är till exempel på Office 365 Enterprise E3.
    
- **Aktiverad:** Antalet licenser som du har köpt för ett visst licensabonnemang.
    
- **ConsumedUnits:** Antalet licenser som du har tilldelat användare från en specifik licensplan.
    
Om du vill visa information Microsoft 365 tjänster som är tillgängliga i alla dina licensplaner visar du först en lista över dina licensplaner.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Lagra sedan information om licensplaner i en variabel.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Visa sedan tjänsterna i ett visst licensabonnemang.

```powershell
$licenses[<index>].ServicePlans
```

\<index> är ett heltal som anger radnumret för licensplanen från visningen av `Get-AzureADSubscribedSku | Select SkuPartNumber` kommandot, minus 1.

Om visningen av kommandot `Get-AzureADSubscribedSku | Select SkuPartNumber` till exempel är följande:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Kommandot för att visa tjänsterna för ENTERPRISEPREMIUM-licensplanen är följande:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM är den tredje raden. Därför är indexvärdet (3 –1) eller 2.

En fullständig lista över licensplaner (kallas även produktnamn), deras inkluderade tjänstplaner och deras motsvarande eget namn finns i Produktnamn och [tjänstplansidentifierare för licensiering.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory för Windows PowerShell

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

>[!Note]
>Det finns ett PowerShell-skript som automatiserar procedurerna som beskrivs i det här avsnittet. Med skriptet kan du visa och inaktivera tjänster i din organisation Microsoft 365, inklusive Sway. Mer information finns i Inaktivera [åtkomst till Sway med PowerShell.](disable-access-to-sway-with-microsoft-365-powershell.md)
>
    
Kör följande kommando om du vill visa sammanfattningsinformation om dina aktuella licensabonnemang och tillgängliga licenser för varje abonnemang:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.
>

Resultatet innehåller följande information:
  
- **AccountSkuId:** Visa organisationens tillgängliga licensplaner med syntaxen `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ är det värde som du angav när du registrerade dig i Microsoft 365, och är unikt för din organisation. Värdet _\<LicensingPlan>_ är detsamma för alla. I värdet är till exempel företagsnamnet och licensplanens namn , som är `litwareinc:ENTERPRISEPACK` `litwareinc` `ENTERPRISEPACK` systemnamnet för det Office 365 Enterprise E3.
    
- **ActiveUnits:** Antalet licenser som du har köpt för ett visst licensabonnemang.
    
- **WarningUnits:** Antalet licenser i ett licensabonnemang som du inte har förnyat och som upphör efter respitperioden på 30 dagar.
    
- **ConsumedUnits:** Antalet licenser som du har tilldelat användare från en specifik licensplan.
    
Om du vill visa Microsoft 365 tjänster som är tillgängliga i alla dina licensplaner kör du följande kommando:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

I följande tabell visas Microsoft 365 tjänstplaner och deras eget namn för de vanligaste tjänsterna. Listan med tjänstplaner kan se annorlunda ut. 
  
|**Serviceplan**|**Beskrivning**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365-appar för företag *(kallades tidigare Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype för företag – Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online-abonnemang 2  <br/> |
   
En fullständig lista över licensplaner (kallas även produktnamn), deras inkluderade tjänstplaner och deras motsvarande eget namn finns i Produktnamn och [tjänstplansidentifierare för licensiering.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

Om du vill visa information Microsoft 365 tjänster som är tillgängliga i en viss licensplan använder du följande syntax.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

Det här exemplet visar de tjänster som är tillgängliga i licensplanen litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3).
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)