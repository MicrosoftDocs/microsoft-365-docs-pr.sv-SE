---
title: Hantera en isolerad SharePoint Online-gruppwebbplats
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Hantera en isolerad SharePoint Online-gruppwebbplats, lägga till nya användare och grupper, ta bort användare och grupper och skapa en undermapp med anpassade behörigheter.
ms.openlocfilehash: d66f9a349bd5834d07fbc13146127bde522923e4
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308273"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Hantera en isolerad SharePoint Online-gruppwebbplats

 **Sammanfattning:** Hantera din isolerade SharePoint Online-gruppwebbplats med de här procedurerna.
  
I den här artikeln beskrivs vanliga hanterings åtgärder för en isolerad SharePoint Online-gruppwebbplats.
  
## <a name="add-a-new-user"></a>Lägga till en ny användare

När någon ny ansluter till webbplatsen måste du bestämma deras deltagande på webbplatsen:
  
- Administration: lägga till det nya användar kontot i gruppen webbplats administratörs åtkomst
    
- Aktivt samarbete: lägga till användar kontot i gruppen webbplats medlemmar
    
- Visa: lägga till användar kontot i gruppen webbplats visnings åtkomst
    
Om du hanterar användar konton och grupper via AD DS (Active Directory Domain Services) lägger du till de användare du vill använda i de lämpliga åtkomst grupperna med din vanliga AD DS-användare och grupp hanterings procedurer och väntar på synkronisering med ditt abonnemang.
  
Om du hanterar användar konton och grupper via Microsoft 365 kan du använda Microsoft 365 Admin Center eller Microsoft PowerShell:
  
- För administrations centret för Microsoft 365 loggar du in med ett användar konto som har tilldelats rollen användar konto administratör eller företags administratör och använder grupper för att lägga till rätt användare i lämpliga åtkomst grupper.
    
- För PowerShell, [Anslut först med Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Om du vill lägga till ett användar konto i en åtkomst grupp med dess huvud namn (UPN) använder du följande PowerShell-kommando block:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Om du vill lägga till ett användar konto i en åtkomst grupp med dess visnings namn använder du följande PowerShell-kommando block:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Lägga till en ny grupp

Om du vill lägga till åtkomst till en hel grupp måste du bestämma hur många medlemmar i gruppen som ska delta på webbplatsen:
  
- Administration: lägga till gruppen i gruppen webbplats administratörer
    
- Aktivt samarbete: lägga till gruppen i gruppen webbplats medlemmar
    
- Visa: lägga till gruppen i gruppen webbplats visnings program
    
Om du använder AD DS för att hantera användar konton och grupper kan du lägga till lämpliga grupper i lämpliga grupper med hjälp av dina vanliga procedurer för AD DS-användare och-grupper och vänta på synkronisering med ditt abonnemang.
  
Om du hanterar användar konton och grupper via Office 365 kan du använda Microsoft 365 Admin Center eller PowerShell:
  
- För administrations centret för Microsoft 365 loggar du in med ett användar konto som har tilldelats rollen användar konto administratör eller företags administratör och använder grupper för att lägga till lämpliga grupper i lämpliga åtkomst grupper.
    
- För PowerShell, [Anslut först med Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
 Använd sedan följande PowerShell-kommandon:
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Ta bort en användare

När någons åtkomst måste tas bort från webbplatsen tar du bort dem från den åtkomst grupp för vilken de för närvarande är medlemmar baserat på deras deltagande på webbplatsen:
  
- Administration: ta bort användar kontot från gruppen webbplats administratörs åtkomst
    
- Aktivt samarbete: ta bort användar kontot från gruppen webbplats medlemmar
    
- Visa: ta bort användar kontot från gruppen webbplats visnings åtkomst
    
Om du hanterar användar konton och grupper via AD DS tar du bort de lämpliga användarna från lämpliga åtkomst grupper med hjälp av dina vanliga procedurer för AD DS-användare och-grupper och väntar på synkronisering med ditt abonnemang.
  
Om du hanterar användar konton och grupper via Office 365 kan du använda Microsoft 365 Admin Center eller PowerShell:
  
- För administrations centret för Microsoft 365 loggar du in med ett användar konto som har tilldelats rollen användar konto administratör eller företags administratör och använder grupper för att ta bort lämpliga användare från lämpliga åtkomst grupper.
    
- För PowerShell, [Anslut först med Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
Om du vill ta bort ett användar konto från en åtkomst grupp med dess UPN kan du använda följande PowerShell-kommando block:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Om du vill ta bort ett användar konto från en åtkomst grupp med dess visnings namn kan du använda följande PowerShell-kommando block:
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Ta bort en grupp

Om du vill ta bort åtkomst för en hel grupp tar du bort gruppen från den åtkomst grupp för vilken de för närvarande är medlemmar baserat på deras deltagande på webbplatsen:
  
- Administration: ta bort gruppen från gruppen webbplats administratörer
    
- Aktivt samarbete: ta bort gruppen från gruppen webbplats medlemmar
    
- Visa: ta bort gruppen från gruppen webbplats visnings åtkomst
    
Om du hanterar användar konton och grupper via Windows Server Active Directory tar du bort lämpliga grupper från lämpliga åtkomst grupper med hjälp av dina vanliga procedurer för AD DS-användare och grupp hantering och väntar på synkronisering med ditt abonnemang.
  
Om du hanterar användar konton och grupper via Office 365 kan du använda Microsoft 365 Admin Center eller PowerShell:
  
- För administrations centret för Microsoft 365 loggar du in med ett användar konto som har tilldelats rollen användar konto administratör eller företags administratör och använder grupper för att ta bort lämpliga grupper från lämpliga åtkomst grupper.
    
- För PowerShell, [Anslut först med Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).    
Om du vill ta bort en grupp från en åtkomst grupp med deras visnings namn kan du använda följande PowerShell-kommando block:
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Skapa en undermapp för dokument med anpassade behörigheter

I vissa fall måste en delmängd av de personer som arbetar inom den isolerade webbplatsen vara en privat plats för att samar beta. För SharePoint Online-webbplatser kan du skapa en undermapp i mappen dokument på webbplatsen och tilldela anpassade behörigheter. Dessa utan behörigheter visas inte i undermappen.
  
Gör så här om du vill skapa en undermapp för dokument med anpassade behörigheter:
  
1. Logga in på ett konto som är medlem i gruppen Administratörer för webbplatsen. Mer information finns i [Så här loggar du in i Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Gå till den isolerade grupp webbplatsen och klicka på **dokument**.
    
3. Bläddra till mappen i mappen dokument som ska innehålla undermappen med anpassade behörigheter, skapa mappen och öppna den.
    
4. Klicka på **dela**.
    
5. Klicka på **delas med > Avancerat**.
    
6. Klicka på **sluta ärva behörigheter**och klicka sedan på **OK**.
    
7. Klicka på **dela**.
    
8. Klicka på **delas med > Avancerat**.
    
9. Klicka på **bevilja behörigheter > delas med > Avancerat**.
    
10. Klicka på ** \<site name> medlemmar i listan**på sidan behörigheter.
    
11. På sidan ** \<site name> medlemmar** markerar du kryss rutan bredvid gruppen webbplats medlemmar, klickar på **åtgärder**, klickar på **ta bort användare från grupp**och klickar sedan på **OK**.
    
12. Om du vill lägga till specifika medlemmar i den här undermappen klickar du på **ny > lägga till användare**.
    
13. I dialog rutan **dela** skriver du namnen på de användar konton som kan samar beta med filer i undermappen och klickar sedan på **dela**.
    
14. Uppdatera webb sidan för att se de nya resultaten.
    
15. Klicka på gruppen ** \<site name> besökare** under **grupper** i det vänstra navigerings fältet och Använd stegen 11-14 för att ange den uppsättning användar konton som kan visa filerna i undermappen (efter behov).
    
16. Under **grupper** i det vänstra navigerings fältet klickar du på gruppen ** \<site name> ägare** och använder steg 11-14 för att ange den uppsättning användar konton som kan hantera behörigheterna i undermappen (efter behov).
    
17. Stäng fliken **personer och grupper** i webbläsaren.
    
## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)
  
[Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md)

[Distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md)



