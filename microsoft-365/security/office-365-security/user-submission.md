---
title: Princip för användarinskickningar
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
description: Administratörer kan ta reda på hur de konfigurerar en postlåda för att samla in skräppost och nätfiske som rapporterats av användare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6022d2ca0e4357b422a20490fee7486affefa09c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287275"
---
# <a name="user-submissions-policy"></a>Princip för användarinskickningar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga. När användare skickar meddelanden med de olika rapportalternativen kan du använda den här postlådan för att snappa upp meddelanden (endast skicka till den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft). Den här funktionen fungerar med följande alternativ för meddelanderapportering:

- [Tillägget Rapportmeddelande](enable-the-report-message-add-in.md)

- [Tillägget Rapportfiske](enable-the-report-phish-add-in.md)

- [Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (hette tidigare Outlook Web App)

- [Inbyggd rapportering i Outlook för iOS och Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Om rapportering har [inaktiverats i Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)på webben åsidosätter aktiveringen av användarinsändning här den inställningen och gör att användare kan rapportera meddelanden i Outlook på webben igen.

Du kan också konfigurera verktyg för meddelanderapportering från tredje part så att meddelanden vidarebefordras till den postlåda som du anger.

Om du levererar användarrapporterade meddelanden till en egen postlåda i stället för direkt till Microsoft kan dina administratörer selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av inskickade [administratörer.](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>Anpassade postlådekrav

Använd följande artiklar för att konfigurera förutsättningarna som krävs så att användarrapporterade meddelanden går till din anpassade postlåda:

- Hoppa över skräppostfiltrering i den anpassade postlådan genom att skapa en regel för Exchange-e-postflöde som anger nivån för skräppostförtroende. Se Använda EAC för att skapa en e-postflödesregel som anger [SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) för ett meddelande till **-1.**

- Inaktivera genomsökning av bifogade filer för skadlig programvara i den anpassade postlådan. Använd Konfigurera principer för säkra bifogade filer i Defender för [Office 365](set-up-atp-safe-attachments-policies.md) för att skapa en princip för säkra bifogade filer med inställningen Av för okänt svar om säkra **bifogade filer.** 

- Inaktivera URL-genomsökning av meddelanden i den anpassade postlådan. Använd Konfigurera principer för säkra länkar i Defender för [Office 365](set-up-atp-safe-links-policies.md) och skapa en princip för säkra länkar med inställningen Av för Markera åtgärden för okända potentiellt skadliga **URL-adresser i meddelanden.** 

- Skapa en policy för skadlig programvara för att inaktivera Automatisk rensning för skadlig programvara utan timme. Se [Använda Säkerhets- & Center](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) för efterlevnad för att skapa principer för skydd mot skadlig programvara och ange Automatisk rensning under nolltimmar som **av.** 

- Skapa en policy för skräppostfilter om du vill inaktivera zap (Zero-hour Auto Purge) för skräppost och nätfiske i den anpassade postlådan. Se [Använda Säkerhets- & Efterlevnadscenter](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) för att skapa  principer för skydd mot skräppost och avmarkera kryssrutorna På för **Spam ZAP** och **Phish ZAP.**

- Inaktivera skräppostregeln i den anpassade postlådan. Använd [Konfigurera skräppostinställningar för Exchange Online-postlådor till](configure-junk-email-settings-on-exo-mailboxes.md) att inaktivera skräppostregeln. När eOP har inaktiverats kan eOP inte flytta meddelanden till  mappen Skräppost baserat på åtgärden för filtrering av skräppost Flytta meddelandet till mappen Skräppost eller samlingen lista över säkra e-postmeddelanden i postlådan.

När du har kontrollerat att din postlåda uppfyller alla tillämpliga krav kan du använda Säkerhets- och [&-efterlevnadscentret](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) för att konfigurera postlådan för användarinskickningar (i den här artikeln).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt **till sidan för användarinskickade** uppgifter använder du <https://protection.office.com/userSubmissionsReportMessage> .

- Om du vill ändra konfigurationen för användarinskickningar måste du vara medlem i någon av följande rollgrupper:

  - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
  - **Organisationshantering** i [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)

- Du behöver åtkomst till Exchange Online PowerShell. Om kontot som du försöker använda inte har åtkomst till Exchange Online PowerShell får du ett felmeddelande som ser ut så här när du anger postlådan för inskickade uppgifter:

  > Ange en e-postadress i din domän

  Mer information om hur du aktiverar eller inaktiverar åtkomst till Exchange Online PowerShell finns i följande avsnitt:

  - [Aktivera eller inaktivera åtkomst till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Klientåtkomstregler i Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Använd Säkerhets- & center för efterlevnad för att konfigurera postlådan för användarinskickning

1. Gå till användarinskick för & för **hothanteringspolicy** \>  \> **i Säkerhets- och efterlevnadscenter.**

2. Välj **något av följande** alternativ på sidan användarinskickade användare som visas:

   1. Aktivera funktionen Rapportmeddelande för **Outlook (rekommenderas)**: Välj det här alternativet om du använder tillägget Rapportmeddelande, tillägget Rapportfiske eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:

      - **Anpassa bekräftelsemeddelandet för slutanvändaren: Klicka** på den här länken. Konfigurera **följande inställningar i det** utfällfällo för att anpassa bekräftelsemeddelandet som visas:

      - **Före inskickning:**  I meddelanderutorna Rubrik och Bekräftelse anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med hjälp av tilläggen Rapportmeddelande eller Rapport nätfiske.  Du kan använda variabeln %type% för att inkludera inskickingstypen (skräppost, inte skräppost, phish osv.).

        Om du väljer ett alternativ som skickar de rapporterade meddelandena till Microsoft läggs följande text också till i meddelandet:

        > Ditt e-postmeddelande skickas som det är till Microsoft för analys. Vissa e-postmeddelanden kan innehålla personlig eller känslig information.

      - **Efter inskickning**: Klicka ![ på ikonen ](../../media/scc-expand-icon.png) Visa. I **meddelanderutorna** Rubrik och Bekräftelse anger du den beskrivande text som användarna ser när de rapporterar ett meddelande med hjälp av tilläggen Rapportmeddelande eller Rapport nätfiske.  Du kan använda variabeln %type% för att inkludera inskickingstypen.

      Klicka på **Spara** när du är klar. Om du vill ta bort dessa värden **klickar du** på Återställ igen på **sidan användarindata.**

      - **Skicka de rapporterade meddelandena till:** Gör något av följande val:

        - **Microsoft (rekommenderas)**: Postlådan för användarinskickade meddelanden används inte (alla rapporterade meddelanden skickas till Microsoft).

        - **Microsoft och en egen postlåda:** I rutan som visas anger du e-postadressen till en befintlig Exchange Online-postlåda. Distributionsgrupper är inte tillåtna. Användarinskickningar skickas till både Microsoft för analys och till den anpassade postlådan som administratören eller säkerhetsteamet kan analysera.

        - **Anpassad postlåda:** I rutan som visas anger du e-postadressen till en befintlig Exchange Online-postlåda. Distributionsgrupper är inte tillåtna. Använd det här alternativet om du vill att meddelandet endast ska gå till en administratör eller säkerhetsteamet för analys först. Meddelanden skickas inte till Microsoft om inte administratören vidarebefordrar dem själva.

        > [!NOTE]
        > Amerikanska statliga myndigheter (GCC, GCC-H och DoD) kan endast konfigurera **en anpassad postlåda.** De andra två alternativen är inaktiverade.

      Klicka på Bekräfta när du är **klar.**

      > [!CAUTION]
      > Om du har inaktiverat skräppostrapportering i [Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) på webben med postlådeprinciperna för Outlook på webben, men du konfigurerar någon av de tidigare inställningarna för att rapportera meddelanden till Microsoft, kan användarna rapportera meddelanden till Microsoft i Outlook på webben med hjälp av tillägget Rapportmeddelande eller Tillägget Rapport nätfiske.

   - Inaktivera funktionen Rapportmeddelande för **Outlook:** Välj det här alternativet om du använder rapporteringsverktyg från tredje part i stället för tillägget Rapportmeddelande, tillägget Rapport nätfiske eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:

      Välj **Använd den här anpassade postlådan för att ta emot användarrapporter.** I rutan som visas anger du e-postadressen till en befintlig postlåda som redan finns i Office 365. Det måste vara en befintlig postlåda i Exchange Online som kan ta emot e-post.

      Klicka på Bekräfta när du är **klar.**

## <a name="message-submission-format"></a>Format för meddelandeinskickning

Meddelanden som skickas till anpassade postlådor måste ha ett särskilt format för inskickade e-postmeddelanden. Ämne (kuvertrubrik) för den inskickade sändningen ska ha följande format:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

där SafetyAPIAction är ett av följande heltalsvärden:

- 1: Skräppost
- 2: Inte skräppost
- 3: Nätfiske

I följande exempel:

- Meddelandet rapporteras som nätfiske.
- Nätverksmeddelande-ID är 49871234-6dc6-43e8-abcd-08d797f20abe.
- Avsändar-IP är 167.220.232.101.
- Från-adressen är test@contoso.com.
- Meddelandets ämnesrad är "testa nätfiske inskickat"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Meddelanden som inte följer det här formatet visas inte korrekt i portalen för inskickade meddelanden.
