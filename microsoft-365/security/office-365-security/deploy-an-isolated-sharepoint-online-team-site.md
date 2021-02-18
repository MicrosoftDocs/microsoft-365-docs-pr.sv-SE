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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Använd den här stegvisa distributionsguiden för att skapa och konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d226a545c3f8dc274f02e5d54d39739fe5d981ea
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288353"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Distribuera en isolerad SharePoint Online-gruppwebbplats

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

 **Sammanfattning:** Distribuera en ny isolerad SharePoint Online-gruppwebbplats med de här stegvisa instruktionerna.

Den här artikeln är en stegvis distributionsguide för hur du skapar och konfigurerar en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365. I de här stegen förutsätts det att de tre standardgrupperna i SharePoint och motsvarande behörighetsnivåer används, med en enda Azure Active Directory-baserad åtkomstgrupp (AD) för varje åtkomstnivå.

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Fas 1: Skapa och fylla i åtkomstgrupper för gruppwebbplatser

I den här fasen skapar du de tre Azure AD-baserade åtkomstgrupperna för de tre standardgrupperna i SharePoint och fyller dem med lämpliga användarkonton.

> [!NOTE]
> Följande steg förutsätter att alla nödvändiga användarkonton redan finns och har tilldelats lämpliga licenser. Annars kan du lägga till dem och tilldela licenser innan du fortsätter med steg 1.

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Steg 1: Lista SharePoint Online-administratörerna för webbplatsen

Fastställ den uppsättning användarkonton som motsvarar SharePoint Online-administratörerna för den isolerade gruppwebbplatsen.

Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda Windows PowerShell gör du en lista över deras användarhuvudnamn (UPN) (exempel UPN: belindan@contoso.com).

### <a name="step-2-list-the-members-for-the-site"></a>Steg 2: Lista medlemmar för webbplatsen

Fastställ vilken uppsättning användarkonton som motsvarar medlemmarna för den isolerade gruppwebbplatsen, de som ska samarbeta med resurser som lagras på webbplatsen.

Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda PowerShell gör du en lista med deras UPN-namn. Om det finns många medlemmar på webbplatsen kan du lagra listan med UPN-namn i en textfil och lägga till dem alla med ett enda PowerShell-kommando.

### <a name="step-3-list-the-viewers-for-the-site"></a>Steg 3: Lista användarna för webbplatsen

Bestäm vilken uppsättning användarkonton som motsvarar de som visar den isolerade gruppwebbplatsen, de som kan visa de resurser som finns lagrade på webbplatsen men inte ändra dem eller samarbeta direkt med innehållet.

Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda PowerShell gör du en lista med deras UPN-namn. Om det finns många medlemmar på webbplatsen kan du lagra listan med UPN-namn i en textfil och lägga till dem alla med ett enda PowerShell-kommando.

Användare för webbplatsen kan omfatta ledning, juridisk rådgivning eller mellan avdelningars intressenter.

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Steg 4: Skapa de tre åtkomstgrupperna för webbplatsen i Azure AD

Du måste skapa följande åtkomstgrupper i Azure AD:

- Webbplatsadministratörer (som kommer att innehålla listan från steg 1)
- Webbplatsmedlemmar (som kommer att innehålla listan från steg 2)
- Webbplatsvisare (som kommer att innehålla listan från steg 3)

1. Gå till Azure-portalen i webbläsaren och logga in med autentiseringsuppgifterna för ett konto som har tilldelats rollen Användarhanteringsadministratör eller <https://portal.azure.com> Företagsadministratör.

2. I Azure-portalen klickar du på **Azure Active Directory > Grupper**.

3. Gå till bladet **Grupper – Alla grupper** och klicka på **+ Ny grupp**.

4. I **bladet Ny** grupp:

   - Välj **Säkerhet** i **Grupptyp**.

   - Skriv gruppnamnet i **Namn.**

   - Skriv en beskrivning av gruppen i **gruppbeskrivningen.**

   - Välj **Tilldelad** i **Typ av medlemskap**.

5. Klicka på **Skapa** och stäng sedan bladet **Grupp**.

6. Upprepa steg 3–5 för de övriga grupperna.

> [!NOTE]
> Du måste använda Azure Portal för att skapa grupperna så att de har Office-funktioner aktiverade. Om en sharePoint Online-isolerad webbplats senare konfigureras som en webbplats med mycket konfidentiell information med azure informationsskydd-etiketten för att kryptera filer och tilldela behörighet till specifika grupper, måste de tillåtna grupperna ha skapats med Office-funktioner aktiverade. Du kan inte ändra Office-funktioner för en Azure AD-grupp när den har skapats.

Här är den resulterande konfigurationen med de tre grupperna för webbplatsåtkomst.

![De tre åtkomstgrupperna för din distribution av en isolerad SharePoint Online-webbplats.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Steg 5: Lägga till användarkontona i åtkomstgrupper

I det här steget gör du följande:

1. Lägg till listan med användare från steg 1 i åtkomstgruppen för webbplatsadministratörer.
2. Lägg till listan med användare från steg 2 i åtkomstgruppen för webbplatsmedlemmar.
3. Lägg till listan med användare från steg 3 i åtkomstgruppen för webbplatsvisare.

Om du hanterar användarkonton och grupper via Active Directory DS (AD DS) kan du lägga till användare i lämpliga åtkomstgrupper med dina vanliga procedurer för användar- och grupphantering i AD DS och vänta på synkronisering med Microsoft 365-prenumerationen.

Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell. Om du har dubbletter av gruppnamn för någon av åtkomstgrupperna bör du använda administrationscentret för Microsoft 365.

I administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Som administratör för användarkonto eller Företagsadministratör, och använder Grupper för att lägga till användarkonton och grupper i lämpliga åtkomstgrupper.

För PowerShell ska du [först ansluta till Azure Active Directory PowerShell för Graph-modulen.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

Använd sedan följande kommandoblock för att lägga till ett enskilt användarkonto i en åtkomstgrupp:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Om du har lagrat UPN-namn för användarkonton för någon av åtkomstgrupperna i en textfil kan du använda följande PowerShell-kommandoblock för att lägga till dem alla samtidigt:

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

Resultatet bör vara följande:

- Webbplatsadministratörerna för Azure AD-gruppen innehåller användarkonton eller grupper för webbplatsadministratörer
- Azure AD-gruppen för webbplatsmedlemmar innehåller användarkonton eller grupper för webbplatsmedlemmar
- Azure AD-gruppen för webbplatsvisningsprogram innehåller användarkonton eller grupper som bara kan visa webbplatsinnehållet

Validera listan över gruppmedlemmar för varje åtkomstgrupp med administrationscentret för Microsoft 365 eller med följande PowerShell-kommandoblock:

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Här är den resulterande konfigurationen med de tre grupperna för webbplatsåtkomst som är ifyllda med användarkonton eller grupper.

![De tre åtkomstgrupperna som är ifyllda med användarkonton.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Fas 2: Skapa och konfigurera den isolerade gruppwebbplatsen

I den här fasen skapar du den isolerade SharePoint Online-webbplatsen och konfigurerar behörigheterna för standardbehörighetsnivåerna i SharePoint Online till att använda de nya Azure AD-baserade åtkomstgrupperna. Som standard innehåller nya gruppwebbplatser en Microsoft 365-grupp och andra relaterade resurser, men i det här fallet skapar vi en gruppwebbplats utan en Microsoft 365-grupp. På så sätt kan du underhålla behörigheter helt och hållet via SharePoint.

Börja med att skapa SharePoint Online-gruppwebbplatsen med de här stegen.

1. Logga in på administrationscentret för Microsoft 365 med ett konto som också kommer att användas för att administrera SharePoint Online-gruppwebbplatsen (en SharePoint Online-administratör). Mer information finns i [Så här loggar du in i Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Klicka på SharePoint i administrationscentret för Microsoft 365, under **Administrationscenter.**

3. I administrationscentret för SharePoint expanderar **du Webbplatser** och klickar **på Aktiva webbplatser.**

4. Klicka **på Skapa** och välj sedan Andra **alternativ.**

5. Välj **Gruppwebbplats i** listan Välj **en mall.**

6. Ange **ett namn** på gruppwebbplatsen i Webbplatsnamn.

7. I **Primär administratör** anger du det konto som du är inloggad med.

8. Klicka på **Slutför**.

Konfigurera sedan behörigheter från den nya SharePoint Online-gruppwebbplatsen.

1. Klicka på inställningsikonen i verktygsfältet och klicka sedan på **Webbplatsbehörigheter**.

2. Klicka **på Ändra hur** medlemmar kan dela under **Webbplatsdelning.**

3. Välj endast **webbplatsägare som kan dela filer, mappar och webbplatsen.**

4. Ställ **in Tillåt åtkomstförfrågningar** på **Av.**

5. Klicka på **Spara**.

6. Klicka på **Avancerade** behörighetsinställningar i **fönstret Behörigheter.**

7. Klicka **på Medlemmar** i listan på fliken **\<site name> Behörigheter** i webbläsaren.

8. Klicka **på Nytt i** Personer och **grupper.**

9. Skriv namnet **på** åtkomstgruppen webbplatsmedlemmar i dialogrutan Dela, markera den och klicka sedan på **Dela.**

10. Klicka på bakåtknappen i webbläsaren.

11. Klicka **\<site name> på** Ägare i listan.

12. Klicka **på Nytt i Personer** och **grupper.**

13. Skriv namnet **på** åtkomstgruppen webbplatsadministratörer i dialogrutan Dela, markera den och klicka sedan på **Dela.**

14. Klicka på bakåtknappen i webbläsaren.

15. Klicka **\<site name> på** Besökare i listan.

16. Klicka **på Nytt i Personer** och **grupper.**

17. I dialogrutan **Dela** skriver du namnet på gruppen webbplatsvisare, markerar den och klickar sedan på **Dela.**

18. Stäng **fliken Behörigheter** i webbläsaren.

Resultatet av de här behörighetsinställningarna är:

- SharePoint-gruppen Ägare innehåller webbplatsadministratörsåtkomstgruppen, där alla medlemmar har **behörighetsnivån Fullständig** behörighet. **\<site name>**
- **\<site name> SharePoint-gruppen** Medlemmar innehåller gruppen webbplatsmedlemmar, där alla medlemmar har **behörighetsnivån** Redigera.
- **\<site name> SharePoint-gruppen** Besökare innehåller gruppen Webbplatsläsaråtkomst, där alla medlemmar har **behörighetsnivån** Läsa.
- Möjligheten för medlemmar att bjuda in andra medlemmar eller för icke-medlemmar att begära åtkomst inaktiveras.

Här är den resulterande konfigurationen med de tre SharePoint-grupperna för webbplatsen som konfigurerats för att använda de tre åtkomstgrupperna, som är ifyllda med användarkonton eller Azure AD-grupper.

![Den slutliga konfigurationen av din isolerade SharePoint Online-webbplats med åtkomstgrupper och användarkonton.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

Du och webbplatsens medlemmar, via gruppmedlemskap i någon av åtkomstgrupperna, kan nu samarbeta med hjälp av webbplatsens resurser.

## <a name="next-step"></a>Nästa steg

Om du behöver ändra medlemskap i en webbplatsåtkomstgrupp eller skapa en dokumentmapp med anpassad behörighet kan du läsa Hantera [en isolerad SharePoint Online-gruppwebbplats.](manage-an-isolated-sharepoint-online-team-site.md)

## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)

[Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md)

[Hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md)
