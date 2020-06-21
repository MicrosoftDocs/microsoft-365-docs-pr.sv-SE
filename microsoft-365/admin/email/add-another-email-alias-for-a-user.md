---
title: Lägga till ytterligare ett e-postalias för en användare
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
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Läs om hur du kan ha mer än en e-postadress, ett så kallat e-postalias, kopplat till ditt Microsoft 365 för företagskonto. '
ms.openlocfilehash: c0e71ef150ccf592ea4f808a5e6609e1675767a4
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780295"
---
# <a name="add-another-email-alias-for-a-user"></a>Lägga till ytterligare ett e-postalias för en användare

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Den här artikeln är avsedd för Microsoft 365-administratörer som har företagsprenumerationer. Den är inte avsedd för hemanvändare.
  
En primär e-postadress i Microsoft 365 är vanligtvis den e-postadress som en användare tilldelades när deras konto skapades. När användaren skickar e-post till någon annan är det vanligtvis den primära e-postadressen som visas i fältet  *Från*  i e-postappar. De kan också ha mer än en e-postadress kopplad till sitt Microsoft 365 för företagskonto. Dessa ytterligare adresser kallas alias. 
  
Anta till exempel att Jenna har e-postadressen jenna@contosoco.com, men hon vill också få e-post på jen@contosoco.com eftersom vissa personer hänvisar till henne med det namnet. Du kan skapa alias för henne så att båda e-postadresserna går till Jennas inkorg.
<br><br>  
  
Du kan skapa upp till 400 alias för en användare. Inga ytterligare avgifter eller licenser tillkommer.
  
> [!Tip]
> Om du vill att flera personer ska hantera e-post som skickas till en enda e-postadress som info@NodPublishers.com eller sales@NodPublishers.com skapar du en delad postlåda. Mer information finns i [Skapa en delad postlåda](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Lägga till e-postalias för en användare
<a name="AddEmailPreview"> </a>

Du måste ha [administratörsbehörighet](../add-users/about-admin-roles.md) för att kunna göra detta. 

  
::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. På sidan **Aktiva användare** väljer du användaren > **Hantera e-postalias**. Det här alternativet visas inte om personen inte har tilldelats någon licens. 
    
3. Välj **+ Lägg till ett alias** och ange ett nytt alias för användaren.   
    
    > [!Important] 
    > Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet "EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en. Konfigurationen kan ta upp till 4 timmar. Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen. Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.
    
  
    > [!IMPORTANT]
    > Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern. 
  
    > [!TIP]
    > E-postaliaset måste sluta med en domän från listrutan. Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 
  
     
5. När du är klar väljer du **Spara ändringar**.
    
6. Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365.
    
    Användaren har nu en primär adress och ett alias. Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.
    
  
7. **När användaren svarar blir *från-adressen* hennes primära e-postalias.** Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg. När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>. 
    
    
2. På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.

3. Välj **Redigera** **bredvid Användarnamn/E-postalias**.

    > [!Important] 
    > Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet "EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en. Konfigurationen kan ta upp till 4 timmar. Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen. Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.

4. Skriv den första delen av det nya e-postaliaset i textrutan under **Alias.** Om du har lagt till din egen domän i Office 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan. Välj sedan **Lägg till**.

    > [!IMPORTANT]
    > Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern. 
  
    > [!TIP]
    > E-postaliaset måste sluta med en domän från listrutan. Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 

5. När du är klar väljer du **Spara**.

6. Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365. 
    
    Användaren har nu en primär adress och ett alias. Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.
    
  
7. **När användaren svarar blir *från-adressen* hennes primära e-postalias.** Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg. När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>. 

    
2. På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.

3. Välj **Redigera** **bredvid Användarnamn/E-postalias**.

    > [!Important] 
    > Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet "EmailAddresses**", betyder det att det tar lite längre tid att konfigurera din klient, eller din anpassade domän om du nyligen lagt till en. Konfigurationen kan ta upp till 4 timmar. Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen. Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.

4. Skriv den första delen av det nya e-postaliaset i textrutan under **Alias.** Om du har lagt till din egen domän i Office 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan. Välj sedan **Lägg till**.

    > [!IMPORTANT]
    > Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern. 
  
    > [!TIP]
    > E-postaliaset måste sluta med en domän från listrutan. Information om hur du lägger till ett annat domännamn i listan finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 

5. När du är klar väljer du **Spara**.

6. Vänta 24 timmar medan de nya aliasadresserna fylls i i hela Office 365. 
    
    Användaren har nu en primär adress och ett alias. Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.
    
  
7. **När användaren svarar blir *från-adressen* hennes primära e-postalias.** Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och det kommer till Elizas inkorg. När Erna besvarar meddelandet visas hennes primära e-postadress som avsändare, inte Sales@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Fick du "En parameter kan inte hittas som matchar parameternamnet EmailAddresses"?


Om du får felmeddelandet "**En parameter kan inte hittas som matchar parameternamnet EmailAddresses**" betyder det att det tar lite längre tid att slutföra inrättandet av din klient, eller din anpassade domän om du nyligen lagt till en. Konfigurationen kan ta upp till 4 timmar. Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen. Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Har du köpt prenumerationen från GoDaddy eller från en annan partner?


Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.
  
## <a name="related-articles"></a>Relaterade artiklar

[Skicka e-post från en annan adress](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Ändra ett användarnamn och en e-postadress](../add-users/change-a-user-name-and-email-address.md)
  

