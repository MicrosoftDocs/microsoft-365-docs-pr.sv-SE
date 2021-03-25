---
title: Ta bort blockerade användare från portalen med åtkomstbegränsade användare
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Administratörer kan få information om hur de tar bort användare från portalen för åtkomstbegränsade användare i Office 365. Användare läggs till i portalen med åtkomstbegränsade användare för att de skickat utgående skräppost, oftast som ett resultat av kontointrång.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 32748d717762d7af727a1583226b6d47ee7697c6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207151"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a>Ta bort blockerade användare från portalen med åtkomstbegränsade användare i Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Om en användare överskrider någon av de utgående sändningsgränserna som anges i [tjänstbegränsningarna](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) eller i [utgående skräppostprinciper](configure-the-outbound-spam-policy.md), begränsas användaren från att skicka e-post, men de kan fortfarande ta emot e-post.

Användaren läggs till i portalen med åtkomstbegränsade användare i säkerhets- och efterlevnadscentret. När de försöker skicka e-post returneras meddelandet i en rapport om utebliven leverans (kallas även för ett NDR eller icke-leveranskvitto) med felkoden [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) och följande text:

> “Det gick inte att leverera meddelandet eftersom du inte godkändes som en giltig avsändare. Vanligtvis beror detta på att din e-postadress är misstänkt för att skicka skräppost och det är inte längre tillåten att skicka e-post.  Kontakta e-postadministratören om du behöver hjälp. Fjärrservern returnerade '550 5.1.8 åtkomst nekad, felaktig utgående avsändare”.

Administratörer kan ta bort användare från portalen med åtkomstbegränsade avsändare i säkerhets- och efterlevnadscentret eller i Exchange Online PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Använd <https://protection.office.com/restrictedusers> för att gå direkt till sidan med **åtkomstbegränsade användare**.

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill ta bort användare från Portalen för begränsade användare måste du vara medlem i rollgruppen **Organisationsledning** eller **Säkerhetsadministratörer**.
  - För skrivskyddad behörighet till Portalen för begränsade användare måste du vara medlem i rollgruppen **Global läsare** eller **Säkerhetsläsare**.

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  >
  > - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- En avsändare som överskrider gränsen för utgående e-post är ett bevis på ett komprometterat konto. Innan du tar bort användaren från portalen för åtkomstbegränsade användare måste du följa de nödvändiga stegen för att återfå kontroll över kontot. Mer information finns i [Svara på ett komprometterat e-postkonto i Office 365](responding-to-a-compromised-email-account.md).

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a>Använda Säkerhets- och efterlevnadscentret för att ta bort en användare från listan med begränsade användare

1. I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Begränsade användare**.

2. Leta rätt på och markera den användare som du vill avblockera. I kolumnen **Åtgärder** klickar du på **Avblockera**.

3. En utfällbar meny kommer att visa information om det konto vars sändning är begränsad. Vi rekommenderar att du går igenom rekommendationerna för att se till att du vidtar lämpliga åtgärder om kontot faktiskt är komprometterat. Välj **Nästa** när du är klar.

4. På nästa skärm finns rekommendationer för att förhindra framtida intrång. Att aktivera multifaktorautentisering (MFA) och ändra lösenord är ett bra skydd. Klicka **Avblockera användare** när du är klar.

5. Bekräfta ändringen genom att klicka på **Ja**.

   > [!NOTE]
   > Det kan ta upp till 24 timmar innan alla begränsningar tas bort från användaren.

## <a name="verify-the-alert-settings-for-restricted-users"></a>Verifiera aviseringsinställningarna för begränsade användare

Standardaviseringsprincipen med namnet **Användare med restriktioner för att skicka e-post** meddelar automatiskt administratörer när användare hindras från att skicka utgående e-post. Du kan kontrollera inställningarna och lägga till fler användare som ska meddelas. Gå till [Varningsregler i Säkerhets- och efterlevnadscentret](../../compliance/alert-policies.md) om du vill ha mer information om varningsprinciper.

> [!IMPORTANT]
> För att varningar ska fungera måste Granskningsloggsökning aktiveras. Du kan läsa mer i [Aktivera och inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).

1. Gå till **Aviseringar** \> **Aviseringsprinciper** i Säkerhets- och efterlevnadscentret.

2. Sök efter och välj principen **Användare som begränsas från att skicka e-postavisering**.

3. I den utfällbara meny som visas kan du verifiera eller konfigurera följande inställningar:

   - **Status**: verifiera att meddelandet är aktiverat ![Aktivera](../../media/scc-toggle-on.png).

   - **E-postmottagare**: Klicka på **Redigera** och verifiera eller konfigurera följande inställningar i den utfällbara menyn **Redigera mottagare** som visas:

     - **Skicka e-postmeddelanden**: kontrollera att kryssrutan är markerad (**På**).

     - **E-postmottagare**: standardvärdet är **TenantAdmins** (d.v.s. **Globala administratör** medlemmar). Klicka i ett tomt område i rutan om du vill lägga till fler mottagare. En lista med mottagare visas, och du kan börja skriva ett namn för att filtrera och välja en mottagare. Du kan ta bort en befintlig mottagare från rutan genom att klicka på ![Ta bort ikon](../../media/scc-remove-icon.png) bredvid namnet.

     - **Daglig aviseringsgräns**: standardvärdet är **Ingen gräns**, men du kan välja en gräns för max antal aviseringar per dag.

     Klicka på **Spara** när du är klar.

4. När du är tillbaka vid den utfällbara menyn **Användare som begränsats från att skicka e-post** klickar du på **Stäng**.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Använd Exchange Online PowerShell för att visa och ta bort användare från listan med åtkomstbegränsade användare

Om du vill visa en lista med användare som begränsas från att skicka e-post kör du följande kommando:

```powershell
Get-BlockedSenderAddress
```

Om du vill visa information om särskilda användare ersätter du \<emailaddress\> med deras e-postadress och kör följande kommando:

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

Se [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress) för detaljerad information om syntax och parametrar.

Om du vill ta bort användare från listan med åtkomstbegränsade användare ersätter du \<emailaddress\> med deras e-postadress och kör följande kommando:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Se [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress) för detaljerad information om syntax och parametrar.