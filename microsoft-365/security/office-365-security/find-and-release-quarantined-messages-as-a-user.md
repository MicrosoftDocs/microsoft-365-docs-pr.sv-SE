---
title: Hitta och släppa meddelanden i karantän som användare
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Användare kan läsa mer om hur de visar och hanterar meddelanden i karantän i Exchange Online Protection (EOP) som borde ha levererats till dem.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 68656d21b8c10157ebae5d030e56293ba1ce07f7
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539125"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>Hitta och släppa meddelanden i karantän som användare i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden. Mer information finns i [Karantän i EOP](quarantine-email-messages.md).

Som användare kan du visa, släppa och ta bort meddelanden i karantän där du är mottagare och där meddelandet har satts i karantän som skräppost eller massutskick. Från och med april 2020 kan du visa eller ta bort phishing-meddelanden i karantän (ej nätfiske med hög konfidens) där du är mottagare. Du visar och hanterar dina meddelanden i karantän i Säkerhets- och efterlevnadscenter eller (om en administratör har konfigurerat detta) i [slutanvändarens skräppostmeddelanden](use-spam-notifications-to-release-and-report-quarantined-messages.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter. Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.

- Administratörer kan konfigurera hur länge meddelanden behålls i karantän innan de tas bort permanent (principer för skräppostskydd). Meddelanden som har upphört att gälla och tas bort från karantänen går inte att återställa. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

- Administratörer kan även [aktivera skräppostaviseringar för slutanvändare](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) i principer för skräppostskydd. Användare kan släppa skräppost i karantän direkt från dessa aviseringar. Användare kan granska phishing-meddelanden i karantän (inte phishing-meddelanden med hög förtroende) direkt från dessa meddelanden. Mer information finns i [Skräppostaviseringar för slutanvändare i EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

- Meddelanden som sattes i karantän för phishing, malware eller e-postflödesregler (även kända som transportregler) är bara tillgängliga för administratörer och är inte synliga för användare. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).

- Du kan bara släppa ett meddelande och rapportera det som en falsk positiv identifiering (inte skräppost) en gång.

## <a name="view-your-quarantined-messages"></a>Visa meddelanden i karantän

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Granska** \> **Karantän**.

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
     - **Nätfiske**

   - **Principtyp**: filtrera meddelanden efter principtyp:
     - **Princip för skydd mot nätfiske**
     - **Filterprincip för värdbaserat innehåll** (Skräppostprincip)

   Tryck på **Rensa** om du vill ta bort filtret. Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.

4. Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden. Jokertecken stöds inte. Du kan söka efter följande värden:

   - **Meddelande-ID**: Meddelandets globalt unika identifierare. Om du väljer ett meddelande i listan visas värdet för **Meddelande-ID** i den utfällbara rutan **Information** som visas. Administratörer kan använda [meddelandespårning](message-trace-scc.md) för att söka efter meddelanden med motsvarande värden för meddelande-ID.

   - **Avsändarens e-postadress**: En enskild avsändarens e-postadress.

   - **Principnamn**: använd meddelandets hela principnamn. Sökningen är inte skiftlägeskänslig.

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

- **Orsak till karantän**: Visar om ett meddelande har identifierats som **Skräppost**, **Bulk** (massutskick) eller **Nätfiske**.

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

- **Ta bort från karantän**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort.

- **Spärra avsändare**: Lägg till avsändaren i listan Spärrade avsändare i din postlåda. Mer information finns i [Spärra e-postavsändare](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

Lägg till avsändaren i listan Spärrade avsändare i din postlåda. Mer information finns i [Spärra e-postavsändare](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

Klicka på **Stäng** när du är klar.

Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Vidta åtgärder för flera e-postmeddelanden i karantän

När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:

- **Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.

- **Ta bort meddelanden**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort utan att skickas till de ursprungliga mottagarna.

Klicka på **Stäng** när du är klar.
