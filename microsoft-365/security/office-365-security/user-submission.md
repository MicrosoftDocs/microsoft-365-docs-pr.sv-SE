---
title: Princip för användarinskick
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig hur de konfigurerar en postlåda för att samla in skräppost och nätfiske som rapporterats av användare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0ac1028ca3485f75518ccca298a1fd85a7bf40ec
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922396"
---
# <a name="user-submissions-policy"></a>Princip för användarinskick

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga. När användare skickar meddelanden med de olika rapportalternativen kan du använda postlådan för att snappa upp meddelanden (skicka endast till den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft). Den här funktionen fungerar med följande alternativ för meddelanderapportering:

- [Tillägget Rapportmeddelande](enable-the-report-message-add-in.md)

- [Tillägget Rapport om nätfiske](enable-the-report-phish-add-in.md)

- [Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (kallades tidigare Outlook Web App)

- [Inbyggd rapportering i Outlook för iOS och Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Om rapportering har [inaktiverats](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)i Outlook på webben, åsidosätts den inställningen och användare kan rapportera meddelanden i Outlook på webben igen om de har möjlighet att skicka rapporter här.

Du kan också konfigurera verktyg för meddelanderapportering från tredje part så att meddelanden vidarebefordras till den postlåda du anger.

Genom att leverera användarrapporterade meddelanden till en egen postlåda i stället för direkt till Microsoft kan dina administratörer selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av inskickad [administratör.](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>Anpassade postlådekrav

Använd följande artiklar för att konfigurera förutsättningarna som krävs så att användarrapporterade meddelanden går till din anpassade postlåda:

- Hoppa över skräppostfiltrering på den anpassade postlådan genom att skapa en regel för Exchange-e-postflöde för att ange konfidensnivån för skräppost. Se Använda EAC för att skapa en e-postflödesregel som anger [SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) för ett meddelande till **-1.**

- Inaktivera genomsökning av bifogade filer för skadlig programvara i den anpassade postlådan. Använd Konfigurera principer för säkra bifogade filer i Defender för [Office 365](set-up-atp-safe-attachments-policies.md) för att skapa en princip för säkra bifogade filer med inställningen Av för okänd skadlig programvara för **säkra bifogade filer.** 

- Inaktivera URL-genomsökning av meddelanden i den anpassade postlådan. Använd Konfigurera principer för säkra länkar i Defender för [Office 365](set-up-atp-safe-links-policies.md) och skapa en princip för säkra länkar med inställningen Av för Välj åtgärden för okända potentiellt skadliga **URL-adresser i meddelanden.** 

- Skapa en princip mot skadlig programvara för att inaktivera automatisk rensning av skadlig programvara utan timme. Se [Använda Säkerhets- & Efterlevnadscenter](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) för att skapa principer för skydd mot skadlig programvara och ange Automatisk rensning under **nolltimmar till** **Av.**

- Skapa en policy för skräppostfilter för att inaktivera ZAP (Zero-hour Auto Purge) för skräppost och nätfiske i den anpassade postlådan. Se [Använda Säkerhets- & efterlevnadscenter](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) för att skapa  principer för skydd mot skräppost och avmarkera kryssrutorna On för **Spam ZAP** och **Phish ZAP.**

- Inaktivera skräppostregeln i den anpassade postlådan. Använd [Konfigurera skräppostinställningar för Exchange Online-postlådor för](configure-junk-email-settings-on-exo-mailboxes.md) att inaktivera skräppostregeln. När EOP har inaktiverats kan det inte flytta meddelanden till  mappen Skräppost baserat på åtgärden skräppostfiltreringsåtgärden Flytta meddelandet till mappen Skräppost eller samlingen lista över säkra e-postmeddelanden i postlådan.

När du har kontrollerat att din postlåda uppfyller alla tillämpliga krav använder du säkerhets- och [&-efterlevnadscentret](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) för att konfigurera postlådan för användarinskick (i den här artikeln).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. För att gå direkt till **sidan användarinskickade** uppgifter använder du <https://protection.office.com/userSubmissionsReportMessage> .

- Du måste vara medlem i någon av följande rollgrupper för att kunna ändra konfigurationen för användarinskick:

  - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
  - **Organisationshantering** i [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)

- Du behöver åtkomst till Exchange Online PowerShell. Om kontot som du försöker använda inte har åtkomst till Exchange Online PowerShell får du ett felmeddelande som ser ut så här när du anger postlådan för inskickade inskickade meddelanden:

  > Ange en e-postadress i din domän

  Mer information om hur du aktiverar eller inaktiverar åtkomst till Exchange Online PowerShell finns i följande avsnitt:

  - [Aktivera eller inaktivera åtkomst till Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Klientåtkomstregler i Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Använd Säkerhets- & kompatibilitetscenter för att konfigurera postlådan för användarinskick

1. Gå till användarinskick & av  hothanteringspolicyn i \>  \> **Säkerhets- och efterlevnadscenter.**

2. På sidan **Användarinskickade** objekt som visas väljer du något av följande alternativ:

      1. Aktivera funktionen Rapportmeddelande för **Outlook (rekommenderas)**: Välj det här alternativet om du använder tillägget Rapportmeddelande, tillägget Rapport nätfiske eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:

    - **Anpassa bekräftelsemeddelandet för slutanvändaren:** Klicka på den här länken. I den **utfällo** för bekräftelsemeddelandet Anpassa som visas konfigurerar du följande inställningar:

        - **Före inskickning:**  I rutorna Rubrik och Bekräftelse anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med hjälp av tilläggen Rapportmeddelande eller Rapport nätfiske.  Du kan använda variabeln %type% för att inkludera inskickad typ (skräppost, inte skräppost, phish osv.).

            Som nämnts läggs följande text även till i meddelandet om du väljer ett alternativ som skickar de rapporterade meddelandena till Microsoft:

        > Ditt e-postmeddelande skickas som det är till Microsoft för analys. Vissa e-postmeddelanden kan innehålla personlig eller känslig information.

        - **Efter inskickat** meddelande : Klicka ![ på ikonen Expandera ](../../media/scc-expand-icon.png) . I **rutorna** Rubrik och Bekräftelse anger du den beskrivande text som användarna ser när de rapporterar ett meddelande med hjälp av tilläggen Rapportmeddelande eller Rapport nätfiske.  Du kan använda variabeln %type% för att inkludera inskickingstypen.

      Klicka på **Spara** när du är klar. Om du vill ta bort dessa värden **klickar du** på Återställ på **sidan Användarinskick.**
    
    - **Anpassa alternativ för rapportering av slutanvändare: Klicka** på den här länken. I den **utfällande alternativ för** Anpassa rapportering för slutanvändare som visas anger du den beskrivande texten för Rapporteringsalternativ för skräppost. 
Under **Alternativ som visar när meddelanden rapporteras** väljer du minst ett av följande alternativ:
        - **Fråga innan du skickar en rapport**
        - **Skicka rapporter automatiskt**
        -  **Skicka aldrig rapporter** \
   Klicka på **Spara** när du är klar.
              - **Skicka de rapporterade meddelandena** till: Gör något av följande val:
              - **Microsoft (rekommenderas)**: Användarens inskickade postlåda används inte (alla rapporterade meddelanden går till Microsoft).
              - **Både Microsoft och en anpassad postlåda:** I rutan som visas anger du e-postadressen till en befintlig Exchange Online-postlåda. Distributionsgrupper tillåts inte. Användarinskickade användare går till både Microsoft för analys och den anpassade postlådan som administratören eller säkerhetsteamet kan analysera.
              - **Endast anpassad postlåda:** I rutan som visas anger du e-postadressen till en befintlig Exchange Online-postlåda. Distributionsgrupper tillåts inte. Använd det här alternativet om du vill att meddelandet bara ska gå till en administratör eller säkerhetsgruppen för analys först. Meddelanden kommer inte att gå till Microsoft om inte administratören vidarebefordrar det själva.

        > [!NOTE]
        > U.S. Government organizations (GCC, GCC-H och DoD) kan bara konfigurera **anpassad postlåda.** De andra två alternativen är inaktiverade.

      När du är klar klickar du på **Bekräfta.**

      > [!CAUTION]
      > Om du har inaktiverat skräppostrapportering i [Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) på webben med postlådeprinciperna för Outlook på webben, men konfigurerar någon av de tidigare inställningarna för att rapportera meddelanden till Microsoft, kommer användarna att kunna rapportera meddelanden till Microsoft i Outlook på webben med hjälp av tillägget Rapportmeddelande eller tillägget Rapportfiske.


    1. **Inaktivera funktionen Rapportmeddelande** för Outlook: Välj det här alternativet om du använder rapporteringsverktyg från tredje part i stället för tillägget Rapportmeddelande, tillägget Rapport nätfiske eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:

          Välj **Använd den här anpassade postlådan för att ta emot användarrapporter**. I rutan som visas anger du e-postadressen till en befintlig postlåda som redan finns i Office 365. Det måste vara en befintlig postlåda i Exchange Online som kan ta emot e-post.

          När du är klar klickar du på **Bekräfta.**

## <a name="message-submission-format"></a>Format för meddelandeinskick

Meddelanden som skickas till anpassade postlådor måste följa ett särskilt e-postformat för inskickade inskickade meddelanden. Ämne (Kuvertrubrik) för inskickat material ska vara i följande format:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

där SafetyAPIAction är ett av följande heltalsvärden:

- 1: Skräppost
- 2: Inte skräppost
- 3: Nätfiske

I följande exempel:

- Meddelandet rapporteras som nätfiske.
- Id för nätverksmeddelande är 49871234-6dc6-43e8-abcd-08d797f20abe.
- Sender IP is 167.220.232.101.
- Från-adressen är test@contoso.com.
- Meddelandets ämnesrad är "testa nätfiske"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Meddelanden som inte följer det här formatet visas inte korrekt i portalen för inskickade meddelanden.