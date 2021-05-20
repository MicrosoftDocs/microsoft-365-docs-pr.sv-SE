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
description: Logga in med ditt Microsoft 365 för att återställa lösenord för användare i Microsoft 365 för företag-prenumeration.
ms.openlocfilehash: 8d4666eb70b1d5349f71c906f05510a8a54ded74
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571979"
---
# <a name="reset-passwords"></a>Återställ lösenord

I den här artikeln förklaras hur du återställer lösenord för dig själv och för dina användare när du har en Microsoft 365 för företag-prenumeration.

## <a name="before-you-begin"></a>Innan du börjar

Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening. Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen. [Vad är ett administratörskonto?](../../business-video/admin-center-overview.md).

Du måste vara global [administratör eller lösenordsadministratör för att](about-admin-roles.md) utföra de här stegen.

## <a name="watch-reset-a-business-password-for-a-user"></a>Titta: Återställa ett företagslösenord för en användare

Titta på en kort video om hur du återställer användarlösenord.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP]

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../../business-video/index.yml).
  
## <a name="steps-reset-a-business-password-for-a-user"></a>Steg: Återställa ett företagslösenord för en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Markera användaren **på** sidan Aktiva användare och välj sedan **Återställ lösenord.**

3. Följ instruktionerna på **sidan Återställ** lösenord om du vill generera ett nytt lösenord automatiskt för användaren eller skapa ett åt det och välj sedan **Återställ**.  

4. Ange en e-postadress som användaren kan komma åt så att han eller hon får det nya lösenordet och följ upp med dem för att vara säker på att de har fått det.

## <a name="let-users-reset-their-own-passwords"></a>Låt användare återställa sina egna lösenord

Vi rekommenderar att du konfigurerar återställning av egna lösenord. På så vis behöver du inte manuellt återställa lösenord för användarna. Läs i så fall [Låt användare återställa sina egna lösenord i Office 365](let-users-reset-passwords.md).

## <a name="reset-my-admin-password"></a>Återställa administratörslösenordet

Använd de här stegen om du har glömt ditt lösenord men kan logga in på Microsoft 365 eftersom lösenordet till exempel har sparats i webbläsaren:

1. Välj ditt namn (ikon) i det övre högra hörnet > **Personlig information för** Mitt  >  **konto.**

2. Kontrollera **att din** alternativa e-postadress är korrekt och att du har angett ett mobiltelefonnummer under Kontaktinformation.  Ändra dem annars nu.

3. Logga ut: välj ditt namn i det övre högra hörnet \> **Logga ut**.

4. Logga nu in igen: skriv ditt användarnamn \> **Nästa och** \> välj sedan Glömt **lösenord**.

5. Följ anvisningarna i guiden för att återställa lösenordet. De alternativa kontaktuppgifterna används för att verifiera att du är rätt person som ska återställa lösenordet.

Om du har glömt ditt lösenord och inte kan logga in:

- Be en annan global administratör i företaget att återställa lösenordet åt dig.

- Se till att du har angett alternativ kontaktinformation, bland annat ett mobiltelefonnummer.

- Du kan också [kontakta Microsoft Support](../../business-video/get-help-support.md).

## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Återställa alla företagslösenord för alla i organisationen samtidigt
<a name="bkmk_forgot"> </a>

Dessa anvisningar fungerar för verksamheter med dussintals användare. Om du har tusentals användare kan du gå till nästa avsnitt om hur du återställer flera lösenord samtidigt (högst 40 användare åt gången).
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Välj alternativet bredvid **Visningsnamn för** att välja alla i företaget. Avmarkera sedan dig själv. Du kan inte återställa ditt eget lösenord samtidigt som du återställer alla andras lösenord.

3. Välj **Återställ lösenord.** 

4. Följ instruktionerna på **sidan Återställ** lösenord och välj **Återställ**.  Om du valde att generera lösenorden automatiskt visas de nya tillfälliga lösenorden.

5. Ange en e-postadress där du kan få de tillfälliga lösenorden. Du måste meddela användarna om deras tillfälliga lösenord.
  
## <a name="reset-business-passwords-in-bulk"></a>Massåterställning av företagslösenord
<a name="bkmk_forgot"> </a>

Använd PowerShell! Kolla in det här inlägget av Eyal Doron: [Hantera lösenord med PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
<!-- Here's a related article: [Set the passwords for multiple user accounts](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). -->
  
Mer information finns i [Hantera Microsoft 365 med PowerShell.](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Tvinga fram ändring av lösenord för alla i företaget

Läs det här blogginlägget av Vasil Michev, Microsoft MVP: [Framtvinga ändring av lösenord för alla användare i Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="i-dont-have-a-microsoft-365-for-business-subscription"></a>Jag har ingen prenumeration på Microsoft 365 för företag

Läs mer i den här artikeln: [Jag har glömt användarnamnet eller lösenordet för kontot som jag använder med Office.](https://support.microsoft.com/office/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## <a name="related-content"></a>Relaterat innehåll
  
[Låt användare återställa sina egna lösenord](../add-users/let-users-reset-passwords.md) (artikel)

[Återställ lösenord](../add-users/reset-passwords.md) (artikel)

[Ange att en enskild användares lösenord aldrig ska förfalla](set-password-to-never-expire.md)(artikel)

[Ange förfalloprincip för lösenord för din organisation](../manage/set-password-expiration-policy.md) (artikel)

[Microsoft 365 om utbildningsvideor för företag](../../business-video/index.yml) (länksida)