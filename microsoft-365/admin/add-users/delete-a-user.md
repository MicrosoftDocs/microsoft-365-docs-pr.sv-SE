---
title: Ta bort en användare från organisationen
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
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Lär dig hur du tar bort ett användarkonto och vad du gör med användarens e-post och OneDrive innehåll och om du vill behålla produktlicensen.
ms.openlocfilehash: c30edb598f659337778ec956737934da5fedad18
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593411"
---
# <a name="delete-a-user-from-your-organization"></a>Ta bort en användare från organisationen
  
**Letar du efter information om hur *du Microsoft 365* ditt eget användarkonto på arbetet eller i skolan? Kontakta den tekniska supporten på ditt arbete eller universitet som kan göra de här stegen åt dig.**

## <a name="before-you-begin"></a>Innan du börjar

- Endast personer som Microsoft 365 [global administratör eller](about-admin-roles.md) användarhanteringsbehörighet för företaget eller skolan kan ta bort användarkonton.
- Du har 30 dagar på dig att [återställa](restore-user.md) kontot innan användarens data tas bort permanent.
- Om du vill behålla användarens OneDrive-information flyttar du den till en annan plats. Du kan även flytta data upp till 30 dagar efter att kontot tagits bort. Se [Få åtkomst till och säkerhetskopiera en tidigare anställds användardata](get-access-to-and-back-up-a-former-user-s-data.md). Du har fortfarande åtkomst till användarens SharePoint-filer och behöver inte flytta dem.
- Om du vill behålla användarens e-post flyttar du den till en annan plats **INNAN** du tar bort kontot. Om du redan har tagit bort kontot kan du återställa det inom 30 dagar. Flytta sedan e-postdata och ta bort kontot. Se [Få åtkomst till och säkerhetskopiera en tidigare anställds användardata](get-access-to-and-back-up-a-former-user-s-data.md).
- Om du har en Enterprise-prenumeration som Office 365 Enterprise E3 kan du bevara e-postdata för ett borttagna användarkonto genom att göra om det till en *inaktiv postlåda.* Lär dig mer i [Hantera inaktiva postlådor i Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Global administratör: Ta bort medarbetare, sluta betala för deras licens och välj vad du vill göra med deras e-postadress och OneDrive-innehåll

Om du är global administratör och tar bort en användare kan du ge andra användare tillgång till användarens e-post. Du kan också välja vad du vill göra med OneDrive-innehållet.

### <a name="things-to-consider"></a>Saker att tänka på

Innan du börjar ska du bestämma dig för vad du vill göra med användarens e-post och OneDrive-innehåll, och om du vill behålla licensen eller sluta betala för den.
  
|Objekt | Beskrivning |
|:-----|:-----|
|Produktlicenser  <br/> |Du kan ta bort licensen från användaren och ta bort den från dina prenumerationer om du vill sluta betala för den licensen. Om du väljer det här alternativet kommer licensen att tas bort automatiskt från dina prenumerationer.  <br/><br/> **Du kan inte ta bort licensen** om du har köpt den via en partner eller via volymlicensiering. Om du betalar för ett årsabonnemang eller om du är mitt i en faktureringsperiod kan du inte ta bort licensen från prenumerationen förrän abonnemanget har slutförts.  <br/> |
|OneDrive-innehåll  <br/> |Om användaren har sparat sina filer i OneDrive kan du ge en annan användare tillgång till filerna.  <br/><br/> Du måste flytta filerna som du vill behålla inom den kvarhållningstid som har angetts för OneDrive-filer. **Kvarhållningstiden är som standard 30 dagar.** Om du inte flyttar filerna inom kvarhållningstiden efter att du har tagit bort användaren tas OneDrive-innehållet bort permanent. Om du vill öka antalet dagar som du kvarhåller OneDrive-filer för borttagna konton kan du läsa mer i [Ange OneDrive-kvarhållning för borttagna användare](/onedrive/set-retention).  <br/><br/> **Viktigt!** Om den borttagna användaren använde en personlig dator när denna ladda ned filer från SharePoint och OneDrive är det omöjligt för dig att rensa filerna som de har lagrat på datorn. Användaren har fortfarande åtkomst till alla filer som har synkroniserats från OneDrive.           |
|E-post  <br/> | Om du ger en annan användare tillgång till den borttagna användarens e-post konverteras den borttagna användarens postlåda till en delad postlåda. Då har den nya ägaren till postlådan tillgång till den och kan kontrollera nya e-postmeddelanden. Du har även följande alternativ:  <br/>  <br/>Ändra visningsnamnet – Vi rekommenderar att du ändrar visningsnamnet så att det blir enklare att identifiera den delade postlådan i listan **Aktiva** användare.  <br/>  Aktivera automatiska svar - Det finns redan ett färdigt, artigt automatiskt svar skrivet. Du kan skicka olika automatiska svar till personer inom organisationen och till personer utanför organisationen.  <br/> <br/> Rensa alias-adresser – Ytterligare e-postadresser för användare kallas alias. De används inte i en del organisationer, så om du inte har några behöver du inte göra något mera här. Om användaren har alias rekommenderar vi att du tar bort dem så att du kan återanvända de e-postadresserna. Annars kan du inte återanvända de e-postadresserna förrän bevarandetiden för borttagna postlådor har passerat. Som standard är en borttagen postlåda möjlig att återskapa i 30 dagar. Mer information finns i [ta bort eller återställa användarpostlådor i Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox). <br/> |
|Active Directory  <br/> |Om ditt företag använder **Active Directory** som synkroniseras med Azure AD måste du ta bort användarkontot från Active Directory. Du kan inte göra det via Office 365. Anvisningar finns i[Ta bort ett användarkonto](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).  <br/> |

### <a name="get-started"></a>Komma igång

Du blir guidad genom processen för att ta bort en användare. Så här kommer du igång.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

::: moniker-end

2. Markera den användare som du vill ta bort och välj sedan Ta **bort användare.**

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Användarhanteringsadministratör: Ta bort en eller flera användare från Office 365

> [!IMPORTANT]
> Ta inte bort en användares konto [](../email/convert-user-mailbox-to-shared-mailbox.md) om du har konverterat det till en delad postlåda eller om du har ställt in vidarebefordran av e-post för kontot. Dessa funktioner behöver kontot. En delad postlåda kräver ingen licens. Om du har konverterat kontot till en delad postlåda kan du [sluta betala för licensen.](#stop-paying-for-the-license) Om du har ställt in vidarebefordran av e-post för kontot kan du inte ta bort licensen. Då avbryts vidarebefordran av e-post och postlådan inaktiveras.
  
::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.  

2. Markera namnen på de användare som du vill ta bort, välj de tre punkterna (fler åtgärder) och välj sedan Ta **bort användare.**

   **Du betalar fortfarande för licensen** även om du har tagit bort användarens konto. Se nästa procedur om du vill sluta betala för licensen.  Du kan sedan tilldela licensen till en annan användare. Den kommer inte automatiskt att tilldelas till någon.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Markera namnen på de användare som du vill ta bort och välj **Ta bort användare** i rutan **Massåtgärder**. 

   **Du betalar fortfarande för licensen** även om du har tagit bort användarens konto. Se nästa procedur om du vill sluta betala för licensen.  Du kan sedan tilldela licensen till en annan användare. Den kommer inte automatiskt att tilldelas till någon.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Markera namnen på de användare som du vill ta bort och välj **Ta bort användare** i rutan **Massåtgärder**. 

   **Du betalar fortfarande för licensen** även om du har tagit bort användarens konto. Se nästa procedur om du vill sluta betala för licensen.  Du kan sedan tilldela licensen till en annan användare. Den kommer inte automatiskt att tilldelas till någon.

::: moniker-end

### <a name="stop-paying-for-the-license"></a>Sluta betala för licensen

Att minska antalet licenser är ett separat steg som endast kan utföras av den globala administratören eller faktureringsadministratören.
  
::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>. Om du inte ser det här alternativet är du inte en global administratör eller faktureringsadministratör och kan inte genomföra detta steg.

2. På fliken **Produkter** väljer du den prenumeration som du vill ta bort licenser för.

3. På sidan prenumerationsinformation väljer du Ta **bort licenser.**

4. I fönstret **Ta bort** licenser, under  **Nytt** antal, i rutan Totalt antal licenser anger du det totala antalet licenser som du vill använda för prenumerationen. Om du till exempel har 100 licenser och vill ta bort fem av dem anger du 95.

5. Välj **Spara**.

När du sedan följer anvisningarna och lägger till en annan person i verksamheten uppmanas du samtidigt att köpa en licens.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret. Om du inte ser det här alternativet är du inte en global administratör eller faktureringsadministratör och kan inte genomföra detta steg.

2. Markera prenumerationen (om du har fler än en) och välj sedan **Lägg till/ta bort licenser** för att ta bort licensen så att du inte betalar för den förrän du anställer en ny person.  

   När du sedan följer anvisningarna och lägger till en annan person i verksamheten uppmanas du samtidigt att köpa en licens.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret. Om du inte ser det här alternativet är du inte en global administratör eller faktureringsadministratör och kan inte genomföra detta steg.

2. Markera prenumerationen (om du har fler än en) och välj sedan **Lägg till/ta bort licenser** för att ta bort licensen så att du inte betalar för den förrän du anställer en ny person.  

   När du sedan följer anvisningarna och lägger till en annan person i verksamheten uppmanas du samtidigt att köpa en licens.

::: moniker-end

## <a name="delete-many-users-at-the-same-time"></a>Ta bort flera användare samtidigt

Läs mer om PowerShell-cmdleten [Remove-MsolUser](/powershell/module/msonline/remove-msoluser).

## <a name="fix-issues-with-deleting-a-user"></a>Åtgärda problem med att ta bort en användare

Här är de vanligaste problemen som uppstår när du tar bort en användare:
  
- **Du får ett felmeddelande i linje med "Användare kan inte tas bort. Försök igen senare."** Kontrollera om kontot är inställt att vidarebefordra e-post eller om det har konverterats till en delad postlåda. Båda dessa kan orsaka felet. Ta inte bort kontot om det har vidarebefordran av e-post eller om det har konverterats till en delad postlåda.

- **Du har inte tillräckliga behörigheter för att ta bort en användare**. Endast personer som är [Microsoft 365 globala administratörer eller användarhanteringsadministratörer kan](about-admin-roles.md) ta bort användare. Det är i regel skolans eller företagets tekniska support.

- **Du kan ta bort användaren, men hans eller hennes namn fortsätter visas i den globala adressboken**. Detta inträffar när ett företag använder Active Directory. Du måste ta bort användarkontot från Active Directory. Anvisningar finns i Ta [bort ett användarkonto.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**Vill du ta bort Microsoft 365 datorn? Gå till [Avsluta prenumerationen.](../../commerce/subscriptions/cancel-your-subscription.md)**

## <a name="related-content"></a>Relaterat innehåll

[Återställa en användare](restore-user.md) (artikel)
  
[Ta bort en postlåda permanent](/exchange/permanently-delete-a-mailbox-exchange-2013-help) (artikel)

[Ta bort en tidigare anställd från Office 365](remove-former-employee.md) (artikel)

[Lägga till en ny anställd i Office 365](add-new-employee.md) (artikel)

[Ta bort ett användarkonto](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)): Gör följande om ditt företag använder **Active Directory** som synkroniseras med Azure AD. Du kan inte göra det via Office 365. (artikel)