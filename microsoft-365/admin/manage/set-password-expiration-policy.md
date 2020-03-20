---
title: Ange förfalloprincip för lösenord i organisationen
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Lär dig hur du anger en förfalloprincip för lösenord i organisationen i administrationscentret för Microsoft 365. '
ms.openlocfilehash: 88953317bea2b96c04c291dd028a4e9131b9a83e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42811218"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Ange förfalloprincip för lösenord i organisationen

Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening.  

Om du är en användare har du inte behörighet att ange att ditt lösenord aldrig ska upphöra. Be den tekniska supporten på ditt företag eller din skola att göra stegen i denna artikel åt dig.

Som administratör kan du göra så att användarlösenord upphör efter ett visst antal dagar, eller ställa in så att lösenord aldrig upphör. 

> [!Tip]
> Standard är att lösenord är inställda på att upphöra efter 90 dagar. Aktuella undersökningar tyder starkt på att tvingande lösenordsändringar gör mer skada än nytta. Det får användarna att välja svagare lösenord, återanvända lösenord eller uppdatera gamla lösenord på ett sätt som gör det enkelt för hackare att gissa sig till dem. Om du ställer in lösenord att aldrig upphöra rekommenderar vi att du aktiverar [multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md).

Följ anvisningarna nedan om du vill ställa in så att användarlösenorden ska upphöra efter en viss tid.
> [!IMPORTANT]
> Endast [globala administratörer för Office 365](../add-users/about-admin-roles.md) kan utföra de här stegen.
  
1. I administrationscentret går du till **Inställningar** \> **Inställningar**.

2. Gå till sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Säkerhet och sekretess</a>.
 Om du inte är global administratör för Office 365 visas inte alternativet Säkerhet och sekretess.
  
3. Välj **Förfalloprincip för lösenordet**.
  
4. Om du inte vill att användarna ska behöva ändra lösenord markerar du kryssrutan bredvid **Ställ in så att användarlösenord upphör att gälla efter ett visst antal dagar**.
  
5. Ange hur ofta lösenord ska upphöra. Välj ett antal dagar mellan 14 och 730.
  
6. I den andra rutan anger du när användarna underrättas om att deras lösenord upphör att gälla och väljer sedan **Spara**. Du kan välja ett antal dagar mellan 1 och 30.
    
7. När användarens lösenord slutar gälla, visas ett meddelande om detta i det nedre högra hörnet på skärmen.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Viktiga saker du behöver veta om funktionen för lösenords giltighetstid

Här är några saker som kan vara bra att känna till om hur denna funktion fungerar från och med januari 2018:
  
- Personer som endast använder Outlook-appen tvingas inte återställa lösenordet för Office 365 förrän det slutar gälla i cachen. Det kan dröja flera dagar från det faktiska utgångsdatumet. Det finns ingen lösning på det här felet på administratörsnivå.
    
- Användarna får inget e-postmeddelande om att lösenordet slutar gälla om X dagar. Vill du ha den här funktionen? **[Rösta här!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**
    
## <a name="prevent-last-password-from-being-used-again"></a>Förhindra att det senaste lösenordet används igen

Om du vill förhindra återanvändning av gamla lösenord kan du göra det i Azure AD. Se [Ange förfalloprincip för lösenord i organisationen](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide).

Om en medarbetare använder en mobil enhet för att komma åt Office 365 kan du också rensa den för att säkerställa att lösenordet inte längre lagras och återanvänds därifrån. Mer information finns i [Rensa och blockera en tidigare anställds mobila enhet](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-office-365"></a>Synkronisera användares lösenords-hashar från lokal Active Directory till Azure AD (Office 365)

Den här artikeln handlar om att ange förfalloprincipen för användare som bara använder molnet (Azure AD). Den gäller inte för hybrididentitetsanvändare som använder synkronisering av lösenordshashar, direktautentisering och lokal federation som ADFS.
  
Information om hur du synkroniserar användarlösenordshashar från lokal AD till Azure AD finns i [Implementera synkronisering av lösenordshashar med Azure AD Connect-synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).
