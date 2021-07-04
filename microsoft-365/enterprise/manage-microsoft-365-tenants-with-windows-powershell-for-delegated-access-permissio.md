---
title: Hantera Microsoft 365 med Windows PowerShell dap-partner
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
description: I den här artikeln lär du dig att använda PowerShell för Microsoft 365 att hantera dina kundantag.
ms.openlocfilehash: 96c2c148b64d638ea977922f6a0ae3d5e23a8ace
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289109"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Hantera Microsoft 365-klientorganisationen med Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Windows PowerShell tillåter att Syndication- och Molnlösningsleverantör-partner (CSP) enkelt kan administrera och rapportera inställningar för kundföretag som inte är tillgängliga i Administrationscenter för Microsoft 365. Observera att Behörigheten Administrera för AOBO krävs för att partneradministratörens konto ska kunna ansluta till sina kundantag.

DAP-partner (Delegerad åtkomstbehörighet) är syndicerings- och molnlösningsleverantörer (CSP). De är ofta nätverks- eller telekommunikationsleverantörer till andra företag. De paketar Microsoft 365 prenumerationer till sina tjänsteerbjudanden till sina kunder. När de säljer en Microsoft 365-prenumeration tilldelas de automatiskt behörigheten Administrera för (AOBO) för kundens företag så att de kan administrera och rapportera om kundrelationerna.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Procedurerna i det här avsnittet kräver att du ansluter [till Anslut och Microsoft 365 med PowerShell.](connect-to-microsoft-365-powershell.md)

Du behöver också autentiseringsuppgifterna för partnerklientorganisationen.

## <a name="what-do-you-want-to-do"></a>Vad vill du göra?

### <a name="list-all-tenant-ids"></a>Visa alla klientorganisations-ID

> [!NOTE]
> Om du har fler än 500 innehavare kan du begränsa cmdlet-syntaxen med _antingen -All_ eller _-MaxResultsParameter._ Det här gäller andra cmdlets som kan ge stora utdata, till exempel **Get-MsolUser.**

Om du vill visa alla klientorganisations-ID:n som du har tillgång till kör du det här kommandot.

```powershell
Get-MsolPartnerContract -All | Select-Object TenantId
```

Då visas en lista över alla dina kundklienter efter **TenantId.**

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.
>

### <a name="get-a-tenant-id-by-using-the-domain-name"></a>Hämta ett klientorganisations-ID genom att använda domännamnet

Kör det här **kommandot för att** få klientorganisationens ID för en viss kundklient genom att köra det här kommandot. Ersätt _<domainname.onmicrosoft.com>_ domännamnet för den kundklientorganisation som du vill använda.

```powershell
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a>Lista alla domäner för en klientorganisation

Om du vill skaffa alla domäner för en kundklientorganisation kör du det här kommandot. Ersätt  _<customer TenantId value>_ med det faktiska värdet.

```powershell
Get-MsolDomain -TenantId <customer TenantId value>
```

Om du har registrerat ytterligare domäner returneras alla domäner som är kopplade till kundens **Klientorganisations-ID.**

### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a>Få en mappning av alla klienter och registrerade domäner

I de tidigare kommandona för PowerShell för Microsoft 365 visades hur du hämtar antingen klientorganisations-ID:er eller domäner, men inte båda samtidigt, och utan en tydlig mappning mellan dem alla. Det här kommandot genererar en lista över alla dina klientorganisations-ID och deras domäner.

```powershell
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a>Skaffa alla användare för en klientorganisation

Då visas **UserPrincipalName,** **DisplayName** och **statusen ärLicensed för** alla användare för en viss klientorganisation. Ersätt _<customer TenantId value>_ med det faktiska värdet.

```powershell
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a>Få all information om en användare

Om du vill se alla egenskaper för en viss användare kör du det här kommandot. Ersätt  _<customer TenantId value>_ och med de faktiska _<user principal name value>_ värdena.

```powershell
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a>Lägga till användare, ange alternativ och tilldela licenser

Att massskapa, konfigurera och licensiera Microsoft 365 är särskilt effektivt med PowerShell för Microsoft 365. I den här tvåstegsprocessen skapar du först poster för alla användare som du vill lägga till i en fil med kommaavgränsade värden (CSV) och sedan importerar du filen med PowerShell för Microsoft 365.

#### <a name="create-a-csv-file"></a>Skapa en CSV-fil

Skapa en CSV-fil med det här formatet:

`UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`

där:

- **Användninglokalisering:** Värdet för det här är användarens ISO-lands-/regionskod på två bokstäver. Landskoderna/regionskoderna kan du hitta på[ISO-webbplattformen online.](https://go.microsoft.com/fwlink/p/?LinkId=532703) Koden för USA är till exempel USA och koden för Brasilien är BR.

- **LicenseAssignment:** Värdet för det här använder följande format: `syndication-account:<PROVISIONING_ID>` . Om du till exempel tilldelar kunder klientorganisationsanvändare O365_Business_Premium licenser ser värdet **Licenstilldelning** ut så här: **syndication-account:O365_Business_Premium**. Du hittar de PROVISIONING_IDs i Syndication-partnerportalen som du har åtkomst till som Syndication- eller CSP-partner.

#### <a name="import-the-csv-file-and-create-the-users"></a>Importera CSV-filen och skapa användarna

När du har skapat CSV-filen kör du det här kommandot för att skapa användarkonton med lösenord som inte upphör att gälla och som användaren måste ändra vid första inloggningen och som tilldelar licensen du anger. Se till att ersätta rätt CSV-filnamn.

```powershell
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a>Se även

[Hjälp för partners](https://go.microsoft.com/fwlink/p/?LinkId=533477)
