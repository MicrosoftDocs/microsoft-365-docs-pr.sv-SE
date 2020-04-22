---
title: Utvecklings-/testmiljö för en isolerad resursgrupp online
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
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Sammanfattning: Konfigurera en SharePoint Online-gruppwebbplats som är isolerad från resten av organisationen i microsoft 365-utvecklings-/testmiljön.'
ms.openlocfilehash: 2a1c728f5cbc1d622bb46ffd7532f1103a7995d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634128"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Utvecklings-/testmiljö för en isolerad resursgrupp online

 **Sammanfattning:** Konfigurera en SharePoint Online-gruppwebbplats som är isolerad från resten av organisationen i microsoft 365-utvecklings-/testmiljön.

SharePoint Online-gruppwebbplatser i Microsoft 365 är platser för samarbete med hjälp av ett gemensamt dokumentbibliotek, en OneNote-anteckningsbok och andra tjänster. I många fall vill du ha bred åtkomst och samarbete mellan avdelningar eller organisationer. Men i vissa fall vill du styra åtkomsten och behörigheterna för samarbete mellan en liten grupp personer.

Åtkomst till SharePoint Online-gruppwebbplatser och vad användarna kan göra styrs av SharePoint-grupper och behörighetsnivåer. Som standard har SharePoint Online-webbplatser tre åtkomstnivåer:

- **Medlemmar**, som kan visa, skapa och ändra resurser på webbplatsen.

- **Ägare**, som har fullständig kontroll över webbplatsen, inklusive möjligheten att ändra behörigheter.

- **Besökare**, som bara kan visa resurser på webbplatsen.

I den här artikeln får du hjälp med konfigurationen av en isolerad SharePoint Online-gruppwebbplats för ett hemligt forskningsprojekt med namnet ProjectX. Tillträdeskraven är:

- Endast medlemmar i projektet kan komma åt webbplatsen och dess innehåll (dokument, OneNote Notebook, Pages), med redigerings- och visa SharePoint-behörighetsnivåer som styrs genom gruppmedlemskap.

- Endast webbplatsskaparen och medlemmarna i en administratörsgrupp för webbplatsen kan utföra webbplatsadministration, vilket inkluderar ändring av behörigheter på webbplatsnivå.

Det finns tre faser för att konfigurera en isolerad SharePoint Online-gruppwebbplats i microsoft 365-utvecklings-/testmiljön:

1. Skapa utvecklings-/testmiljön för Microsoft 365.

2. Skapa användare och grupper för ProjectX.

3. Skapa en ny ProjectX SharePoint Online-gruppwebbplats och isolera den.

> [!TIP]
> Klicka [här](https://aka.ms/catlgstack) om du vill ha en visuell karta till alla artiklar i One Microsoft Cloud Test Lab Guide-stacken.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>Fas 1: Bygg ut din lätta eller simulerade företagsmiljö för Microsoft 365-utveckling/test

Om du bara vill skapa en isolerad SharePoint Online-gruppwebbplats på ett lättviktssätt med minimikraven följer du instruktionerna i faserna 2 och 3 i [Microsoft 365 dev/test-miljö](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).

Om du vill skapa en isolerad SharePoint Online-gruppwebbplats i en simulerad företagskonfiguration följer du instruktionerna i [DirSync för din utvecklings-/testmiljö för Microsoft 365](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).

> [!NOTE]
> För att skapa en isolerad SharePoint Online-webbplats krävs inte den simulerade företagsutvecklings-/testmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa en isolerad SharePoint Online-webbplats och experimentera med den i en miljö som representerar en typisk organisation.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fas 2: Skapa användarkonton och åtkomstgrupper

Använd instruktionerna i [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) för att ansluta till din utvärderingsprenumeration med ditt globala administratörskonto från:

- Datorn (för den lätta utvecklings-/testmiljön för Microsoft 365).

- Den virtuella klienten1-datorn (för det simulerade företaget Microsoft 365 dev/test-miljö).

Om du vill skapa de nya åtkomstgrupperna för ProjectX SharePoint Online-gruppwebbplatsen kör du dessa kommandon från Windows Azure Active Directory Module för Windows PowerShell-prompten:

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

Fyll i organisationsnamnet (t.ex. contosotoycompany), landskoden med två tecken för din plats och kör sedan följande kommandon från Windows Azure Active Directory Module för Windows PowerShell-prompt:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Från visningen av kommandot **New-MsolUser** noterar du det genererade lösenordet för Lead Designer-kontot och spelar in det på en säker plats.

Kör följande kommandon från Windows Azure Active Directory Module för Windows PowerShell-prompt:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Från visningen av kommandot **New-MsolUser** noterar du det genererade lösenordet för kontot leda forskare och registrera det på en säker plats.

Kör följande kommandon från Windows Azure Active Directory Module för Windows PowerShell-prompt:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Från visningen av kommandot **New-MsolUser** noterar du det genererade lösenordet för utvecklings-VP-kontot och registrerar det på en säker plats.

Om du vill lägga till de nya kontona i de nya åtkomstgrupperna kör du dessa PowerShell-kommandon från Windows Azure Active Directory Module för Windows PowerShell-prompt:

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

Resultat:

- Åtkomstgruppen ProjectX-medlemmar innehåller användarkontona Lead Designer och Lead Researcher

- Åtkomstgruppen ProjectX-Admins innehåller det globala administratörskontot för din utvärderingsprenumeration

- Åtkomstgruppen ProjectX-Viewers innehåller användarkontot För utvecklingsvp

Figur 1 visar åtkomstgrupperna och deras medlemskap.

**Bild 1**

![Microsoft 365-grupperna och deras medlemskap för en isolerad SharePoint Online Group-webbplats](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fas 3: Skapa en ny ProjectX SharePoint Online-gruppwebbplats och isolera den

Så här skapar du en SharePoint Online-gruppwebbplats för ProjectX:

1. Logga in i Microsoft 365-administrationscentret ( microsoft 365 med[https://admin.microsoft.com](https://admin.microsoft.com)hjälp av en webbläsare på din lokala dator (lättkonfiguration) eller på KLIENT1 (simulerad företagskonfiguration) med hjälp av ditt globala administratörskonto.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya fliken SharePoint i webbläsaren klickar du på **+ Skapa webbplats**.

4. Skriv **ProjectX** **i Gruppplatsnamn**. I **Sekretessinställningar**väljer du **Privat - endast medlemmar kan komma åt den här webbplatsen**.

5. Skriv **SharePoint-webbplats för ProjectX i** **Gruppplatsbeskrivning**och klicka sedan på **Nästa**.

6. På vem **vill du lägga till?** klickar du på **Slutför**.

7. Klicka på inställningsikonen i verktygsfältet på den nya fliken **ProjectX-Start** i webbläsaren och klicka sedan på **Webbplatsbehörigheter**.

8. I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.

9. Klicka på **Inställningar för åtkomstbegäran**i den nya **behörigheten: Project X** i webbläsaren .

10. I dialogrutan **Inställningar för åtkomstbegäranden** avmarkerar du **Tillåt medlemmar att dela webbplatsen och enskilda filer och mappar** och tillåt **åtkomstbegäranden** (så att alla tre kryssrutorna är avmarkerade) och klickar sedan på **OK**.

11. Klicka på **ProjectX-medlemmar** i listan.

12. På sidan **Personer och grupper** klickar du på **Nytt**.

13. Skriv **ProjectX-medlemmar**i dialogrutan **Dela** , markera det och klicka sedan på **Dela**.

14. Klicka på bakåtknappen i webbläsaren.

15. Klicka på **ProjectX-ägare** i listan.

16. På sidan **Personer och grupper** klickar du på **Nytt**.

17. Skriv **ProjectX-Administratörer**i dialogrutan **Dela** , markera det och klicka sedan på **Dela**.

18. Klicka på bakåtknappen i webbläsaren.

19. Klicka på **ProjectX-besökare** i listan.

20. På sidan **Personer och grupper** klickar du på **Nytt**.

21. Skriv **ProjectX-Tittare**i dialogrutan **Dela** , markera det och klicka sedan på **Dela**.

22. Stäng fliken **Personer och grupper** i webbläsaren, klicka på fliken **ProjectX-Start** i webbläsaren och stäng sedan fönstret **Webbplatsbehörigheter.**

Här är resultatet av att konfigurera behörigheter:

- Gruppen ProjectX-medlemmars SharePoint innehåller endast åtkomstgruppen ProjectX-medlemmar (som endast innehåller användarkontona lead designer och lead forskare) och ProjectX-gruppen (som endast innehåller det globala administratörsanvändarkontot).

- Gruppen ProjectX-ägares SharePoint innehåller endast åtkomstgruppen ProjectX-Admins (som bara innehåller det globala administratörsanvändarkontot).

- Gruppen ProjectX-besökares SharePoint innehåller endast åtkomstgruppen ProjectX-Tittare (som bara innehåller användarkontot För utveckling vp).

- Medlemmar kan inte ändra behörigheter på webbplatsnivå (detta kan endast göras av medlemmar i gruppen ProjectX-Administratörer).

- Andra användarkonton kan inte komma åt webbplatsen eller dess resurser. De kan inte heller begära åtkomst till webbplatsen.

Figur 2 visar SharePoint-grupperna och deras medlemskap.

**Bild 2**

![SharePoint Online-grupperna och deras medlemskap för en isolerad SharePoint Online Group-webbplats](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Nu ska vi visa åtkomst med hjälp av Lead Designer-användarkontot:

1. Stäng fliken **ProjectX-Start** i webbläsaren och klicka sedan på fliken **Start i Microsoft Office** i webbläsaren.

2. Klicka på namnet på den globala administratören och klicka sedan på **Logga ut**.

3. Logga in på Microsoft 365[https://admin.microsoft.com](https://admin.microsoft.com)administrationscenter ( ) med lead designer-kontonamnet och dess lösenord.

4. Klicka på **SharePoint** i listan med paneler.

5. På den nya **fliken SharePoint** i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på ProjectX-gruppwebbplatsen. **ProjectX** Du bör se en ny flik i webbläsaren för ProjectX-gruppwebbplatsen.

6. Klicka på inställningsikonen. Observera att det inte finns något alternativ för **webbplatsbehörigheter**. Detta är korrekt eftersom endast medlemmarna i gruppen ProjectX-administratörer kan ändra behörigheter på webbplatsen

7. Öppna Anteckningar eller en textredigerare som du väljer.

8. Kopiera URL:en för ProjectX-gruppwebbplatsen och klistra in den på en ny rad i Anteckningar eller textredigeraren.

9. Klicka på **Dokument**på den nya fliken **ProjectX-Start** i webbläsaren .

10. Kopiera URL:en för mappen ProjectX-dokument och klistra in den på en ny rad i Anteckningar eller textredigeraren.

11. Klicka på **Nytt > Word-dokument**på fliken **Nya ProjektX-dokument** i webbläsaren .

12. Skriv text på sidan, vänta tills statusen visas **Sparad,** klicka på bakåtknappen i webbläsaren och uppdatera sedan sidan. Du bör se ett nytt **Document.docx** i mappen **Dokument.**

13. Klicka på ellipsen för **Document.docx-dokumentet** och klicka sedan på **Hämta en länk**.

14. Kopiera webbadressen i dialogrutan **Dela "Document.docx"** och klistra in den på en ny rad i Anteckningar eller textredigeraren och stäng sedan dialogrutan **Dela "Document.docx".**

15. Stäng **flikarna ProjectX-dokument** och **SharePoint** i webbläsaren och klicka sedan på fliken **Start i Microsoft Office.**

16. Klicka på **leaddesignerns** namn och klicka sedan på **Logga ut**.

Nu ska vi visa åtkomst med hjälp av utvecklings-VP-användarkontot:

1. Logga in på Microsoft 365[https://admin.microsoft.com](https://admin.microsoft.com)administrationscenter ( ) med hjälp av utvecklings-VP-kontonamnet och dess lösenord.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya **fliken SharePoint** i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på ProjectX-gruppwebbplatsen. **ProjectX** Du bör se en ny flik i webbläsaren för ProjectX-gruppwebbplatsen.

4. Klicka på **Dokument**och sedan på **filen Document.docx.**

5. Försök att ändra texten på fliken **Document.docx** i webbläsaren. Du bör se ett meddelande om att **det här dokumentet är skrivskyddat.** Detta förväntas eftersom användarkontot för utvecklingsvp endast har visningsbehörighet för webbplatsen.

6. Stäng flikarna **Document.docx,** **ProjectX-Documents**och **SharePoint** i webbläsaren.

7. Klicka på fliken **Start i Microsoft Office,** klicka på namnet **utveckling vp** och klicka sedan på **Logga ut**.

Nu ska vi visa åtkomst med ett användarkonto som inte har några behörigheter:

1. Logga in på Microsoft 365[https://admin.microsoft.com](https://admin.microsoft.com)administrationscenter ( ) med användar3-kontonamnet och dess lösenord.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya **fliken SharePoint** i webbläsaren skriver du **ProjectX** i sökrutan och aktiverar sedan sökningen. Du bör se meddelandet **Ingenting här matchar din sökning.**

4. Kopiera URL:en för ProjectX-webbplatsen till webbläsarens adressfält från den öppna förekomsten av Anteckningar eller textredigeraren och tryck på **Retur**. Du bör se en **åtkomst nekad** sida.

5. Kopiera URL:en för mappen ProjectX-dokument i webbläsarens adressfält från Anteckningar eller textredigeraren och tryck på **Retur**. Du bör se en **åtkomst nekad** sida.

6. Kopiera URL:en för filen Documents.docx i webbläsarens adressfält från Anteckningar eller textredigeraren och tryck på **Retur**. Du bör se en **åtkomst nekad** sida.

7. Stäng **fliken SharePoint** i webbläsaren, klicka på fliken **Start för Microsoft Office,** klicka på **namnet Användare 3** och klicka sedan på **Logga ut**.

Din isolerade SharePoint Online-webbplats är nu klar för ytterligare experiment.

## <a name="next-step"></a>Nästa steg

När du är redo att distribuera en isolerad SharePoint Online-gruppwebbplats i produktion kan du läsa de steg för steg-informationen om utformning i [Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)

[Testlabbguider för integrering med molntjänster](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Utvecklings-/testmiljö för baskonfiguration](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)

[Utvecklings-/testmiljö för Microsoft 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)

[Införande av moln- och hybridlösningar](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




