---
title: Ange en post låda för användar överföringar av skräp post och nät fiske meddelanden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa hur du konfigurerar en post låda för att samla in skräp post och nätfiske som rapporteras av användare.
ms.openlocfilehash: 458938105d03cb82dfa4e9a7824f8b026fddec5d
ms.sourcegitcommit: 89b2ad0793c68415f178b8792a9757b9448345a6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/28/2020
ms.locfileid: "47294759"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Ange en post låda för användar överföringar av skräp post och nät fiske meddelanden i Exchange Online

I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en post låda som tar emot meddelanden som användare rapporterar som skadlig eller inte skadlig. När användarna skickar meddelanden med olika rapporterings alternativ kan du använda den här post lådan för att avlyssna meddelanden (endast skicka till den anpassade post lådan) eller ta emot kopior av meddelanden (skicka till den anpassade post lådan och Microsoft). Den här funktionen fungerar med följande alternativ för meddelande rapportering:

- [Tillägget rapport](enable-the-report-message-add-in.md)

- [Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare Outlook Web App)

- [Inbyggd rapportering i Outlook för iOS och Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Om rapportering har [inaktiverats i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), åsidosätter du den inställningen och gör att användare kan rapportera meddelanden i Outlook på webben igen.

Du kan också konfigurera meddelande rapporterings verktyg från tredje part så att meddelanden vidarebefordras till den post låda som du anger.

Om du levererar rapporter till en egen post låda i stället för direkt till Microsoft kan administratören selektivt och manuellt rapportera meddelanden till Microsoft via [Administratörs överföring](admin-submission.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **användar överföring** kan du använda <https://protection.office.com/userSubmissionsReportMessage> .

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:

  - Om du vill ändra konfigurationen för användar inlämningar måste du vara medlem i någon av följande roll grupper:

    - **[Exchange-administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** i Azure AD **och organisations hantering** eller **säkerhets administratör** och i [Center för säkerhets &](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Om du vill ha skrivskyddad åtkomst till användar innehåll måste du vara medlem i båda följande roll grupper:

    - **Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
    - **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Konfigurera e-postpost lådan för användare via säkerhets & efterlevnad

1. Gå till användar tillägget för **Threat Management** policy i säkerhets & efterlevnad \> **Policy** \> **User submissions**.

2. På sidan **användar inlägg** som visas väljer du något av följande alternativ:

   a. **Aktivera funktionen rapport meddelande för Outlook (rekommenderas)**: Välj det här alternativet om du använder tillägget rapportera meddelande eller inbyggd rapportering i Outlook på webben och konfigurera sedan följande inställningar:

      - **Anpassa slutanvändarens bekräftelse meddelande**: Klicka på den här länken. Konfigurera följande inställningar i den utfällda **bekräftelse meddelandet** som visas:

      - **Före inlämning**: Ange den beskrivande text som användarna ser innan de rapporterar ett meddelande med hjälp av tillägget rapport meddelande i rutorna **rubrik** och **bekräftelse meddelande** . Du kan använda variabeln% Type% för att inkludera sändnings typen (skräp, inte skräp post, Phish, osv.).

        Om du väljer ett alternativ som skickar det rapporterade meddelandet till Microsoft läggs även följande text till i meddelandet:

        > Din e-post skickas till Microsoft för analys. Vissa e-postmeddelanden kan innehålla personlig eller känslig information.

      - **Efter sändning**: Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) . Ange den **Title** beskrivande text som användarna ser efter att de har rapporterat ett meddelande med hjälp av rapport tillägget. **Confirmation message** Du kan använda variabel% Type% för att inkludera överförings typen.

      Klicka på **Spara** när du är klar. Om du vill rensa de här värdena klickar du på **Återställ** bakåt på sidan **användar inlägg** .

      - **Skicka rapporterade meddelanden till**: gör något av följande:

        - **Microsoft (rekommenderas)**: post lådan användar meddelanden används inte (alla rapporterade meddelanden skickas till Microsoft).

        - **Microsoft och en anpassad post låda**: i rutan som visas anger du e-postadressen för en befintlig Exchange Online-postlåda. Distributions grupper är inte tillåtet. Användar inlämningar kommer att gå till både Microsoft för analys och den anpassade post lådan för din administratör eller säkerhets åtgärd för att analysera.

        - **Anpassad post låda**: i rutan som visas anger du e-postadressen för en befintlig Exchange Online-postlåda. Distributions grupper är inte tillåtet. Använd det här alternativet om du vill att meddelandet endast ska skickas till en administratör eller säkerhets åtgärds teamet för analys. Meddelanden går inte till Microsoft såvida inte administratören vidarebefordrar det själva.

        > [!NOTE]
        > Amerikanska statliga organisationer (GCC, GCC-H och DoD) kan endast konfigurera **anpassade post lådor**. De två andra alternativen är inaktiverade. 

      När du är klar klickar du på **Bekräfta**.

      > [!CAUTION]
      > Om du har [inaktiverat skräp post rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) med hjälp av Outlook på principer för Internet-postlådor, men du konfigurerar något av de föregående inställningarna för att rapportera meddelanden till Microsoft, kan användarna rapportera meddelanden till Microsoft i Outlook på webben med hjälp av rapport tillägget.

   - **Inaktivera funktionen rapport meddelande för Outlook**: Välj det här alternativet om du använder rapporterings verktyg från tredje part i stället för rapport tillägget eller den inbyggda rapporteringen i Outlook på webben och konfigurera sedan följande inställningar:

      Välj **Använd den här anpassade post lådan för att ta emot inlämning av användare**. I rutan som visas anger du e-postadressen för en befintlig post låda som redan finns i Office 365. Detta måste vara en befintlig post låda i Exchange Online som kan ta emot e-post.

      När du är klar klickar du på **Bekräfta**.

## <a name="message-submission-format"></a>Meddelande överförings format

Meddelanden som skickas till anpassade post lådor måste följa ett visst e-postformat. Ämnets rubrik (Envelope) för sändningen ska vara i det här formatet:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

var SafetyAPIAction är ett av följande heltals värden:

- 1: skräp post
- 2: NotJunk
- 3: Phish

I följande exempel:

- Meddelandet rapporteras som Phish.
- Nätverks meddelandets ID är 49871234-6dc6-43e8-ABCD-08d797f20abe.
- Avsändarens IP är 167.220.232.101.
- Från-adressen är test@contoso.com.
- Meddelandets ämnesrad är "testa Phish-sändning"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

Meddelanden som inte följer det här formatet kommer inte att visas korrekt i portalen med inlämning.
