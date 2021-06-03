---
title: Hantera Microsoft 365-grupper med PowerShell
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: I den här artikeln får du lära dig hur du utför vanliga administrativa uppgifter Microsoft 365 grupper i PowerShell.
ms.openlocfilehash: 22bf4d1f3187746483d8d904378e675562a62142
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730564"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Hantera Microsoft 365-grupper med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

I den här artikeln beskrivs hur du utför vanliga administrativa uppgifter för grupper i Microsoft PowerShell. Den innehåller även PowerShell-cmdlets för grupper. Information om hur du hanterar SharePoint-webbplatser finns i [Hantera SharePoint Online-webbplatser med PowerShell.](/sharepoint/manage-team-and-communication-sites-in-powershell)

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Länk till dina riktlinjer Microsoft 365 Grupper
<a name="BK_LinkToGuideLines"> </a>

När användare [skapar eller redigerar en grupp i Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)kan du visa dem en länk till organisationens riktlinjer för användning. Det kan till exempel vara att ett visst prefix eller suffix ska läggas till i gruppnamnet.

Använd PowerShell Azure Active Directory (Azure AD) för att få användarna att peka på organisationens riktlinjer för användning Microsoft 365 grupper. Läs mer [Azure Active Directory cmdlets för](/azure/active-directory/enterprise-users/groups-settings-cmdlets) att konfigurera gruppinställningar  och följ stegen i Skapa inställningar på katalognivån för att definiera hyperlänken till riktlinje för användning. När du kör cmdleten AAD ser användarna länken till dina riktlinjer när de skapar eller redigerar en grupp i Outlook.

![Skapa en ny grupp med länken för riktlinjer för användning](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Klicka på Riktlinjer för användning av grupp om du vill se organisationens Office 365 för grupper](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Tillåt användare att skicka som Microsoft 365 grupp
<a name="BK_LinkToGuideLines"> </a>

Om du vill aktivera dina Microsoft 365-grupper till "Skicka som" använder du [cmdletarna Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) och [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) för att konfigurera detta. När du har aktiverar den Microsoft 365 gruppanvändare använda Outlook eller Outlook på webben för att skicka och svara på e-post Microsoft 365 gruppen. Användare kan gå till gruppen, skapa ett nytt e-postmeddelande och ändra fältet "Skicka som" till gruppens e-postadress.

([Du kan också göra det Exchange administrationscentret](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)

Använd följande skript, som ersätter med alias för den grupp som du vill uppdatera och med alias för den användare *\<GroupAlias\>* som du vill tilldela *\<UserAlias\>* behörigheter. [Anslut att Exchange Online PowerShell för](/powershell/exchange/connect-to-exchange-online-powershell) att köra det här skriptet.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

När cmdleten körs kan användare gå till Outlook eller Outlook på webben för att skicka som gruppen genom att lägga till gruppens e-postadress i fältet **Från.**

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Skapa klassificeringar för Microsoft 365 grupper i organisationen

Du kan skapa känslighetsetiketter som användarna i organisationen kan ange när de skapar en Microsoft 365 grupp. Om du vill klassificera grupper rekommenderar vi att du använder känslighetsetiketter i stället för den tidigare klassificeringsfunktionen för grupper. Mer information om hur du använder känslighetsetiketter finns i Använda känslighetsetiketter för att skydda innehåll i [Microsoft Teams, Microsoft 365 grupper och SharePoint webbplatser.](../compliance/sensitivity-labels-teams-groups-sites.md)

> [!IMPORTANT]
> Om du använder klassificeringsetiketter är de inte längre tillgängliga för användare som skapar grupper när känslighetsetiketter har aktiverats.

Du kan fortfarande använda den tidigare klassificeringsfunktionen för grupper. Du kan skapa klassificeringar som användarna i organisationen kan ange när de skapar en Microsoft 365 grupp. Du kan till exempel tillåta att användare anger "Standard", "Hemlig" och "Top Secret" för grupper som de skapar. Gruppklassificeringarna anges inte som standard och du måste skapa dem för att användarna ska kunna ange dem. Använd Azure Active Directory PowerShell för att få användarna att peka på organisationens riktlinjer för användning Microsoft 365 Groups.

Läs mer [Azure Active Directory cmdlets](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) för att konfigurera gruppinställningar  och följ stegen i Skapa inställningar på katalognivån för att definiera klassificeringen för Microsoft 365 grupper.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

För att koppla en beskrivning till varje klassificering kan du använda inställningsattributet *Klassificeringsbeskrivningar.*

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

där Klassificering matchar strängarna i Klassificeringslistan.

Exempel:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

När du har kört Azure Active Directory-cmdleten ovan för att ange din klassificering kör du cmdleten [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) om du vill ange klassificeringen för en viss grupp.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Eller skapa en ny grupp med en klassificering.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Läs [Använda PowerShell med Exchange Online](/powershell/exchange/exchange-online-powershell) och [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) om du vill ha mer information om hur du använder Exchange Online PowerShell.

När de här inställningarna har aktiverats kan gruppägaren välja en klassificering från listmenyn i Outlook på webben och  Outlook och spara den från sidan Redigera grupp.

![Välj Microsoft 365 gruppklassificering](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Dölj Microsoft 365 grupper i den globala adresslistan.
<a name="BKMK_CreateClassification"> </a>

Du kan ange om en Microsoft 365 grupp ska visas i den globala adresslistan (GAL) och andra listor i organisationen. Om du till exempel har en juridisk avdelningsgrupp som du inte vill ska visas i adresslistan kan du hindra att den gruppen visas i GAL. Kör cmdleten Set-Unified Grupp för att dölja gruppen från adresslistan så här:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Tillåt endast interna användare att skicka meddelanden till Microsoft 365 grupper
<a name="BKMK_CreateClassification"> </a>

Om du inte vill att användare från andra organisationer ska skicka e-postmeddelanden till Microsoft 365 grupp kan du ändra inställningarna för den gruppen. Då kan endast interna användare skicka e-postmeddelanden till gruppen. Om en extern användare försöker skicka ett meddelande till den gruppen avvisas det.

Kör cmdleten Set-UnifiedGroup för att uppdatera den här inställningen, så här:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Lägga till e-posttips Microsoft 365 grupper
<a name="BKMK_CreateClassification"> </a>

När en avsändare försöker skicka ett e-postmeddelande till Microsoft 365 grupp visas ett e-posttips för dem.

Kör cmdleten Set-Unified Grupp för att lägga till ett e-posttips i gruppen:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Tillsammans med e-posttips kan du också ange MailTipTranslations, som anger ytterligare språk för e-posttipset. Anta att du vill ha den spanska översättningen och kör sedan följande kommando:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Ändra visningsnamnet för gruppen Microsoft 365 grupp

Visningsnamnet anger namnet på gruppen Microsoft 365 grupp. Du kan se det här namnet i administrationscentret för Exchange Microsoft 365 administrationscenter. Du kan redigera visningsnamnet för gruppen eller tilldela ett visningsnamn till en befintlig grupp Microsoft 365 genom att köra kommandot Set-UnifiedGroup namn:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Ändra standardinställningen för gruppen Microsoft 365 för Outlook till offentlig eller privat
<a name="BKMK_CreateClassification"> </a>

Microsoft 365 Grupper i Outlook skapas som privata som standard. Om organisationen vill att Microsoft 365 grupper ska skapas som offentliga som standard (eller tillbaka till privata) använder du följande syntax för PowerShell-cmdlet:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Så här anger du den till Privat:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Så här verifierar du inställningen:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Mer information finns i [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) och [Get-OrganizationConfig.](/powershell/module/exchange/get-organizationconfig)

## <a name="microsoft-365-groups-cmdlets"></a>Microsoft 365 Cmdlets för grupper

Följande cmdlets kan användas med Microsoft 365 Grupper.

|**Cmdlet-namn**|**Beskrivning**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |Använd denna cmdlet för att slå upp Microsoft 365 grupper och för att visa egenskaper för gruppobjektet  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |Uppdatera egenskaperna för en viss Microsoft 365 grupp  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |Skapa en ny Microsoft 365 grupp. Den här cmdleten innehåller en minimal uppsättning parametrar. Om du vill ange värden för utökade egenskaper använder Set-UnifiedGroup när du har skapat den nya gruppen  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |Ta bort en Microsoft 365 grupp  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |Hämta information om medlemskap och ägare för en Microsoft 365 grupp  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |Lägga till medlemmar, ägare och prenumeranter i en Microsoft 365 grupp <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |Ta bort ägare och medlemmar från en befintlig Microsoft 365 grupp  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |Används för att visa information om användarfotot som är kopplat till ett konto. Användarfoton lagras i Active Directory  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |Används för att koppla ett användarfoto till ett konto. Användarfoton lagras i Active Directory  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |Ta bort fotot för en Microsoft 365 grupp  <br/> |

## <a name="related-topics"></a>Relaterade ämnen

[Uppgradera distributionslistor till Microsoft 365 grupper](/office365/admin/manage/upgrade-distribution-lists)

[Hantera vilka som kan skapa Microsoft 365 Grupper](/office365/admin/create-groups/manage-creation-of-groups)

[Hantera gäståtkomst till Microsoft 365 grupper](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Ändra statiska gruppmedlemskap till dynamiskt i](/azure/active-directory/users-groups-roles/groups-change-type)
