---
title: Välj den domän som ska användas när du skapar Microsoft 365 grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
recommendations: false
description: Lär dig att välja den domän som ska användas när du Microsoft 365 grupper genom att konfigurera principer för e-postadresser med PowerShell.
ms.openlocfilehash: 4d620c3344f83f56afd05c00d78615331dd413ed
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583154"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Välj den domän som ska användas när du skapar Microsoft 365 grupper

Vissa organisationer använder separata e-postdomäner för att dela upp olika delar av verksamheten. Du kan ange vilken domän som ska användas när användarna skapar Microsoft 365 grupper.
  
Om din organisation kräver att användare skapar sina grupper i andra domäner än den godkända standarddomänen för ditt företag kan du tillåta det genom att konfigurera principer för e-postadresser med PowerShell.

Innan du kan köra PowerShell-cmdlets laddar du ned och installerar en modul som gör att du kan prata med din organisation. Läs [Anslut till Exchange Online med fjärr-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="example-scenarios"></a>Exempelscenarier

Anta att företagets huvuddomän är en Contoso.com. Men din organisations godkända standarddomän är service.contoso.com. Det innebär att grupper skapas i service.contoso.com (till exempel jimsteam@service.contoso.com).
  
Anta att du även har underdomäner konfigurerade i din organisation. Du vill också att grupper ska skapas i dessa domäner:
  
- students.contoso.com för studenter
    
- faculty.contoso.com för lärare och övrig personal
    
I följande två scenarier förklaras hur du ska göra detta.

> [!NOTE]
> Om du har flera EP:er utvärderas de i prioritetsordning. Värdet 1 innebär högsta prioritet. När en e-postadresser matchar utvärderas inte några ytterligare e-postadresser och adresser som märks i gruppen godkänns enligt den matchande e-postadresser. > om inga e-postprogram matchar de angivna villkoren får gruppen etableras i organisationens godkända standarddomän. Mer information om hur du lägger till en godkänd domän finns i [Hantera godkända domäner i Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
  
### <a name="scenario-1"></a>Scenario 1

Följande exempel visar hur du etablerar alla Microsoft 365 grupper i organisationen i groups.contoso.com domän.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Scenario 2

Anta att du vill styra vilka underdomäner Microsoft 365 grupper skapas i. Du vill ha:
  
- Grupper som skapas av elever (användare där **Avdelning har** **angetts till Studenter**) i students.groups.contoso.com domän. Använd det här kommandot:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Grupper som skapas av lärare  och andra (användare där Avdelning har angetts till Lärare eller E-postadress **innehåller faculty.contoso.com)** i faculty.groups.contoso.com domän. Använd det här kommandot:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Grupper som har skapats av någon annan skapas i groups.contoso.com domän. Använd det här kommandot:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>Ändra principer för e-postadresser

Använd cmdleten Set-EmailAddressPolicy för att ändra mallar för prioritet eller e-postadress för en befintlig princip för e-postadresser.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

Om en princip för e-postadresser ändras påverkar det inte de grupper som redan har etablerats.
  
## <a name="delete-email-address-policies"></a>Ta bort principer för e-postadresser

Använd cmdleten Remove-EmailAddressPolicy om du vill ta bort en princip för e-postadresser.
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

Om en princip för e-postadresser ändras påverkar det inte de grupper som redan har etablerats.
  
## <a name="hybrid-requirements"></a>Hybridkrav

Om organisationen är konfigurerad i ett hybridscenario kan du läsa Konfigurera Microsoft 365-grupper med en lokal [Exchange-hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) för att kontrollera att organisationen uppfyller kraven för att Microsoft 365 grupper. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Mer information om hur du använder principer för e-postadresser:

Det finns några fler saker att veta:
  
- Hur snabbt grupper skapas beror på hur många e-skaps som konfigurerats i din organisation.
    
- Administratörer och användare kan också ändra domäner när de skapar grupper.
    
- Grupper av användare bestäms med standardfrågorna (Användaregenskaper) som redan finns tillgängliga. Information om [filtrerbara egenskaper som stöds finns i Filtrerbara egenskaper för parametern -RecipientFilter.](/powershell/exchange/recipientfilter-properties) 
    
- Om du inte konfigurerar några principer för e-postadresser för grupper väljs den godkända standarddomänen när en grupp skapas.
    
- Om du tar bort en godkänd domän bör du uppdatera principerna för e-postadresser först - annars påverkas gruppetableringen.
    
- Högst 100 principer för e-postadresser kan konfigureras för en organisation.
    
## <a name="related-content"></a>Relaterat innehåll

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (artikel)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md) (artikel)

[Skapa en Microsoft 365 grupp i administrationscentret](../admin/create-groups/create-groups.md) (artikel)