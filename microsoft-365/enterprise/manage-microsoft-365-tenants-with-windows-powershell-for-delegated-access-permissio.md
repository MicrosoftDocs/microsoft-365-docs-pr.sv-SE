---
title: Hantera Microsoft 365-klient organisationer med Windows PowerShell för DAP partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: I den här artikeln lär du dig hur du använder PowerShell för Microsoft 365 för att hantera kund innehav.
ms.openlocfilehash: 14290f04159e3ba0ce46971d204b71d3bb1600d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694447"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Hantera Microsoft 365-klient organisationer med Windows PowerShell för DAP-partners (delegerade åtkomst behörigheter)

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Med Windows PowerShell kan syndikerings-och moln lösnings partners (CSP) enkelt administrera och rapportera kund innehavs inställningar som inte är tillgängliga i administrations centret för Microsoft 365. Observera att för partner administratörs kontot för att administrera AOBO behörigheter måste du ha åtkomst till dess kund innehavare.
  
DAP-partners (delegerade åtkomst behörigheter) för syndikering och moln lösnings leverantörer. De är ofta nätverks-eller Telekom-leverantörer i andra företag. De fördelar Microsoft 365-abonnemang till sina kunder. När de säljer en Microsoft 365-prenumeration beviljas de automatiskt administration på uppdrag av (AOBO) behörigheter till kundens innehav så att de kan administrera och rapportera om kundens innehavare.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Procedurerna i det här avsnittet kräver att du ansluter till [Microsoft 365 med PowerShell](connect-to-microsoft-365-powershell.md).
  
Du behöver också dina autentiseringsuppgifter för partner klient organisation.
  
## <a name="what-do-you-want-to-do"></a>Vad vill du göra?

### <a name="list-all-tenant-ids"></a>Lista alla klient-ID

> [!NOTE]
> Om du har fler än 500 klient organisationer kan du använda cmdlet-syntaxen med antingen  _-all_ eller _-MaxResultsParameter_. Detta gäller för andra cmdlets som kan ge en stor utmatning, till exempel **Get-MsolUser**.
  
Om du vill visa alla klient organisations-ID: n som du har åtkomst till kör du det här kommandot.
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

Då visas en lista över alla dina kund innehavare av **TenantId**.

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a>Skaffa ett klient-ID genom att använda domän namnet

Kör det här kommandot för att hämta **TenantId** för en viss kund klient organisation via domän namn. Ersätt _<domainname.onmicrosoft.com>_ med det faktiska domän namnet för den klient organisation som du vill använda.
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a>Visa en lista över alla domäner för en innehavare

Kör det här kommandot för att få alla domäner för en klient organisation. Ersätt  _<customer TenantId value>_ med det faktiska värdet.
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

Om du har registrerat fler domäner kommer detta att returnera alla domäner som är kopplade till kunden **TenantId**.
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a>Få en mappning av alla innehavare och registrerade domäner

De föregående PowerShell för Microsoft 365-kommandon visar hur du hämtar antingen klient-ID: n eller domäner, men inte båda samtidigt, och utan en tydlig mappning mellan dem. Det här kommandot skapar en lista över alla klient organisations-ID: n och deras domäner.
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a>Skaffa alla användare för en klient organisation

Då visas **userPrincipalName**, **DisplayName**och **ärlicensierad** status för alla användare för en viss klient organisation. Ersätt _<customer TenantId value>_ med det faktiska värdet.
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a>Få all information om en användare

Om du vill se alla egenskaper för en viss användare kör du det här kommandot. Ersätt  _<customer TenantId value>_ och _<user principal name value>_ med faktiska värden.
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a>Lägga till användare, ange alternativ och tilldela licenser

Det är särskilt effektivt att skapa, konfigurera och licensiera för Microsoft 365-användare genom att använda PowerShell för Microsoft 365. I den här processen skapar du först poster för alla användare som du vill lägga till i en CSV-fil och sedan importerar filen genom att använda PowerShell för Microsoft 365. 
  
#### <a name="create-a-csv-file"></a>Skapa en CSV-fil

Skapa en CSV-fil i det här formatet:
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
där:
  
- **UsageLocation**: värdet för det här är ISO-lands-/regionkoden för användaren. Lands-/regionkoder kan hittas på[ISO online-webbplattformen](https://go.microsoft.com/fwlink/p/?LinkId=532703). Koden för USA är till exempel amerikansk och koden för Brasilien är BR. 
    
- **LicenseAssignment**: värdet för detta format: `syndication-account:<PROVISIONING_ID>` . Om du till exempel tilldelar kund klient organisationer O365_Business_Premium-licenser, ser det **LicenseAssignment** värdet ut så här: **syndikering-konto: O365_Business_Premium**. Du hittar PROVISIONING_IDs i syndikerings partner portalen som du har åtkomst till som syndikering eller CSP-partner.
    
#### <a name="import-the-csv-file-and-create-the-users"></a>Importera CSV-filen och skapa användare

När du har skapat CSV-filen kör du det här kommandot för att skapa användar konton med lösen ord som inte upphör att gälla när du loggar in för första gången och att den licens du anger tilldelas. Glöm inte att ersätta rätt CSV-fil.
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a>Se även

#### 

[Hjälp för partners](https://go.microsoft.com/fwlink/p/?LinkId=533477)

