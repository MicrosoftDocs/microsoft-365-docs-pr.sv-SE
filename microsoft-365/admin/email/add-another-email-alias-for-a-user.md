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
description: 'Läs om hur du kan ha mer än en e-postadress, ett så kallat e-postalias, kopplat till ditt Microsoft 365 för företag-konto. '
ms.openlocfilehash: 00e1c55edfcfa9937ab6a18b4bf268adb858b775
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107128"
---
# <a name="add-another-email-alias-for-a-user"></a>Lägga till ytterligare ett e-postalias för en användare
  
Den här artikeln är Microsoft 365 administratörer som har företagsprenumerationer. Den är inte avsedd för hemanvändare.
  
En primär e-postadress Microsoft 365 vanligtvis den e-postadress som användaren tilldelades när kontot skapades. När användaren skickar e-post till någon annan är det vanligtvis den primära e-postadressen som visas i fältet  *Från*  i e-postappar. De kan också ha mer än en e-postadress kopplad till sitt Microsoft 365 för företag-konto. Dessa ytterligare adresser kallas alias. 
  
Anta till exempel att Jenna har e-postadressen jenna@contosoco.com, men hon vill också ta emot e-post på jen@contosoco.com eftersom vissa personer hänvisar till henne med det namnet. Du kan skapa alias för henne så att båda e-postadresserna går till Jennas inkorg.
<br><br>  
  
Du kan skapa upp till 400 alias för en användare. Inga ytterligare avgifter eller licenser tillkommer.
  
> [!Tip]
> Om du vill att flera personer ska hantera e-post som skickas till en enskild e-postadress, info@NodPublishers.com eller sales@NodPublishers.com, kan du skapa en delad postlåda. Mer information finns i Skapa [en delad postlåda](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Lägga till e-postalias för en användare
<a name="AddEmailPreview"> </a>

Du måste ha [administratörsbehörighet för](../add-users/about-admin-roles.md) att göra detta. 

  
::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. På sidan **Aktiva användare** väljer du den användare som > användarnamn **och e-post**. Du ser inte det här alternativet om personen inte har någon tilldelad licens. 
    
3. Välj **+ Lägg till ett alias** och ange ett nytt alias för användaren.   
    
    > [!Important] 
    > Om du får felmeddelandet " Det hittades ingen parameter som matchar **parameternamnet**'E-postadresser'" innebär det att det tar lite längre tid att slutföra klientorganisationen eller den anpassade domänen, om du nyligen har lagt till en sådan. Konfigurationen kan ta upp till 4 timmar. Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen. Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.
    
  
    > [!IMPORTANT]
    > Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern. 
  
    > [!TIP]
    > E-postaliaset måste sluta med en domän från listrutan. Om du vill lägga till ett annat domännamn i listan kan du [gå till Lägga till en domän Microsoft 365](../setup/add-domain.md). 
  
     
5. När du är klar väljer du **Spara ändringar.**
    
6. Vänta 24 timmar för att de nya aliasen ska fyllas i Microsoft 365.
    
    Användaren har nu en primär adress och ett alias. Till exempel skickas all e-post som skickas till Erna Hanssons primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, till Ernas inkorg.
    
  
7. **När användaren svarar beror *Av-adressen* på hennes egen Outlook klient. Outlook på webben använder aliaset som e-postmeddelandet togs emot från (vi kallar detta ping-principle). Outlook datorn kommer att använda hennes primära e-postalias.** Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och kommer till Ernas inkorg. När Erna svarar på meddelandet Outlook datorn visas hennes primära e-postadress Eliza@NodPublishers.com, inte Sales@NodPublishers.com.
    
::: moniker-end

::: moniker range="o365-germany"
    
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>. 
    
    
2. På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.

3. Bredvid **Användarnamn/E-postalias** väljer du **Redigera.**

    > [!Important] 
    > Om du får felmeddelandet " Det hittades ingen parameter som matchar **parameternamnet**'E-postadresser'" innebär det att det tar lite längre tid att slutföra klientorganisationen eller den anpassade domänen, om du nyligen har lagt till en sådan. Konfigurationen kan ta upp till 4 timmar. Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen. Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.

4. I textrutan under **Alias skriver du** den första delen av det nya e-postaliaset. Om du har lagt till din egen domän i Microsoft 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan. Välj sedan Lägg **till**.

    > [!IMPORTANT]
    > Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern. 
  
    > [!TIP]
    > E-postaliaset måste sluta med en domän från listrutan. Om du vill lägga till ett annat domännamn i listan kan du [gå till Lägga till en domän Microsoft 365](../setup/add-domain.md). 

5. Välj Spara när du är **klar.**

6. Vänta 24 timmar för att de nya aliasen ska fyllas i Microsoft 365. 
    
    Användaren har nu en primär adress och ett alias. Till exempel skickas all e-post som skickas till Erna Hanssons primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, till Ernas inkorg.
    
  
7. **När användaren svarar beror *Av-adressen* på hennes egen Outlook klient. Outlook på webben använder aliaset som e-postmeddelandet togs emot från (vi kallar detta ping-principle). Outlook datorn kommer att använda hennes primära e-postalias.** Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och kommer till Ernas inkorg. När Erna svarar på meddelandet Outlook datorn visas hennes primära e-postadress Eliza@NodPublishers.com, inte Sales@NodPublishers.com.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>. 

    
2. På sidan **Aktiva användare** väljer du namnet på den person som du vill redigera.

3. Bredvid **Användarnamn/E-postalias** väljer du **Redigera.**

    > [!Important] 
    > Om du får felmeddelandet " Det hittades ingen parameter som matchar **parameternamnet**'E-postadresser'" innebär det att det tar lite längre tid att slutföra klientorganisationen eller den anpassade domänen, om du nyligen har lagt till en sådan. Konfigurationen kan ta upp till 4 timmar. Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen. Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.

4. I textrutan under **Alias skriver du** den första delen av det nya e-postaliaset. Om du har lagt till din egen domän i Microsoft 365 kan du välja domänen för det nya e-postaliaset med hjälp av listrutan. Välj sedan Lägg **till**.

    > [!IMPORTANT]
    > Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern. 
  
    > [!TIP]
    > E-postaliaset måste sluta med en domän från listrutan. Om du vill lägga till ett annat domännamn i listan kan du [gå till Lägga till en domän Microsoft 365](../setup/add-domain.md). 

5. Välj Spara när du är **klar.**

6. Vänta 24 timmar för att de nya aliasen ska fyllas i Microsoft 365. 
    
    Användaren har nu en primär adress och ett alias. Till exempel skickas all e-post som skickas till Erna Hanssons primära adress, Eliza@NodPublishers.com, och hennes alias, Sales@NodPublishers.com, till Ernas inkorg.
    
  
7. **När användaren svarar beror *Av-adressen* på hennes egen Outlook klient. Outlook på webben använder aliaset som e-postmeddelandet togs emot från (vi kallar detta ping-principle). Outlook datorn kommer att använda hennes primära e-postalias.** Anta till exempel att ett meddelande skickas till Sales@NodPublishers.com och kommer till Ernas inkorg. När Erna svarar på meddelandet Outlook datorn visas hennes primära e-postadress Eliza@NodPublishers.com, inte Sales@NodPublishers.com.

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Fick du meddelandet "Det hittades ingen parameter som matchar parameternamnet E-postadresser"?


Om du får felmeddelandet " Det hittades ingen parameter som matchar **parameternamnet E-postadresser**" innebär det att det tar lite längre tid att slutföra klientorganisationen eller den anpassade domänen, om du nyligen har lagt till en sådan. Konfigurationen kan ta upp till 4 timmar. Vänta en stund så att konfigurationen hinner slutföras och försök sedan igen. Om problemet kvarstår kan du ringa supporten så att de kan göra en fullständig synkronisering åt dig.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Har du köpt prenumerationen från GoDaddy eller från en annan partner?


Om du har köpt prenumerationen från GoDaddy eller från en annan partner och vill ange ett nytt alias som den primära e-postadressen måste du gå till hanteringskonsolen för GoDaddy eller partnern.

## <a name="sending-email-from-the-proxy-address-easily"></a>Skicka enkelt e-post från proxyadressen

En ny funktion lanseras i april 2021 som gör att användare enkelt kan skicka från sina alias när de Outlook på webben. När funktionen distribueras till ett innehavaradministratör som använder cmdleten får användare inom innehavarorganisationen tillgång till en lista med kryssrutor där varje post motsvarar ett alias i `Set-OrganizationConfig -SendFromAliasEnabled $true` Outlook inställningar. När du väljer ett alias visas det i listrutan Från i formuläret Skriv.
  
## <a name="related-articles"></a>Relaterade artiklar

[Skicka e-post från en annan adress](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Ändra ett användarnamn och en e-postadress](../add-users/change-a-user-name-and-email-address.md)
