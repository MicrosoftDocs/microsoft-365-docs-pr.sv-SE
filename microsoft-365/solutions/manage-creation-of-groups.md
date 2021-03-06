---
title: Hantera vilka som kan skapa Microsoft 365 Grupper
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
recommendations: false
description: Lär dig hur du styr vilka användare som kan Microsoft 365 grupper.
ms.openlocfilehash: 19a106d255708f4b1df8f798219ea7ea778bbef3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539185"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Hantera vilka som kan skapa Microsoft 365 Grupper

Som standard kan alla användare skapa Microsoft 365 grupper. Det här är den rekommenderade metoden eftersom den gör att användarna kan börja samarbeta utan att behöva hjälp från IT-

Om ditt företag kräver att du begränsar vem som kan skapa grupper kan du begränsa möjligheten Microsoft 365 till att skapa grupper till medlemmar i en Microsoft 365 grupp eller säkerhetsgrupp.

Om du är orolig för användare som skapar team eller grupper som inte uppfyller dina affärsstandarder kan du överväga att kräva att användare slutför en kurs och sedan lägger till dem i gruppen med tillåtna användare.

När du begränsar vem som kan skapa en grupp påverkar det alla tjänster som är beroende av grupper för åtkomst, inklusive:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (klassisk)
- Project för webben/Översikt

Stegen i den här artikeln hindrar inte medlemmar i vissa roller från att skapa grupper. Office 365 Globala administratörer kan skapa grupper via Microsoft 365, Planner, Exchange och SharePoint Online. Andra roller kan skapa grupper på ett begränsat sätt, som anges nedan.

- Exchange Administratör: Exchange administrationscenter, Azure AD
- Partner Tier1-support: Microsoft 365, administrationscentret Exchange, Azure AD
- Partner Tier2-support: Microsoft 365 administrationscenter, Exchange administrationscenter, Azure AD
- Katalogskrivare: Azure AD
- SharePoint Administratör: SharePoint administrationscenter, Azure AD
- Teams Tjänstadministratör: Teams administrationscenter, Azure AD
- Användaradministratör: Microsoft 365 administrationscenter, Azure AD

Om du har en av dessa roller kan du skapa Microsoft 365 grupper för begränsade användare och sedan tilldela användaren som gruppens ägare.

## <a name="licensing-requirements"></a>Licensieringskrav

För att hantera vem som skapar grupper behöver följande personer Azure AD Premium-licenser eller Azure AD Basic EDU-licenser tilldelade till dem:

- Administratören som konfigurerar inställningarna för att skapa grupper
- Medlemmar i gruppen som har tillåtelse att skapa grupper

> [!NOTE]
> Se [Tilldela eller ta bort licenser Azure Active Directory portal](/azure/active-directory/fundamentals/license-users-groups) för mer information om hur du tilldelar Azure-licenser.

Följande personer behöver inte ha Azure AD Premium- eller Azure AD Basic EDU-licenser tilldelade till sig:

- Personer som är medlemmar Microsoft 365 grupper och som inte har möjlighet att skapa andra grupper.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Steg 1: Skapa en grupp för användare som behöver skapa Microsoft 365 grupper

Endast en grupp i organisationen kan användas för att styra vem som kan skapa grupper. Du kan däremot kapsla in andra grupper som medlemmar i den här gruppen.

Administratörer i de roller som anges ovan behöver inte vara medlemmar i den här gruppen: de behåller sin förmåga att skapa grupper.

1. Gå till sidan Grupper i [administrationscentret.](https://admin.microsoft.com/adminportal/home#/groups)

2. Klicka på Lägg **till en grupp.**

3. Välj den grupptyp du vill använda. Kom ihåg namnet på gruppen! Du behöver det senare.

4. Konfigurera gruppen och lägg till personer eller andra grupper som du vill ska kunna skapa grupper i organisationen.

Detaljerade instruktioner finns i [Skapa, redigera eller ta bort en säkerhetsgrupp i Microsoft 365 administrationscenter.](../admin/email/create-edit-or-delete-a-security-group.md)

## <a name="step-2-run-powershell-commands"></a>Steg 2: Kör PowerShell-kommandon

Du måste använda förhandsversionen av Azure Active Directory PowerShell för [Graph (AzureAD) (modulnamnet](/powershell/azure/active-directory/install-adv2) **AzureADPreview)** om du vill ändra inställningen för gäståtkomst på gruppnivå:

- Om du inte har installerat någon version av Azure AD PowerShell-modulen tidigare, se Installera [Azure AD-modulen](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) och följ anvisningarna för att installera den offentliga förhandsversionen.

- Om du har den 2.0 allmänt tillgängliga versionen av Azure AD PowerShell-modulen (AzureAD) installerad måste du avinstallera den genom att köra den i PowerShell-sessionen och sedan installera förhandsversionen genom att köra `Uninstall-Module AzureAD` `Install-Module AzureADPreview` .

- Om du redan har installerat förhandsgranskningsversionen kör `Install-Module AzureADPreview` du för att kontrollera att det är den senaste versionen av den här modulen.

Kopiera skriptet nedan till en textredigerare, till exempel Anteckningar, eller till [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Ersätt *\<GroupName\>* med namnet på gruppen du skapade. Till exempel:

`$GroupName = "Group Creators"`

Spara filen som GroupCreators.ps1.

I PowerShell-fönstret går du till den plats där du sparade filen (skriv <FileLocation> "CD").

Kör skriptet genom att skriva:

`.\GroupCreators.ps1`

och [logga in med ditt administratörskonto när](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) du uppmanas att göra det.

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
    $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

Den sista raden i skriptet visar de uppdaterade inställningarna:

![Skärmbild av PowerShell-skriptresultat.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Om du senare vill ändra vilken grupp som används kan du köra skriptet igen med namnet på den nya gruppen.

Om du vill inaktivera begränsningen för att skapa grupper och återigen tillåta alla användare att skapa grupper anger du $GroupName till "" och $AllowGroupCreation till "True" och kör skriptet igen.

## <a name="step-3-verify-that-it-works"></a>Steg 3: Kontrollera att det fungerar

Det kan ta trettio minuter eller mer innan ändringarna har verkställs. Du kan kontrollera de nya inställningarna genom att göra följande:

1. Logga in Microsoft 365 konto med ett användarkonto för någon som INTE ska ha möjlighet att skapa grupper. De är då inte medlemmar i gruppen du skapade eller en administratör.

2. Välj **panelen Planner.**

3. I Planner väljer du **Ny plan i** det vänstra navigeringsfältet för att skapa en plan.

4. Du bör få ett meddelande om att plan och skapande av grupper är inaktiverat.

Prova samma procedur igen när du är medlem i gruppen.

> [!NOTE]
> Om medlemmar i gruppen inte kan skapa grupper kontrollerar du att de inte blockeras av sin [OWA-postlådeprincip.](/powershell/module/exchange/set-owamailboxpolicy)

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)

[Komma igång med Office 365 PowerShell](../enterprise/getting-started-with-microsoft-365-powershell.md)

[Konfigurera grupphantering med självbetjäning i Azure Active Directory](/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory cmdlets för att konfigurera gruppinställningar](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
