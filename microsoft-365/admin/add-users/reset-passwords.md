---
title: Återställ lösenord
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
description: 'Läs om hur du återställer lösenord för en användare i Microsoft 365 för företag-prenumeration. '
ms.openlocfilehash: 0cd9bfe2b4f60ed0150e95f35d1f24994724ca60
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208204"
---
# <a name="reset-passwords"></a>Återställ lösenord

Titta på en kort video om hur du återställer användarlösenord.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="let-users-reset-their-own-passwords"></a>Låt användare återställa sina egna lösenord

Vi rekommenderar att du konfigurerar återställning av egna lösenord. På så vis behöver du inte manuellt återställa lösenord för användarna. Läs i så fall [Låt användare återställa sina egna lösenord i Office 365](let-users-reset-passwords.md).
  
## <a name="reset-a-business-password-for-someone-else"></a>Återställa ett företagslösenord för någon annan

De här stegen är endast avsedda för personer som använder en Microsoft 365 för affärsplan. För att kunna göra dem måste du logga in med ditt Microsoft 365-administratörskonto. [Vad är ett administratörskonto?](../admin-overview/admin-overview.md)

 
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
 
  
## <a name="reset-my-admin-password"></a>Återställa mitt administratörslösenord

Gör så här om du har glömt ditt lösenord men kan logga in på Microsoft 365 eftersom ditt lösenord till exempel sparas i webbläsaren: 
    
1. Välj ditt namn (ikon) i det övre högra hörnet > Personlig information **för mitt konto**  >  **Personal Info**. 
          
2. Under **Kontaktuppgifter**dubbelkollar du att din **alternativa e-postadress** är korrekt och att du har angett ett mobiltelefonnummer. Ändra dem annars nu. 
        
3. Logga ut: välj ditt namn i det övre högra hörnet (i bilden ovan, visad som **Diane**) \> **Logga ut**. 
        
4. Logga in igen: skriv ditt användarnamn \> **Nästa** \> och välj sedan Glömt **lösenord**. 
    
5. Följ anvisningarna i guiden för att återställa lösenordet. De alternativa kontaktuppgifterna används för att verifiera att du är rätt person som ska återställa lösenordet. 
    
Om du har glömt ditt lösenord och inte kan logga in: 
    
- Be en annan global administratör i företaget att återställa lösenordet åt dig.

- Kontrollera att du har angett alternativ kontaktinformation, inklusive ett mobiltelefonnummer. 
    
- Du kan också [kontakta Microsoft Support](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). 
    
## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Återställa alla företagslösenord för alla i organisationen samtidigt
<a name="bkmk_forgot"> </a>

Dessa anvisningar fungerar för verksamheter med dussintals användare. Om du har hundratals eller tusentals användare läser du nästa avsnitt om hur du återställer lösenord i grupp (max 40 användare åt gången).
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
    
2. Välj alternativet **bredvid Visa namn** om du vill välja alla i ditt företag. Avmarkera sedan dig själv. Du kan inte återställa ditt eget lösenord samtidigt som du återställer alla andras lösenord.
    
3. Välj **Återställ lösenord**. 

4. Följ instruktionerna på sidan **Återställ lösenord** och välj **Återställ**.  Om du har valt att automatiskt generera lösenorden visas de nya tillfälliga lösenorden.   
    
5. Ange en e-postadress där du kan få de tillfälliga lösenorden. Du måste meddela användarna vilka tillfälliga lösenord de är.
    

  
## <a name="reset-business-passwords-in-bulk"></a>Återställa företagslösenord i grupp
<a name="bkmk_forgot"> </a>

Använd PowerShell! Kolla in det här inlägget av Eyal Doron: [Hantera lösenord med PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
Här är en relaterad artikel: [Ange lösenorden för flera användarkonton](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).
  
Översiktsinformation finns i [PowerShell för Microsoft 365-administratörer](https://support.microsoft.com/en-us/office/powershell-for-office-365-administrators-40fdcbd4-c34f-42ab-8678-8b3751137ef1).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Tvinga fram ändring av lösenord för alla i företaget
<a name="bkmk_forgot"> </a>

Läs det här blogginlägget av Vasil Michev, Microsoft MVP: [Framtvinga ändring av lösenord för alla användare i Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="im-lost"></a>Det går inte!
<a name="bkmk_forgot"> </a>

Läs mer i den här artikeln: [Jag har glömt användarnamnet eller lösenordet för kontot som jag använder med Office.](https://support.office.com/article/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## <a name="related-articles"></a>Relaterade artiklar
<a name="bkmk_forgot"> </a>
  
[Låt användare återställa sina egna lösenord](let-users-reset-passwords.md)

[Ange att en enskild användares lösenord aldrig ska förfalla](set-password-to-never-expire.md)

[Ange förfalloprincip för lösenord i organisationen](../manage/set-password-expiration-policy.md)

[Återställa en användare](restore-user.md)

[Ta bort en tidigare anställd](remove-former-employee.md)

[Utbildningsvideor för Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
