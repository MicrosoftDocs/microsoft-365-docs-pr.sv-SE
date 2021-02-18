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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Hantera en isolerad SharePoint Online-gruppwebbplats, lägg till nya användare och grupper, ta bort användare och grupper och skapa en dokumentundermapp med anpassade behörigheter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289527"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Hantera en isolerad SharePoint Online-gruppwebbplats

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 abonnemang 1](office-365-atp.md)
- SharePoint Online 

 **Sammanfattning:** Hantera din isolerade SharePoint Online-gruppwebbplats med de här procedurerna.

I den här artikeln beskrivs vanliga hanteringsåtgärder för en isolerad SharePoint Online-gruppwebbplats.

## <a name="add-a-new-user"></a>Lägga till en ny användare

När någon ny ansluter till webbplatsen måste du bestämma i vilken grad de vill delta på webbplatsen:

- Administration: Lägg till det nya användarkontot i åtkomstgruppen för webbplatsadministratörer

- Aktivt samarbete: Lägg till användarkontot i åtkomstgruppen för webbplatsmedlemmar

- Visa: Lägga till användarkontot i åtkomstgruppen för webbplatsvisningsprogram

Om du hanterar användarkonton och grupper via Active Directory DS (AD DS) lägger du till rätt användare i lämpliga åtkomstgrupper med dina vanliga procedurer för hantering av AD DS och grupper och väntar på synkronisering med din prenumeration.

Om du hanterar användarkonton och grupper via Microsoft 365 kan du använda administrationscentret för Microsoft 365 eller Microsoft PowerShell:

- I administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Som administratör för användarkonto eller Företagsadministratör, och använder Grupper för att lägga till rätt användare i lämpliga åtkomstgrupper.

- För PowerShell ska du [först ansluta till Azure Active Directory PowerShell för Graph-modulen.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) Om du vill lägga till ett användarkonto i en åtkomstgrupp med dess huvudnamn (UPN) använder du följande PowerShell-kommandoblock:

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

Om du vill lägga till åtkomst till en hel grupp måste du bestämma i vilken grad alla medlemmar i gruppen ska delta på webbplatsen:

- Administration: Lägg till gruppen i åtkomstgruppen för webbplatsadministratörer

- Aktivt samarbete: Lägg till gruppen i åtkomstgruppen för webbplatsmedlemmar

- Visa: Lägga till gruppen i åtkomstgruppen för webbplatsvisningsprogram

Om du hanterar användarkonton och grupper via AD DS kan du lägga till lämpliga grupper i lämpliga grupper med dina vanliga användar- och grupphanteringsprocedurer AD DS och vänta på synkronisering med din prenumeration.

Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:

- I administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Som administratör för användarkonto eller Företagsadministratör, och använder Grupper för att lägga till lämpliga grupper i lämpliga åtkomstgrupper.

- För PowerShell ska du [först ansluta till Azure Active Directory PowerShell för Graph-modulen.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 Använd sedan följande PowerShell-kommandon:

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Ta bort en användare

När någons åtkomst måste tas bort från webbplatsen tar du bort dem från åtkomstgruppen för vilken de för närvarande är medlemmar baserat på deras deltagande på webbplatsen:

- Administration: Ta bort användarkontot från åtkomstgruppen för webbplatsadministratörer

- Aktivt samarbete: Ta bort användarkontot från åtkomstgruppen för webbplatsmedlemmar

- Visa: Ta bort användarkontot från åtkomstgruppen för webbplatsvisningsprogram

Om du hanterar användarkonton och grupper via AD DS kan du ta bort lämpliga användare från lämpliga åtkomstgrupper med dina vanliga procedurer AD DS för användar- och grupphantering och vänta på synkronisering med din prenumeration.

Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:

- I administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Som administratör för användarkonto eller Företagsadministratör, och använder Grupper för att ta bort rätt användare från lämpliga åtkomstgrupper.

- För PowerShell ska du [först ansluta till Azure Active Directory PowerShell för Graph-modulen.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Om du vill ta bort ett användarkonto från en åtkomstgrupp med dess UPN använder du följande PowerShell-kommandoblock:

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

Om du vill ta bort åtkomst för en hel grupp tar du bort gruppen från den åtkomstgrupp där de för närvarande är medlemmar baserat på deras deltagande på webbplatsen:

- Administration: Ta bort gruppen från åtkomstgruppen för webbplatsadministratörer

- Aktivt samarbete: Ta bort gruppen från åtkomstgruppen för webbplatsmedlemmar

- Visa: Ta bort gruppen från åtkomstgruppen för webbplatsvisningsprogram

Om du hanterar användarkonton och grupper via Windows Server Active Directory kan du ta bort lämpliga grupper från lämpliga åtkomstgrupper med dina vanliga procedurer för användar- och grupphantering i AD DS och vänta på synkronisering med din prenumeration.

Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:

- I administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Som administratör för användarkonto eller Företagsadministratör, och använder Grupper för att ta bort lämpliga grupper från lämpliga åtkomstgrupper.

- För PowerShell ska du [först ansluta till Azure Active Directory PowerShell för Graph-modulen.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Om du vill ta bort en grupp från en åtkomstgrupp med hjälp av deras visningsnamn använder du följande PowerShell-kommandoblock:

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Skapa en dokumentundermapp med anpassade behörigheter

I vissa fall behöver en del av de personer som arbetar på den isolerade webbplatsen en mer privat plats för samarbete. För SharePoint Online-webbplatser kan du skapa en undermapp i mappen Dokument på webbplatsen och tilldela anpassade behörigheter. De som inte har behörighet kan inte se undermappen.

Så här skapar du en dokumentundermapp med anpassad behörighet:

1. Logga in på ett konto som är medlem i administratörsåtkomstgruppen för webbplatsen. Mer information finns i [Så här loggar du in i Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Gå till den isolerade gruppwebbplatsen och klicka på **Dokument.**

3. Bläddra till mappen i dokumentmappen som innehåller undermappen med anpassade behörigheter, skapa mappen och öppna den sedan.

4. Klicka **på Dela.**

5. Klicka **på Delas > Avancerat.**

6. Klicka **på Sluta ärva behörigheter** och klicka sedan på **OK.**

7. Klicka **på Dela.**

8. Klicka **på Delas > Avancerat.**

9. Klicka **på Bevilja behörigheter > Delas med > Avancerat.**

10. Klicka på Medlemmar i **\<site name> listan på behörighetssidan.**

11. På sidan **\<site name> Medlemmar** markerar du kryssrutan bredvid åtkomstgruppen Webbplatsmedlemmar, klickar på **Åtgärder,** klickar på Ta bort användare från grupp och klickar sedan på **OK.**

12. Om du vill lägga till specifika medlemmar i den här undermappen **klickar du på > Lägg till användare.**

13. I dialogrutan **Dela** skriver du namnen på användarkontona som kan samarbeta med filer i undermappen och klickar sedan på **Dela.**

14. Uppdatera webbsidan för att se de nya resultaten.

15. Under **Grupper** i det vänstra **\<site name>** navigeringsfältet klickar du på gruppen Besökare och använder steg 11–14 för att ange vilken uppsättning användarkonton som kan visa filerna i undermappen (vid behov).

16. Under **Grupper i** det vänstra **\<site name>** navigeringsfältet klickar du på gruppen Ägare och använder steg 11–14 för att ange den uppsättning användarkonton som kan administrera behörigheterna i undermappen (vid behov).

17. Stäng fliken **Personer och** grupper i webbläsaren.

## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)

[Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md)

[Distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md)
