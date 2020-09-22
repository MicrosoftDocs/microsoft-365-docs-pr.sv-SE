---
title: Isolerad SharePoint Online-grupps dev-och test miljö
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
description: 'Sammanfattning: Konfigurera en SharePoint Online-gruppwebbplats som är isolerad från resten av organisationen i din Microsoft 365-miljö.'
ms.openlocfilehash: e21dccb9ef535bb997d6e62b70e5576bf531041c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199667"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Isolerad SharePoint Online-grupps dev-och test miljö

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **Sammanfattning:** Konfigurera en SharePoint Online-gruppwebbplats som är isolerad från resten av organisationen i din Microsoft 365-miljö.

SharePoint Online-gruppwebbplatser i Microsoft 365 är platser för samarbete med ett gemensamt dokument bibliotek, en OneNote-anteckningsbok och andra tjänster. I många fall vill du ha bred åtkomst och samarbete mellan avdelningar och organisationer. I vissa fall vill du dock noggrant kontrol lera åtkomst och behörigheter för samarbete mellan en liten grupp med personer.

Åtkomst till SharePoint Online-gruppwebbplatser och vilka användare som kan göra styrs av SharePoint-grupper och behörighets nivåer. Som standard har SharePoint Online-webbplatser tre åtkomst nivåer:

- **Medlemmar**, som kan visa, skapa och ändra resurser på webbplatsen.

- **Ägare**, som har fullständig kontroll över webbplatsen, inklusive möjligheten att ändra behörigheter.

- **Besökare**, vilka bara kan visa resurser på webbplatsen.

I den här artikeln beskrivs hur du konfigurerar en isolerad SharePoint Online-gruppwebbplats för ett hemligt forsknings projekt med namnet ProjectX. Åtkomst kraven är:

- Endast medlemmar i projektet kan komma åt webbplatsen och dess innehåll (dokument, OneNote-anteckningsbok, sidor) med redigera och visa SharePoint-behörighets nivåer som styrs via grupp medlemskap.

- Endast webbplats skaparen och medlemmar i en administratörs grupp för webbplatsen kan utföra webbplats administration, vilket inkluderar ändringar på webbplats nivå.

Det finns tre faser för att konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft 365 dev/test-miljön:

1. Skapa utvecklings-och test miljön för Microsoft 365.

2. Skapa användare och grupper för ProjectX.

3. Skapa en ny ProjectX SharePoint Online-gruppwebbplats och isolera den.

> [!TIP]
> Klicka [här](https://aka.ms/catlgstack) för en visuell karta till alla artiklar i den One-guiden för Microsoft Cloud Test Lab.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>Fas 1: skapa en lätt eller simulerad företags support för Microsoft 365 dev/test

Om du bara vill skapa en isolerad SharePoint Online-gruppwebbplats på ett enkelt sätt med minimi kraven följer du instruktionerna i steg 2 och 3 i [Lightweight Base Configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).

Om du vill skapa en isolerad SharePoint Online-gruppwebbplats i en simulerad företags konfiguration följer du anvisningarna i [Synkronisera lösen ord för din Microsoft 365 test miljö](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).

> [!NOTE]
> Att skapa en isolerad SharePoint Online-webbplats kräver inte den simulerade företags dev/test miljön som innehåller ett simulerat intranät som är kopplat till Internet och katalog för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ för att testa en isolerad SharePoint Online-webbplats och experimentera med den i en miljö som representerar en typisk organisation.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fas 2: skapa användar konton och åtkomst grupper

Använd anvisningarna i [Anslut till Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) för att ansluta till utvärderings prenumerationen med ditt globala administratörs konto från:

- Din dator (för den lättviktiga Microsoft 365-miljön).

- Den virtuella KLIENT1-datorn (för den simulerade företags Microsoft 365-miljön).

Kör de här kommandona från Windows Azure Active Directory-modulen för Windows PowerShell för att skapa nya åtkomst grupper för SharePoint Online-ProjectX:

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

Fyll i organisationens namn (till exempel: contosotoycompany), lands koden med två tecken för din plats och kör sedan följande kommandon från Windows Azure Active Directory-modulen för Windows PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Observera det genererade lösen ordet för det Lead Designer-konto som visas på en säker plats med kommandot **ny-MsolUser** .

Kör följande kommandon från Windows Azure Active Directory-modulen för Windows PowerShell-uppmaningen:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Observera det genererade lösen ordet för kontot leads för forskare från visningen av det **nya-MsolUser-** kommandot och registrera det på en säker plats.

Kör följande kommandon från Windows Azure Active Directory-modulen för Windows PowerShell-uppmaningen:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Observera det genererade lösen **New-MsolUser** ordet för utvecklings direktörs kontot och registrera det på en säker plats.

För att lägga till nya konton i de nya åtkomst grupperna kör du dessa PowerShell-kommandon från Windows Azure Active Directory-modulen för Windows PowerShell:

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

Resultat

- Åtkomst gruppen ProjectX-medlemmar innehåller användar kontona för lead designer och ledar forskare

- Åtkomst gruppen ProjectX-administratörer innehåller det globala administratörs kontot för utvärderings prenumerationen

- Åtkomst gruppen ProjectX-visnings program innehåller användar kontot för utvecklings användare

Bild 1 visar åtkomst grupper och deras medlemskap.

**Bild 1**

![Microsoft 365-grupperna och deras medlemskap för en isolerad SharePoint Online-gruppwebbplats](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fas 3: skapa en ny ProjectX för SharePoint Online och isolera den

Så här skapar du en SharePoint Online-gruppwebbplats för ProjectX:

1. Med en webbläsare på din lokala dator (Lightweight Configuration) eller på KLIENT1 (simulerad företags konfiguration) loggar du in på Microsoft 365 Admin Center ( [https://admin.microsoft.com](https://admin.microsoft.com) ) med ditt globala administratörs konto.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya fliken SharePoint i webbläsaren klickar du på **+ Skapa webbplats**.

4. I **grupp webbplatsens namn**skriver du **ProjectX**. Välj privata medlemmar i **Sekretess inställningar**för **att få åtkomst till webbplatsen**.

5. I **grupp webbplats Beskrivning**skriver du **SharePoint-webbplats för ProjectX**och klickar sedan på **Nästa**.

6. På sidan **vem vill du lägga till**? klickar du på **Slutför**.

7. På den nya **ProjectX-** fliken i webbläsaren klickar du på ikonen Inställningar och sedan på **webbplats behörigheter**i verktygsfältet.

8. I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.

9. Klicka på **Inställningar**för åtkomstbegäran på fliken ny **behörighet: Project X** i webbläsaren.

10. I dialog rutan **Inställningar för åtkomst förfrågningar** avmarkerar **du Tillåt medlemmar att dela webbplatsen och enskilda filer och mappar** och **tillåta åtkomst förfrågningar** (så att alla tre kryss rutor är avmarkerade) och klickar sedan på **OK**.

11. Klicka på **ProjectX medlemmar** i listan.

12. På sidan **Personer och grupper** klickar du på **Nytt**.

13. I dialog rutan **dela** skriver du **ProjectX-members**, markerar den och klickar sedan på **dela**.

14. Klicka på bakåtknappen i webbläsaren.

15. Klicka på **ProjectX ägare** i listan.

16. På sidan **Personer och grupper** klickar du på **Nytt**.

17. Skriv **ProjectX – administratörer**i dialog rutan **dela** och klicka sedan på **dela**.

18. Klicka på bakåtknappen i webbläsaren.

19. Klicka på **ProjectX besökare** i listan.

20. På sidan **Personer och grupper** klickar du på **Nytt**.

21. Skriv **ProjectX-visnings program**i dialog rutan **dela** och klicka på **dela**.

22. Stäng fliken **personer och grupper** i webbläsaren, klicka på **ProjectX-** fliken i webbläsaren och stäng sedan fönstret **webbplats behörigheter** .

Här är resultatet av att konfigurera behörigheter:

- SharePoint-gruppen ProjectX medlemmar innehåller bara gruppen ProjectX-medlemmar (som bara innehåller Lead Designer och användar konton för ledar forskare) och ProjectX-gruppen (som bara innehåller det globala administratörs användar kontot).

- SharePoint-gruppen ProjectX-ägare innehåller bara gruppen ProjectX-administratörer (som bara innehåller det globala administratörs kontot).

- SharePoint-gruppen ProjectX besökare innehåller bara gruppen ProjectX-visnings åtkomst (som bara innehåller användar kontot utvecklings direktör).

- Medlemmar kan inte ändra behörigheter på webbplats nivå (detta kan bara göras av medlemmar i ProjectX-administratörs gruppen).

- Andra användarkonton kan inte komma åt webbplatsen eller dess resurser. De kan inte heller begära åtkomst till webbplatsen.

Bild 2 visar SharePoint-grupperna och deras medlemskap.

**Bild 2**

![SharePoint Online-grupper och deras medlemskap för en isolerad SharePoint Online-gruppwebbplats](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Nu kan du Visa åtkomst med hjälp av användar kontot för lead designer:

1. Stäng **ProjectX-** fliken i webbläsaren och klicka sedan på **Microsoft Office** -fliken Start i webbläsaren.

2. Klicka på namnet på den globala administratören och klicka sedan på **Logga ut**.

3. Logga in på administrations centret för Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ) med namnet Lead Designer och lösen ordet.

4. Klicka på **SharePoint** i listan med paneler.

5. På den nya **SharePoint** -fliken i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på **ProjectX** -grupp webbplatsen. En ny flik visas i din webbläsare för ProjectX-gruppwebbplatsen.

6. Klicka på ikonen Inställningar. Observera att det inte finns något alternativ för **webbplats behörigheter**. Det här är korrekt eftersom endast medlemmar i ProjectX-administratörs gruppen kan ändra behörigheter på webbplatsen

7. Öppna Anteckningar eller en text redigerare.

8. Kopiera URL-adressen till ProjectX och klistra in den på en ny rad i anteckningar eller i text redigeraren.

9. Klicka på **dokument**på fliken ny **ProjectX-start** i webbläsaren.

10. Kopiera URL-adressen till ProjectX-mappen och klistra in den på en ny rad i anteckningar eller i text redigeraren.

11. På fliken ny **ProjectX-dokument** i webbläsaren klickar du på **nytt > Word-dokument**.

12. Skriv lite text på sidan, vänta tills statusen har **sparats**, klicka på knappen tillbaka i webbläsaren och uppdatera sidan. Du bör se en ny **Document.docx** i mappen **dokument** .

13. Klicka på ellipsen för **Document.docx** -dokumentet och klicka sedan på **Hämta en länk**.

14. Kopiera URL-adressen i dialog rutan **dela Document.docx** och klistra in den på en ny rad i anteckningar eller text redigeraren och stäng sedan dialog rutan **dela Document.docx** .

15. Stäng **ProjectX-dokument** och **SharePoint** -flikar i webbläsaren och klicka sedan på fliken **Microsoft Office hem** .

16. Klicka på namnet på **Lead Designer** och sedan på **Logga ut**.

Nu kan du Visa åtkomst med användar kontot för utvecklings chef:

1. Logga in på administrations centret för Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ) med konto namnet för utvecklings sidan och lösen ordet.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya **SharePoint** -fliken i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på **ProjectX** -grupp webbplatsen. En ny flik visas i din webbläsare för ProjectX-gruppwebbplatsen.

4. Klicka på **dokument**och sedan på **Document.docx** .

5. Prova att ändra texten på fliken **Document.docx** i webbläsaren. Du bör se ett meddelande om att **dokumentet är skrivskyddat.** Det förväntas på grund av att användar kontot för utvecklings personen endast har behörigheten Visa för webbplatsen.

6. Stäng flikarna **Document.docx**, **ProjectX**och **SharePoint** i webbläsaren.

7. Klicka på fliken **Microsoft Office-start** , klicka på **utvecklings direktörens** namn och klicka sedan på **Logga ut**.

Nu kan du Visa Access med ett användar konto som inte har behörighet:

1. Logga in på administrations centret för Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ) med användare 3-kontonamnet och lösen ordet.

2. Klicka på **SharePoint** i listan med paneler.

3. Skriv **ProjectX** i sökrutan och aktivera sedan sökningen på den nya **SharePoint** -fliken i webbläsaren. Du bör se meddelandet **ingenting här matchar din sökning.**

4. Från den öppna instansen av anteckningar eller text redigeraren kopierar du URL-adressen för ProjectX-webbplatsen till adress fältet i webbläsaren och trycker på **RETUR**. Sidan **åtkomst nekad** bör visas.

5. I anteckningar eller text redigeraren kopierar du URL-adressen för ProjectX-dokument till adress fältet i webbläsaren och trycker på **RETUR**. Sidan **åtkomst nekad** bör visas.

6. I anteckningar eller text redigeraren kopierar du URL-adressen för Documents.docx filen till webbläsarens Adress fält och trycker på **RETUR**. Sidan **åtkomst nekad** bör visas.

7. Stäng **SharePoint** -fliken i webbläsaren, klicka på fliken **Microsoft Office start** , klicka på **användare 3** -namnet och klicka sedan på **Logga ut**.

Din SharePoint Online-webbplats är nu klar för dig.

## <a name="next-step"></a>Nästa steg

När du är redo att distribuera en isolerad SharePoint Online-gruppwebbplats i produktion kan du läsa de steg för steg-informationen om utformning i [Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Se även

[Isolerade SharePoint Online-gruppwebbplatser](isolated-sharepoint-online-team-sites.md)

[Testlabbguider för integrering med molntjänster](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Baskonfiguration för simulerat företag](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[Den enkla baskonfigurationen](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[Integrering av moln- och hybridlösningar](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
