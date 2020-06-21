---
title: Ta bort en tidigare anställd
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'Följ den här checklistan om du vill ta bort en anställd från Microsoft 365 och säkra data. '
ms.openlocfilehash: adf5c683828b30a978199145fa2c54f17d1b6b37
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780583"
---
# <a name="remove-a-former-employee"></a>Ta bort en tidigare anställd

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
## <a name="sign-out-now"></a>Logga ut nu!

::: moniker range="o365-worldwide"

Titta på en kort video om att ta bort en anställd. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Så här tar du bort en medarbetare:

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Markera rutan bredvid användarens namn och välj sedan **Återställ lösenord**.

3. Ange ett nytt lösenord och välj sedan **Återställ**. (Skicka den inte till dem.)
    
4. Markera användarens namn för att gå till deras egenskapsfönster och välj **Initiera utloggning**på fliken **OneDrive** .

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Markera användaren och välj sedan **Återställ lösenord**.

3. Ange ett nytt lösenord och välj sedan **Återställ**. (Skicka den inte till dem.)

4. Markera användaren igen, expandera **OneDrive-inställningar**och välj sedan **Initiera bredvid** **Logga ut**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Markera användaren och välj sedan **Återställ lösenord**.

3. Ange ett nytt lösenord och välj sedan **Återställ**. (Skicka den inte till dem.)

4. Markera användaren igen, expandera **OneDrive-inställningar**och välj sedan **Initiera bredvid** **Logga ut**.

::: moniker-end

    
Inom en timme - eller efter att de lämnar den aktuella Microsoft 365-sidan de är på - kommer de att uppmanas att logga in igen. (En åtkomsttoken är bra i en timme, så tidslinjen beror på hur mycket tid som återstår på den token och om de navigerar från sin nuvarande webbsida.)
  
 **VARNING**: Om användaren är inne på Outlook på webben och bara klickar runt i postlådan, kanske han/hon inte kastas ut direkt. Så fort de väljer en annan panel, till exempel OneDrive, eller uppdaterar webbläsaren initieras ut logga ut. 
  
Mer information om att använda PowerShell till att logga ut en användare direkt finns i cmdleten [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345). 
  
Mer information om hur lång tid det tar att avsluta en persons e-post finns i [Vad du behöver veta om att avsluta en anställds e-postsession](#what-you-need-to-know-about-terminating-an-employees-email-session).
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Översikt över alla steg för att ta bort en anställd och säkra data
<a name="bkmk_now"> </a>

En fråga vi ofta får är: "Vad ska jag göra för att skydda data när en anställd lämnar organisationen?" I den här artikeln beskrivs hur du blockerar åtkomsten till Microsoft 365 och de åtgärder du bör vidta för att skydda dina data.
  
> [!NOTE]
> Om du är global administratör kan du ta bort medarbetaren, vidarebefordra deras e-post, välja vad de ska göra med deras OneDrive-innehåll med hjälp av den nya guidade upplevelsen. Mer information finns i [Global admin: Ta bort en användare](remove-former-employee.md). Vi rekommenderar dock att du slutför alla ytterligare steg som anges här för att säkerställa att medarbetaren inte har åtkomst till företagets data. 
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**Steg** <br/> |**Varför** <br/> |
|1. [Spara innehållet i en tidigare anställds postlåda](#save-the-contents-of-a-former-employees-mailbox) <br/> |Det är användbart för den som ska ta över den anställdas arbete, samt i händelse av tvist.  <br/> |
|2. [Vidarebefordra en före detta anställds e-post till en annan anställd eller konvertera till en delad postlåda](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3. [Rensa och blockera en tidigare anställds mobil enhet](#wipe-and-block-a-former-employees-mobile-device) <br/> |Tar bort affärsdata från telefonen eller surfplattan.  <br/> |
|4. [Blockera en tidigare anställds åtkomst till Microsoft 365-data](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Det hindrar personen från att komma åt sin gamla Microsoft 365-postlåda och data.  <br/><br/> **Tips:** När du blockerar en användares åtkomst betalar du fortfarande för deras licens. Du måste ta bort licensen från prenumerationen för att slippa betala för den (steg 5).           |
|5. [Flytta medarbetarens OneDrive-innehåll](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Om du bara tar bort en användares licens, men inte tar bort kontot, kommer innehållet på användarens OneDrive att finnas tillgängligt för dig även efter 30 dagar.  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |Om en personlig dator använts för att ladda ned filer från OneDrive och SharePoint, i stället för en företagsdator, går det inte att rensa dessa filer.  <br/><br/> Åtkomst kvarstår till alla filer som har synkroniserats till datorn.  <br/> |
|6. [Ta bort och ta bort Microsoft 365-licensen från en tidigare anställd](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7. [Ta bort en tidigare anställds användarkonto](#delete-a-former-employees-user-account)<br/> |Då tas kontot bort från administrationscentret. Hjälper dig att hålla ordning och reda.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>Spara innehållet i en tidigare anställds postlåda
<a name="bkmk_preserve"> </a>

Det finns två sätt du kan spara innehållet i den tidigare anställdas postlåda:
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    ELLER
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    När du har konverterar postlådan till en inaktiv postlåda kan administratörer, efterlevnadsansvariga och hanterare av arkivhandlingar använda lokala eDiscovery-verktyg i Exchange Online för att komma åt och söka i innehållet.
    
    Inaktiva postlådor kan inte ta emot e-post och visas inte i organisationens delade adressbok och andra listor.
    
    Mer information om hur du spärrar en postlåda finns [i Hantera inaktiva postlådor i Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>Vidarebefordra en före detta anställds e-post till en annan anställd eller konvertera till en delad postlåda
<a name="bkmk_forward"> </a>

I det här steget tilldelar du den tidigare anställdas e-postadress till en annan anställd eller [konverterar postlådan till en delad postlåda](../email/convert-user-mailbox-to-shared-mailbox.md) du har skapat. 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- Om du vidarebefordrar e-postmeddelanden kommer bara  *nya*  e-postmeddelanden som skickas till den tidigare anställda att skickas till nuvarande anställda. 
    
- Vidarebefordran av e-post kräver att den tidigare anställdas konto har en licens.
    
 > [!IMPORTANT] 
 > Om du konfigurerar vidarebefordran av e-post eller en delad postlåda ska du i slutet inte ta bort den tidigare medarbetarens konto. Kontot måste finnas där för att förankra vidarebefordran av e-post eller den delade postlådan. 

::: moniker range="o365-worldwide"  

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Markera namnet på den medarbetare som du vill blockera och välj sedan fliken **E-post.**

3. Under **Vidarebefordran av e-post**väljer du **Hantera vidarebefordran av e-post**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Välj **Spara**. 
    
6. Kom ihåg att inte ta bort den tidigare anställdas konto.
 
::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Markera den medarbetare som du vill blockera och expandera **E-postinställningar**.

3. Välj **Redigera** **bredvid Vidarebefordring av e-post**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Välj **Spara**. 
    
6. Kom ihåg att inte ta bort den tidigare anställdas konto.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Markera den medarbetare som du vill blockera och expandera **E-postinställningar**.

3. Välj **Redigera** **bredvid Vidarebefordring av e-post**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Välj **Spara**. 
    
6. Kom ihåg att inte ta bort den tidigare anställdas konto.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Rensa och blockera en tidigare anställds mobil enhet
<a name="bkmk_mobile"> </a>

Om den tidigare anställde hade en företagstelefon kan du använda Administrationscenter för Exchange för att rensa och blockera enheten så att alla organisationsdata tas bort från enheten och så att enheten inte längre kan ansluta till Office 365.
  

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

3. I Administrationscenter för Exchange går du till **Mottagare** \> **Postlådor**. 
    
4. Välj användaren och välj Visa **information**under **Mobila enheter**. 
    
5. Välj den mobila enheten på sidan **Information om mobil enhet,** välj **rensa datarensningsenhet**under Mobila **enheter**och välj ![ sedan ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **Blockera**. 
    
6. Välj **Spara**. 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Blockera en tidigare anställds åtkomst till Microsoft 365-data
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > Det kan ta upp till 24 timmar att blockera ett konto. Om du omedelbart behöver förhindra att en användare har inloggning bör du [återställa lösenordet](reset-passwords.md) och sedan initiera en engångshändelse som loggar ut dem från Microsoft 365-sessioner på alla enheter. Se [Logga ut nu!](#sign-out-now)
 

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Välj namnet på den medarbetare som du vill blockera och välj symbolen för Blockera den **här användaren**under användarens namn .

3. Välj **Blockera användaren från att logga in**och välj sedan **Spara**. 

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Välj den medarbetare som du vill blockera och välj sedan **Blockera inloggning**.

3. Välj **Blockera användaren från att logga in**och välj sedan **Spara**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Välj den medarbetare som du vill blockera och välj sedan **Blockera inloggning**.

3. Välj **Blockera användaren från att logga in**och välj sedan **Spara**. 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Blockera en tidigare anställds åtkomst till e-post (Exchange Online)
<a name="bkmk_block_email"> </a>

Om du har e-post som en del av din Microsoft 365-prenumeration måste du logga in på administrationscentret för Exchange för att följa dessa steg för att blockera din tidigare medarbetare från att komma åt deras e-post.
  

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.
     
2. I Administrationscenter för Exchange går du till **Mottagare** \> **Postlådor**. 
    
3. Dubbelklicka på användaren och gå till sidan **Postlådefunktioner.** Under **Mobila enheter**väljer du Inaktivera Exchange **ActiveSync** och **Inaktivera OWA för enheter** och svarar **ja** på båda när du uppmanas att göra det. 
    
4. Under **E-postanslutning**väljer du **Inaktivera** och svarar **Ja** när du uppmanas att göra det. 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>Ta bort och ta bort Microsoft 365-licensen från en tidigare anställd
<a name="bkmk_remove"> </a>

Så du fortsätter inte att betala för en licens efter att någon har lämnat organisationen, du måste ta bort deras Microsoft 365-licens och sedan ta bort den från din prenumeration. Om du väljer att inte radera licensen från prenumerationen kan du tilldela den till en annan användare.
  
När du tar bort licensen bevaras användarens alla data i 30 dagar. Du kan [komma åt](get-access-to-and-back-up-a-former-user-s-data.md) alla data, eller [återställa](restore-user.md) kontot om användaren kommer tillbaka. Efter 30 dagar raderas alla användares data (förutom dokument som lagras på SharePoint Online) permanent från Microsoft 365 och kan inte återställas. 

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Välj namnet på den medarbetare som du vill blockera och välj sedan fliken **Licenser och appar.**

4. Avmarkera kryssrutorna för den licens(er) som du vill ta bort och välj sedan **Spara ändringar**.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Välj den medarbetare som du vill blockera och välj sedan **Redigera**bredvid **Produktlicenser**.

3. På sidan **Produktlicenser** växlar du av de licenser som du vill ta bort och väljer sedan **Spara**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Välj den medarbetare som du vill blockera och välj sedan **Redigera**bredvid **Produktlicenser**.

3. På sidan **Produktlicenser** växlar du av de licenser som du vill ta bort och väljer sedan **Spara**.

::: moniker-end


**Om du vill minska antalet licenser som du betalar för** tills du anställer en annan person kan du göra följande: 

::: moniker range="o365-worldwide"



1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.


::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.

::: moniker-end
    
2. Välj **Lägg till/ta bort licenser** om du vill ta bort licensen så att du inte betalar för den förrän du anställer en annan person.

När du [lägger till](add-users.md) en annan person i ditt företag uppmanas du att köpa en licens samtidigt, med bara ett steg!
    
Mer information om hur du hanterar användarlicenser för Microsoft 365 för företag finns [i Tilldela licenser till användare i Microsoft 365 för företag](../manage/assign-licenses-to-users.md)och Ta bort licenser från användare i Microsoft [365 för företag](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Så här påverkas Skype för företag när en anställds konto tas bort
<a name="bkmk_remove"> </a>

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## <a name="delete-a-former-employees-user-account"></a>Ta bort en tidigare anställds användarkonto
<a name="bkmk_delete"> </a>

När du har sparat och kommit åt den tidigare anställdes alla användardata kan du ta bort den tidigare anställdes konto.
  
Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Markera namnet på den medarbetare som du vill ta bort.

3. Under användarens namn väljer du symbolen för **Ta bort användare**. Välj önskade alternativ för den här användaren och välj sedan **Ta bort användare**.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Markera namnet på den medarbetare som du vill ta bort.

3. Högst upp på sidan väljer du **Ta bort användare**. Välj önskade alternativ för den här användaren och välj sedan **Ta bort användare**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Markera namnet på den medarbetare som du vill ta bort.

3. Högst upp på sidan väljer du **Ta bort användare**. Välj önskade alternativ för den här användaren och välj sedan **Ta bort användare**.

::: moniker-end

When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
### <a name="does-your-organization-use-active-directory"></a>Använder ni Active Directory i organisationen?

Om din organisation synkroniserar användarkonton med Microsoft 365 från en lokal Active Directory-miljö måste du ta bort och återställa dessa användarkonton i den lokala Active Directory-tjänsten. Du kan inte ta bort eller återställa dem i Office 365.
  
Anvisningar finns i artikeln: [Ta bort ett användarkonto](https://go.microsoft.com/fwlink/?linkid=841808).
  
Om du använder Azure Active Directory refererar du till PowerShell-cmdleten [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230). 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Vad du behöver veta om att avsluta en anställds e-postsession
<a name="bkmk_session"> </a>

Här finns information om hur du avslutar en anställds e-post (Exchange).
  
|||
|:-----|:-----|
|**Vad du kan göra** <br/> |**Hur gör du det?** <br/> |
|Avsluta en session (till exempel Outlook på webben, Outlook, Exchange ActiveSync, etc.) och framtvinga en ny session  <br/> |Återställa lösenord  <br/> |
|Avsluta en session och blockera åtkomst till framtida sessioner (för alla protokoll)  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Avbryt sessionen för ett visst protokoll (till exempel ActiveSync)  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
Åtgärderna ovan kan göras på 3 platser:
  
|||
|:-----|:-----|
|**Om du avslutar sessionen här** <br/> |**Hur lång tid det tar** <br/> |
|I administrationscentret för Exchange eller med PowerShell  <br/> |Förväntad fördröjning mindre än 30 minuter  <br/> |
|I Azure Active Directory-administratörcenter  <br/> |Förväntad fördröjning mindre än 60 minuter  <br/> |
|I en lokal miljö  <br/> |Förväntad fördröjning 3 timmar eller mer  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>Så här får du snabbast svar vid kontouppsägning

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## <a name="related-articles"></a>Relaterade artiklar

[Återställa en användare](restore-user.md)
  
