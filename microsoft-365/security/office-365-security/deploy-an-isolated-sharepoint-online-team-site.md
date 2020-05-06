---
title: Distribuera en isolerad SharePoint Online-gruppwebbplats
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Använd den här steg-för-steg-distributionsguiden för att skapa och konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365.
ms.openlocfilehash: 772a9e5ea08871857a70cc840e377046d459a314
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036457"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Distribuera en isolerad SharePoint Online-gruppwebbplats

 **Sammanfattning:** Distribuera en ny isolerad SharePoint Online-gruppwebbplats med de här steg-för-steg-instruktionerna.
  
Den här artikeln är en steg-för-steg-distributionsguide för att skapa och konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365. Dessa steg förutsätter att de tre standard-SharePoint-grupperna och motsvarande behörighetsnivåer används, med en enda AZURE Active Directory-baserad åtkomstgrupp för varje åtkomstnivå.
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Fas 1: Skapa och fylla i åtkomstgrupper för gruppwebbplatser

I den här fasen skapar du de tre Azure AD-baserade åtkomstgrupperna för de tre standarddoahPoint-grupperna och fyller dem med lämpliga användarkonton.
  
> [!NOTE]
> Följande steg förutsätter att alla nödvändiga användarkonton redan finns och tilldelas lämpliga licenser. Om inte, lägg till dem och tilldela licenser innan du fortsätter till steg 1. 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Steg 1: Lista SharePoint Online-administratörer för webbplatsen

Bestäm den uppsättning användarkonton som motsvarar SharePoint Online-administratörerna för den isolerade gruppwebbplatsen.
  
Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda Windows PowerShell gör du en lista över deras användarnamn (UPN) (t.belindan@contoso.com ex.
  
### <a name="step-2-list-the-members-for-the-site"></a>Steg 2: Lista medlemmarna för webbplatsen

Bestäm den uppsättning användarkonton som motsvarar medlemmarna för den isolerade gruppwebbplatsen, de som ska samarbeta på resurser som lagras på webbplatsen.
  
Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda PowerShell gör du en lista över deras UPN-nätverk. Om det finns många webbplatsmedlemmar kan du lagra listan över UPN i en textfil och lägga till dem alla med ett enda PowerShell-kommando.
  
### <a name="step-3-list-the-viewers-for-the-site"></a>Steg 3: Lista tittarna för webbplatsen

Bestäm den uppsättning användarkonton som motsvarar visningssidan på den isolerade gruppwebbplatsen, de som kan visa de resurser som lagras på webbplatsen men inte ändra dem eller direkt samarbeta om innehållet.
  
Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda PowerShell gör du en lista över deras UPN-nätverk. Om det finns många webbplatsmedlemmar kan du lagra listan över UPN i en textfil och lägga till dem alla med ett enda PowerShell-kommando.
  
Tittare för webbplatsen kan inkludera chefshantering, juridisk rådgivning eller intressenter mellan avdelningar.
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Steg 4: Skapa de tre åtkomstgrupperna för webbplatsen i Azure AD

Du måste skapa följande åtkomstgrupper i Azure AD:
  
- Webbplatsadministratörer (som kommer att innehålla listan från steg 1)
    
- Webbplatsmedlemmar (som kommer att innehålla listan från steg 2)
    
- Webbplatsvisning (som kommer att innehålla listan från steg 3)
    
1. I webbläsaren går du till [https://portal.azure.com](https://portal.azure.com) Azure-portalen och loggar in med autentiseringsuppgifterna för ett konto som har tilldelats med användarhanteringsadministratör eller företagsadministratörsroll.
    
2. I Azure-portalen klickar du på **Azure Active Directory > Grupper**.
    
3. Gå till bladet **Grupper – Alla grupper** och klicka på **+ Ny grupp**.
    
4. På den **nya koncernen** blad:
    
    - Välj **Säkerhet** i **Grupptyp**.

    - Skriv gruppnamnet i **Namn**.

    - Skriv en beskrivning av gruppen i **Gruppbeskrivning**.

    - Välj **Tilldelad** i **Typ av medlemskap**.
    
5. Klicka på **Skapa** och stäng sedan bladet **Grupp**.
    
6. Upprepa steg 3-5 för dina ytterligare grupper.
    
> [!NOTE]
> Du måste använda Azure-portalen för att skapa grupper så att de har Office-funktioner aktiverade. Om en isolerad SharePoint Online-webbplats senare konfigureras som en mycket konfidentiell webbplats med en Azure Information Protection-etikett för att kryptera filer och tilldela behörighet till specifika grupper, måste de tillåtna grupperna ha skapats med Office-funktioner aktiverade. Du kan inte ändra inställningen för Office-funktioner för en Azure AD-grupp när den har skapats. 
  
Här är din resulterande konfiguration med de tre platsåtkomstgrupperna.
  
![De tre åtkomstgrupperna för distributionen av en isolerad SharePoint Online-webbplats.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Steg 5. Lägga till användarkontona i åtkomstgrupperna

Gör så här i det här steget:
  
1. Lägga till listan över användare från steg 1 i åtkomstgruppen för webbplatsadministratörer
    
2. Lägga till listan över användare från steg 2 i åtkomstgruppen för webbplatsmedlemmar
    
3. Lägga till listan över användare från steg 3 i åtkomstgruppen för webbplatsvisningsprogram
    
Om du hanterar användarkonton och grupper via AD DS (Active Directory Domain Services) lägger du till användare i lämpliga åtkomstgrupper med hjälp av dina vanliga AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din Microsoft 365-prenumeration.
  
Om du hanterar användarkonton och grupper via Office 365 kan du använda microsoft 365-administrationscentret eller PowerShell. Om du har dubbla gruppnamn för någon av åtkomstgrupperna bör du använda administrationscentret för Microsoft 365.
  
För administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Administratör för användarkonto eller Företagsadministratör och använder grupper för att lägga till lämpliga användarkonton och grupper i lämpliga åtkomstgrupper.
  
För PowerShell, anslut först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Använd sedan följande kommandoblock för att lägga till ett enskilt användarkonto i en åtkomstgrupp:
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
Om du har lagrat UPN för användarkonton för någon av åtkomstgrupperna i en textfil kan du använda följande PowerShell-kommandoblock för att lägga till dem alla på en gång:
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

För PowerShell använder du följande kommandoblock för att lägga till en enskild grupp i en åtkomstgrupp:
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

Resultaten bör vara följande:
  
- Azure AD-gruppen för webbplatsadministratörer innehåller användarkonton eller grupper för webbplatsadministratörer
    
- Webbplatsmedlemmarna Azure AD-gruppen innehåller användarkonton eller grupper för webbplatsmedlemsanvändare
    
- Webbplatsens tittare Azure AD-gruppen innehåller användarkonton eller grupper som bara kan visa webbplatsens innehåll
    
Verifiera listan över gruppmedlemmar för varje åtkomstgrupp med Microsoft 365-administrationscentret eller med följande PowerShell-kommandoblock:
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Här är din resulterande konfiguration med de tre platsåtkomstgrupperna som fylls med användarkonton eller grupper.
  
![De tre åtkomstgrupperna som fylls med användarkonton.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Fas 2: Skapa och konfigurera den isolerade gruppplatsen

I den här fasen skapar du den isolerade SharePoint Online-webbplatsen och konfigurerar behörigheterna för standardbehörighetsnivåerna för SharePoint Online för att använda dina nya Azure AD-baserade åtkomstgrupper. Som standard innehåller nya gruppwebbplatser en Microsoft 365-grupp och andra relaterade resurser, men i det här fallet skapar vi en gruppwebbplats utan en Microsoft 365-grupp. Detta gör det möjligt att behålla behörigheter helt via SharePoint.
  
Skapa först SharePoint Online-gruppwebbplatsen med de här stegen.
  
1. Logga in på Microsoft 365-administrationscentret med ett konto som också används för att administrera SharePoint Online-gruppwebbplatsen (en SharePoint Online-administratör). Mer information finns i [Så här loggar du in i Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Klicka på **SharePoint**under **Administrationscenter**i Microsoft 365.

3. Expandera **Webbplatser** i administrationscentret för SharePoint och klicka på **Aktiva webbplatser.**

4. Klicka på **Skapa**och välj sedan **Andra alternativ**.

5. Välj **Gruppwebbplats**i listan **Välj en mall** .
   
6. Skriv ett namn för gruppwebbplatsen i **Platsnamn.** 
    
7. I **Primär administratör**skriver du det konto som du är inloggad med.
 
8. Klicka på **Slutför**.
    
Konfigurera sedan behörigheter från den nya SharePoint Online-gruppwebbplatsen.
  
1. Klicka på inställningsikonen i verktygsfältet och klicka sedan på **Webbplatsbehörigheter**.

2. Klicka på **Ändra hur medlemmar kan dela**under **Webbplatsdelning.**

3. Välj de **enda webbplatsägare som kan dela filer, mappar och webbplatsen**.

4. Ange **Tillåt åtkomstbegäranden** till **Av**.

5. Klicka på **Spara**.
    
6. Klicka på **Avancerade behörighetsinställningar**i fönstret **Behörigheter.**
    
7. Klicka på ** \<webbplatsnamn> medlemmar** i listan på fliken **Behörigheter** i webbläsaren.
    
8. Klicka på **Nytt**i **Personer och grupper.**
    
9. Skriv namnet på åtkomstgruppen för webbplatsmedlemmar i dialogrutan **Dela,** markera det och klicka sedan på **Dela**.
    
10. Klicka på bakåtknappen i webbläsaren.
    
11. Klicka på ** \<webbplatsnamnet> ägare** i listan.
    
12. Klicka på **Nytt**i **Personer och grupper.**
    
13. Skriv namnet på åtkomstgruppen för webbplatsadministratörer i dialogrutan **Dela,** markera det och klicka sedan på **Dela**.
    
14. Klicka på bakåtknappen i webbläsaren.
    
15. Klicka på ** \<webbplatsnamnet> besökare** i listan.
    
16. Klicka på **Nytt**i **Personer och grupper.**
    
17. Skriv namnet på åtkomstgruppen för webbplatsvisning i dialogrutan **Dela,** markera det och klicka sedan på **Dela**.
    
18. Stäng fliken **Behörigheter** i webbläsaren.
    
Resultatet av dessa behörighetsinställningar är:
  
- ** \<Webbplatsnamnet> SharePoint-gruppen ägare** innehåller åtkomstgruppen för webbplatsadministratörer, där alla medlemmar har behörighetsnivån **Fullständig behörighet.**
    
- ** \<Webbplatsnamnet> SharePoint-gruppen medlemmar** innehåller åtkomstgruppen för webbplatsmedlemmar, där alla medlemmar har **behörighetsnivån Redigera.**
    
- ** \<Webbplatsnamnet> SharePoint-gruppen för besökare** innehåller åtkomstgruppen för webbplatsvisningsbesökare, där alla medlemmar har **läsbehörighetsnivån.**
    
- Möjligheten för medlemmar att bjuda in andra medlemmar eller för icke-medlemmar att begära åtkomst är inaktiverad.
    
Här är din resulterande konfiguration med de tre SharePoint-grupperna för webbplatsen konfigurerad för att använda de tre åtkomstgrupperna, som fylls i med användarkonton eller Azure AD-grupper.
  
![Den slutliga konfigurationen av din isolerade SharePoint Online-webbplats med åtkomstgrupper och användarkonton.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
Du och medlemmarna på webbplatsen, genom gruppmedlemskap i en av åtkomstgrupperna, kan nu samarbeta med hjälp av webbplatsens resurser.
  
## <a name="next-step"></a>Nästa steg

När du behöver ändra medlemskap i webbplatsåtkomstgrupp eller skapa en dokumentmapp med anpassade behörigheter läser du [Hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)
  
[Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md)
  
[Hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md)
  



