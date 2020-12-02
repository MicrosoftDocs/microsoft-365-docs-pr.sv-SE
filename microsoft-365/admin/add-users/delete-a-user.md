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
description: Lär dig hur du tar bort ett användar konto. Bestäm vad som ska göras med användarens e-post-och OneDrive-innehåll. Och bestäm om du vill behålla produkt licensen eller sluta betala för den.
ms.openlocfilehash: 45cf8b9173a3a4260fe664b809f47ab14b57d9fe
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551382"
---
# <a name="delete-a-user-from-your-organization"></a>Ta bort en användare från organisationen
  
**Letar du efter hur du tar bort ditt *eget* Microsoft 365-konto som du använder på jobbet eller skolan? Kontakta den tekniska supporten på ditt arbete eller University för att utföra de här stegen för dig.**

## <a name="what-you-need-to-know-about-deleting-users"></a>Allt du behöver veta om att ta bort användare

- Endast personer som har [Microsoft 365 global administratör](about-admin-roles.md) eller användar hanterings behörigheter för företaget eller skolan kan ta bort användar konton.
- Du har 30 dagar på dig att [återställa](restore-user.md) kontot innan användarens data tas bort permanent.
- Om du vill behålla användarens OneDrive-information flyttar du den till en annan plats. Du kan till och med flytta informationen upp till 30 dagar efter att du har tagit bort kontot. Se [Få åtkomst till och säkerhetskopiera en tidigare anställds användardata](get-access-to-and-back-up-a-former-user-s-data.md). Du har fortfarande åtkomst till användarens SharePoint-filer och behöver inte flytta dem.
- Om du vill behålla användarens e-post flyttar du den till en annan plats **INNAN** du tar bort kontot. Om du redan har tagit bort kontot kan du återställa det inom 30 dagar. Flytta sedan e-postdata och ta bort kontot. Se [Få åtkomst till och säkerhetskopiera en tidigare anställds användardata](get-access-to-and-back-up-a-former-user-s-data.md).
- Om du har ett företags abonnemang som Office 365 Enterprise E3 kan du bevara post lådorna för ett borttaget användar konto genom att förvandla det till en *inaktiv post låda*. Lär dig mer i [Hantera inaktiva postlådor i Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Global administratör: Ta bort medarbetare, sluta betala för deras licens och välj vad du vill göra med deras e-postadress och OneDrive-innehåll

Om du är global administratör och tar bort en användare kan du ge andra användare tillgång till användarens e-post. Du kan också välja vad du vill göra med OneDrive-innehållet.

### <a name="things-to-consider"></a>Saker att tänka på ...

Innan du börjar ska du bestämma dig för vad du vill göra med användarens e-post och OneDrive-innehåll, och om du vill behålla licensen eller sluta betala för den.
  
|Objekt | Beskrivning |
|:-----|:-----|
|Produktlicenser  <br/> |Du kan ta bort licensen från användaren och ta bort den från dina prenumerationer om du vill sluta betala för den licensen. Om du väljer det här alternativet kommer licensen att tas bort automatiskt från dina prenumerationer.  <br/><br/> **Du kan inte ta bort licensen** om du har köpt den via en partner eller via volymlicensiering. Om du betalar för en årlig plan eller om du befinner dig i en fakturerings cykel kan du inte ta bort licensen från ditt abonnemang förrän åtagandet är klart.  <br/> |
|OneDrive-innehåll  <br/> |Om användaren har sparat sina filer i OneDrive kan du ge en annan användare tillgång till filerna.  <br/><br/> Du måste flytta filerna som du vill behålla inom den kvarhållningstid som har angetts för OneDrive-filer. **Kvarhållningstiden är som standard 30 dagar.** Om du inte flyttar filerna inom kvarhållningstiden efter att du har tagit bort användaren tas OneDrive-innehållet bort permanent. Om du vill öka antalet dagar som du kvarhåller OneDrive-filer för borttagna konton kan du läsa mer i [Ange OneDrive-kvarhållning för borttagna användare](https://docs.microsoft.com/onedrive/set-retention).  <br/><br/> **Viktigt!** Om den borttagna användaren använde en personlig dator när denna ladda ned filer från SharePoint och OneDrive är det omöjligt för dig att rensa filerna som de har lagrat på datorn. Användaren har fortfarande åtkomst till alla filer som har synkroniserats från OneDrive.           |
|E-post  <br/> | Om du ger en annan användare tillgång till den borttagna användarens e-post konverteras den borttagna användarens postlåda till en delad postlåda. Då har den nya ägaren till postlådan tillgång till den och kan kontrollera nya e-postmeddelanden. Du har även följande alternativ:  <br/>  <br/>Ändra visnings namnet-vi rekommenderar att du ändrar visnings namnet så att det blir lättare att identifiera den delade post lådan i listan **aktiva användare** .  <br/>  Aktivera automatiska svar - Det finns redan ett färdigt, artigt automatiskt svar skrivet. Du kan skicka olika autosvar till personer inom organisationen och personer utanför din organisation.  <br/> <br/> Rensa alias-adresser – Ytterligare e-postadresser för användare kallas alias. De används inte i en del organisationer, så om du inte har några behöver du inte göra något mera här. Om användaren har alias rekommenderar vi att du tar bort dem så att du kan återanvända dessa e-postadresser. Annars kan du inte återanvända de här e-postadresserna förrän lagrings perioden för borttagna post lådor. Som standard är en borttagen postlåda möjlig att återskapa i 30 dagar. Mer information finns i [ta bort eller återställa användarpostlådor i Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox). <br/> |
|Active Directory  <br/> |Om ditt företag använder **Active Directory** som synkroniseras med Azure AD måste du ta bort användarkontot från Active Directory. Du kan inte göra det via Office 365. Anvisningar finns i[Ta bort ett användarkonto](https://go.microsoft.com/fwlink/p/?linkid=841808).  <br/> |

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

2. Välj den användare du vill ta bort och välj sedan **ta bort användare**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Användarhanteringsadministratör: Ta bort en eller flera användare från Office 365

> [!IMPORTANT]
> Ta inte bort en användares konto om du har [konverterat det till en delad post låda](../email/convert-user-mailbox-to-shared-mailbox.md) eller om du har konfigurerat e-postvidarekoppling för kontot. De här funktionerna behöver fortfarande kontot. Ingen licens krävs för en delad post låda. Om du har konverterat kontot till en delad post låda kan du [sluta betala för licensen](#stop-paying-for-the-license). Om du har konfigurerat e-postvidarekoppling på kontot kan du inte ta bort licensen. Nu kommer du att stoppa e-postvidarekoppling och inaktivera post lådan.
  
::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.  

2. Markera namnen på de användare som du vill ta bort, välj **Fler alternativ** (**...**) och sedan **Ta bort användare**. 

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

2. På fliken **produkter** väljer du den prenumeration där du vill ta bort licenser.

3. På sidan prenumerations information väljer du **ta bort licenser**.

4. I fönstret **ta bort licenser** , under **ny kvantitet**, i rutan **Totalt antal licenser** anger du det totala antalet licenser som du vill använda för det här abonnemanget. Om du till exempel har 100 licenser och vill ta bort fem av dem, anger du 95.

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

Läs mer om PowerShell-cmdleten [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230).

## <a name="fix-issues-with-deleting-a-user"></a>Åtgärda problem med att ta bort en användare

Här är de vanligaste problemen som uppstår när du tar bort en användare:
  
- **Du får ett fel meddelande längs raderna för användaren kan inte tas bort. Försök igen senare. "** Kontrol lera om det finns e-postvidarekoppling för kontot eller om det har konverterats till en delad post låda. Dessa fel kommer att uppstå. Ta inte bort kontot om det har e-postvidarekoppling eller om det har konverterats till en delad post låda.

- **Du har inte tillräckliga behörigheter för att ta bort en användare**. Endast personer som är [Microsoft 365-globala administratörer eller användar hanterings administratörer](about-admin-roles.md) kan ta bort användare. Det är i regel skolans eller företagets tekniska support.

- **Du kan ta bort användaren, men hans eller hennes namn fortsätter visas i den globala adressboken**. Detta inträffar när ett företag använder Active Directory. Du måste ta bort användar kontot från Active Directory. Anvisningar finns i [ta bort ett användar konto.](https://go.microsoft.com/fwlink/p/?linkid=841808)

**Vill du ta bort Microsoft 365 från datorn? Gå till [Avbryt prenumerationen](../../commerce/subscriptions/cancel-your-subscription.md).**

## <a name="related-articles"></a>Relaterade artiklar

[Återställa en användare](restore-user.md)
  
[Ta bort meddelande permanent](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[Ta bort en tidigare anställd från Office 365](remove-former-employee.md)

[Lägga till en ny anställd i Office 365](add-new-employee.md)

[Ta bort ett användarkonto](https://go.microsoft.com/fwlink/p/?linkid=841808): Gör följande om ditt företag använder **Active Directory** som synkroniseras med Azure AD. Du kan inte göra det via Office 365.