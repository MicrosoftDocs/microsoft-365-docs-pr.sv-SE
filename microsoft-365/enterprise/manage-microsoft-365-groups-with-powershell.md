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
description: I den här artikeln lär du dig hur du utför vanliga hanterings uppgifter för Microsoft 365-grupper i PowerShell.
ms.openlocfilehash: 1cad2aa39a6b106cbb4dbfbafa995899b2442ed1
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830621"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Hantera Microsoft 365-grupper med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

I den här artikeln finns anvisningar för att utföra vanliga hanterings uppgifter för grupper i Microsoft PowerShell. Dessutom visas PowerShell-cmdletar för grupper. Information om hur du hanterar SharePoint-webbplatser finns i [hantera SharePoint Online-webbplatser med PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Länk till dina användnings rikt linjer för Microsoft 365-grupper
<a name="BK_LinkToGuideLines"> </a>

När användare [skapar eller redigerar en grupp i Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)kan du visa dem en länk till organisationens rikt linjer för användning. Om du till exempel vill lägga till ett prefix eller suffix i ett grupp namn.

Använd Azure Active Directory (Azure AD) PowerShell för att hänvisa användarna till organisationens användnings rikt linjer för Microsoft 365 Groups. Kolla in [Azure Active Directory-cmdlets för att konfigurera grupp inställningar](https://go.microsoft.com/fwlink/?LinkID=827484) och följ stegen i **skapa inställningar på katalog nivå** för att definiera länken för användnings rikt linjer. När du kör AAD-cmdleten visas länken till dina rikt linjer när de skapar eller redigerar en grupp i Outlook.

![Skapa en ny grupp med länken för användnings regler](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Klicka på rikt linjer för grupp användning för att se dina organisationers Office 365-regler](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Tillåt användare att skicka som Microsoft 365-grupp
<a name="BK_LinkToGuideLines"> </a>

Om du vill aktivera dina Microsoft 365-grupper till "Skicka som" använder du cmdletarna [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) och [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) för att konfigurera detta. När du aktiverar den här inställningen kan Microsoft 365 Group-användare använda Outlook eller Outlook på webben för att skicka och svara på e-post som Microsoft 365-gruppen. Användare kan gå till gruppen, skapa ett nytt e-postmeddelande och ändra fältet "Skicka som" till gruppens e-postadress.

([Du kan också göra det i administrations centret för Exchange](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)

Använd följande skript, Ersätt *\<GroupAlias\>* med alias för den grupp du vill uppdatera och *\<UserAlias\>* med alias för den användare som du vill ge behörighet till. [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) för att köra det här skriptet.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

När cmdleten körs kan användarna gå till Outlook eller Outlook på webben och skicka som grupper genom att lägga till gruppens e-postadress i fältet **från** .

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Skapa klassificeringar för Microsoft 365-grupper i organisationen

Du kan skapa känslighets etiketter som användarna i organisationen kan ange när de skapar en Microsoft 365-grupp. Om du vill klassificera grupper rekommenderar vi att du använder känslighets etiketter i stället för de tidigare funktionerna för grupp klassificering. Information om hur du använder känslighets etiketter finns i [använda känslighets etiketter för att skydda innehåll i Microsoft Teams, microsoft 365 Groups och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!IMPORTANT]
> Om du använder klassificerings etiketter är de inte längre tillgängliga för användare som skapar grupper när du har aktiverat känslighets etiketter.

Du kan fortfarande använda den föregående gruppen klassificerings funktion. Du kan skapa klassificeringar som användarna i organisationen kan ange när de skapar en Microsoft 365-grupp. Du kan till exempel låta användarna ställa in "standard", "hemligt" och "Top Secret" i grupper som de skapar. Grupp klassificeringar är inte standard och du måste skapa det för att användarna ska kunna ställa in den. Använd Azure Active Directory PowerShell för att hänvisa användarna till organisationens användnings rikt linjer för Microsoft 365 Groups.

Kolla in [Azure Active Directory-cmdlets för att konfigurera grupp inställningar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) och följ stegen i **skapa inställningar på katalog nivå** för att definiera klassificeringen för Microsoft 365-grupper.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Om du vill koppla en beskrivning till varje klassificering kan du använda attributet Settings  *klassificerings beskrivningar* för att definiera.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

där klassificering matchar strängarna i klassificerings lista.

Exempel:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

När du har kört den här Azure Active Directory-cmdleten för att ange din klassificering kör du cmdleten [set-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) om du vill ange klassificering för en viss grupp.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Eller skapa en ny grupp med en klassificering.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Läs [Använda PowerShell med Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) och [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) om du vill ha mer information om hur du använder Exchange Online PowerShell.

När de här inställningarna är aktiverade kan gruppens ägare välja en klassificering från den nedrullningsbara menyn i Outlook på webben och i Outlook och sedan spara den från sidan **Redigera** grupp.

![Välj Microsoft 365-grupp klassificering](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Dölj Microsoft 365-grupper från den globala adress listan.
<a name="BKMK_CreateClassification"> </a>

Du kan ange om en Microsoft 365-grupp visas i den globala adress listan (GAL) och andra listor i organisationen. Om du till exempel har en juridisk avdelnings grupp som du inte vill visa i adress listan kan du stoppa gruppen från att visas i GAL. Kör cmdleten Set-Unified Group för att dölja gruppen från adress listan så här:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Tillåt endast interna användare att skicka meddelanden till Microsoft 365-grupper
<a name="BKMK_CreateClassification"> </a>

Om du inte vill att användare från andra organisationer ska kunna skicka e-post till en Microsoft 365-grupp kan du ändra inställningarna för gruppen. Den tillåter bara interna användare att skicka ett e-postmeddelande till din grupp. Om en extern användare försöker skicka ett meddelande till gruppen kommer den att nekas.

Kör cmdleten Set-UnifiedGroup för att uppdatera inställningen, så här:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Lägga till e-posttips för Microsoft 365-grupper
<a name="BKMK_CreateClassification"> </a>

När en avsändare försöker skicka ett e-postmeddelande till en Microsoft 365-grupp kan en posttips visas för dem.

Kör cmdleten Set-Unified Group för att lägga till en posttips i gruppen:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Tillsammans med posttips kan du också ange MailTipTranslations som anger ytterligare språk för posttips. Anta att du vill ha en spansk översättning och kör följande kommando:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Ändra visnings namnet för Microsoft 365-gruppen

Visnings namnet anger namnet på Microsoft 365-gruppen. Du kan se detta namn i administrations centret för Exchange eller Microsoft 365 Admin Center. Du kan redigera gruppens visnings namn eller tilldela ett visnings namn till en befintlig Microsoft 365-grupp genom att köra kommandot Set-UnifiedGroup:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Ändra standardinställningen för Microsoft 365 Groups för Outlook till offentlig eller privat
<a name="BKMK_CreateClassification"> </a>

Microsoft 365-grupper i Outlook skapas som privata som standard. Om din organisation vill att Microsoft 365-grupper ska skapas som offentliga som standard (eller tillbaka till privat) använder du följande PowerShell-cmdlet:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Så här anger du till privat:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Så här kontrollerar du inställningen:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Mer information finns i [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).

## <a name="microsoft-365-groups-cmdlets"></a>Cmdlets för Microsoft 365 Groups

Följande cmdletar kan användas med Microsoft 365 Groups.

|**Namn på cmdlet**|**Beskrivning**|
|:-----|:-----|
|[Get-Unifiedgrouphttps](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |Använd denna cmdlet för att slå upp befintliga Microsoft 365-grupper och för att visa egenskaperna för gruppobjektet  <br/> |
|[Set-Unifiedgrouphttps](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |Uppdatera egenskaperna för en viss Microsoft 365-grupp  <br/> |
|[New-Unifiedgrouphttps](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |Skapa en ny Microsoft 365-grupp. Denna cmdlet ger en minimal uppsättning parametrar. Om du vill ange värden för utökade egenskaper kan du använda Set-UnifiedGroup när du har skapat den nya gruppen  <br/> |
|[Remove-Unifiedgrouphttps](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |Ta bort en befintlig Microsoft 365-grupp  <br/> |
|[Get-Unifiedgrouplinkshttps](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |Hämta information om medlemskap och ägare för en Microsoft 365-grupp  <br/> |
|[Add-Unifiedgrouplinkshttps](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |Lägga till medlemmar, ägare och abonnenter i en befintlig Microsoft 365-grupp <br/> |
|[Remove-Unifiedgrouplinkshttps](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |Ta bort ägare och medlemmar från en befintlig Microsoft 365-grupp  <br/> |
|[Get-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |Används för att visa information om användar fotot som är kopplat till ett konto. Användar foton lagras i Active Directory  <br/> |
|[Set-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |Används för att koppla en användar bild till ett konto. Användar foton lagras i Active Directory  <br/> |
|[Remove-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |Ta bort fotot för en Microsoft 365-grupp  <br/> |

## <a name="related-topics"></a>Relaterade ämnen

[Uppgradera distributions listor till Microsoft 365-grupper](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[Hantera vilka som kan skapa Microsoft 365 Grupper](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[Hantera gäst åtkomst till Microsoft 365-grupper](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Ändra medlemskap i statisk grupp till dynamisk i](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
