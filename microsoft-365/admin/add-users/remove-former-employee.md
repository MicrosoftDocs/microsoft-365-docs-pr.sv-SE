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
description: 'Följ den här checklistan för att ta bort en anställd från Microsoft 365 och säkra data. '
ms.openlocfilehash: 50355a20e0d0e8ff782deebd9be65fdabf875bb2
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860779"
---
# <a name="remove-or-delete-a-former-employee"></a>Ta bort en tidigare anställd

## <a name="sign-out-now"></a>Logga ut nu!

::: moniker range="o365-worldwide"

Titta på en kort video om att ta bort en anställd. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Så här hindrar du en anställd från att logga in:

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera rutan bredvid användarens namn och välj sedan **Återställ lösenord**.
3. Ange ett nytt lösenord och välj sedan **Återställ**. (Skicka det inte till dem.)
4. Välj användarens namn för att gå till egenskapsfönstret och välj Initiera ut logga **ut på fliken Konto.** 

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Markera användaren och välj sedan **Återställ lösenord.**

3. Ange ett nytt lösenord och välj sedan **Återställ**. (Skicka det inte till dem.)

4. Välj användarens namn för att gå till egenskapsfönstret och välj Initiera ut logga **ut på fliken Konto.** 

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Markera användaren och välj sedan **Återställ lösenord.**

3. Ange ett nytt lösenord och välj sedan **Återställ**. (Skicka det inte till dem.)

4. Välj användarens namn för att gå till egenskapsfönstret och välj Initiera ut logga **ut på fliken Konto.** 

::: moniker-end

> [!NOTE]
> Du måste vara global administratör för att kunna starta ut logga ut.

Inom en timme – eller efter att de lämnar den Microsoft 365-sida de befinner sig på – uppmanas de att logga in igen. En åtkomsttoken är bra i en timme, så tidslinjen beror på hur mycket tid som återstår för den tokenen och om de navigerar från den aktuella webbsidan.
  
> [!IMPORTANT]
> Om användaren är i Outlook på webben, bara klickar runt i postlådan, kanske han/hon inte sparkas ut direkt. Så snart de väljer en annan panel, till exempel OneDrive, eller uppdaterar sin webbläsare initieras ut logga ut.
  
Mer information om att använda PowerShell till att logga ut en användare direkt finns i cmdleten [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken).
  
Mer information om hur lång tid det tar att avsluta en persons e-post finns i [Vad du behöver veta om att avsluta en anställds e-postsession](#what-you-need-to-know-about-terminating-an-employees-email-session).
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Översikt över alla steg för att ta bort en anställd och säkra data

En fråga vi ofta får är "Vad ska jag göra för att skydda data när en anställd lämnar organisationen?" I den här artikeln förklaras hur du blockerar åtkomsten till Microsoft 365 och de steg du bör vidta för att skydda dina data.
  
> [!NOTE]
> Om du är global administratör kan du ta bort den anställda, vidarebefordra deras e-post, välja vad du vill göra med OneDrive-innehållet med den nya guidade upplevelsen. Mer information finns i Global [administratör: Ta bort en användare.](remove-former-employee.md) Vi rekommenderar dock att du slutför alla ytterligare steg som anges här för att säkerställa att den anställda inte har åtkomst till ditt företags data. 
  
Här följer en snabb översikt: Varje steg beskrivs i detalj i den här artikeln.
  
|||
|:-----|:-----|
|**Steg** <br/> |**Varför** <br/> |
|1. [Spara innehållet i en tidigare anställds postlåda](#save-the-contents-of-a-former-employees-mailbox) <br/> |Det är användbart för den person som ska ta över den anställdas arbete, eller om det finns tvister.  <br/> |
|2. [Vidarebefordra en före detta anställds e-post till en annan anställd eller konvertera till en delad postlåda](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |Då kan du hålla den före detta anställdas e-postadress aktiv. Om du har kunder eller partners som fortfarande skickar e-post till den före detta anställdas e-postadress hamnar den hos den person som har tagit över arbetet.  <br/> |
|3. [Rensa och blockera en tidigare anställds mobil enhet](#wipe-and-block-a-former-employees-mobile-device) <br/> |Tar bort affärsdata från telefonen eller surfplattan.  <br/> |
|4. [Blockera en tidigare anställds åtkomst till Microsoft 365-data](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Det hindrar personen från att komma åt sin gamla Microsoft 365-postlåda och data.  <br/><br/> **Tips:** När du blockerar en användares åtkomst betalar du fortfarande för användarens licens. Ta bort licensen från prenumerationen (steg 5) om du vill sluta betala för den.  |
|5. [Flytta medarbetarens OneDrive-innehåll](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Om du bara tar bort en användares licens, men inte tar bort kontot, kommer innehållet på användarens OneDrive att finnas tillgängligt för dig även efter 30 dagar.  <br/><br/> Innan du tar bort kontot bör du flytta innehållet på deras OneDrive till en annan plats som är enkel att komma åt. Efter att du tagit bort en anställds konto bevaras innehållet på deras OneDrive under **30** dagar. Under de 30 dagarna kan du dock återställa användarens konto och få åtkomst till deras OneDrive-innehåll. Om du återskapar användarens konto kommer OneDrive-innehållet att finnas tillgängligt för dig även efter 30 dagar.  <br/> |
|5a. Vad kan jag göra om personen använt sin egen dator för att komma åt OneDrive och SharePoint?  <br/> |Om en personlig dator använts för att ladda ned filer från OneDrive och SharePoint, i stället för en företagsdator, går det inte att rensa dessa filer.  <br/><br/> De har fortfarande åtkomst till alla filer som har synkroniserats till sin dator.  <br/> |
|6. [Ta bort Microsoft 365-licensen från en tidigare anställd](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |När du tar bort en licens kan du tilldela någon annan den. Du kan också radera licensen så att du inte behöver betala för den förrän du anställer någon ny.  <br/><br/> När du tar bort eller raderar en licens sparas användarens gamla e-post, kontakter och kalender i **30 dagar**, och tas sedan bort permanent. Om du tar bort eller raderar en licens, men inte tar bort kontot, kommer innehållet på användarens OneDrive att finnas tillgängligt för dig även efter 30 dagar.  <br/> |
|7. [Ta bort en tidigare anställds användarkonto](#delete-a-former-employees-user-account)<br/> |Det här tar bort kontot från administrationscentret. Hjälper dig att hålla ordning och reda.  <br/> |

## <a name="save-the-contents-of-a-former-employees-mailbox"></a>Spara innehållet i en tidigare anställds postlåda

Det finns två sätt du kan spara innehållet i den tidigare anställdas postlåda:
  
1. Lägg till den tidigare anställdas e-postadress till din version av Outlook 2013 eller 2016 och exportera sedan alla data till en PST-fil. Du kan importera dessa data till ett annat e-postkonto vid behov. Mer information om hur du gör det finns i [Få åtkomst till och säkerhetskopiera en tidigare anställds användardata](get-access-to-and-back-up-a-former-user-s-data.md).

    ELLER

2. Aktivera Bevarande av juridiska skäl eller Lokalt bevarande för postlådan innan du tar bort användarkontot. Det här är mycket mer komplicerat än det första alternativet, men värt att välja om: företagsabonnemanget omfattar arkivering och bevarande av juridiska skäl, det finns risk för tvister och du har en tekniskt stark IT-avdelning.

    När du har konverterat postlådan till en inaktiv postlåda kan administratörer, efterlevnadsansvariga och hanterare av arkivhandlingar använda In-Place eDiscovery-verktyg i Exchange Online för att komma åt och söka i innehållet.

    Inaktiva postlådor kan inte ta emot e-post och visas inte i organisationens delade adressbok och andra listor.

    Mer information om hur du placerar ett väntande på en postlåda finns i [Hantera inaktiva postlådor i Exchange Online.](../../compliance/create-and-manage-inactive-mailboxes.md)

## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>Vidarebefordra en före detta anställds e-post till en annan anställd eller konvertera till en delad postlåda

I det här steget tilldelar du den tidigare anställdas e-postadress till en annan anställd eller [konverterar postlådan till en delad postlåda](../email/convert-user-mailbox-to-shared-mailbox.md) du har skapat.
  
- Att skapa en delad postlåda är det billigaste alternativet eftersom du inte behöver betala för en licens **så länge postlådan är mindre än 50 GB**. Över 50 GB så måste du tilldela en licens till den.
- Om du konverterar postlådan till en delad postlåda blir även gamla e-postmeddelanden tillgängliga. Det kan ta upp mycket utrymme.
- Om du vidarebefordrar e-postmeddelanden kommer bara  *nya*  e-postmeddelanden som skickas till den tidigare anställda att skickas till nuvarande anställda.

 > [!IMPORTANT]
 > Om du inställningar för vidarebefordran av e-post eller en delad postlåda i slutet ska du inte ta bort den tidigare anställdas konto. Kontot måste finnas där för att förankra vidarebefordran av e-post eller den delade postlådan.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera namnet på den anställda du vill blockera och välj sedan fliken **E-post.**
3. Under **Vidarebefordran av e-post** väljer du **Hantera vidarebefordran av e-post**.
4. Aktivera **Vidarebefordra all e-post som skickats till den här postlådan**. I rutan **Adress för vidarebefordran** skriver du e-postadressen till den aktuella medarbetaren som ska få e-postmeddelandet.
5. Välj **Spara**.
6. Kom ihåg att inte ta bort den tidigare anställdas konto.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Markera den anställda som du vill blockera och expandera **E-postinställningar.**

3. Bredvid **Vidarebefordran av e-post** väljer du **Redigera**.

4. Aktivera **Vidarebefordra all e-post som skickats till den här postlådan**. I rutan **Adress för vidarebefordran** skriver du e-postadressen till den aktuella medarbetaren (eller den delade postlådan) dit e-posten ska skickas.
  
5. Välj **Spara**.

6. Kom ihåg att inte ta bort den tidigare anställdas konto.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Markera den anställda som du vill blockera och expandera **E-postinställningar.**

3. Bredvid **Vidarebefordran av e-post** väljer du **Redigera**.

4. Aktivera **Vidarebefordra all e-post som skickats till den här postlådan**. I rutan **Adress för vidarebefordran** skriver du e-postadressen till den aktuella medarbetaren (eller den delade postlådan) dit e-posten ska skickas.
  
5. Välj **Spara**.

6. Kom ihåg att inte ta bort den tidigare anställdas konto.

::: moniker-end

## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Rensa och blockera en tidigare anställds mobil enhet

Om den tidigare anställde hade en organisationstelefon kan du använda administrationscentret för Exchange för att rensa och blockera enheten så att alla organisationsdata tas bort från enheten och inte längre kan ansluta till Office 365.

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.
2. I Administrationscenter för Exchange går du till **Mottagare** \> **Postlådor**.
3. Markera användaren och välj Visa **information** under Mobila **enheter.**
4. På sidan **Information om mobil** enhet under Mobila **enheter** väljer du den mobila enheten, sedan Rensa dataruteenhet och sedan  ![ ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **Blockera**.
5. Välj **Spara**.
   > [!TIP]
   > Se till att du tar bort eller inaktiverar användaren från din lokala Blackberry Enterprise Service. Du bör dessutom inaktivera alla Blackberry-enheter för användaren. Läs i Blackberry Business Cloud Services Administration Guide om du behöver specifika anvisningar om hur du inaktiverar användaren.

## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Blockera en tidigare anställds åtkomst till Microsoft 365-data

 > [!IMPORTANT]
 > Det kan ta upp till 24 timmar innan blockeringen av ett konto verkställs. Om du omedelbart behöver förhindra en användares inloggningsåtkomst bör du återställa användarens lösenord och sedan initiera en händelse som loggar ut användaren från Microsoft 365-sessioner på alla enheter. [](reset-passwords.md) Läs [Logga ut nu!](#sign-out-now)

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera namnet på den anställda som du vill blockera och välj symbolen för Blockera den här användaren under **användarnamnet.**
3. Välj **Blockera användaren från att logga in** och välj sedan **Spara**.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Markera den anställda du vill blockera och välj sedan **Blockera inloggning.**

3. Välj **Blockera användaren från att logga in** och välj sedan **Spara**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Markera den anställda du vill blockera och välj sedan **Blockera inloggning.**

3. Välj **Blockera användaren från att logga in** och välj sedan **Spara**.

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Blockera en tidigare anställds åtkomst till e-post (Exchange Online)

Om du har e-post som en del av Microsoft 365-prenumerationen måste du logga in på Exchange admin center för att följa de här stegen för att blockera den tidigare anställda från att komma åt sin e-post.
  
1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.
2. I Administrationscenter för Exchange går du till **Mottagare** \> **Postlådor**.
3. Dubbelklicka på användaren och gå till sidan **Postlådefunktioner.** Under **Mobila enheter** väljer du Inaktivera Exchange **ActiveSync och** Inaktivera **OWA** för enheter och svarar **Ja** på båda när du uppmanas att göra det.
4. Under **E-postanslutning** väljer **du Inaktivera** och svarar Ja **när** du uppmanas att göra det.

## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>Ta bort och radera Microsoft 365-licensen från en tidigare anställd

När någon lämnar organisationen måste du ta bort hans eller hons Microsoft 365-licens och radera den så att du inte fortsätter betala för den. Om du väljer att inte radera licensen från prenumerationen kan du tilldela den till en annan användare.
  
När du tar bort licensen bevaras användarens alla data i 30 dagar. Du kan [komma åt](get-access-to-and-back-up-a-former-user-s-data.md) alla data, eller [återställa](restore-user.md) kontot om användaren kommer tillbaka. Efter 30 dagar tas alla användarens data (utom dokument som lagras på SharePoint Online) permanent bort från Microsoft 365 och kan inte återställas.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera namnet på den anställda som du vill blockera och välj sedan **fliken Licenser och** appar.
3. Avmarkera kryssrutorna för den eller de licenser du vill ta bort och välj sedan **Spara ändringar.**

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Markera den anställda du vill blockera och välj sedan **Redigera** bredvid **Produktlicenser.**

3. På **sidan Produktlicenser** inaktiverar du de licenser du vill ta bort och väljer sedan **Spara**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Markera den anställda du vill blockera och välj sedan **Redigera** bredvid **Produktlicenser.**

3. På **sidan Produktlicenser** inaktiverar du de licenser du vill ta bort och väljer sedan **Spara**.

::: moniker-end

**Om du vill minska antalet licenser som du betalar för tills** du anställer en annan person gör du följande:

::: moniker range="o365-worldwide"
1. I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Fakturering dina</a> produkter och väljer **fliken** Produkter.
2. Välj den prenumeration som du vill ta bort licenser från.
3. Välj Ta bort licenser på **informationssidan.**
4. I fönstret **Ta bort** licenser, under  Nytt antal, i rutan Totalt antal licenser anger du det totala antalet licenser som du vill använda för prenumerationen. Om du till exempel har 25 licenser och vill ta bort en av dem anger du 24.
5. Välj **Spara**.
::: moniker-end

::: moniker range="o365-germany"
1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.
2. Välj **Lägg till/ta bort** licenser för att ta bort licensen så att du inte betalar för den förrän du anställer en annan person.
::: moniker-end

::: moniker range="o365-21vianet"
1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.
2. Välj **Lägg till/ta bort** licenser för att ta bort licensen så att du inte betalar för den förrän du anställer en annan person.
::: moniker-end

När [du lägger till](add-users.md) ytterligare en person i företaget uppmanas du samtidigt att köpa en licens med bara ett steg!

Mer information om hur du hanterar användarlicenser för Microsoft 365 för företag finns i Tilldela användare licenser i [Microsoft 365](../manage/assign-licenses-to-users.md)för företag och Ta bort licenser från användare i [Microsoft 365 för företag.](../manage/remove-licenses-from-users.md)
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Så här påverkas Skype för företag när en anställds konto tas bort

När du tar bort en användares licens från Office 365 frigörs PSTN-telefonnumret som är kopplat till användaren. Du kan tilldela det till en annan användare.
  
Om användaren tillhör en kögrupp är användaren inte längre ett möjligt mål för agenter från samtalskön. Därför rekommenderar vi att användaren också tas bort från de grupper som är kopplade till samtalskön.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>Konfigurera vidareringning av samtal till personer i organisationen

Om du behöver ställa in vidareringning av den uppsagda medarbetarens telefonnummer kan inställningen för vidareringning under samtalsprinciper ställa in vidarebefordran där inkommande samtal kan vidarebefordras till andra användare eller ringa upp en annan person samtidigt. Mer information finns i [Samtalsprinciper i Microsoft Teams.](/microsoftteams/teams-calling-policy)
  
## <a name="delete-a-former-employees-user-account"></a>Ta bort en tidigare anställds användarkonto

När du har sparat och kommit åt den tidigare anställdes alla användardata kan du ta bort den tidigare anställdes konto.
  
Ta inte bort kontot om du har konfigurerat vidarebefordran av e-post eller konverterat postlådan till en delad postlåda. Kontot krävs för att kunna använda vidarebefordran av e-post eller den delade postlådan.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera namnet på den anställda som du vill ta bort.
3. Under användarens namn väljer du symbolen för Ta **bort användare.** Välj de alternativ du vill använda för användaren och välj sedan Ta **bort användare.**

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Markera namnet på den anställda som du vill ta bort.

3. Högst upp på sidan väljer du Ta **bort användare**. Välj de alternativ du vill använda för användaren och välj sedan Ta **bort användare.**

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Markera namnet på den anställda som du vill ta bort.

3. Högst upp på sidan väljer du Ta **bort användare**. Välj de alternativ du vill använda för användaren och välj sedan Ta **bort användare.**

::: moniker-end

När du tar bort en användare blir dennes konto inaktivt i ca 30 dagar. Du har tills dess på dig att återställa kontot innan det tas bort permanent.
  
### <a name="does-your-organization-use-active-directory"></a>Använder ni Active Directory i organisationen?

Om din organisation synkroniserar användarkonton till Microsoft 365 från en lokal Active Directory-miljö måste du ta bort och återställa dessa användarkonton i din lokala Active Directory-tjänst. Du kan inte ta bort eller återställa dem i Office 365.
  
Mer information om hur du tar bort och återställer användarkonton i Active Directory finns [i Ta bort ett användarkonto.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))
  
Om du använder Azure Active Directory, se [cmdleten Remove-MsolUser](https://docs.microsoft.com/powershell/module/msonline/remove-msoluser) PowerShell.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Vad du behöver veta om att avsluta en anställds e-postsession

Här finns information om hur du avslutar en anställds e-post (Exchange).
  
|||
|:-----|:-----|
|**Vad du kan göra** <br/> |**Hur gör du det?** <br/> |
|Avsluta en session (till exempel Outlook på webben, Outlook, Exchange ActiveSync, etc.) och framtvinga en ny session  <br/> |Återställa lösenord  <br/> |
|Avsluta en session och blockera åtkomst till framtida sessioner (för alla protokoll)  <br/> |Inaktivera kontot. Till exempel (i administrationscentret för Exchange eller med PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Avbryt sessionen för ett visst protokoll (till exempel ActiveSync)  <br/> |Inaktivera protokollet. Till exempel (i administrationscentret för Exchange eller med PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

Åtgärderna ovan kan utföras på tre platser:
  
|||
|:-----|:-----|
|**Om du avslutar sessionen här** <br/> |**Hur lång tid det tar** <br/> |
|I administrationscentret för Exchange eller med PowerShell  <br/> |Förväntad fördröjning mindre än 30 minuter  <br/> |
|I Azure Active Directory-administratörcenter  <br/> |Förväntad fördröjning mindre än 60 minuter  <br/> |
|I en lokal miljö  <br/> |Förväntad fördröjning 3 timmar eller mer  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>Så här får du snabbast svar vid kontouppsägning

 **Snabbast**: Använd administrationscentret för Exchange (använd PowerShell) eller administrationscentret för Azure Active Directory. Det kan ta flera timmar att synkronisera ändringar genom DirSync i en lokal miljö.
  
 **Snabbast för en användare med närvaro lokalt och i Exchange-datacentret**: Avbryt sessionen med administrationscentret för Azure Active Directory/administrationscentret för Exchange OCH gör även ändringen i den lokala miljön. Ändringen i administrationscentret för Azure Active Directory/administrationscentret för Exchange kommer annars att skrivas över av DirSync.
  
## <a name="related-articles"></a>Relaterade artiklar

[Återställa en användare](restore-user.md)