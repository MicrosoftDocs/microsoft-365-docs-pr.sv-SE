---
title: Ta bort en användare från organisationen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Lär hur du tar bort ett användarkonto. Bestäm vad du ska göra med användarens e-postadress, OneDrive-innehåll och om du vill behålla produktlicensen eller sluta betala för den.
ms.openlocfilehash: 59d06a075b5badeda410b4b25d60fa135b9ce5f7
ms.sourcegitcommit: a955324e33097bbd2fc4ad7f2b8d1f3d87bc8580
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43608132"
---
# <a name="delete-a-user-from-your-organization"></a>Ta bort en användare från organisationen
  
||
|:-----|
|**Letar du efter information om hur du tar bort ditt *eget* Office 365-användarkonto på jobbet eller skolan? Kontakta den tekniska supporten på ditt arbete eller universitet som kan utföra de här stegen åt dig.**|
   
## <a name="what-you-need-to-know-about-deleting-users"></a>Allt du behöver veta om att ta bort användare

- Bara personer som har [globala Office 365-administratörsbehörigheter](about-admin-roles.md) eller behörighet att hantera användare för företaget eller skolan kan ta bort användarkonton. 
    
- Du har 30 dagar på dig att [återställa](restore-user.md) kontot innan användarens data tas bort permanent. 
    
- Om du vill behålla användarens OneDrive-information flyttar du den till en annan plats. Du kan göra det upp till 30 dagar efter du tagit bort kontot. Se [Få åtkomst till och säkerhetskopiera en tidigare anställds användardata](get-access-to-and-back-up-a-former-user-s-data.md). Du har fortfarande åtkomst till användarens SharePoint-filer och behöver inte flytta dem.
    
- Om du vill behålla användarens e-post flyttar du den till en annan plats **INNAN** du tar bort kontot. Om du redan har tagit bort kontot kan du återställa det inom 30 dagar. Flytta sedan e-postdata och ta bort kontot. Se [Få åtkomst till och säkerhetskopiera en tidigare anställds användardata](get-access-to-and-back-up-a-former-user-s-data.md).
    
- Om du har ett Enterprise-abonnemang, t.ex. Office 365 Enterprise E3, kan du bevara e-postdata för ett borttaget Office 365-användarkonto genom att omvandla det till en *inaktiv postlåda*. Lär dig mer i [Hantera inaktiva postlådor i Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Global administratör: Ta bort medarbetare, sluta betala för deras licens och välj vad du vill göra med deras e-postadress och OneDrive-innehåll

Om du är global administratör och tar bort en användare kan du ge andra användare tillgång till användarens e-post. Du kan också välja vad du vill göra med OneDrive-innehållet. 

  
### <a name="things-to-consider"></a>Saker att tänka på ...

Innan du börjar ska du bestämma dig för vad du vill göra med användarens e-post och OneDrive-innehåll, och om du vill behålla licensen eller sluta betala för den.
  
|||
|:-----|:-----|
|Produktlicenser  <br/> |Du kan ta bort licensen från användaren och ta bort den från dina prenumerationer om du vill sluta betala för den licensen. Om du väljer det här alternativet kommer licensen att tas bort automatiskt från dina prenumerationer.  <br/><br/> **Du kan inte ta bort licensen** om du har köpt den via en partner eller via volymlicensiering. Om du betalar för ett årsabonnemang eller om du är mitt i en faktureringsperiod kan du inte ta bort licensen från din prenumeration förrän abonnemanget har gått ut.  <br/> |
|OneDrive-innehåll  <br/> |Om användaren har sparat sina filer i OneDrive kan du ge en annan användare tillgång till filerna.  <br/><br/> Du måste flytta filerna som du vill behålla inom den kvarhållningstid som har angetts för OneDrive-filer. **Kvarhållningstiden är som standard 30 dagar.** Om du inte flyttar filerna inom kvarhållningstiden efter att du har tagit bort användaren tas OneDrive-innehållet bort permanent. Om du vill öka antalet dagar som du kvarhåller OneDrive-filer för borttagna konton kan du läsa mer i [Ange OneDrive-kvarhållning för borttagna användare](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).  <br/><br/> **Viktigt!** Om den borttagna användaren använde en personlig dator när denna ladda ned filer från SharePoint och OneDrive är det omöjligt för dig att rensa filerna som de har lagrat på datorn. Användaren har fortfarande åtkomst till alla filer som har synkroniserats från OneDrive.           |
|E-post  <br/> | Om du ger en annan användare tillgång till den borttagna användarens e-post konverteras den borttagna användarens postlåda till en delad postlåda. Då har den nya ägaren till postlådan tillgång till den och kan kontrollera nya e-postmeddelanden. Du har även följande alternativ:  <br/>  <br/>Ändra visningsnamnet – Vi rekommenderar att du ändrar visningsnamnet så att det blir enklare att identifiera den delade postlådan i listan över aktiva användare.  <br/>  Aktivera automatiska svar – Det finns redan ett färdigt, artigt automatiskt svar skrivet. Du kan skicka olika automatiska svar till personer inom organisationen och till personer utanför organisationen.  <br/> <br/> Rensa alias-adresser – Ytterligare e-postadresser för användare kallas alias. De används inte i en del organisationer, så om du inte har några behöver du inte göra något mera här. Om användaren har ett eller flera alias rekommenderar vi att du tar bort dem så att du kan använda de e-postadresserna igen. Annars kan du inte använda de e-postadresserna förrän kvarhållningstiden för e-postadressen har gått ut. Som standard är en borttagen postlåda möjlig att återskapa i 30 dagar. Mer information finns i [ta bort eller återställa användarpostlådor i Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox). <br/> |
|Active Directory  <br/> |Om ditt företag använder **Active Directory** som synkroniseras med Azure AD måste du ta bort användarkontot från Active Directory. Du kan inte göra det via Office 365. Anvisningar finns i[Ta bort ett användarkonto](https://go.microsoft.com/fwlink/p/?linkid=841808).  <br/> |
   
### <a name="get-started"></a>Komma igång

::: moniker range="o365-worldwide"

> [!NOTE]
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.

::: moniker-end

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

2. Markera användaren som du vill ta bort och välj sedan **Ta bort användare**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Användarhanteringsadministratör: Ta bort en eller flera användare från Office 365


> [!IMPORTANT]
> Ta inte bort en användares konto om du har [konverterat det till en delad postlåda](../email/convert-user-mailbox-to-shared-mailbox.md) eller om du har konfigurerat vidarebefordran av e-post på kontot. Dessa funktioner behöver fortfarande kontot. En delad postlåda kräver ingen licens. Om du har konverterat kontot till en delad postlåda kan du [sluta betala för licensen](#stop-paying-for-the-license). Om du har konfigurerat vidarebefordran av e-post på kontot kan du inte ta bort licensen. Om du gör det stoppas vidarebefordran av e-post och inaktiverar postlådan.
  
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

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produkter och tjänster</a>. Om du inte ser det här alternativet är du inte en global administratör eller faktureringsadministratör och kan inte genomföra detta steg.

2. Markera prenumerationen (om du har fler än en) och välj sedan **Lägg till/ta bort licenser** för att ta bort licensen så att du inte betalar för den förrän du anställer en ny person.  

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
  
- **Du får ett felmeddelande i stil med "Användare kan inte tas bort. Försök igen senare."** Kontrollera om kontot är inställt att vidarebefordra e-post eller om det har konverterats till en delad postlåda. Båda dessa kan orsaka felet. Ta inte bort ett konto som vidarebefordrar e-postmeddelanden eller har konverterats till en delad postlåda.

- **Du har inte tillräckliga behörigheter för att ta bort en användare**. Bara personer som är [globala Office 365-administratörer eller användarhanteringsadministratörer](about-admin-roles.md) kan ta bort användare. Det är i regel skolans eller företagets tekniska support.

- **Du kan ta bort användaren, men hans eller hennes namn fortsätter visas i den globala adressboken**. Detta inträffar när ett företag använder Active Directory. Du måste ta bort användarkontot från Active Directory. Anvisningar finns i den här TechNet-artikeln: [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808) (Ta bort ett användarkonto).

||
|:-----|
|**Vill du ta bort Office 365 från datorn? Gå till [avsluta prenumerationen](../../commerce/subscriptions/cancel-your-subscription.md).**|
   
## <a name="related-articles"></a>Relaterade artiklar

[Återställa en användare](restore-user.md)
  
[Ta bort meddelande permanent](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[Ta bort en tidigare anställd från Office 365](remove-former-employee.md)

[Lägga till en ny anställd i Office 365](add-new-employee.md)

[Ta bort ett användarkonto](https://go.microsoft.com/fwlink/p/?linkid=841808): Gör följande om ditt företag använder **Active Directory** som synkroniseras med Azure AD. Du kan inte göra det via Office 365.
