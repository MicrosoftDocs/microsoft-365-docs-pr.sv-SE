---
title: Isolerad utvecklings-/testmiljö för SharePoint Online-gruppwebbplats
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
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Sammanfattning: Konfigurera en SharePoint Online-gruppwebbplats som isoleras från resten av organisationen i utvecklings-/testmiljön för Microsoft 365.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286615"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Isolerad utvecklings-/testmiljö för SharePoint Online-gruppwebbplats

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 abonnemang 1](office-365-atp.md)
- SharePoint Online 


 **Sammanfattning:** Konfigurera en SharePoint Online-gruppwebbplats som isoleras från resten av organisationen i utvecklings-/testmiljön för Microsoft 365.

SharePoint Online-gruppwebbplatser i Microsoft 365 är platser för samarbete med hjälp av ett gemensamt dokumentbibliotek, en OneNote-anteckningsbok och andra tjänster. I många fall vill du ha bred åtkomst och samarbete mellan avdelningar eller organisationer. Men i vissa fall vill du ha nära kontroll över åtkomst och behörighet för samarbete mellan en liten grupp personer.

Åtkomsten till SharePoint Online-gruppwebbplatser och vad användarna kan göra styrs av SharePoint-grupper och behörighetsnivåer. Som standard har SharePoint Online-webbplatser tre åtkomstnivåer:

- **Medlemmar,** som kan visa, skapa och ändra resurser på webbplatsen.
- **Ägare,** som har fullständig kontroll över webbplatsen, inklusive möjligheten att ändra behörigheter.
- **Besökare,** som bara kan visa resurser på webbplatsen.

Den här artikeln beskriver hur du kan konfigurera en isolerad SharePoint Online-gruppwebbplats för ett hemligt forskningsprojekt med namnet ProjectX. Åtkomstkraven är:

- Endast medlemmar i projektet kan komma åt webbplatsen och dess innehåll (dokument, OneNote-anteckningsbok, sidor), med behörighetsnivåer för redigering och visning av SharePoint som styrs av gruppmedlemskap.

- Endast webbplatsskaparen och medlemmar i en administratörsgrupp för webbplatsen kan utföra webbplatsadministration, vilket omfattar att ändra behörigheter på webbplatsnivå.

Det finns tre faser för att konfigurera en isolerad SharePoint Online-gruppwebbplats i utvecklings-/testmiljön för Microsoft 365:

1. Skapa utvecklings-/testmiljön för Microsoft 365.

2. Skapa användare och grupper för ProjectX.

3. Skapa en ny ProjectX SharePoint Online-gruppwebbplats och isolera den.

> [!TIP]
> Klicka [här](https://aka.ms/catlgstack) för en visuell karta till alla artiklar i en Microsoft Cloud Test Lab Guide-stack.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>Fas 1: Bygg ut din lättaste eller simulerade utvecklings-/testmiljö för Microsoft 365

Om du bara vill skapa en isolerad SharePoint Online-gruppwebbplats på ett lätt sätt med minimikraven följer du anvisningarna i fas 2 och 3 i den lätta [grundkonfigurationen.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

Om du vill skapa en isolerad SharePoint Online-gruppwebbplats i en simulerad företagskonfiguration följer du anvisningarna i synkronisering av lösenordshashar för [Microsoft 365-testmiljön.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)

> [!NOTE]
> Om du skapar en isolerad SharePoint Online-webbplats krävs inte den simulerade utvecklings-/testmiljön för företag, vilket omfattar en simulerad intranätanslutning till Internet och katalogsynkronisering för en Active Directory DS-skog (AD DS). Här finns ett alternativ för att testa en isolerad SharePoint Online-webbplats och experimentera med den i en miljö som representerar en vanlig organisation.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Steg 2: Skapa användarkonton och komma åt grupper

Följ anvisningarna i [Ansluta till Office 365 PowerShell för](../../enterprise/connect-to-microsoft-365-powershell.md) att ansluta till utvärderingsprenumerationen med ditt globala administratörskonto från:

- Din dator (för den lätta utvecklings-/testmiljön för Microsoft 365).

- Den virtuella KLIENT1-datorn (för det simulerade företagets utvecklings-/testmiljö för Microsoft 365).

Skapa de nya åtkomstgrupperna för ProjectX SharePoint Online-gruppwebbplatsen genom att köra följande kommandon från kommandotolken för Windows Azure Active Directory-modulen för Windows PowerShell:

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

Fyll i ditt organisationsnamn (exempel: contosotoycompany), landskoden för de två tecken som finns på din plats och kör sedan följande kommandon från kommandotolken för Windows Azure Active Directory-modulen för Windows PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Notera det genererade lösenordet för Lead Designer-kontot från visningen av kommandot **New-MsolUser** och registrera det på en säker plats.

Kör följande kommandon från uppmaningen Windows Azure Active Directory-modul för Windows PowerShell:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Notera det genererade lösenordet för lead researcher-kontot från visningen av kommandot **New-MsolUser** och registrera det på en säker plats.

Kör följande kommandon från uppmaningen Windows Azure Active Directory-modul för Windows PowerShell:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Notera det genererade lösenordet för Development VP-kontot från visningen av **kommandot New-MsolUser** och registrera det på en säker plats.

Om du vill lägga till nya konton i de nya åtkomstgrupperna kör du följande PowerShell-kommandon från uppmaningen Windows Azure Active Directory-modul för Windows PowerShell:

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

- Gruppen ProjectX-Members innehåller användarkontona Lead Designer och Lead Researcher

- Gruppen ProjectX-Admins innehåller det globala administratörskontot för utvärderingsprenumerationen

- Gruppen ProjectX-Viewers innehåller användarkontot Development VP

I bild 1 visas åtkomstgrupperna och deras medlemskap.

**Bild 1:**

![Microsoft 365-grupperna och deras medlemskap för en isolerad SharePoint Online-gruppwebbplats](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fas 3: Skapa en ny ProjectX SharePoint Online-gruppwebbplats och isolera den

Så här skapar du en SharePoint Online-gruppwebbplats för ProjectX:

1. Med hjälp av en webbläsare på din lokala dator (enkel konfiguration) eller på CLIENT1 (simulerad företagskonfiguration) loggar du in på administrationscentret för Microsoft 365 () med ditt <https://admin.microsoft.com> globala administratörskonto.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya fliken SharePoint i webbläsaren klickar du på **+ Skapa webbplats**.

4. Skriv ProjectX **i** **gruppwebbplatsens namn.** Välj **Privat i Sekretessinställningar** **– endast medlemmar kan komma åt den här webbplatsen.**

5. Skriv **SharePoint-webbplats** för **ProjectX i beskrivningen av gruppwebbplatsen** och klicka sedan på **Nästa.**

6. På knappen **Vem vill du lägga till?** klickar du på **Slutför.**

7. Klicka på ikonen för inställningar i verktygsfältet på den nya **fliken ProjectX-Start** i webbläsaren och klicka sedan på **Webbplatsbehörigheter.**

8. I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.

9. I den nya **behörighetsfliken: Project X** i webbläsaren klickar du på **Inställningar för åtkomstbegäran.**

10. Avmarkera **Tillåt** medlemmar att dela  webbplatsen och enskilda filer och mappar och Tillåt åtkomstbegäranden **(så** att alla tre kryssrutorna avmarkeras) i dialogrutan Inställningar för åtkomstbegäranden och klicka sedan på **OK.**

11. Klicka **på ProjectX-medlemmar** i listan.

12. På sidan **Personer och grupper** klickar du på **Nytt**.

13. Skriv  **ProjectX-Members** i dialogrutan Dela, markera den och klicka sedan på **Dela.**

14. Klicka på bakåtknappen i webbläsaren.

15. Klicka **på ProjectX-ägare** i listan.

16. På sidan **Personer och grupper** klickar du på **Nytt**.

17. Skriv  **ProjectX-administratörer** i dialogrutan Dela, markera det och klicka sedan på **Dela.**

18. Klicka på bakåtknappen i webbläsaren.

19. Klicka **på ProjectX-besökare** i listan.

20. På sidan **Personer och grupper** klickar du på **Nytt**.

21. Skriv  **ProjectX-Viewers** i dialogrutan Dela, markera det och klicka sedan på **Dela.**

22. Stäng fliken **Personer och** grupper i webbläsaren, klicka på fliken **ProjectX-Start** i webbläsaren och stäng sedan fönstret **Webbplatsbehörigheter.**

Här är resultatet av att konfigurera behörigheter:

- SharePoint-gruppen ProjectX-medlemmar innehåller endast åtkomstgruppen ProjectX-Members (som endast innehåller användarkontona Lead Designer och Lead Researcher) och ProjectX-gruppen (som endast innehåller användarkontot för global administratör).

- SharePoint-gruppen ProjectX-ägare innehåller ProjectX-Admins gruppen (som endast innehåller användarkontot för global administratör).

- SharePoint-gruppen ProjectX Visitors innehåller endast ProjectX-Viewers åtkomstgrupp (som endast innehåller development VP-användarkontot).

- Medlemmar kan inte ändra behörigheter på webbplatsnivå (detta kan endast utföras av medlemmar i ProjectX-Admins gruppen).

- Andra användarkonton kan inte komma åt webbplatsen eller dess resurser. De kan inte heller begära åtkomst till webbplatsen.

Bild 2 visar SharePoint-grupperna och deras medlemskap.

**Bild 2**

![SharePoint Online-grupperna och deras medlemskap för en isolerad SharePoint Online-gruppwebbplats](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Nu visar vi åtkomst med hjälp av leaddesignerns användarkonto:

1. Stäng fliken **ProjectX-Home** i webbläsaren och klicka sedan på fliken **Microsoft Office Start** i webbläsaren.

2. Klicka på den globala administratörens namn och klicka sedan på **Logga ut.**

3. Logga in på administrationscentret för Microsoft 365 <https://admin.microsoft.com> () med hjälp av leaddesignerns kontonamn och lösenord.

4. Klicka på **SharePoint** i listan med paneler.

5. På den nya **SharePoint-fliken** i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på ProjectX-gruppwebbplatsen.  Du bör se en ny flik i webbläsaren för ProjectX-gruppwebbplatsen.

6. Klicka på inställningsikonen. Observera att det inte finns något alternativ för **webbplatsbehörigheter.** Det här är rätt eftersom endast medlemmar i ProjectX-Admins kan ändra behörigheter på webbplatsen

7. Öppna Anteckningar eller en valfri textredigerare.

8. Kopiera WEBBADRESSen till ProjectX-gruppwebbplatsen och klistra in den på en ny rad i Anteckningar eller i textredigeraren.

9. Klicka på **Dokument på den nya fliken ProjectX-Start** i **webbläsaren.**

10. Kopiera WEBBADRESSen till mappen ProjectX-dokument och klistra in den på en ny rad i Anteckningar eller i textredigeraren.

11. På den nya **fliken ProjectX-Dokument** i webbläsaren klickar du på **Nytt > Word-dokument.**

12. Skriv lite text på sidan, vänta tills statusen visar Sparad, klicka på tillbaka-knappen i webbläsaren och uppdatera sedan sidan. Du bör se en **Document.docx** objekt i **mappen** Dokument.

13. Klicka på ellipsen för **Document.docx** och klicka sedan **på Hämta en länk.**

14. Kopiera WEBBADRESSen i dialogrutan Dela **Document.docx** och klistra in den på en ny rad i Anteckningar  eller textredigeraren och stäng sedan dialogrutan Dela Document.docx.

15. Stäng **flikarna ProjectX-Dokument** **och SharePoint** i webbläsaren och klicka sedan på fliken **Start i Microsoft Office.**

16. Klicka på **leaddesignerns** namn och klicka sedan **på Logga ut.**

Nu visar vi åtkomst med hjälp av development VP-användarkontot:

1. Logga in på Administrationscenter för Microsoft 365 () med <https://admin.microsoft.com> hjälp av development VP-kontonamnet och dess lösenord.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya **SharePoint-fliken** i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på ProjectX-gruppwebbplatsen.  Du bör se en ny flik i webbläsaren för ProjectX-gruppwebbplatsen.

4. Klicka **på** Dokument och sedan på **Document.docx** dokumentfilen.

5. I **Document.docx** i webbläsaren kan du försöka ändra texten. Du bör se ett meddelande som **säger att det här dokumentet är skrivskyddade.** Detta förväntas eftersom development VP-användarkontot bara har visningsbehörigheter för webbplatsen.

6. Stäng **flikarnaDocument.docx,** **ProjectX-Dokument** och **SharePoint** i webbläsaren.

7. Klicka på **fliken Microsoft Office Home,** klicka på **development VP-namnet** och klicka sedan på **Logga ut.**

Nu ska vi visa åtkomst med ett användarkonto som inte har någon behörighet:

1. Logga in på administrationscentret för Microsoft 365 <https://admin.microsoft.com> () med användarnamnet och lösenordet för User 3-kontot.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya **SharePoint-fliken** i webbläsaren skriver du **ProjectX** i sökrutan och aktiverar sökningen. Du bör se meddelandet **Inget här matchar din sökning.**

4. I den öppna instansen av Anteckningar eller textredigeraren kopierar du URL-adressen för ProjectX-webbplatsen till adressfältet i webbläsaren och trycker på **Retur.** Du bör se en sida **om nekad** åtkomst.

5. Kopiera WEBBADRESSen för mappen ProjectX-dokument från Anteckningar eller textredigeraren till adressfältet i webbläsaren och tryck på **Retur.** Du bör se en sida **om nekad** åtkomst.

6. I Anteckningar eller i textredigeraren kopierar du URL:en för Documents.docx filen i adressfältet i webbläsaren och trycker på **Retur.** Du bör se en sida **om nekad** åtkomst.

7. Stäng **fliken SharePoint** i webbläsaren, klicka på fliken Start i **Microsoft Office,** klicka på namnet Användare **3** och klicka sedan **på Logga ut.**

Din isolerade SharePoint Online-webbplats är nu redo att experimentera ytterligare.

## <a name="next-step"></a>Nästa steg

När du är redo att distribuera en isolerad SharePoint Online-gruppwebbplats i produktion kan du läsa de steg för steg-informationen om utformning i [Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)

[Testlabbguider för integrering med molntjänster](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[Baskonfiguration för simulerat företag](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[Den enkla baskonfigurationen](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[Microsoft 365-center för lösningar och arkitektur](../../solutions/index.yml)