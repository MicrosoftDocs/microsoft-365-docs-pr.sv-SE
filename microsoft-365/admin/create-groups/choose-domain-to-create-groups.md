---
title: Välj vilken domän som ska användas när Microsoft 365-grupper skapas
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'Lär dig att välja vilken domän du vill använda när du skapar Microsoft 365-grupper genom att konfigurera e-postadressprinciper med PowerShell. '
ms.openlocfilehash: 5569f42f15835be02a20166e64ce09a08b146dd7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44388215"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Välj vilken domän som ska användas när Microsoft 365-grupper skapas

 Vissa organisationer använder separata e-postdomäner för att dela upp olika delar av verksamheten. Du kan ange vilken domän som ska användas när användarna skapar Microsoft 365-grupper.
  
Om din organisation behöver användare för att skapa sina grupper i andra domäner än företagets standard accepterade domän kan du tillåta detta genom att konfigurera EPP-adresser (EAPs) med PowerShell.
  
Innan du kan köra PowerShell-cmdlets hämtar och installerar du en modul som låter dig prata med din organisation. Läs [Anslut till Exchange Online med fjärr-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).
  
## <a name="example-scenarios"></a>Exempel på scenarier

Anta att ditt företags huvuddomän är Contoso.com. Men organisationens standard accepterad domän är service.contoso.com. Det innebär att grupper skapas i service.contoso.com (till exempel jimsteam@service.contoso.com).
  
Anta att du också har konfigurerat underdomäner i organisationen. Du vill också att grupper ska skapas i dessa domäner:
  
- students.contoso.com för studenter
    
- faculty.contoso.com för lärare och övrig personal
    
Följande två scenarier förklarar hur du skulle åstadkomma detta.
  
> [!NOTE]
> När du har flera EA:er utvärderas de i prioritetsordning. Värdet 1 innebär högsta prioritet. När en EAP matchar utvärderas ingen ytterligare EAP och adresser som stämplas i gruppen är enligt den matchade EAP. > Om inga EAPs matchar de angivna villkoren etableras gruppen i organisationens standard accepterade domän. Mer information om hur du lägger till en godkänd domän finns i [Hantera godkända domäner i Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428). 
  
### <a name="scenario-1"></a>Scenario 1

I följande exempel visas hur du etablerar alla Microsoft 365-grupper i organisationen i domänen groups.contoso.com.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Scenario 2

Anta att du vill styra vilka underdomäner som Microsoft 365-grupper skapas i. Du vill ha:
  
- Grupper som skapats av studenter (användare som har **institutionen** inställd **på Studenter)** i domänen students.groups.contoso.com. Använd det här kommandot:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Grupper som skapats av fakultetsmedlemmar (användare som har **institutionen** inställd **på fakultet eller e-postadress innehåller faculty.contoso.com)**) i domänen faculty.groups.contoso.com. Använd det här kommandot:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Alla andra användare i domänen groups.contoso.com. Använd det här kommandot:
    
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

Om din organisation är konfigurerad i ett hybridscenario kan du läsa [Konfigurera Microsoft 365-grupper med lokal Exchange-hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) för att se till att din organisation uppfyller kraven för att skapa Microsoft 365-grupper. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Ytterligare information om hur du använder e-postadressprincipgrupper:

Det finns några fler saker att veta:
  
- Hur snabbt grupper skapas beror på antalet EAPs som konfigurerats i din organisation.
    
- Administratörer och användare kan också ändra domäner när de skapar grupper.
    
- Grupper av användare bestäms med standardfrågorna (Användaregenskaper) som redan finns tillgängliga. [Incheckning filterbara egenskaper för parametern -RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918) för filterbara egenskaper som stöds. 
    
- Om du inte konfigurerar några principer för e-postadresser för grupper väljs den godkända standarddomänen när en grupp skapas.
    
- Om du tar bort en godkänd domän bör du uppdatera principerna för e-postadresser först - annars påverkas gruppetableringen.
    
- Högst 100 principer för e-postadresser kan konfigureras för en organisation.
    
## <a name="related-articles"></a>Relaterade artiklar

[Skapa en Microsoft 365-grupp i administrationscentret](create-groups.md)
