---
title: Ta bort blockerade användare från portalen med begränsade användare
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
description: Administratörer kan få information om hur de tar bort användare från sidan för begränsade användare i Microsoft 365 Defender-portalen. Användare läggs till i portalen med begränsade användare för att de har skickat skräppost, oftast som ett resultat av kontointrång.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082858"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a>Ta bort blockerade användare från portalen med begränsade användare i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Om en användare överskrider någon av de utgående sändningsgränserna som anges i [tjänstbegränsningarna](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) eller i [utgående skräppostprinciper](configure-the-outbound-spam-policy.md), begränsas användaren från att skicka e-post, men de kan fortfarande ta emot e-post.

Användaren läggs till på sidan **Begränsade användare** i Microsoft 365 Defender-portalen. När de försöker skicka e-post returneras meddelandet i en rapport om utebliven leverans (kallas även för ett NDR eller icke-leveranskvitto) med felkoden [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) och följande text:

> “Det gick inte att leverera meddelandet eftersom du inte godkändes som en giltig avsändare. Vanligtvis beror detta på att din e-postadress är misstänkt för att skicka skräppost och det är inte längre tillåten att skicka e-post.  Kontakta e-postadministratören om du behöver hjälp. Fjärrservern returnerade '550 5.1.8 åtkomst nekad, felaktig utgående avsändare”.

Administratörer kan ta bort användare från sidan för begränsade användare i Microsoft 365 Defender eller Exchange Online PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>. Om du vill gå direkt till sidan med **Begränsade användare** använder du <https://security.microsoft.com/restrictedusers>.

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill ta bort användare från portalen med begränsade användare måste du vara medlem i en av rollgrupperna **Organisationsledning** eller **Säkerhetsadministratör**.
  - För skrivskyddad åtkomst till portalen med begränsade användare måste du vara medlem i en av rollgrupperna **Global läsare** eller **Säkerhetsläsare**.

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  >
  > - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- En avsändare som överskrider gränsen för utgående e-post är ett bevis på ett komprometterat konto. Innan du tar bort användaren från portalen med begränsade användare måste du följa de nödvändiga stegen för att återfå kontrollen över deras konto. Mer information finns i [Åtgärda ett komprometterat e-postkonto i Office 365](responding-to-a-compromised-email-account.md).

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a>Använd Microsoft 365 Defender-portalen för att ta bort en användare från listan med begränsade användare

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** > **Granska** > **Begränsade användare**.

2. På sidan **Begränsade användare** letar du upp och väljer den användare som du vill avblockera genom att klicka på användaren.

3. Klicka på åtgärden **Avblockera** som visas.

4. I den utfällbara menyn **Avblockera användare** som visas kan du läsa information om det begränsade kontot. Du bör gå igenom rekommendationerna för att se till att du vidtar rätt åtgärder om kontot har komprometterats.

   Klicka på **Nästa** när du är klar.

5. På nästa skärm finns rekommendationer för att förhindra framtida intrång. Att aktivera multifaktorautentisering (MFA) och återställa lösenordet är ett bra skydd.

   Klicka på **Skicka in** när du är klar.

6. Bekräfta ändringen genom att klicka på **Ja**.

   > [!NOTE]
   > Det kan ta upp till 24 timmar innan alla begränsningar tas bort från användaren.

## <a name="verify-the-alert-settings-for-restricted-users"></a>Verifiera aviseringsinställningarna för begränsade användare

Standardaviseringsprincipen med namnet **Användare med restriktioner för att skicka e-post** meddelar automatiskt administratörer när användare hindras från att skicka utgående e-post. Du kan kontrollera inställningarna och lägga till fler användare som ska meddelas. Mer information om aviseringsprinciper finns i [Principer för aviseringar i Microsoft 365](../../compliance/alert-policies.md).

> [!IMPORTANT]
> För att varningar ska fungera måste Granskningsloggsökning aktiveras. Du kan läsa mer i [Aktivera och inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Principer och regler** \> **Varningsprincip**.

2. På sidan **Varningsprincip** letar du upp och väljer varningen med namnet **Användare som inte kan skicka e-post**. Du kan sortera principerna efter namn eller använda **Sökrutan** för att hitta principen.

3. I den utfällbara menyn **Användare som inte kan skicka e-post** som visas kontrollerar eller konfigurerar du följande inställningar:
   - **Status**: verifiera att meddelandet är aktiverat ![Aktivera](../../media/scc-toggle-on.png).
   - **E-postmottagare**: Klicka på **Redigera** och verifiera eller konfigurera följande inställningar i den utfällbara menyn **Redigera mottagare** som visas:
     - **Skicka e-postmeddelanden**: Kontrollera att kryssrutan är markerad (**På**).
     - **E-postmottagare**: standardvärdet är **TenantAdmins** (d.v.s. **Globala administratör** medlemmar). Klicka i ett tomt område i rutan om du vill lägga till fler mottagare. En lista med mottagare visas, och du kan börja skriva ett namn för att filtrera och välja en mottagare. Du kan ta bort en befintlig mottagare från rutan genom att klicka på ![Ta bort ikon](../../media/m365-cc-sc-remove-selection-icon.png) bredvid namnet.
     - **Daglig aviseringsgräns**: standardvärdet är **Ingen gräns**, men du kan välja en gräns för max antal aviseringar per dag.

     Klicka på **Spara** när du är klar.

4. När du är tillbaka vid den utfällbara menyn **Användare som begränsats från att skicka e-post** klickar du på **Stäng**.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Använd Exchange Online PowerShell för att visa och ta bort användare från listan med begränsade användare

Om du vill visa en lista med användare som begränsas från att skicka e-post kör du följande kommando:

```powershell
Get-BlockedSenderAddress
```

Om du vill visa information om särskilda användare ersätter du \<emailaddress\> med deras e-postadress och kör följande kommando:

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

Se [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress) för detaljerad information om syntax och parametrar.

Om du vill ta bort användare från listan med begränsade användare ersätter du \<emailaddress\> med deras e-postadress och kör följande kommando:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Se [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress) för detaljerad information om syntax och parametrar.
