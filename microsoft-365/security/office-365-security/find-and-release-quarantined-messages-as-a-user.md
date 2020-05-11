---
title: Hitta och släppa meddelanden i karantän som användare
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du kan visa och hantera meddelanden i karantän i Säkerhets- och efterlevnadscenter för Microsoft 365.
ms.openlocfilehash: ff6cb3dbf9a0a2010bf792115c53265689873090
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173386"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a>Hitta och släppa meddelanden i karantän som användare

Karantänen lagrar potentiellt farliga eller oönskade meddelanden i Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor. Mer information finns i [Karantän i Office 365](quarantine-email-messages.md).

Som användare kan du visa, släppa och ta bort meddelanden i karantän där du är mottagare och där meddelandet har satts i karantän som skräppost eller massutskick. Från och med april 2020 kan du visa eller ta bort phishing-meddelanden i karantän (ej nätfiske med hög konfidens) där du är mottagare. Du visar och hanterar dina meddelanden i karantän i Säkerhets- och efterlevnadscenter eller (om en administratör har konfigurerat detta) i [slutanvändarens skräppostmeddelanden](use-spam-notifications-to-release-and-report-quarantined-messages.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter. Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.

- Administratörer kan konfigurera hur länge meddelanden behålls i karantän innan de tas bort permanent (principer för skräppostskydd). Meddelanden som har upphört att gälla och tas bort från karantänen går inte att återställa. Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

- Administratörer kan även [aktivera skräppostaviseringar för slutanvändare](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) i principer för skräppostskydd. Användare kan släppa skräppostmeddelanden i karantän men inte nätfiskemeddelanden i karantän direkt från dessa aviseringar. Mer information finns i artikeln om [skräppostaviseringar för slutanvändare i Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).

- Meddelanden som har satts i karantän för nätfiske via e-post med hög konfidens, skadlig kod eller via e-postflödesregler (kallas även transportregler) är endast tillgängliga för administratörer. Nätfiskemeddelanden kan granskas av användare men bara ges ut av administratörer. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).

- Du kan bara släppa ett meddelande och rapportera det som en falsk positiv identifiering (inte skräppost) en gång.

## <a name="view-your-quarantined-messages"></a>Visa meddelanden i karantän

1. I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.

2. Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik. Klicka på **Ändra kolumner** för att visa högst sju kolumner. Standardvärdena är markerade med en asterisk (<sup>\*</sup>):

   - **Mottaget**<sup>\*</sup>

   - **Avsändare**<sup>\*</sup>

   - **Ämne**<sup>\*</sup>

   - **Orsak till karantän**<sup>\*</sup>

   - **Släppt?**<sup>\*</sup>

   - **Principtyp**<sup>\*</sup>

   - **Upphör**<sup>\*</sup>

   - **Mottagare**

   - **Meddelande-ID**

   - **Principnamn**

   - **Storlek**

   - **Riktning**

   Klicka på **Spara** eller på **Ställ in på standard** när du är klar.

3. Om du vill filtrera resultaten klickar du på **Filter**. Följande filter är tillgängliga:

   - **Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:

     - **I dag**

     - **Kommande 2 dagarna**

     - **Kommande 7 dagarna**

     - **Anpassad**: Ange ett **Startdatum** och **Slutdatum**.

   - **Togs emot**: Ange ett **Startdatum** och **Slutdatum**.

   - **Orsak till karantän**:

     - **Bulk** (Massutskick)

     - **Skräppost**

     - **Nätfiske** (från och med april 2020)

   Tryck på **Rensa** om du vill ta bort filtret. Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.

4. Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden. Jokertecken stöds inte. Du kan söka efter följande värden:

   - **Meddelande-ID**: Meddelandets globalt unika identifierare. Om du väljer ett meddelande i listan visas värdet för **Meddelande-ID** i den utfällbara rutan **Information** som visas. Administratörer kan använda [meddelandespårning](message-trace-scc.md) för att söka efter meddelanden med motsvarande värden för meddelande-ID.

   - **Avsändarens e-postadress**: En enskild avsändarens e-postadress.

   - **Mottagarens e-postadress**: En enskild mottagares e-postadress.

   - **Ämne**: Använd meddelandets hela ämne. Sökningen är inte skiftlägeskänslig.

   När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.

När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).

### <a name="export-message-results"></a>Exportera meddelanderesultat

1. Markera de meddelanden du är intresserad av och klicka på **Exportera resultat**.

2. Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.

3. När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.

### <a name="view-quarantined-message-details"></a>Visa information om meddelanden i karantän

När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information**:

- **Meddelande-ID**: Meddelandets globalt unika identifierare.

- **Avsändarens adress**

- **Mottaget**: Datumet/tiden då meddelandet togs emot.

- **Ämne**

- **Orsak till karantän**: Visar om ett meddelande har identifierats som **Skräppost**, **Bulk** (massutskick) eller (från och med april 2020) **Nätfiske**.

- **Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.

- **Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.

- **Släppt till**: Alla e-postadresser som meddelandet har släppts till.

- **Släppt till**: Alla e-postadresser som meddelandet har släppts till.

### <a name="take-action-on-quarantined-email"></a>Vidta åtgärder för e-post i karantän

När du har valt ett meddelande finns det alternativ för vad du kan göra med meddelanden i den utfällbara rutan **Information**:

- **Släpp meddelandet**: Välj om du vill **Rapportera meddelanden till Microsoft för analys** i den utfällbara rutan. Det här alternativet är markerat som standard och rapporterar meddelandet som felaktigt har satts i karantän till Microsoft som en falsk positiv identifiering.

  Klicka på **Släpp meddelandet** när du är klar.

- **Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text. Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften). Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):

- **Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:

  - **Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.
  
  - **Textvy**: Visar meddelandetexten som oformaterad text.

- **Ladda ned meddelande**: Välj **Jag är medveten om riskerna om jag laddar ned meddelandet** i den utfällbara rutan som visas om du vill spara en lokal kopia av meddelandet i .eml-format.

- **Ta bort från karantän**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort.

Klicka på **Stäng** när du är klar.

Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Vidta åtgärder för flera e-postmeddelanden i karantän

När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:

- **Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.

- **Ta bort meddelanden**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort utan att skickas till de ursprungliga mottagarna.

Klicka på **Stäng** när du är klar.
