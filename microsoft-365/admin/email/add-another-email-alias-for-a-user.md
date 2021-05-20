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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Läs om hur du kan ha mer än en e-postadress, ett så kallat e-postalias, som är kopplat till Microsoft 365 för företagskonto. '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572111"
---
# <a name="add-another-email-alias-for-a-user"></a>Lägga till ytterligare ett e-postalias för en användare
  
Den här artikeln är Microsoft 365 administratörer som har företagsprenumerationer. Den är inte avsedd för hemanvändare.
  
En primär e-postadress Microsoft 365 vanligtvis är den e-postadress som en användare tilldelades när deras konto skapades. När användaren skickar e-post till någon annan är det vanligtvis den primära e-postadressen som visas i fältet  *Från*  i e-postappar. De kan också ha mer än en e-postadress kopplad till Microsoft 365 för företagskonto. Dessa ytterligare adresser kallas alias. 
  
Låt oss till exempel säga att Jenna har e-postadressen jenna@contosoco.com, men hon vill också få e-post på jen@contosoco.com eftersom vissa hänvisar till henne med det namnet. Du kan skapa alias för henne så att båda e-postadresserna går till Jennas inkorg.
  
Du kan skapa upp till 400 alias för en användare. Inga ytterligare avgifter eller licenser tillkommer.
  
> [!Tip]
> Om du vill att flera personer ska hantera e-post som skickas till en enda e-postadress info@NodPublishers.com eller sales@NodPublishers.com skapar du en delad postlåda. Mer information finns i Skapa [en delad postlåda](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Lägga till e-postalias för en användare

Du måste ha [administratörsbehörighet för](../add-users/about-admin-roles.md) att kunna göra detta. 

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. På sidan **Aktiva användare** väljer du användarens > användarnamn **och e-post**. Du ser inte det här alternativet om personen inte har tilldelats en licens. 
    
3. Välj **+ Lägg till ett alias** och ange ett nytt alias för användaren.   
    
    > [!Important] 
    > Om du får felmeddelandet " Det går inte att hitta en parameter som **matchar parameternamnet 'EmailAddresses**' betyder det att det tar lite längre tid att slutföra inställningen av din klient eller din anpassade domän om du nyligen har lagt till en. Konfigurationen kan ta upp till 4 timmar. Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen. Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.
    
  
    > [!IMPORTANT]
    > Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern. 
  
    > [!TIP]
    > E-postaliaset måste sluta med en domän från listrutan. Mer om du vill lägga till ett annat domännamn i listan finns [i Lägga till en domän i Microsoft 365](../setup/add-domain.md). 
  
     
5. När du är klar väljer du **Spara ändringar**.
    
6. Vänta 24 timmar tills de nya aliasen fyller i Microsoft 365.
    
    Användaren kommer nu att ha en primär adress och ett alias. Till exempel kommer all post som skickas till Eliza Hoffmans primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, att gå till Elizas inkorg.
    
  
7. **När användaren svarar beror *från-adressen* på hennes Outlook klienten. Outlook på webben kommer att använda aliaset där e-postmeddelandet togs emot (vi kallar detta pingisprincipen). Outlook använder hennes primära e-postalias.** Låt oss till exempel säga att ett meddelande skickas till Sales@NodPublishers.com och det anländer till Elizas inkorg. När Eliza svarar på meddelandet med Outlook skrivbord visas hennes primära e-postadress som Eliza@NodPublishers.com, inte Sales@NodPublishers.com.
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Fick du "Det går inte att hitta en parameter som matchar parameternamnet EmailAddresses"?

Om du får felmeddelandet "**Det går inte att hitta en parameter som matchar parameternamnet EmailAddresses**" betyder det att det tar lite längre tid att slutföra inställningen av din klient eller din anpassade domän om du nyligen har lagt till en. Konfigurationen kan ta upp till 4 timmar. Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen. Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Har du köpt prenumerationen från GoDaddy eller från en annan partner?


Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.

## <a name="sending-email-from-the-proxy-address-easily"></a>Skicka e-post från proxyadressen enkelt

En ny funktion lanseras i april 2021 som gör det möjligt för användare att enkelt skicka från sina alias när Outlook på webben. När funktionen distribueras till en hyresrätt där klient `Set-OrganizationConfig -SendFromAliasEnabled $true` administratören använder cmdleten får användare i hyresrätten åtkomst till en lista med kryssrutor där varje post motsvarar ett alias i sina Outlook inställningar. Om du väljer ett alias visas det i listrutan Från i formuläret Skriv.
  
## <a name="related-content"></a>Relaterat innehåll

[Skicka e-post från en annan adress](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artikel)

[Ändra användarnamn och e-postadress](../add-users/change-a-user-name-and-email-address.md) (artikel)

[Konfigurera vidarebefordran av e-post i Microsoft 365](configure-email-forwarding.md) (artikel)
