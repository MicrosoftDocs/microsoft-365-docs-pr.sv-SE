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
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 'Sammanfattning: Hantera din isolerade SharePoint Online-gruppwebbplats med dessa procedurer.'
ms.openlocfilehash: 59c86c869ed38c3e64ff19974660cf96ec4c715e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810399"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Hantera en isolerad SharePoint Online-gruppwebbplats

 **Sammanfattning:** Hantera din isolerade SharePoint Online-gruppwebbplats med dessa procedurer.
  
I den här artikeln beskrivs vanliga hanteringsåtgärder för en isolerad SharePoint Online-gruppwebbplats.
  
## <a name="add-a-new-user"></a>Lägga till en ny användare

När någon ny ansluter till webbplatsen måste du bestämma deras deltagande nivå på webbplatsen:
  
- Administration: Lägga till det nya användarkontot i åtkomstgruppen för webbplatsadministratörer
    
- Aktivt samarbete: Lägga till användarkontot i åtkomstgruppen för webbplatsmedlemmar
    
- Visa: Lägga till användarkontot i åtkomstgruppen för webbplatstittare
    
Om du hanterar användarkonton och grupper via AD DS (Active Directory Domain Services) lägger du till lämpliga användare i lämpliga åtkomstgrupper med hjälp av dina normala AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med Office 365 Prenumeration.
  
Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller Microsoft PowerShell:
  
- Logga in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller företagsadministratör i Microsoft 365 och använd grupper för att lägga till lämpliga användare i lämpliga åtkomstgrupper.
    
- För PowerShell ansluter du först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Om du vill lägga till ett användarkonto i en åtkomstgrupp med dess användarnamn (UPN) använder du följande PowerShell-kommandoblock:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Om du vill lägga till ett användarkonto i en åtkomstgrupp med visningsnamnet använder du följande PowerShell-kommandoblock:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Lägga till en ny grupp

Om du vill lägga till åtkomst till en hel grupp måste du bestämma hur många medlemmar i gruppen på webbplatsen ska delta:
  
- Administration: Lägga till gruppen i åtkomstgruppen för webbplatsadministratörer
    
- Aktivt samarbete: Lägga till gruppen i åtkomstgruppen för webbplatsmedlemmar
    
- Visa: Lägga till gruppen i åtkomstgruppen för webbplatstittare
    
Om du hanterar användarkonton och grupper via AD DS lägger du till lämpliga grupper i lämpliga grupper med hjälp av dina normala AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din Office 365-prenumeration.
  
Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:
  
- Logga in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller företagsadministratör i Microsoft 365 och använd grupper för att lägga till lämpliga grupper i lämpliga åtkomstgrupper.
    
- För PowerShell ansluter du först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
 Använd sedan följande PowerShell-kommandon:
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Ta bort en användare

När någons åtkomst måste tas bort från webbplatsen tar du bort dem från den åtkomstgrupp som de för närvarande är medlemmar för baserat på deras deltagande på webbplatsen:
  
- Administration: Ta bort användarkontot från åtkomstgruppen för webbplatsadministratörer
    
- Aktivt samarbete: Ta bort användarkontot från åtkomstgruppen för webbplatsmedlemmar
    
- Visa: Ta bort användarkontot från åtkomstgruppen för webbplatstittare
    
Om du hanterar användarkonton och grupper via AD DS tar du bort lämpliga användare från lämpliga åtkomstgrupper med hjälp av dina normala AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din Office 365-prenumeration.
  
Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:
  
- Logga in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller företagsadministratör i Microsoft 365 och använd grupper för att ta bort lämpliga användare från lämpliga åtkomstgrupper.
    
- För PowerShell ansluter du först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
Om du vill ta bort ett användarkonto från en åtkomstgrupp med UPN använder du följande PowerShell-kommandoblock:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Om du vill ta bort ett användarkonto från en åtkomstgrupp med visningsnamnet använder du följande PowerShell-kommandoblock:
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Ta bort en grupp

Om du vill ta bort åtkomsten för en hel grupp tar du bort gruppen från åtkomstgruppen som de för närvarande är medlemmar för baserat på deras deltagande på webbplatsen:
  
- Administration: Ta bort gruppen från åtkomstgruppen för webbplatsadministratörer
    
- Aktivt samarbete: Ta bort gruppen från åtkomstgruppen för webbplatsmedlemmar
    
- Visa: Ta bort gruppen från åtkomstgruppen för webbplatstittare
    
Om du hanterar användarkonton och grupper via Windows Server Active Directory tar du bort lämpliga grupper från lämpliga åtkomstgrupper med hjälp av dina normala AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med Office 365 Prenumeration.
  
Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:
  
- Logga in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller företagsadministratör i Microsoft 365 och använd grupper för att ta bort lämpliga grupper från lämpliga åtkomstgrupper.
    
- För PowerShell ansluter du först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).    
Om du vill ta bort en grupp från en åtkomstgrupp med hjälp av deras visningsnamn använder du följande PowerShell-kommandoblock:
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Skapa en undermapp för dokument med anpassade behörigheter

I vissa fall behöver en delmängd av de personer som arbetar på den isolerade webbplatsen en mer privat plats för att samarbeta. För SharePoint Online-webbplatser kan du skapa en undermapp i mappen Dokument på webbplatsen och tilldela anpassade behörigheter. De utan behörighet ser inte undermappen.
  
Så här skapar du en undermapp för dokument med anpassade behörigheter:
  
1. Logga in på Office 365 med ett konto som är medlem i administratörsåtkomstgruppen för webbplatsen. Mer information finns i [Var du kan logga in på Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Gå till den isolerade gruppwebbplatsen och klicka på **Dokument**.
    
3. Bläddra till mappen i dokumentmappen som ska innehålla undermappen med anpassade behörigheter, skapa mappen och öppna den sedan.
    
4. Klicka på **Dela**.
    
5. Klicka på **Delas med > Avancerat**.
    
6. Klicka på **Sluta ärva behörigheter**och klicka sedan på **OK**.
    
7. Klicka på **Dela**.
    
8. Klicka på **Delas med > Avancerat**.
    
9. Klicka på **Bevilja behörigheter > delas med > Avancerat**.
    
10. Klicka på ** \<webbplatsnamn> medlemmar i listan**på behörighetssidan.
    
11. Markera kryssrutan bredvid åtkomstgruppen för webbplatsmedlemmar på sidan ** \<Webbplatsnamn> medlemmar,** klicka på **Åtgärder,** klicka på **Ta bort användare från gruppen**och klicka sedan på **OK**.
    
12. Om du vill lägga till specifika medlemmar i den här undermappen klickar du på **Ny > Lägg till användare**.
    
13. I dialogrutan **Dela** skriver du namnen på de användarkonton som kan samarbeta om filer i undermappen och klickar sedan på **Dela**.
    
14. Uppdatera webbsidan för att se de nya resultaten.
    
15. Under **Grupper** i den vänstra navigeringen klickar du på ** \<webbplatsnamnet> besöksgruppen** och använder steg 11-14 för att ange den uppsättning användarkonton som kan visa filerna i undermappen (efter behov).
    
16. Under **Grupper** i den vänstra navigeringen klickar du på ** \<webbplatsnamnet> ägargruppen** och använder steg 11-14 för att ange den uppsättning användarkonton som kan administrera behörigheterna i undermappen (efter behov).
    
17. Stäng fliken **Kontakter och grupper** i webbläsaren.
    
## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)
  
[Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md)

[Distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md)



