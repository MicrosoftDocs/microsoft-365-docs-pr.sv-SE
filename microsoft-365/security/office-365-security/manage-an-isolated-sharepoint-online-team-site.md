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
description: Hantera en isolerad SharePoint Online-gruppwebbplats, lägga till nya användare och grupper, ta bort användare och grupper och skapa en undermapp för dokument med anpassade behörigheter.
ms.openlocfilehash: 05e3cf742482d34c158e14253eed9d1b99c82995
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036638"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Hantera en isolerad SharePoint Online-gruppwebbplats

 **Sammanfattning:** Hantera din isolerade SharePoint Online-gruppwebbplats med dessa procedurer.
  
I den här artikeln beskrivs vanliga hanteringsåtgärder för en isolerad SharePoint Online-gruppwebbplats.
  
## <a name="add-a-new-user"></a>Lägga till en ny användare

När någon ny ansluter till webbplatsen måste du bestämma deras deltagande i webbplatsen:
  
- Administration: Lägga till det nya användarkontot i åtkomstgruppen för webbplatsadministratörer
    
- Aktivt samarbete: Lägg till användarkontot i åtkomstgruppen för webbplatsmedlemmar
    
- Visa: Lägga till användarkontot i åtkomstgruppen för webbplatsvisningsprogram
    
Om du hanterar användarkonton och grupper via AD DS (Active Directory Domain Services) lägger du till lämpliga användare i lämpliga åtkomstgrupper med hjälp av dina vanliga AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din prenumeration.
  
Om du hanterar användarkonton och grupper via Microsoft 365 kan du använda Microsoft 365-administrationscentret eller Microsoft PowerShell:
  
- För administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller Företagsadministratör och använder grupper för att lägga till lämpliga användare i lämpliga åtkomstgrupper.
    
- För PowerShell, anslut först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Om du vill lägga till ett användarkonto i en åtkomstgrupp med användarens huvudnamn (UPN) använder du följande PowerShell-kommandoblock:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Om du vill lägga till ett användarkonto i en åtkomstgrupp med dess visningsnamn använder du följande PowerShell-kommandoblock:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Lägga till en ny grupp

Om du vill lägga till åtkomst till en hel grupp måste du bestämma nivån för deltagande av alla medlemmar i gruppen på webbplatsen:
  
- Administration: Lägga till gruppen i åtkomstgruppen för webbplatsadministratörer
    
- Aktivt samarbete: Lägg till gruppen i åtkomstgruppen för webbplatsmedlemmar
    
- Visa: Lägga till gruppen i åtkomstgruppen för webbplatstittare
    
Om du hanterar användarkonton och grupper via AD DS lägger du till lämpliga grupper i lämpliga grupper med hjälp av dina vanliga AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din prenumeration.
  
Om du hanterar användarkonton och grupper via Office 365 kan du använda Microsoft 365-administrationscentret eller PowerShell:
  
- För administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller Företagsadministratör och använder grupper för att lägga till lämpliga grupper i lämpliga åtkomstgrupper.
    
- För PowerShell, anslut först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
 Använd sedan följande PowerShell-kommandon:
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Ta bort en användare

När någons åtkomst måste tas bort från webbplatsen tar du bort dem från den åtkomstgrupp som de för närvarande är medlem i baserat på deras deltagande på webbplatsen:
  
- Administration: Ta bort användarkontot från åtkomstgruppen för webbplatsadministratörer
    
- Aktivt samarbete: Ta bort användarkontot från åtkomstgruppen för webbplatsmedlemmar
    
- Visa: Ta bort användarkontot från åtkomstgruppen för webbplatsvisningsprogram
    
Om du hanterar användarkonton och grupper via AD DS tar du bort lämpliga användare från lämpliga åtkomstgrupper med hjälp av dina vanliga AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din prenumeration.
  
Om du hanterar användarkonton och grupper via Office 365 kan du använda Microsoft 365-administrationscentret eller PowerShell:
  
- För administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller Företagsadministratör och använder grupper för att ta bort lämpliga användare från lämpliga åtkomstgrupper.
    
- För PowerShell, anslut först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
Om du vill ta bort ett användarkonto från en åtkomstgrupp med upn-programmet använder du följande PowerShell-kommandoblock:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Om du vill ta bort ett användarkonto från en åtkomstgrupp med dess visningsnamn använder du följande PowerShell-kommandoblock:
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Ta bort en grupp

Om du vill ta bort åtkomsten för en hel grupp tar du bort gruppen från den åtkomstgrupp som de för närvarande är medlem i baserat på deras deltagande på webbplatsen:
  
- Administration: Ta bort gruppen från åtkomstgruppen för webbplatsadministratörer
    
- Aktivt samarbete: Ta bort gruppen från åtkomstgruppen för webbplatsmedlemmar
    
- Visa: Ta bort gruppen från åtkomstgruppen för webbplatstittare
    
Om du hanterar användarkonton och grupper via Active Directory i Windows Server tar du bort lämpliga grupper från lämpliga åtkomstgrupper med hjälp av dina vanliga AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din prenumeration.
  
Om du hanterar användarkonton och grupper via Office 365 kan du använda Microsoft 365-administrationscentret eller PowerShell:
  
- För administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller Företagsadministratör och använder grupper för att ta bort lämpliga grupper från lämpliga åtkomstgrupper.
    
- För PowerShell, anslut först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).    
Om du vill ta bort en grupp från en åtkomstgrupp med deras visningsnamn använder du följande PowerShell-kommandoblock:
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Skapa en undermapp för dokument med anpassade behörigheter

I vissa fall behöver en delmängd av de personer som arbetar inom den isolerade platsen en mer privat plats för att samarbeta. För SharePoint Online-webbplatser kan du skapa en undermapp i mappen Dokument på webbplatsen och tilldela anpassade behörigheter. De som inte har behörighet kommer inte att se undermappen.
  
Så här skapar du en undermapp för dokument med anpassade behörigheter:
  
1. Logga in på ett konto som är medlem i åtkomstgruppen för administratörer för webbplatsen. Mer information finns i [Så här loggar du in i Microsoft 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Gå till den isolerade gruppwebbplatsen och klicka på **Dokument**.
    
3. Bläddra till mappen i dokumentmappen som ska innehålla undermappen med anpassade behörigheter, skapa mappen och öppna den sedan.
    
4. Klicka på **Dela**.
    
5. Klicka på **Delas med > Avancerat**.
    
6. Klicka på **Sluta ärva behörigheter**och klicka sedan på **OK**.
    
7. Klicka på **Dela**.
    
8. Klicka på **Delas med > Avancerat**.
    
9. Klicka på **Bevilja behörigheter > delas med > Avancerat**.
    
10. Klicka på ** \<webbplatsnamn> medlemmar i listan**på behörighetssidan .
    
11. På ** \<sidan webbplatsnamn> medlemmar** markerar du bocken bredvid åtkomstgruppen för webbplatsmedlemmar, klickar på **Åtgärder,** klickar på **Ta bort användare från gruppen**och klickar sedan på **OK**.
    
12. Om du vill lägga till specifika medlemmar i den här undermappen klickar du på **Ny > Lägg till användare**.
    
13. Skriv namnen på de användarkonton som kan samarbeta om filer i undermappen i dialogrutan **Dela** och klicka sedan på **Dela**.
    
14. Uppdatera webbsidan för att se de nya resultaten.
    
15. Under **Grupper** i den vänstra navigeringen klickar du på ** \<webbplatsnamnet>** gruppen Besökare och använder steg 11–14 för att ange den uppsättning användarkonton som kan visa filerna i undermappen (efter behov).
    
16. Under **Grupper** i den vänstra navigeringen klickar du på ** \<webbplatsnamnet> ägargruppen** och använder steg 11–14 för att ange den uppsättning användarkonton som kan administrera behörigheterna i undermappen (efter behov).
    
17. Stäng fliken **Personer och grupper** i webbläsaren.
    
## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)
  
[Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md)

[Distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md)



