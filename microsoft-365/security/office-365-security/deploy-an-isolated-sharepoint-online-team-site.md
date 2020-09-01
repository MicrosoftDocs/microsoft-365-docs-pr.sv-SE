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
description: Använd den här stegvisa distributions guiden för att skapa och konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365.
ms.openlocfilehash: 3465ec28db8c2045bad6e6c48112861818629524
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308421"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Distribuera en isolerad SharePoint Online-gruppwebbplats

 **Sammanfattning:** Distribuera en ny isolerad SharePoint Online-gruppwebbplats med de här stegvisa anvisningarna.
  
Den här artikeln är en steg-för-steg-guide för hur du skapar och konfigurerar en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365. De här stegen förutsätter användning av de tre SharePoint-standardgrupperna och motsvarande behörighets nivåer, med en enda Azure Active Directory (AD)-baserad åtkomst grupp för varje åtkomst nivå.
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Fas 1: skapa och fylla i åtkomst grupperna för grupp webbplatser

I den här fasen skapar du de tre Azure AD-baserade åtkomst grupperna för de tre SharePoint-standardgrupperna och fyller dem med rätt användar konton.
  
> [!NOTE]
> Följande anvisningar förutsätter att alla nödvändiga användar konton redan finns och har tilldelats rätt licenser. Om inte, Lägg till dem och tilldela licenser innan du går vidare till steg 1. 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Steg 1: lista SharePoint Online-administratörer för webbplatsen

Bestäm vilka användar konton som motsvarar SharePoint Online-administratörer för den isolerade grupp webbplatsen.
  
Om du hanterar användar konton och grupper via Microsoft 365 och vill använda Windows PowerShell kan du skapa en lista över deras UPN-namn (exempel på UPN: belindan@contoso.com).
  
### <a name="step-2-list-the-members-for-the-site"></a>Steg 2: lista medlemmar för webbplatsen

Bestäm vilka användar konton som motsvarar medlemmarna för den isolerade grupp webbplatsen, de som samarbetar med resurser som lagras på webbplatsen.
  
Om du hanterar användar konton och grupper via Microsoft 365 och vill använda PowerShell kan du skapa en lista över deras UPN-objekt. Om det finns många webbplats medlemmar kan du lagra listan med UPN i en textfil och lägga till alla med ett enda PowerShell-kommando.
  
### <a name="step-3-list-the-viewers-for-the-site"></a>Steg 3: Visa webbplatsens visnings program

Ta reda på vilka användar konton som motsvarar läsarna på den isolerade grupp webbplatsen, de som kan visa resurserna som lagras på webbplatsen, men inte ändra dem eller samar beta direkt i deras innehåll.
  
Om du hanterar användar konton och grupper via Microsoft 365 och vill använda PowerShell kan du skapa en lista över deras UPN-objekt. Om det finns många webbplats medlemmar kan du lagra listan med UPN i en textfil och lägga till alla med ett enda PowerShell-kommando.
  
Visnings program för webbplatsen kan omfatta företags ledning, juridisk rådgivning eller intressenter mellan institutioner.
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Steg 4: skapa de tre åtkomst grupperna för webbplatsen i Azure AD

Du måste skapa följande åtkomst grupper i Azure AD:
  
- Webbplats administratörer (som kommer att innehålla listan från steg 1)
    
- Webbplats medlemmar (som kommer att innehålla listan från steg 2)
    
- Webbplats visnings program (som kommer att innehålla listan från steg 3)
    
1. I din webbläsare går du till Azure-portalen [https://portal.azure.com](https://portal.azure.com) och loggar in med autentiseringsuppgifterna för ett konto som har tilldelats användar hanterings administratören eller administratörs rollen för administratörer.
    
2. I Azure-portalen klickar du på **Azure Active Directory > Grupper**.
    
3. Gå till bladet **Grupper – Alla grupper** och klicka på **+ Ny grupp**.
    
4. I det **nya grupp** bladet:
    
    - Välj **Säkerhet** i **Grupptyp**.

    - Skriv grupp namnet i **namn**.

    - Ange en beskrivning av gruppen i **grupp beskrivningen**.

    - Välj **Tilldelad** i **Typ av medlemskap**.
    
5. Klicka på **Skapa** och stäng sedan bladet **Grupp**.
    
6. Upprepa steg 3-5 för dina fler grupper.
    
> [!NOTE]
> Du måste använda Azure-portalen för att skapa grupperna så att de har aktiverade Office-funktioner. Om en SharePoint Online-isolerad webbplats senare är konfigurerad som en mycket konfidentiell webbplats med en Azure information Protection-etikett för att kryptera filer och tilldela behörigheter till specifika grupper måste de tillåtna grupperna ha skapats med Office-funktioner aktiverade. Du kan inte ändra Office-funktioner för en Azure AD-grupp efter att den har skapats. 
  
Här är din resulterande konfiguration med de tre webbplats åtkomst grupperna.
  
![De tre åtkomst grupperna för en isolerad SharePoint Online-webbplats.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Steg 5: Lägga till användar konton i åtkomst grupperna

I det här steget gör du följande:
  
1. Lägga till listan med användare från steg 1 i gruppen webbplats administratörer
    
2. Lägga till listan med användare från steg 2 till gruppen webbplats medlemmar
    
3. Lägga till listan med användare från steg 3 i gruppen webbplats visnings åtkomst
    
Om du hanterar användar konton och grupper via AD DS (Active Directory Domain Services) lägger du till användare i lämpliga åtkomst grupper med hjälp av din vanliga AD DS-användare och grupp hanterings procedurer och väntar på synkronisering med Microsoft 365-prenumerationen.
  
Om du hanterar användar konton och grupper via Office 365 kan du använda administrations centret för Microsoft 365 eller PowerShell. Om du har dubbletter av grupp namn för någon av åtkomst grupperna bör du använda administrations centret för Microsoft 365.
  
För administrations centret för Microsoft 365 loggar du in med ett användar konto som har tilldelats rollen användar konto administratör eller företags administratör och använder grupper för att lägga till användar konton och grupper i lämpliga åtkomst grupper.
  
För PowerShell, [Anslut först med Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Använd sedan följande kommando block för att lägga till ett enskilt användar konto i en åtkomst grupp:
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
Om du har lagrat UPN för användar konton för någon av åtkomst grupperna i en textfil kan du använda följande PowerShell-kommando block för att lägga till dem samtidigt:
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

För PowerShell använder du följande kommando block för att lägga till en enskild grupp i en Access-grupp:
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

Resultaten bör vara följande:
  
- Webbplats administratörer Azure AD-gruppen innehåller användar kontona för webbplats administratören
    
- Webbplats medlemmarnas Azure AD-grupp innehåller webbplats medlemmarnas användar konton eller grupper
    
- Webbplats visnings program Azure AD-gruppen innehåller användar konton eller grupper som endast kan visa webbplats innehållet
    
Verifiera listan med grupp medlemmar för varje åtkomst grupp med administrations centret för Microsoft 365 eller med följande PowerShell-kommando block:
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Här är din resulterande konfiguration med de tre webbplats åtkomst grupperna som är ifyllda med användar konton eller grupper.
  
![De tre åtkomst grupperna som är ifyllda med användar konton.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Fas 2: skapa och konfigurera den isolerade grupp webbplatsen

I den här fasen skapar du den isolerade SharePoint Online-webbplatsen och konfigurerar behörigheterna för standard behörighets nivåerna i SharePoint Online för att använda de nya Azure AD-baserade åtkomst grupperna. Som standard innehåller nya grupp webbplatser en Microsoft 365-grupp och andra relaterade resurser, men i det här fallet skapar vi en grupp webbplats utan en Microsoft 365-grupp. Detta möjliggör underhåll av behörigheter helt och hållet via SharePoint.
  
Börja med att skapa grupp webbplatsen för SharePoint Online med de här stegen.
  
1. Logga in på administrations centret för Microsoft 365 med ett konto som också används för att administrera SharePoint Online-gruppwebbplatsen (en SharePoint Online-administratör). Mer information finns i [Så här loggar du in i Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Klicka på **SharePoint** **i administrations**centret för Microsoft 365.

3. Expandera **webbplatser** och klicka på **aktiva webbplatser**i administrations centret för SharePoint.

4. Klicka på **skapa**och välj sedan **andra alternativ**.

5. Välj **grupp webbplats**i listan **Välj en mall** .
   
6. Ange ett namn på grupp webbplatsen i **webbplats namn**. 
    
7. I **primär administratör**skriver du det konto som du är inloggad med.
 
8. Klicka på **Slutför**.
    
Sedan kan du konfigurera behörigheter från den nya SharePoint Online-gruppwebbplatsen.
  
1. Klicka på inställningsikonen i verktygsfältet och klicka sedan på **Webbplatsbehörigheter**.

2. Klicka på **ändra hur medlemmar kan dela**under **webbplats delning**.

3. Välj de **enda webbplats ägarna som kan dela filer, mappar och webbplatsen**.

4. Ange **Tillåt åtkomst förfrågningar** till **av**.

5. Klicka på **Spara**.
    
6. I fönstret **behörigheter** klickar du på **avancerade behörigheter**.
    
7. Klicka på ** \<site name> medlemmar** i listan på fliken **behörigheter** i webbläsaren.
    
8. Klicka på **nytt**i **personer och grupper**.
    
9. I dialog rutan **dela** skriver du in namnet på gruppen webbplats medlemmar, markerar den och klickar sedan på **dela**.
    
10. Klicka på bakåtknappen i webbläsaren.
    
11. Klicka på ** \<site name> ägare** i listan.
    
12. Klicka på **nytt**i **personer och grupper**.
    
13. I dialog rutan **dela** skriver du in namnet på gruppen webbplats administratörer, markerar den och klickar sedan på **dela**.
    
14. Klicka på bakåtknappen i webbläsaren.
    
15. Klicka på ** \<site name> besökare** i listan.
    
16. Klicka på **nytt**i **personer och grupper**.
    
17. I dialog rutan **dela** skriver du namnet på gruppen visnings åtkomst för webbplats, markerar den och klickar sedan på **dela**.
    
18. Stäng fliken **behörigheter** i webbläsaren.
    
Resultatet av dessa behörighets inställningar är:
  
- SharePoint-gruppen ** \<site name> ägare** innehåller gruppen webbplats administratörer åtkomst där alla medlemmar har **fullständig** behörighets nivå.
    
- SharePoint-gruppen ** \<site name> medlemmar** innehåller gruppen webbplats medlemmar åtkomst där alla medlemmar har behörighets nivån **Redigera** .
    
- SharePoint-gruppen ** \<site name> besökare** innehåller gruppen webbplats visnings åtkomst där alla medlemmar har behörighets nivån **läsa** .
    
- Möjligheten för medlemmar att bjuda in andra medlemmar eller för icke-medlemmar att begära åtkomst är inaktive rad.
    
Här är din resulterande konfiguration med de tre SharePoint-grupperna för webbplatsen konfigurerade för att använda de tre åtkomst grupperna, som är ifyllda med användar konton eller Azure AD-grupper.
  
![Den sista konfigurationen av din isolerade SharePoint Online-webbplats med åtkomst grupper och användar konton.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
Du och medlemmar av webbplatsen, via grupp medlemskap i en av åtkomst grupperna, kan nu samar beta med webbplats resurserna.
  
## <a name="next-step"></a>Nästa steg

Om du behöver ändra grupp medlemskap för webbplats åtkomst eller skapa en dokumentmapp med anpassade behörigheter läser du [hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)
  
[Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md)
  
[Hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md)
  



