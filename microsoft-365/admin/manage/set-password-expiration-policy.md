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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Lär dig hur en administratör kan ange en förfalloprincip för lösenord för ditt företag, din skola eller en ideell förening i administrationscentret för Microsoft 365.
ms.openlocfilehash: fdd219e4fc99e2388acb5b19eacb2fc470041f79
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286735"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Ange förfalloprincip för lösenord i organisationen

## <a name="before-you-begin"></a>Innan du börjar

Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening. Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen. [Vad är ett administratörskonto?](../../business-video/admin-center-overview.md).

Som administratör kan du göra så att användarlösenord upphör efter ett visst antal dagar eller ange att lösenord aldrig ska upphöra att gälla. Som standard är lösenord inställda på att aldrig upphöra att gälla för din organisation.

Aktuella undersökningar tyder starkt på att tvingande lösenordsändringar gör mer skada än nytta. Det får användarna att välja svagare lösenord, återanvända lösenord eller uppdatera gamla lösenord på ett sätt som gör det enkelt för hackare att gissa sig till dem. Vi rekommenderar att du [multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md). Mer information om lösenordsprincip finns i [Rekommendationer om lösenordsprinciper](../misc/password-policy-recommendations.md).

Du måste vara [global administratör](../add-users/about-admin-roles.md) för att utföra de här stegen.

Om du är en användare har du inte behörighet att ange att ditt lösenord aldrig ska upphöra. Be den tekniska supporten på ditt företag eller din skola att göra det åt dig.

## <a name="set-password-expiration-policy"></a>Ange förfalloprincip för lösenordet

Följ anvisningarna nedan om du vill ställa in så att användarlösenorden ska upphöra efter en viss tid.

1. I administrationscentret för går du till fliken **inställningar** \> **organisationsinställningar**.

2. Gå till sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Säkerhet och sekretess</a>.
 Om du inte är global administratör visas inte alternativet Säkerhet och sekretess.
  
3. Välj **Förfalloprincip för lösenordet**.
  
4. Om du inte vill att användarna ska behöva ändra lösenord avmarkerar du rutan bredvid **Ställ in så att användarlösenord upphör att gälla efter ett visst antal dagar**.
  
5. Ange hur ofta lösenord ska upphöra att gälla. Välj ett antal dagar mellan 14 och 730.
  
6. I den andra rutan skriver du när användarna får ett meddelande om att deras lösenord upphör att gälla och väljer sedan **Spara**. Välj ett antal dagar mellan 1 och 30.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Viktiga saker du behöver veta om funktionen för lösenords giltighetstid
  
Personer som endast använder Outlook-appen tvingas inte återställa lösenordet för Microsoft 365 förrän det slutar gälla i cachen. Det kan dröja flera dagar från det faktiska utgångsdatumet. Det finns ingen lösning på det här felet på administratörsnivå.

## <a name="prevent-last-password-from-being-used-again"></a>Förhindra att det senaste lösenordet används igen

Om du inte vill att användarna ska kunna återanvända gamla lösenord kan du aktivera lösenordshistorik i lokala Active Directory (AD). Se [Skapa en anpassad lösenordspolicy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).

Det går inte att använda det senaste lösenordet igen när användaren byter lösenord i Microsoft Azure Active Directory. Lösenordsprincipen tillämpas på alla användarkonton som skapas och hanteras direkt i Microsoft Azure Active Directory. Du kan inte ändra den här lösenordsprincipen. Se [Lösenordsprinciper för Microsoft Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>Synkronisera användares lösenords-hashar från lokal Active Directory till Azure AD (Microsoft 365)

Den här artikeln handlar om att ange förfalloprincipen för användare som bara använder molnet (Azure AD). Den gäller inte för hybrididentitetsanvändare som använder synkronisering av lösenords-hashar, direktautentisering och lokal federation som ADFS.
  
Information om hur du synkroniserar användarlösenordshashar från lokal AD till Azure AD finns i [Implementera synkronisering av lösenordshashar med Azure AD Connect-synkronisering](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Lösenordsprinciper och kontobegränsningar i Azure Active Directory

Du kan konfigurera fler lösenordsprinciper och begränsningar i Azure Active Directory. Gå till [Lösenordsprinciper och kontobegränsningar i Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) för mer information.

## <a name="update-password-policy"></a>Uppdatera lösenordspolicy

Den ange-MsolPasswordPolicy cmdlet uppdaterar lösenordsprincipen för en specifik domän eller klientorganisation. Två inställningar krävs; den första är att ange hur lång tid ett lösenord förblir giltigt innan det måste ändras och det andra är att ange antalet dagar innan lösenordets utgångsdatum som kommer att trigga när användare kommer att få sitt första meddelande om att deras lösenord snart kommer att löpa ut.

Information om hur du uppdaterar lösenordspolicyn för en specifik domän eller hyresgäst finns i [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy).

## <a name="related-content"></a>Relaterat innehåll

[Låt användare återställa sina egna lösenord](../add-users/let-users-reset-passwords.md) (artikel)\

[Återställ lösenord](../add-users/reset-passwords.md) (artikel)
