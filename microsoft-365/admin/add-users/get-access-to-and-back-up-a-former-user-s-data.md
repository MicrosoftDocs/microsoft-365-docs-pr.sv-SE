---
title: Få åtkomst till och säkerhetskopiera en tidigare anställds användardata.
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Läs om hur du bevarar en medarbetares filer och e-postmeddelanden när personen lämnar organisationen.
ms.openlocfilehash: 13cc1117c52a45f4ec1389d2e8b9f0189f4730e1
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431719"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a>Få åtkomst till och säkerhetskopiera en tidigare anställds användardata.


När en medarbetare lämnar organisationen vill du förmodligen komma åt deras data (dokument och e-postmeddelanden) och antingen granska dem, säkerhetskopiera den eller ge den till en ny medarbetare.
  
    
## <a name="access-a-former-users-onedrive-documents"></a>Komma åt en tidigare användares OneDrive-dokument

Om du tar bort en användares licens men inte tar bort kontot kan du ge dig själv åtkomst till innehållet på användarens OneDrive. Om du tar bort användarens konto har du som standard 30 dagar på dig att komma åt den tidigare användarens OneDrive-data. [Lär dig hur du ställer in OneDrive-kvarhållningen för borttagna användare](/onedrive/set-retention). Om du inte [återställer ett användarkonto](/office365/admin/add-users/restore-user) inom den här tiden tas deras OneDrive-innehåll bort. 

Om du vill bevara en tidigare användares OneDrive-filer ger du dig först åtkomst till deras OneDrive och flyttar sedan de filer du vill behålla. 

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.  
    
2. Välj en användare.

3. Välj **OneDrive**i den högra rutan . Under **Hämta åtkomst till filer**väljer du Skapa länk till **filer**.

4. Välj länken för att öppna filplatsen. Ladda ned filerna till datorn eller välj **Flytta till** eller Kopiera **för att** flytta eller kopiera dem till din egen OneDrive eller till ett delat bibliotek. 

> [!NOTE]
> Du kan flytta eller kopiera upp till 500 MB filer och mappar åt gången.<br/>
> När du flyttar eller kopierar dokument med versionshistorik flyttas bara den senaste versionen.  

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.  

2. Välj en användare.

3. Expandera **OneDrive-inställningar i**den högra rutan och välj sedan **Access-filer bredvid** **Access**.

4. Välj länken för att öppna filplatsen. Ladda ned filerna till datorn eller välj **Flytta till** eller Kopiera **för att** flytta eller kopiera dem till din egen OneDrive eller till ett delat bibliotek. 

> [!NOTE]
> Du kan flytta eller kopiera upp till 500 MB filer och mappar åt gången.<br/>
> När du flyttar eller kopierar dokument med versionshistorik flyttas bara den senaste versionen.  

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>. 

2. Välj en användare.

3. Expandera **OneDrive-inställningar i**den högra rutan och välj sedan **Access-filer bredvid** **Access**.

4. Välj länken för att öppna filplatsen. Ladda ned filerna till datorn eller välj **Flytta till** eller Kopiera **för att** flytta eller kopiera dem till din egen OneDrive eller till ett delat bibliotek.  

> [!NOTE]
> Du kan flytta eller kopiera upp till 500 MB filer och mappar åt gången.<br/>
> När du flyttar eller kopierar dokument med versionshistorik flyttas bara den senaste versionen.  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a>Återkalla administratörsåtkomst till en användares OneDrive

Som global administratör kan du ge dig själv tillgång till innehållet på en användares OneDrive, men du kanske vill ta bort din åtkomst när du inte längre behöver det. 

::: moniker range="o365-worldwide"

1. Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret</a> som global administratör eller SharePoint-administratör. 

    Om du får ett meddelande om att du inte har behörighet att komma åt administrationscentret har du inte administratörsbehörighet i organisationen.

::: moniker-end

::: moniker range="o365-germany"

1. Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> som global administratör eller SharePoint-administratör.

    Om du får ett meddelande om att du inte har behörighet att komma åt administrationscentret har du inte administratörsbehörighet i organisationen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> som global administratör eller SharePoint-administratör.

    Om du får ett meddelande om att du inte har behörighet att komma åt administrationscentret har du inte administratörsbehörighet i organisationen.

::: moniker-end

2. Välj **Administrationscenter** \> **SharePoint**i den vänstra rutan . (Du kan behöva välja **Visa alla** för att se listan över administrationscenter.)

3. Om det klassiska Administrationscentret för SharePoint visas väljer du **Öppna det nu** högst upp på sidan för att öppna administrationscentret för SharePoint.

4. Välj **Fler funktioner**i den vänstra rutan .

5. Under **Användarprofiler**väljer du **Öppna**.

6. Under **Kontakter**väljer du **Hantera användarprofiler**.

7. Ange användarens namn och välj **Sök**.

8. Högerklicka på användaren och välj sedan **Hantera webbplatssamlingsägare**.

9. Ta bort personen som inte längre behöver åtkomst till användarens data och välj sedan **OK**.

    
## <a name="access-the-outlook-data-of-a-former-user"></a>Komma åt Outlook-data för en tidigare användare

Om du vill spara e-postmeddelanden, kalender, uppgifter och kontakter för den tidigare medarbetaren exporterar du informationen till en Outlook-datafil (.pst).
  
1. [Lägg till den tidigare anställdes e-post](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) i Outlook (Om du [återställer användarens lösenord](reset-passwords.md)kan du ställa in det till något som bara du vet.)
    
2. Välj **Arkiv**i Outlook .
    
    ![Så här ser menyfliksområdet ut i Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Välj **Öppna &amp; Exportera** \> **import/export**.
    
    ![Kommandot Importera/Exportera i Backstage-vyn](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Välj **Exportera till en fil**och välj sedan **Nästa**.
    
    ![Alternativet Exportera till en fil i Importera-/exporteraguiden](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Välj **Outlook-datafil (.pst)** och välj sedan **Nästa**.
    
6. Välj det konto som du vill exportera genom att välja namn eller e-postadress, till exempel Postlåda - Anne Weiler eller anne@contoso.com. Om du vill exportera allt i ditt konto, inklusive e-post, kalender, kontakter, uppgifter och anteckningar, kontrollerar du att kryssrutan **Inkludera undermappar** är markerad. 
    
    > [!NOTE]
    > Du kan exportera ett konto i taget. Om du vill exportera flera konton upprepar du dessa steg när ett konto har exporterats. 
  
    ![Dialogrutan Exportera Outlook-datafil med den översta mappen markerad och Inkludera undermappar markerad](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Välj **Nästa**.
    
8. Välj **Bläddra** för att välja var Outlook-datafilen (.pst) ska sparas. Skriv ett *filnamn*och välj sedan **OK** för att fortsätta. 
    
    > [!NOTE]
    > Om du har exporterat tidigare visas den förra mappsökvägen och filnamnet. Skriv ett *annat filnamn* innan du väljer **OK**. 
  
9. Om du exporterar till en befintlig Outlook-datafil (.pst) anger du vad du vill göra under **Alternativ** när du exporterar objekt som redan finns i filen.
    
10. Välj **Slutför**.
    
Outlook påbörjar exporten direkt om du inte skapar en ny Outlook-datafil (.pst) eller använder en lösenordskyddad fil.
  
   - Om du skapar en Outlook-datafil (.pst) kan du skydda filen med ett lösenord. När dialogrutan **Skapa Outlook-datafil** visas skriver du *lösenordet* i rutorna **Lösenord** och **Verifiera lösenord** och väljer sedan **OK**. Skriv *lösenordet*i dialogrutan **Lösenord för Outlook-datafil** och välj sedan **OK**.
    
  - Om du exporterar till en befintlig Outlook-datafil (.pst) som är lösenordsskyddad skriver du *lösenordet*i dialogrutan **Lösenord för Outlook-datafil** och väljer sedan **OK**.
    
Lär dig hur du [exporterar eller säkerhetskopierar e-post, kontakter och kalender till en PST-fil](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) i Outlook 2010. 
  
  
  > [!NOTE]
  > Som standard är din e-post tillgänglig offline under en period av 12 månader. Om det behövs kan du se hur du [ökar tillgängliga data offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).
 
## <a name="give-another-user-access-to-a-former-users-email"></a>Ge en annan användare åtkomst till en tidigare användares e-post 

Om du vill ge åtkomst till den tidigare medarbetarens e-postmeddelanden, kalender, uppgifter och kontakter till en annan anställd importerar du informationen till en annan medarbetares Outlook-inkorg.

> [!NOTE]
> Du kan också [konvertera den tidigare användarens postlåda till en delad postlåda](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) eller [vidarebefordra en tidigare anställds e-post till en annan anställd](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).

  
1. Gå till **File** \> ** &amp; Filöppnad** \> **exportimport/export**i Outlook .
    
    När du gör det startas Import-/exportguiden.
    
2. Välj **Importera från ett annat program eller en annan fil**och välj sedan **Nästa**.
    
    ![Import-/exportguiden](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Välj **Outlook-datafil (.pst)** och välj **Nästa**.
    
4. Bläddra till .pst-filen som du vill importera.
    
5. Under **Alternativ**väljer du hur du vill hantera dubbletter
    
6. Välj **Nästa**.
    
7. Om ett lösenord har tilldelats Outlook-datafilen (.pst) anger du lösenordet och väljer sedan **OK**.
    
8. Ange alternativen för importen av objekten. Vanligtvis behöver du inte ändra standardinställningarna.
    
9. Välj **Slutför**.

> [!NOTE]
> Stegen förblir desamma för åtkomst till en befintlig användares OneDrive- och e-postdata.
    
> [!TIP]
> Om du bara vill importera eller återställa ett fåtal objekt från en Outlook-datafil (.pst) kan du öppna Outlook-datafilen. Dra sedan objekten från Outlook-datafilsmappar till befintliga Outlook-mappar i navigeringsfönstret. 
  
  
## <a name="related-articles"></a>Relaterade artiklar
[Ta bort en tidigare anställd från Office 365](remove-former-employee.md)

[Lägga till och ta bort administratörer på ett OneDrive-konto](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[Återställa en borttagen OneDrive](/onedrive/restore-deleted-onedrive)
  
[Bevarande och borttagning av OneDrive](/onedrive/retention-and-deletion)
  
