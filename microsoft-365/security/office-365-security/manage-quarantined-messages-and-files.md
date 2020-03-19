---
title: Hantera meddelanden och filer i karantän som administratör i Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare. Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (transportregler).
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857084"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a>Hantera meddelanden och filer i karantän som administratör i Office 365

Karantänen innehåller potentiellt farliga eller oönskade meddelanden i Office 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor. Mer information finns [i Karantän i Office 365](quarantine-email-messages.md).

Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare. Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (kallas även transportregler). Administratörer kan också rapportera falska positiva identifieringar till Microsoft.

Administratörer i organisationer med Office 365 Advance Threat Protection (ATP) kan också visa, hämta och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.

Du kan visa och hantera meddelanden i karantän i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Office 365-kunder; Exchange Online Protection PowerShell för fristående EOP-kunder).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- & Compliance Center för Office 365 går du till <https://protection.office.com>. Öppna sidan Karantän direkt går <https://protection.office.com/quarantine>du till .

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du ansluter till Exchange Online Protection PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste tilldelas behörigheter innan du kan hantera karantänen som administratör. Behörigheterna styrs av **karantänrollen** i Security & Compliance Center. Som standard tilldelas den här rollen till rollgrupperna **Organisationshantering** (Globala administratörer), **karantänadministratör**och **Säkerhetsadministratör** i säkerhets- & Compliance Center. Mer information finns [i Behörigheter i Säkerhets- & Compliance Center för Office 365.](permissions-in-the-security-and-compliance-center.md)

- Meddelanden i karantän behålls under en standardperiod innan de tas bort automatiskt:

  - Meddelanden i karantän av policyer mot skräppost (skräppost, nätfiske och massmeddelande): 30 dagar. Detta är standard- och maxvärdet. Mer om du vill konfigurera det här värdet finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).

  - Meddelanden i karantän av regler för e-postflöde (regelåtgärden är **Leverera meddelandet till den värdbaserade karantänen):** 30 dagar. Du kan inte ändra det här värdet.

  - Meddelanden som innehåller skadlig kod: 15 dagar.

  När ett meddelande upphör att gälla från karantänen kan du inte återställa det.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Använda Security & Compliance Center för att hantera e-postmeddelanden i karantän

### <a name="view-quarantined-email"></a>Visa e-post i karantän

1. Gå till Karantän för granskning av **hothantering** \> **Review** \> **Quarantine**i säkerhets- och efterlevnadscenter.

2. Kontrollera att **Visa i karantän** är inställt på standardvärdet **e-post**.

3. Du kan sortera resultaten genom att klicka på ett tillgängligt kolumnhuvud. Klicka på **Ändra kolumner** om du vill visa högst sju kolumner. Standardvärdena markeras med en<sup>\*</sup>asterisk ( ):

   - **Fått**<sup>\*</sup>

   - **Avsändaren**<sup>\*</sup>

   - **Ämne**<sup>\*</sup>

   - **Karantän orsak**<sup>\*</sup>

   - **Släppt?**<sup>\*</sup>

   - **Typ av princip**<sup>\*</sup>

   - **Upphör**<sup>\*</sup>

   - **Mottagaren**

   - **Meddelande-ID**

   - **Principnamn**

   - **Storlek**

   - **Riktning**

   När du är klar klickar du på **Spara**eller klickar på **Ange till standard**.

4. Om du vill filtrera resultatet klickar du på **Filtrera**. De tillgängliga filtren är:

   - **Förfaller tid:** Filtrera meddelanden efter när de upphör att gälla från karantän:

     - **Idag**

     - **Nästa 2 dagar**

     - **Nästa 7 dagar**

     - **Anpassad:** Ange ett **startdatum** och **slutdatum**.

   - **Mottagen tid**: Ange ett **startdatum** och **slutdatum**.

   - **Karantän orsak:**

     - **Princip**: Meddelandet matchade villkoren för en regel för e-postflöde (kallas även transportregel).

     - **Bulk**

     - **Phish**

     - **Malware**

     - **Spam**

     - **Högt förtroende Phish**

   - **E-postmottagare**: Alla användare eller endast meddelanden som skickas till dig. Slutanvändare kan bara hantera meddelanden i karantän som skickas till dem.

   Om du vill rensa filtret klickar du på **Rensa**. Om du vill dölja det utfällbara filtret klickar du på **Filter** igen.

5. Använd **Sortera resultat efter** **(knappen Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden. Jokertecken stöds inte. Du kan söka efter följande värden:

   - **Meddelande-ID:** Den globalt unika identifieraren för meddelandet.

        Du använde till exempel [meddelandespårning](message-trace-scc.md) för att leta efter ett meddelande som skickades till en användare i organisationen och du bestämmer att meddelandet sattes i karantän i stället för levererat. Var noga med att inkludera det fullständiga meddelande-ID-värdet, som kan innehålla vinkelparenteser (\<\>). Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Avsändare e-postadress:** En enda avsändare e-postadress.

   - **Mottagarens e-postadress**: En enskild mottagares e-postadress.

   - **Ämne**: Använd hela ämnet för meddelandet. Sökningen är inte skiftlägeskänslig.

   När du har angett sökvillkoren ![klickar](../media/scc-quarantine-refresh.png) du på Uppdatera knappen **Uppdatera** för att filtrera resultaten.

När du har hittat ett visst meddelande i karantän markerar du meddelandet för att visa information om det och vidtar åtgärder för det (till exempel visa, släpp, hämta eller ta bort meddelandet).

#### <a name="export-message-results"></a>Exportera meddelanderesultat

1. Markera de meddelanden du är intresserad av och klicka på **Exportera resultat**.

2. Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att hålla webbläsarfönstret öppet.

3. När exporten är klar kan du namnge och välja hämtningsplats för CSV-filen.

#### <a name="view-quarantined-message-details"></a>Visa meddelandeinformation i karantän

När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i fönstret **Utfällbara information:**

- **Meddelande-ID:** Den globalt unika identifieraren för meddelandet.

- **Avsändaradress**

- **Mottaget**: Datum/tid då meddelandet togs emot.

- **Ämne**

- **Karantänorsak**: Visar om ett meddelande har identifierats som **Skräppost,** **Bulk,** **Phish**, matchade en regel för e-postflöde (**transportregel**) eller har identifierats som innehållande **skadlig kod**.

- **Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelande** eller **Visa meddelandehuvud** för att se hela listan över mottagare.

- **Upphör att gälla**: Det datum/den tid då meddelandet tas bort automatiskt och permanent från karantänen.

- **Släppt till**: Alla e-postadresser (om sådana finns) som meddelandet har släppts till.

- **Ännu inte släppt till**: Alla e-postadresser (om några) som meddelandet ännu inte har släppts.

### <a name="take-action-on-quarantined-email"></a>Vidta åtgärder på e-post i karantän

När du har valt ett meddelande har du flera alternativ för vad du kan göra med meddelandena i fönstret **Utfällbara informationsuppgifter:**

- **Utgivningsmeddelande:** I det utfällbara fönster som visas väljer du följande alternativ:

  - **Rapportera meddelanden till Microsoft för analys**: Detta är markerat som standard och rapporterar det felaktigt i karantän meddelandet till Microsoft som ett falskt positivt. Om meddelandet har satts i karantän som skräppost, bulk, nätfiske eller skadlig kod rapporteras meddelandet också till Microsoft Spam Analysis Team. Beroende på deras analys kan reglerna för skräppostfilter för hela tjänsten justeras så att meddelandet kan skickas igenom.

  - Välj något av följande alternativ:

    - **Släpp meddelanden till alla mottagare**

    - **Släpp meddelanden till specifika mottagare**

    - **Släpp meddelanden till andra**

  När du är klar klickar du på **Släpp meddelanden**.

  Anteckningar om att släppa meddelanden:

  - Du kan inte släppa ett meddelande till samma mottagare mer än en gång.

  - Endast mottagare som inte har tagit emot meddelandet visas i listan över potentiella mottagare.

- **Visa meddelanderubrik:** Välj den här länken om du vill visa meddelanderubrikens text. Om du vill analysera rubrikfälten och värdena på djupet kopierar du meddelandehuvudtexten till Urklipp och väljer sedan **Microsoft Message Header Analyzer** för att gå till Remote Connectivity Analyzer (högerklicka och välj **Öppna på en ny flik** om du inte vill lämna Office 365 för att slutföra den här uppgiften). Klistra in meddelandehuvudet på sidan i avsnittet Meddelandehuvudanalysator och välj **Analysera rubriker:**

- **Förhandsgranskningsmeddelande:** I det utfällbara fönster som visas väljer du något av följande alternativ:

  - **Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.
  
  - **Textvy**: Visar meddelandetexten i oformaterad text.

- **Ta bort från karantänen**: När du klickar på **Ja** i varningen som visas tas meddelandet omedelbart bort utan att skickas till de ursprungliga mottagarna.

- **Hämta meddelande**: I det utfällbara fönstret som visas väljer **du Jag förstår riskerna med** att hämta det här meddelandet för att spara en lokal kopia av meddelandet i .eml-format.

- **Skicka meddelande**: I det utfällbara fönster som visas väljer du följande alternativ:

  - **Objekttyp**: **E-post** (standard), **URL**eller **Bifogad fil**.

  - **Inlämningsformat**: **Nätverksmeddelande-ID** (standard, med motsvarande värde i rutan **Nätverksmeddelande-ID)** eller **Arkiv** (bläddra till en lokal EML- eller MSG-fil). Observera att om du väljer **Arkiv** och sedan väljer **Nätverksmeddelande-ID**är det ursprungliga värdet borta.

  - **Mottagare**: Skriv vid lån en ursprunglig mottagare av meddelandet eller klicka på **Markera alla** för att identifiera alla mottagare. Du kan också klicka på **Markera alla** och sedan selektivt ta bort enskilda mottagare.

  - **Orsak till inlämning:** **Bör inte ha blockerats** (standard) eller **Bör ha blockerats**.

  När du är klar klickar du på **Skicka**.

Om du inte släpper eller tar bort meddelandet tas det bort när standardlagringsperioden för karantän upphör att gälla.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Vidta åtgärder för flera e-postmeddelanden i karantän

När du väljer flera meddelanden i karantän i listan (upp till 100) visas det utfällbara fönstret **Massåtgärder** där du kan vidta följande åtgärder:

- **Utgivningsmeddelanden**: Alternativen är desamma som när du släpper ett enda meddelande, förutom att du inte kan välja **Utgivningsmeddelanden till specifika mottagare.** Du kan bara välja **Utgivningsmeddelande till alla mottagare** eller **Utgivningsmeddelanden till andra.**

- **Ta bort meddelanden**: När du klickar på **Ja** i varningen som visas tas meddelandet omedelbart bort utan att skickas till de ursprungliga mottagarna.

När du är klar klickar du på **Stäng.**

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Endast ATP: Använd Security & Compliance Center för att hantera filer i karantän

> [!NOTE]
> Procedurerna för filer i karantän i det här avsnittet är endast tillgängliga för ATP Plan 1- och Plan 2-prenumeranter.

I organisationer med ATP kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.

### <a name="view-quarantined-files"></a>Visa filer i karantän

1. Gå till Karantän för granskning av **hothantering** \> **Review** \> **Quarantine**i säkerhets- och efterlevnadscenter.

2. Ändra **vy i karantän** till standardvärdefilerna . **files** Du kan sortera i ett fält genom att klicka på ett tillgängligt kolumnhuvud.

3. Du kan sortera resultaten genom att klicka på ett tillgängligt kolumnhuvud. Klicka på **Ändra kolumner** om du vill visa högst sju kolumner. Standardkolumnerna är markerade med<sup>\*</sup>en asterisk ( ):

   - **Användaren**<sup>\*</sup>

   - **Plats**<sup>\*</sup>

   - **Filnamn**<sup>\*</sup>

   - **URL för filer**<sup>\*</sup>

   - **Filstorlek**<sup>\*</sup>

   - **Upphör**<sup>\*</sup>

   - **Släppt?**<sup>\*</sup>

   - **Detekteras av**

   - **Ändrad med tiden**

4. Om du vill filtrera resultatet klickar du på **Filtrera**. De tillgängliga filtren är:

   - **Förfaller tid:** Filtrera meddelanden efter när de upphör att gälla från karantän:

     - **Idag**

     - **Nästa 2 dagar**

     - **Nästa 7 dagar**

     - Ett anpassat datum-/tidsintervall.

   - **Mottagen tid**

   - **Karantän orsak:** Det enda tillgängliga värdet är **Malware**.

När du har hittat en viss fil i karantän markerar du filen för att visa information om den och vidtar åtgärder för den (till exempel visa, släpp, hämta eller ta bort meddelandet).

#### <a name="export-file-results"></a>Exportera filresultat

1. Markera de filer du är intresserad av och klicka på **Exportera resultat**.

2. Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att hålla webbläsarfönstret öppet.

3. När exporten är klar kan du namnge och välja hämtningsplats för CSV-filen.

#### <a name="view-quarantined-file-details"></a>Visa filinformation i karantän

När du markerar en fil i listan visas följande filinformation i fönstret **Utfällbara information:**

- **Filnamn**

- **Fil-URL**: URL som definierar platsen för filen (till exempel i SharePoint Online).

- **Skadligt innehåll har upptäckts på** Datum/tid då filen sattes i karantän.

- **Upphör att gälla**: Det datum då filen tas bort från karantänen.

- **Detekteras av:** ATP (Advanced Threat Protection) eller Microsofts anti-malware-motor.

- **Släppt?**

- **Namn på skadlig kod**

- **Dokument-ID:** En unik identifierare för dokumentet.

- **Filstorlek:** I kilobyte (KB).

- **Organisation** Organisationens unika ID.

- **Senast ändrad**

- **Ändrad av**: Användaren som senast ändrade filen.

- **Värde för säker hashalgoritm 256-bitars (SHA-256):** Du kan använda det här hash-värdet för att identifiera filen i andra ryktesbutiker eller på andra platser i din miljö.

### <a name="take-action-on-quarantined-files"></a>Vidta åtgärder för filer i karantän

När du väljer en fil i listan kan du vidta följande åtgärder för filen i fönstret **Utfällbara informationsuppgifter:**

- **Släpp filer**: Markera (standard) eller avmarkera **rapportfiler till Microsoft för analys**och klicka sedan på Släpp **filer**.

- **Ladda ner fil**

- **Ta bort fil från karantän**

Om du inte släpper eller tar bort filerna tas de bort när standardlagringsperioden för karantän upphör att gälla.

#### <a name="actions-on-multiple-quarantined-files"></a>Åtgärder på filer i flera karantäner

När du väljer flera filer i karantän i listan (upp till 100) visas det utfällbara fönstret **Massåtgärder** där du kan vidta följande åtgärder:

- **Släpp filer**

- **Ta bort filer**: När du klickar på **Ja** i varningen som visas tas filerna omedelbart bort.

När du är klar klickar du på **Stäng.**

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Använda Exchange Online PowerShell eller fristående Exchange Online Protection PowerShell för att visa och hantera meddelanden och filer i karantän

De cmdlets du använder för att visa och hantera meddelanden och filer i karantän är:

- [Ta bort karantänMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [Exportera karantänMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [Hämta karantänMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Observera att den här cmdleten endast är för meddelanden, inte skadliga programfiler från ATP för SharePoint Online, OneDrive för företag eller Teams.

- [Release-KarantänMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
