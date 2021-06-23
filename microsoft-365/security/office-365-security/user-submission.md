---
title: Användarrapporterade meddelandeinställningar
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
ms.openlocfilehash: f59548a1f36e067d8b649f7fe22149362d6fe9c6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083542"
---
# <a name="user-reported-message-settings"></a>Användarrapporterade meddelandeinställningar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365 organisationer med Exchange Online postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga. När användare rapporterar meddelanden med de olika rapportalternativen kan du använda den här postlådan för att snappa upp meddelanden (skicka endast till den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft). Den här funktionen fungerar med följande alternativ för meddelanderapportering:

- [Tillägget Rapportmeddelande](enable-the-report-message-add-in.md)
- [Tillägget Rapport om nätfiske](enable-the-report-phish-add-in.md)
- [Rapporteringsverktyg från tredje part](#third-party-reporting-tools)

Genom att leverera användarrapporterade meddelanden till en egen postlåda i stället för direkt till Microsoft kan dina administratörer selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av inskickad [administratör.](admin-submission.md) Dessa inställningar kallades tidigare användarinskickingsprincip.

  > [!NOTE]
  > Om rapportering har [inaktiverats i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), kommer aktivering av användarrapporter här att åsidosätta den inställningen och göra det möjligt för användare att rapportera meddelanden i Outlook på webben igen.

## <a name="custom-mailbox-prerequisites"></a>Anpassade postlådekrav

Använd följande artiklar för att konfigurera förutsättningarna som krävs så att användarrapporterade meddelanden går till din anpassade postlåda:

- Hoppa över skräppostfiltrering på den anpassade postlådan genom att skapa en regel för Exchange-e-postflöde för att ange konfidensnivån för skräppost. Se [Använda EAC för att skapa en](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) e-postflödesregel som anger SCL för ett meddelande om du vill ange att SCL ska **kringgå skräppostfiltrering.**

- [Skapa en princip Valv för](set-up-safe-attachments-policies.md) bifogade filer som innehåller den anpassade postlåda Valv har inaktiverat genomsökning av bifogade filer **(Valv okänd** svarsavsnitt för bifogade filer – okänd skadlig \> **kod**).

- [Skapa en princip Valv länkar](set-up-safe-links-policies.md) som innehåller den anpassade postlådan där skanningen av Valv-länkar är inaktiverad (Välj åtgärden för okända potentiellt skadliga URL:er i **meddelandeavsnittet** \> **Av**).

- [Skapa en](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) princip mot skadlig programvara som innehåller den anpassade postlådan där nolltimmars automatisk rensning (ZAP) för skadlig programvara är inaktiverat **(avsnittet** Skyddsinställningar Aktivera automatisk rensning utan timme för skadlig programvara har \>  inte valts).

- [Skapa en princip](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) mot skräppost som inkluderar den anpassade postlådan där ZAP för skräppost och ZAP för nätfiske är inaktiverade **(avsnittet** Automatisk rensning utan timme Aktiverad nolltimmars automatisk rensning \> **(ZAP) har** inte valts).

- Inaktivera skräppostregeln i den anpassade postlådan. Använd [Konfigurera skräppostinställningar på Exchange Online för att](configure-junk-email-settings-on-exo-mailboxes.md) inaktivera skräppostregeln. När den är inaktiverad kan EOP inte flytta meddelanden till mappen Skräppost  baserat på åtgärden för filtrering av skräppost Flytta meddelandet till mappen Skräppost eller samlingen lista över säkra e-postmeddelanden i postlådan.

När du har kontrollerat att din postlåda uppfyller alla tillämpliga krav kan du använda procedurerna i den här artikeln för att konfigurera postlådan för användarinskick.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com/>. Använd för att gå **direkt till sidan** Inskickade <https://security.microsoft.com/reportsubmission> material.

- Du måste vara medlem i någon av följande rollgrupper för att kunna ändra konfigurationen för användarinskick:

  - **Organisationshantering** eller **säkerhetsadministratör** i [behörigheter i Microsoft 365 Defender .](permissions-microsoft-365-security-center.md)
  - **Organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Du behöver åtkomst till Exchange Online PowerShell. Om kontot som du försöker använda inte har åtkomst till Exchange Online PowerShell får du ett felmeddelande som ser ut så här när du anger postlådan för inskickade inskickningar:

  > Ange en e-postadress i din domän

  Mer information om hur du aktiverar eller inaktiverar åtkomst till Exchange Online PowerShell finns i följande avsnitt:

  - [Aktivera eller inaktivera åtkomst till Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Klientåtkomstregler i Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Använd Microsoft 365 Defender-portalen för att konfigurera postlådan för användarinskick

1. I Microsoft 365 Defender går du till Principer för **& Principer** för hot andra avsnitt Användare har rapporterat \>  \>  \> **meddelandeinställningar** \> **Användarinskick.**

2. På sidan **Användarinskickade** meddelanden avgörs det du ser av om **knappinställningen för Microsoft-Outlook-rapportmeddelande** är **Av** eller **På:**

   - **Microsoft Outlook För att skicka ett rapportmeddelande** \> **På** ![ Aktivera: Välj det här alternativet om du använder tillägget Rapportmeddelande, tillägget Rapport nätfiske eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar ](../../media/scc-toggle-on.png) följande inställningar:
     - **Skicka de rapporterade meddelandena** till: Välj något av följande alternativ:
       - **Microsoft**: Användarens inskickade postlåda används inte (alla rapporterade meddelanden går till Microsoft).
       - **Microsofts och organisationens postlåda:** I rutan som visas anger du e-postadressen till en befintlig Exchange Online postlåda. Distributionsgrupper tillåts inte. Användarinskickade användare går till både Microsoft för analys och den anpassade postlådan som administratören eller säkerhetsteamet kan analysera.
       - **Organisationens postlåda: I** rutan som visas anger du e-postadressen till en befintlig e-Exchange Online postlåda. Distributionsgrupper tillåts inte. Använd det här alternativet om du vill att meddelandet bara ska gå till en administratör eller säkerhetsgruppen för analys först. Meddelanden kommer inte att gå till Microsoft om inte administratören vidarebefordrar det själva.

          > [!IMPORTANT]
          >
          > Amerikanska statliga myndigheter (GCC, GCC High och DoD) kan bara konfigurera **Min organisations postlåda.** De andra två alternativen är inaktiverade.
          >
          > Om organisationer är konfigurerade att endast skicka till en anpassad postlåda skickas inte rapporterade meddelanden för sökning och resultat i portalen för användarrapporter är alltid tomma.

       Oavsett vilket värde du valde för **Skicka de rapporterade meddelandena till** är följande inställningar tillgängliga:

       - **Låt användarna välja om de vill rapportera meddelandet till Microsoft**
       - **Välj rapportalternativ som är tillgängliga för användare:** Välj minst ett av följande alternativ:
         - **Fråga innan du skickar meddelandet**
         - **Rapportera alltid meddelandet**
         - **Rapportera aldrig meddelandet**

          > [!CAUTION]
          > Om du har inaktiverat skräppostrapportering i [Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) med postlådeprinciper i Outlook på webben, men om du har konfigurerat någon av de tidigare inställningarna för att rapportera meddelanden till Microsoft, kommer användarna att kunna rapportera meddelanden till Microsoft i Outlook på webben med hjälp av tilläggen Rapportmeddelande eller Rapport nätfiske.

     - **Avsnittet Användarrapportering**
       - **Före rapporteringsflik:**  I rutorna Rubrik och Meddelandetext anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med hjälp av tilläggen Rapportmeddelande eller Rapport nätfiske.  Du kan använda variabeln %type% för att inkludera inskickad typ (skräppost, inte skräppost, phish osv.).
       - **Efter rapporteringsfliken:**  Ange den beskrivande text som användarna ser när de rapporterar ett meddelande med hjälp av tilläggen Rapportmeddelande eller Rapport nätfiske i rutorna Rubrik och Bekräftelsemeddelande.  Du kan använda variabeln %type% för att inkludera inskickingstypen.

       Om du väljer ett alternativ som skickar de rapporterade meddelandena till Microsoft läggs följande text även till i meddelandet, så som visas på sidan:

          > Ditt e-postmeddelande skickas som det är till Microsoft för analys. Vissa e-postmeddelanden kan innehålla personlig eller känslig information.

   - **Microsoft Outlook För att skicka ett rapportmeddelande** \> **Av** ![ Inaktivera: Välj det här alternativet om du använder rapporteringsverktyg från tredje part i stället för tillägget Rapportmeddelande, tillägget Rapport nätfiske eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar ](../../media/scc-toggle-off.png) följande inställningar:
     - Välj **Använd den här anpassade postlådan för att ta emot användarrapporter**. I rutan som visas anger du e-postadressen till en befintlig e-Exchange Online som kan ta emot e-post.

   När du är klar klickar du på **Bekräfta.** Om du vill ta bort dessa värden klickar du på **Återställ**

## <a name="third-party-reporting-tools"></a>Rapporteringsverktyg från tredje part

Du kan konfigurera rapporteringsverktyg från tredje part så att rapporterade meddelanden skickas till den anpassade postlådan. Det gör du genom att ange **knappen Microsoft Outlook-rapportmeddelande**  till Av och ange Min organisations postlåda till en valfri Office 365 postlåda. 

Det enda kravet är att det ursprungliga meddelandet tas med som ett . EML eller . Bifogad MSG-fil (inte komprimerad) i meddelandet som skickas till den anpassade postlådan (vidarebefordra inte bara det ursprungliga meddelandet till den anpassade postlådan).

Formateringskraven för meddelanden beskrivs i nästa avsnitt. Formateringen är valfritt, men om det inte följer det bestämt formatet kommer rapporterna alltid att skickas som phish.

## <a name="message-submission-format"></a>Format för meddelandeinskick

För att identifiera de ursprungliga bifogade meddelandena korrekt måste meddelanden som skickas till den anpassade postlådan ha särskild formatering. Om meddelandena inte använder det här formatet identifieras alltid de ursprungliga bifogade meddelandena som nätfiskeinskick.

För att de ursprungliga bifogade meddelandena ska kunna identifieras korrekt måste meddelanden som skickas till den anpassade postlådan använda följande syntax för Ämne (Kuvertrubrik):

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

där SafetyAPIAction är ett av följande heltalsvärden:

- 1: Skräppost
- 2: Inte skräppost
- 3: Nätfiske

I det här exemplet används följande värden:

- Meddelandet rapporteras som nätfiske.
- Id för nätverksmeddelande är 49871234-6dc6-43e8-abcd-08d797f20abe.
- Sender IP is 167.220.232.101.
- Från-adressen är test@contoso.com.
- Meddelandets ämnesrad är "testa nätfiske"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Meddelanden som inte följer det här formatet visas inte korrekt i portalen för inskickade meddelanden.
