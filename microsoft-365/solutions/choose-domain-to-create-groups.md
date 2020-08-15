---
title: Välj den domän som ska användas när du skapar Microsoft 365-grupper
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
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Lär dig hur du väljer den domän som ska användas när du skapar Microsoft 365 Groups genom att konfigurera principer för e-postadresser med PowerShell.
ms.openlocfilehash: 5ce0068f1b4562c37b2ccf2b1fb9a928b392a7ee
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686736"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Välj den domän som ska användas när du skapar Microsoft 365-grupper

Vissa organisationer använder separata e-postdomäner för att dela upp olika delar av verksamheten. Du kan ange vilken domän som ska användas när användarna skapar Microsoft 365 Groups.
  
Om din organisation behöver användare för att skapa grupper i andra domäner än den godkända domänen för ditt företag kan du tillåta detta genom att konfigurera e-postadress principer (principer) med PowerShell.

Innan du kan köra PowerShell-cmdlets laddar du ned och installerar en modul som låter dig prata med din organisation. Läs [Anslut till Exchange Online med fjärr-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).

## <a name="example-scenarios"></a>Exempel scenarier

Låt oss säga att företagets huvudsakliga domän är Contoso.com. Men organisationens standard domän är service.contoso.com. Det innebär att grupper skapas i service.contoso.com (till exempel jimsteam@service.contoso.com).
  
Låt oss säga att du också har konfigurerade under domäner i organisationen. Du vill att grupper ska skapas i dessa domäner också:
  
- students.contoso.com för studenter
    
- faculty.contoso.com för lärare och övrig personal
    
I följande två scenarier förklaras hur du gör det.

> [!NOTE]
> När du har flera principer utvärderas de i prioritetsordning. Värdet 1 innebär högsta prioritet. När ett EAP-nummer matchar har ingen ytterligare EAP utvärderats och adresser som har stämplats i gruppen är som följer den matchade EAP. > om ingen principer matchar de angivna villkoren får gruppen etableringen i organisationens standard domän. Mer information om hur du lägger till en godkänd domän finns i [Hantera godkända domäner i Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428).
  
### <a name="scenario-1"></a>Scenario 1

I följande exempel visas hur du kan etablera alla Microsoft 365-grupper i din organisation i groups.contoso.com-domänen.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Scenario 2

Låt oss säga att du vill kontrol lera vilka under domäner Microsoft 365-grupper skapas i. Du vill ha:
  
- Grupper som skapas av elever (användare som har en **avdelning** som är inställt på **studenter**) i students.Groups.contoso.com-domänen. Använd det här kommandot:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Grupper som skapas av lärare (användare som har en **avdelning** inställd på **lärare eller e-postadress innehåller Faculty.contoso.com)**) i Faculty.Groups.contoso.com-domänen. Använd det här kommandot:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Grupper som skapas av någon annan skapas i domänen groups.contoso.com. Använd det här kommandot:
    
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

Om organisationen har kon figurer ATS i ett hybrid scenario kan du läsa [Konfigurera Microsoft 365-grupper med lokal Exchange-hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) för att kontrol lera att din organisation uppfyller kraven för att skapa Microsoft 365-grupper. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Ytterligare information om hur du använder principer för e-postadresser:

Det finns några saker du bör känna till:
  
- Hur snabbt grupper skapas beror på hur många principer som är konfigurerade i organisationen.
    
- Administratörer och användare kan också ändra domäner när de skapar grupper.
    
- Grupper av användare bestäms med standardfrågorna (Användaregenskaper) som redan finns tillgängliga. Läs filter bara [Egenskaper för parametern-RecipientFilter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) för filter bara egenskaper som stöds. 
    
- Om du inte konfigurerar några principer för e-postadresser för grupper väljs den godkända standarddomänen när en grupp skapas.
    
- Om du tar bort en godkänd domän bör du uppdatera principerna för e-postadresser först - annars påverkas gruppetableringen.
    
- Högst 100 principer för e-postadresser kan konfigureras för en organisation.
    
## <a name="related-articles"></a>Relaterade artiklar

[Skapa en Microsoft 365-grupp i administrations centret](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
