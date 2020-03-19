---
title: Återställa lösenord för Office 365-företag
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
- TopSMBIssues
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7a5d073b-7fae-4aa5-8f96-9ecd041aba9c
description: 'Läs om hur du återställer lösenord för en användare i Office 365 företagsprenumeration. '
ms.openlocfilehash: a19999ceffa140343c079c6758cc831175c09ab1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811535"
---
# <a name="reset-office-365-business-passwords"></a>Återställa lösenord för Office 365-företag

Titta på en kort video om hur du återställer användarlösenord.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="let-users-reset-their-own-passwords"></a>Låt användare återställa sina egna lösenord

Vi rekommenderar att du konfigurerar återställning av egna lösenord. På så vis behöver du inte manuellt återställa lösenord för användarna. Läs i så fall [Låt användare återställa sina egna lösenord i Office 365](let-users-reset-passwords.md).
  
## <a name="reset-an-office-365-business-password-for-someone-else"></a>Återställa ett Office 365 Business-lösenord för någon annan

De här anvisningarna gäller endast Office 365 Business-prenumeranter. För att kunna göra dem måste du logga in med ditt Microsoft 365-administratörskonto. [Vad är ett administratörskonto?](../admin-overview/admin-overview.md)

 
::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

::: moniker-end

2. På sidan **Aktiva användare** väljer du användaren och väljer sedan **Återställ lösenord**.
    
3. Följ instruktionerna på sidan **Återställ lösenord** för att automatiskt generera ett nytt lösenord för användaren eller skapa ett för dem och välj sedan **Återställ**.  
    
4. Ange en e-postadress som användaren kan komma åt så att de får det nya lösenordet och följ upp med dem för att se till att de fick det.
 
  
## <a name="reset-my-office-365-tenant-admin-password"></a>Återställa administratörslösenordet för Office 365-klient

Använd de här stegen om du har glömt ditt lösenord men ändå kan logga in på Office 365 eftersom lösenordet till exempel har sparats i din webbläsare: 
    
1. I Office 365 väljer du **Inställningar för** \> **Office 365** \> **Personlig information**. 
          
2. Kontrollera att **Kontaktinformation**och **Alternativ e-postadress** stämmer. Ändra dem annars nu. 
        
3. Logga ut från Office 365: välj ditt namn i det övre **Diane**högra \> hörnet (i bilden ovan, visad som Diane ) **Logga ut**. 
        
4. Logga in igen: skriv \> ditt användarnamn **Nästa** \> och välj sedan **Glömt lösenord**. 
    
5. Följ anvisningarna i guiden för att återställa lösenordet. De alternativa kontaktuppgifterna används för att verifiera att du är rätt person som ska återställa lösenordet. 
    
Om du har glömt ditt lösenord och inte kan logga in: 
    
- Be en annan global administratör i företaget att återställa lösenordet åt dig.
    
- Du kan också [kontakta Microsoft Support](https://support.office.com/article/contact-support-for-business-products-admin-help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b?ui=en-US&amp;rs=en-US&amp;ad=US#ID0EAADAAA=Phone_support_). 
    
## <a name="reset-all-office-365-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Återställa alla Office 365 Business-lösenord för alla i organisationen samtidigt
<a name="bkmk_forgot"> </a>

Dessa anvisningar fungerar för verksamheter med dussintals användare. Om du har tusentals användare kan du läsa mer om hur du återställer flera lösenord samtidigt i nästa avsnitt.
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
    
2. Välj alternativet **bredvid Visa namn** om du vill välja alla i ditt företag. Avmarkera sedan dig själv. Du kan inte återställa ditt eget lösenord samtidigt som du återställer alla andras lösenord.
    
3. Välj **Återställ lösenord**. 

4. Följ instruktionerna på sidan **Återställ lösenord** och välj **Återställ**.  Om du har valt att automatiskt generera lösenorden visas de nya tillfälliga lösenorden.   
    
5. Ange en e-postadress där du kan få de tillfälliga lösenorden. Du måste meddela användarna vilka tillfälliga lösenord de är.
    

  
## <a name="reset-office-365-business-passwords-in-bulk"></a>Återställa Office 365 Business-lösenord i grupp
<a name="bkmk_forgot"> </a>

Använd PowerShell! Kolla in det här inlägget av Eyal Doron: [Hantera lösenord med PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
Här är en relaterad artikel: [Ange lösenorden för flera användarkonton](https://support.office.com/article/014fc912-bee1-461d-ad00-56b80428b907.aspx#bkmk_password).
  
Mer information finns i [PowerShell för Office 365-administratörer](https://support.office.com/article/40fdcbd4-c34f-42ab-8678-8b3751137ef1.aspx).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Tvinga fram ändring av lösenord för alla i företaget
<a name="bkmk_forgot"> </a>

Läs det här blogginlägget av Vasil Michev, Microsoft MVP: [Framtvinga ändring av lösenord för alla användare i Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="im-lost"></a>Det går inte!
<a name="bkmk_forgot"> </a>

Läs mer i den här artikeln: [Jag har glömt användarnamnet eller lösenordet för kontot som jag använder med Office.](https://support.office.com/article/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## <a name="related-articles"></a>Relaterade artiklar
<a name="bkmk_forgot"> </a>
  
[Låta användare återställa sina egna lösenord i Office 365](let-users-reset-passwords.md)

[Ange att en enskild användares lösenord aldrig ska förfalla](set-password-to-never-expire.md)

[Ange förfalloprincip för lösenord i organisationen](../manage/set-password-expiration-policy.md)

[Återställa en användare i Office 365](restore-user.md)

[Ta bort en tidigare anställd från Office 365](remove-former-employee.md)

[Utbildningsvideor för Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
