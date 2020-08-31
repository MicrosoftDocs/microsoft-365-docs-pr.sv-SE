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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7a5d073b-7fae-4aa5-8f96-9ecd041aba9c
description: 'Lär dig hur du återställer lösen ordet för en användare i Microsoft 365 för företag-prenumeration. '
ms.openlocfilehash: 6159b62cb6c1e09cb86732cc27cc4c4c87328a42
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307295"
---
# <a name="reset-passwords"></a>Återställ lösenord

Titta på en kort video om att återställa användar lösen ord.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="let-users-reset-their-own-passwords"></a>Låt användare återställa sina egna lösenord

Vi rekommenderar att du konfigurerar återställning av egna lösenord. På så vis behöver du inte manuellt återställa lösenord för användarna. Läs i så fall [Låt användare återställa sina egna lösenord i Office 365](let-users-reset-passwords.md).
  
## <a name="reset-a-business-password-for-someone-else"></a>Återställa ett företags lösen ord för någon annan

De här anvisningarna gäller bara för personer som använder ett Microsoft 365 för företag-abonnemang. För att göra det måste du logga in med ditt Microsoft 365-administratörs konto. [Vad är ett administratörs konto?](../admin-overview/admin-overview.md)

 
::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

::: moniker-end

2. På sidan **aktiva användare** väljer du användaren och sedan **Återställ lösen ord**.
    
3. Följ instruktionerna på sidan **Återställ lösen ord** för att automatiskt skapa ett nytt lösen ord för användaren eller skapa ett för dem och välj sedan **Återställ**.  
    
4. Ange en e-postadress som användaren kan komma åt så att de får det nya lösen ordet och följ upp dem för att kontrol lera att de har fått dem.
 
  
## <a name="reset-my-admin-password"></a>Återställa administratörs lösen ordet

Följ de här anvisningarna om du har glömt lösen ordet men du kan logga in på Microsoft 365, till exempel att ditt lösen ord sparas i din webbläsare: 
    
1. Välj ditt namn (ikonen) i det övre högra hörnet **My Account**>  >  **personlig info**för mitt konto. 
          
2. Under **kontakt uppgifter**kontrollerar du att din **alternativa e-postadress** stämmer och att du har angett ett mobiltelefon nummer. Ändra dem annars nu. 
        
3. Logga ut: Välj ditt namn i det övre högra hörnet (i bilden ovan, visas som **Diane**) \> **Logga ut**. 
        
4. Logga nu in igen: Skriv ditt användar namn \> **Next** \> och välj sedan **glömt lösen ord**. 
    
5. Följ anvisningarna i guiden för att återställa lösenordet. De alternativa kontaktuppgifterna används för att verifiera att du är rätt person som ska återställa lösenordet. 
    
Om du har glömt ditt lösen ord och inte kan logga in: 
    
- Be en annan global administratör i företaget att återställa lösenordet åt dig.

- Se till att du har angett en alternativ kontakt information, till exempel ett mobiltelefon nummer. 
    
- Du kan också [kontakta Microsoft Support](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). 
    
## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Återställa alla företags lösen ord för alla i organisationen samtidigt
<a name="bkmk_forgot"> </a>

Dessa anvisningar fungerar för verksamheter med dussintals användare. Om du har hundratals eller tusentals användare, se nästa avsnitt om att återställa lösen ord i bulk (maximalt 40 användare åt gången).
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
    
2. Välj alternativet bredvid **Visa namn** för att välja alla i företaget. Avmarkera sedan dig själv. Du kan inte återställa ditt eget lösenord samtidigt som du återställer alla andras lösenord.
    
3. Välj **Återställ lösen ord**. 

4. Följ instruktionerna på sidan **Återställ lösen ord** och välj **Återställ**.  Om du valt att generera lösen orden automatiskt visas de nya tillfälliga lösen orden.   
    
5. Ange en e-postadress där du kan få de tillfälliga lösen orden. Du måste meddela användarna vilka deras tillfälliga lösen ord är.
    

  
## <a name="reset-business-passwords-in-bulk"></a>Återställ företags lösen ord i bulk
<a name="bkmk_forgot"> </a>

Använd PowerShell! Kolla in det här inlägget av Eyal Doron: [Hantera lösenord med PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
Här är en relaterad artikel: [Ange lösenorden för flera användarkonton](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).
  
Mer information finns i [PowerShell för Microsoft 365-administratörer](https://support.microsoft.com/office/40fdcbd4-c34f-42ab-8678-8b3751137ef1).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Tvinga fram ändring av lösenord för alla i företaget
<a name="bkmk_forgot"> </a>

Läs det här blogginlägget av Vasil Michev, Microsoft MVP: [Framtvinga ändring av lösenord för alla användare i Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="im-lost"></a>Det går inte!
<a name="bkmk_forgot"> </a>

Läs mer i den här artikeln: [Jag har glömt användarnamnet eller lösenordet för kontot som jag använder med Office.](https://support.microsoft.com/office/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## <a name="related-articles"></a>Relaterade artiklar
<a name="bkmk_forgot"> </a>
  
[Låt användare återställa sina egna lösenord](let-users-reset-passwords.md)

[Ange att en enskild användares lösenord aldrig ska förfalla](set-password-to-never-expire.md)

[Ange förfalloprincip för lösenord i organisationen](../manage/set-password-expiration-policy.md)

[Återställa en användare](restore-user.md)

[Ta bort en tidigare anställd](remove-former-employee.md)

[Utbildningsvideor för Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
