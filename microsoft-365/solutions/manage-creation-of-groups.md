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
description: Lär dig hur du styr vilka användare som kan skapa Microsoft 365-grupper.
ms.openlocfilehash: 2954f68dce289d43b37bf8f5c6ff43fe1b5c48c7
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613569"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Hantera vilka som kan skapa Microsoft 365 Grupper

Som standard kan alla användare skapa Microsoft 365-grupper. Det här är den rekommenderade metoden eftersom användarna kan börja samar beta utan att behöva använda det.

Om ditt företag kräver att du begränsar vem som kan skapa grupper kan du göra det genom att följa anvisningarna i den här artikeln. När du begränsar vem som kan skapa en grupp påverkas alla tjänster som är beroende av grupper för åtkomst, till exempel:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (klassisk)
- Projekt för webben/översikt

Du kan förhindra att Microsoft 365-grupper skapas för medlemmar i en viss säkerhets grupp. För att konfigurera det här använder du Windows PowerShell. I den här artikeln får du stegvisa instruktioner.

Åtgärderna i den här artikeln hindrar inte medlemmar från vissa roller från att skapa grupper. Office 365 globala administratörer kan skapa grupper på något sätt, till exempel Microsoft 365 Admin Center, Planner, team, Exchange och SharePoint Online. Andra roller kan skapa grupper via begränsade sätt, i listan nedan.

- Exchange-administratör: administrations Center för Exchange, Azure AD
- Support för partner nivå 1: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD
- Partner nivå 2: support för Microsoft 365 Admin Center, Exchange Admin Center, Azure AD
- Katalog författare: Azure AD
- SharePoint-administratör: administrations Center för SharePoint, Azure AD
- Team tjänst administratör: administrations Center för Teams, Azure AD
- Användar hanterings administratör: Microsoft 365 Admin Center, Yammer, Azure AD

Om du är medlem i en av de här rollerna kan du skapa Microsoft 365-grupper för användare med begränsad behörighet och sedan koppla användaren till gruppen.

## <a name="licensing-requirements"></a>Licens krav

För att hantera vem som skapar grupper måste följande personer ha Azure AD Premium-licenser eller Azure AD Basic EDU-licenser tilldelade till dem:

- Administratören som konfigurerar dessa inställningar för grupp skapande
- Medlemmar i säkerhets gruppen som får skapa grupper

> [!NOTE]
> Se [tilldela eller ta bort licenser i Azure Active Directory-portalen](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) för mer information om hur du tilldelar Azure-licenser.

Följande personer behöver inte Azure AD Premium-eller Azure AD Basic EDU-licenser tilldelade till dem:

- Personer som är medlemmar i Microsoft 365-grupper och som inte har möjlighet att skapa andra grupper.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>Steg 1: skapa en säkerhets grupp för användare som behöver skapa Microsoft 365-grupper

Endast en säkerhets grupp i organisationen kan användas för att styra vilka som kan skapa grupper. Men du kan kapsla andra säkerhets grupper som medlemmar i den här gruppen.

Administratörer i de roller som visas ovan behöver inte vara medlemmar i den här gruppen: de behåller sin möjlighet att skapa grupper.

> [!IMPORTANT]
> Använd en **säkerhets grupp** för att begränsa vem som kan skapa grupper. Det går inte att använda en Microsoft 365-grupp.

1. Gå till [sidan grupper](https://admin.microsoft.com/adminportal/home#/groups)i administrations centret.

2. Klicka på **Lägg till en grupp**.

3. Välj **säkerhet** som grupptyp. Kom ihåg namnet på gruppen! Du behöver det senare.

4. Slutföra konfigurationen av säkerhets gruppen, lägga till personer eller andra säkerhets grupper som du vill kunna skapa grupper i din organisation.

Detaljerade anvisningar finns i [skapa, redigera eller ta bort en säkerhets grupp i administrations centret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).

## <a name="step-2-run-powershell-commands"></a>Steg 2: Kör PowerShell-kommandon

Du måste använda för hands versionen av [Azure Active Directory PowerShell för Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modul name **AzureADPreview**) för att ändra inställningen för gäst åtkomst på grupp nivå:

- Om du inte har installerat någon version av Azure AD PowerShell-modulen förut läser du [Installera Azure AD-modulen](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) och följa anvisningarna för att installera den offentliga för hands versionen.

- Om du har 2,0 General Availability-versionen av Azure AD PowerShell-modulen (AzureAD) installerad måste du avinstallera den genom att köra `Uninstall-Module AzureAD` i din PowerShell-session och sedan installera för hands versionen genom att köra `Install-Module AzureADPreview` .

- Om du redan har installerat för hands versionen måste du `Install-Module AzureADPreview` kontrol lera att den är den senaste versionen av den här modulen.

Kopiera skriptet nedan till en text redigerare, till exempel anteckningar eller [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Ersätt *\<SecurityGroupName\>* med namnet på den säkerhets grupp som du har skapat. Till exempel:

`$GroupName = "Group Creators"`

Spara filen som GroupCreators.ps1.

Gå till den plats där du sparade filen i PowerShell-fönstret (Skriv "CD <FileLocation> ").

Kör skriptet genom att skriva:

`.\GroupCreators.ps1`

och [Logga in med ditt administratörs konto](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) när du uppmanas till det.

```PowerShell
$GroupName = "<SecurityGroupName>"
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

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Om du i framtiden vill ändra vilken säkerhets grupp som används kan du köra skriptet igen med namnet på den nya säkerhets gruppen.

Om du vill inaktivera begränsningen för grupp skapande och återigen tillåta alla användare att skapa grupper kan du ange $GroupName till "" och $AllowGroupCreation till "true" och köra skriptet igen.

## <a name="step-3-verify-that-it-works"></a>Steg 3: Kontrollera att det fungerar

Det kan ta en halvtimme eller mer att göra ändringar. Du kan kontrol lera de nya inställningarna genom att göra följande:

1. Logga in på Microsoft 365 med ett användar konto hos någon som inte borde ha möjlighet att skapa grupper. De är inte medlemmar i säkerhets gruppen som du skapade eller en administratör.

2. Välj panelen **Planner** .

3. I Planner väljer du **nytt abonnemang** i det vänstra navigerings fältet för att skapa en plan.

4. Du bör få ett meddelande om att planen och skapandet av gruppen är inaktiverat.

Prova samma procedur igen med en medlem i säkerhets gruppen.

> [!NOTE]
> Om medlemmar i säkerhets gruppen inte kan skapa grupper kontrollerar du att de inte blockeras genom sin princip för [OWA-postlådan](https://go.microsoft.com/fwlink/?linkid=852135).

## <a name="related-topics"></a>Relaterade ämnen

[Planerings steg-för-steg-samarbete för samarbets styrning](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa en plan för hantering av samarbete](collaboration-governance-first.md)

[Komma igång med Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Konfigurera hantering av self-service i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory-cmdlets för konfiguration av grupp inställningar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
