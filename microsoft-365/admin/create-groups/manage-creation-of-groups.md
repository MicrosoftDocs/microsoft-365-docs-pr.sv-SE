---
title: Hantera vem som kan skapa grupper
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Lär dig hur du styr vilka användare som kan skapa Microsoft 365-grupper.
ms.openlocfilehash: 55b3ec119e8c74982ce340c58f6b8da684c9ffa8
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208348"
---
# <a name="manage-who-can-create-groups"></a>Hantera vem som kan skapa grupper

  
Eftersom det är så enkelt för användare att skapa Microsoft 365-grupper översvämmas du inte av begäranden om att skapa dem för andra personers räkning. Beroende på vilken verksamhet du har kanske du ändå vill styra vilka som har möjlighet att skapa grupper.
  
I den hÃ¤r artikeln beskrivs hur du inaktiverar möjligheten att skapa grupper i alla Microsoft 365-tjänster som anvÃ¤nder grupper, inklusive:
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream
    
- StaffHub
    
- Planner
    
- PowerBI (på andra)

- Översikt
    
Du kan begränsa skapandet av Microsoft 365-grupper till medlemmarna i en viss säkerhetsgrupp. Om du vill konfigurera detta använder du Windows PowerShell. Den här artikeln går igenom de nödvändiga stegen.
  
Stegen i den här artikeln hindrar inte medlemmar i vissa roller från att skapa grupper. Globala administratörer kan skapa grupper på alla sätt, till exempel Microsoft 365-administrationscentret, Planner, Teams, Exchange och SharePoint Online. Andra roller kan skapa grupper med begränsade medel, som anges nedan.
        
  - Exchange-administratör: Administrationscenter för Exchange, Azure AD
    
  - Support för partnernivå 1: Administrationscenter för Microsoft 365, Administrationscenter för Exchange, Azure AD
    
  - Support för partnernivå 2: Administrationscenter för Microsoft 365, Administrationscenter för Exchange, Azure AD
    
  - Katalogförfattare: Azure AD

  - SharePoint-administratör: Administrationscenter för SharePoint, Azure AD
  
  - Teams Service Administrator: Teams Admin center, Azure AD
  
  - Administratör för användarhantering: Microsoft 365 Admin center, Yammer, Azure AD
     
Om du är medlem i någon av dessa roller kan du skapa Microsoft 365-grupper för begränsade användare och sedan tilldela användaren som ägare till gruppen. Användare som har den här rollen kan skapa anslutna grupper i Yammer, oavsett eventuella PowerShell-inställningar som kan förhindra skapande.

## <a name="licensing-requirements"></a>Licenskrav

För att hantera vem som skapar grupper behöver följande personer Azure AD Premium-licenser eller Azure AD Basic EDU-licenser som tilldelats dem:

- Administratören som konfigurerar inställningarna för gruppskapande
- Medlemmarna i säkerhetsgruppen som får skapa grupper

> [!NOTE]
> Mer information om hur du tilldelar Azure-licenser finns [i Tilldela eller ta bort licenser i Azure Active Directory-portalen.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)

Följande personer behöver inte Azure AD Premium- eller Azure AD Basic EDU-licenser som tilldelats dem:

- Personer som är medlemmar i Microsoft 365-grupper och som inte har möjlighet att skapa andra grupper.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>Steg 1: Skapa en säkerhetsgrupp för användare som behöver skapa Microsoft 365-grupper

Endast en säkerhetsgrupp i organisationen kan användas för att styra vem som kan skapa grupper. Men du kan kapsla andra säkerhetsgrupper som medlemmar i den här gruppen. Gruppen Tillåt gruppskapande är till exempel den angivna säkerhetsgruppen och grupperna Microsoft Planner Users och Exchange Online Users är medlemmar i den gruppen.

Administratörer i de roller som anges ovan behöver inte vara medlemmar i den här gruppen: de behåller sin förmåga att skapa grupper.

> [!IMPORTANT]
> Var noga med att använda en **säkerhetsgrupp** för att begränsa vem som kan skapa grupper. Om du försöker använda en Microsoft 365-grupp kan medlemmarna inte skapa en grupp från SharePoint eftersom den söker efter en säkerhetsgrupp. 
    
1. Gå till sidan **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppergrupper i</a> administrationscentret.

2. Klicka på **Lägg till en grupp**.

3. Välj **Säkerhet** som grupptyp. Kom ihåg namnet på gruppen! Du behöver det senare.
  
4. Slutför inrättandet av säkerhetsgruppen och lägg till personer eller andra säkerhetsgrupper som du vill ska kunna skapa grupper i organisationen.
    
Detaljerade instruktioner finns i [Skapa, redigera eller ta bort en säkerhetsgrupp i administrationscentret för Microsoft 365](../email/create-edit-or-delete-a-security-group.md).
 
## <a name="step-2-run-powershell-commands"></a>Steg 2: Kör PowerShell-kommandon

Du måste använda förhandsversionen av [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulnamnet **AzureADPreview)** för att ändra inställningen för gäståtkomst på gruppnivå:

- Om du inte har installerat någon version av Azure AD PowerShell-modulen tidigare läser [du Installera Azure AD-modulen](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) och följer instruktionerna för att installera den offentliga förhandsversionen.

- Om du har installerat 2.0-versionen för allmän tillgänglighet av Azure AD PowerShell-modulen (AzureAD) måste du avinstallera den genom att `Uninstall-Module AzureAD` köras i PowerShell-sessionen och sedan installera förhandsversionen genom att köra `Install-Module AzureADPreview` .

- Om du redan har installerat förhandsversionen kör du `Install-Module AzureADPreview` för att kontrollera att den är den senaste versionen av den här modulen.



Kopiera skriptet nedan till en textredigerare, till exempel Anteckningar, eller [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Ersätt * \< SecurityGroupName \> * med namnet på den säkerhetsgrupp som du skapade. Till exempel:

`$GroupName = "Group Creators"`

Spara filen som GroupCreators.ps1. 

I PowerShell-fönstret navigerar du till den plats där du sparade filen (skriv "CD <FileLocation> ").

Kör skriptet genom att skriva:

`.\GroupCreators.ps1`

och [logga in med ditt administratörskonto](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) när du uppmanas att göra det.

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

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

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

Om du i framtiden vill ändra vilken säkerhetsgrupp som används kan du köra skriptet igen med namnet på den nya säkerhetsgruppen.

Om du vill inaktivera begränsningen för gruppskapande och återigen tillåta alla användare att skapa grupper, ställer du in $GroupName till "" och $AllowGroupCreation till "True" och kör skriptet igen.
    
## <a name="step-4-verify-that-it-works"></a>Steg 4: Kontrollera att det fungerar

Det kan ta trettio minuter eller mer att träda i kraft. Du kan verifiera de nya inställningarna genom att göra följande:

1. Logga in med ett användarkonto för någon som INTE ska ha möjlighet att skapa grupper. Det vill säga, de är inte medlemmar i den säkerhetsgrupp du skapade eller en administratör.
    
2. Välj panelen **Planerare.** 
    
3. Välj Nytt **abonnemang** i den vänstra navigeringen i Planner för att skapa en plan. 
  
4. Du bör få ett meddelande om att planen och gruppskapandet är inaktiverat.

Försök med samma procedur igen med en medlem i säkerhetsgruppen.

> [!NOTE]
> Om medlemmar i säkerhetsgruppen inte kan skapa grupper kontrollerar du att de inte blockeras via principen [för OWA-postlådeprincipen.](https://go.microsoft.com/fwlink/?linkid=852135)
    
## <a name="related-articles"></a>Relaterade artiklar

[Komma igång med Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Konfigurera grupphantering med självbetjäning i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-executionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory-cmdletar för att konfigurera gruppinställningar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
