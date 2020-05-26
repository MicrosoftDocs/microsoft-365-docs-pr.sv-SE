---
title: Hantera meddelanden och filer i karantän som administratör
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
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att visa och hantera meddelanden i karantän för alla användare i Exchange Online Protection (EOP). Administratörer i organisationer med Office 365 Advanced Threat Protection (Office 365 ATP) kan också hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.openlocfilehash: 521268d291c73cc94e8be87f1f2896a17c623678
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352426"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Hantera meddelanden och filer i karantän som administratör i EOP

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden. Mer information finns i [EOP i karantän](quarantine-email-messages.md).

Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare. Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (kallas även transportregler). Administratörer kan också rapportera falska positiva identifieringar till Microsoft.

Administratörer i organisationer med Office 365 Advance Threat Protection (Office 365 ATP) kan också visa, hämta och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.

Du kan visa och hantera meddelanden i karantän i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter. Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste tilldelas behörigheter innan du kan hantera karantänen som administratör. Behörigheterna styrs av **karantänrollen** i Security & Compliance Center. Som standard tilldelas den här rollen till rollgrupperna **Organisationshantering** (Globala administratörer), **karantänadministratör**och **Säkerhetsadministratör** i säkerhets- & Compliance Center. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

- Meddelanden i karantän behålls under en standardperiod innan de tas bort automatiskt:

  - Meddelanden i karantän av policyer mot skräppost (skräppost, nätfiske och massmeddelande): 30 dagar. Detta är standard- och maxvärdet. Mer om du vill konfigurera det här värdet finns i [Konfigurera principer mot skräppost](configure-your-spam-filter-policies.md).

  - Meddelanden som innehåller skadlig kod: 15 dagar.

  När ett meddelande upphör att gälla från karantänen kan du inte återställa det.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Använda Security & Compliance Center för att hantera e-postmeddelanden i karantän

### <a name="view-quarantined-email"></a>Visa e-post i karantän

1. I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.

2. Kontrollera att **Visa i karantän** är inställt på standardvärdet **e-post**.

3. Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik. Klicka på **Ändra kolumner** för att visa högst sju kolumner. Standardvärdena är markerade med en asterisk (<sup>\*</sup>):

   - **Mottaget**<sup>\*</sup>

   - **Avsändare**<sup>\*</sup>

   - **Ämne**<sup>\*</sup>

   - **Orsak till karantän**<sup>\*</sup>

   - **Släppt?**<sup>\*</sup>

   - **Principtyp**<sup>\*</sup>

   - **Mottagare**

   - **Meddelande-ID**

   - **Principnamn**

   - **Storlek**

   - **Riktning**

   Klicka på **Spara** eller på **Ställ in på standard** när du är klar.

4. Om du vill filtrera resultaten klickar du på **Filter**. Följande filter är tillgängliga:

   - **Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:

     - **I dag**

     - **Kommande 2 dagarna**

     - **Kommande 7 dagarna**

     - **Anpassad**: Ange ett **Startdatum** och **Slutdatum**.

   - **Togs emot**: Ange ett **Startdatum** och **Slutdatum**.

   - **Orsak till karantän**:

     - **Princip**: Meddelandet matchade villkoren för en regel för e-postflöde (kallas även transportregel).

     - **Bulk** (Massutskick)

     - **Nätfiske**

     - **Malware**

     - **Skräppost**

     - **Högt förtroende Phish**

   - **E-postmottagare**: Alla användare eller endast meddelanden som skickas till dig. Slutanvändare kan bara hantera meddelanden i karantän som skickas till dem.

   Tryck på **Rensa** om du vill ta bort filtret. Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.

5. Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden. Jokertecken stöds inte. Du kan söka efter följande värden:

   - **Meddelande-ID**: Meddelandets globalt unika identifierare.

     Du använde till exempel [meddelandespårning](message-trace-scc.md) för att leta efter ett meddelande som skickades till en användare i organisationen och du bestämmer att meddelandet sattes i karantän i stället för levererat. Var noga med att inkludera det fullständiga meddelande-ID-värdet, som kan innehålla vinkelparenteser ( \< \> ). Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .

   - **Avsändarens e-postadress**: En enskild avsändarens e-postadress.

   - **Mottagarens e-postadress**: En enskild mottagares e-postadress.

   - **Ämne**: Använd meddelandets hela ämne. Sökningen är inte skiftlägeskänslig.

   När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.

När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).

#### <a name="export-message-results"></a>Exportera meddelanderesultat

1. Markera de meddelanden du är intresserad av och klicka på **Exportera resultat**.

2. Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.

3. När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.

#### <a name="view-quarantined-message-details"></a>Visa information om meddelanden i karantän

När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information**:

- **Meddelande-ID**: Meddelandets globalt unika identifierare.

- **Avsändarens adress**

- **Mottaget**: Datumet/tiden då meddelandet togs emot.

- **Ämne**

- **Karantänorsak**: Visar om ett meddelande har identifierats som **Skräppost,** **Bulk,** **Phish**, matchade en regel för e-postflöde (**transportregel**) eller har identifierats som innehållande **skadlig kod**.

- **Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.

- **Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.

- **Släppt till**: Alla e-postadresser som meddelandet har släppts till.

- **Släppt till**: Alla e-postadresser som meddelandet har släppts till.

### <a name="take-action-on-quarantined-email"></a>Vidta åtgärder för e-post i karantän

När du har valt ett meddelande har du flera alternativ för vad du kan göra med meddelandena i fönstret **Utfällbara informationsuppgifter:**

- **Utgivningsmeddelande:** I det utfällbara fönster som visas väljer du följande alternativ:

  - **Rapportera meddelanden till Microsoft för analys**: Detta är markerat som standard och rapporterar det felaktigt i karantän meddelandet till Microsoft som ett falskt positivt. Om meddelandet har satts i karantän som skräppost, bulk, nätfiske eller skadlig kod rapporteras meddelandet också till Microsoft Spam Analysis Team. Beroende på deras analys kan reglerna för skräppostfilter för hela tjänsten justeras så att meddelandet kan skickas igenom.

  - Välj något av följande alternativ:

    - **Släpp meddelanden till alla mottagare**

    - **Släpp meddelanden till specifika mottagare**

    - **Släpp meddelanden till andra**

  Klicka på **Släpp meddelandet** när du är klar.

  Anteckningar om att släppa meddelanden:

  - Du kan inte släppa ett meddelande till samma mottagare mer än en gång.

  - Endast mottagare som inte har tagit emot meddelandet visas i listan över potentiella mottagare.

- **Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text. Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften). Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):

- **Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:

  - **Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.
  
  - **Textvy**: Visar meddelandetexten som oformaterad text.

- **Ta bort från karantänen**: När du klickar på **Ja** i varningen som visas tas meddelandet omedelbart bort utan att skickas till de ursprungliga mottagarna.

- **Ladda ned meddelande**: Välj **Jag är medveten om riskerna om jag laddar ned meddelandet** i den utfällbara rutan som visas om du vill spara en lokal kopia av meddelandet i .eml-format.

- **Skicka meddelande**: I det utfällbara fönster som visas väljer du följande alternativ:

  - **Objekttyp**: **E-post** (standard), **URL**eller **Bifogad fil**.

  - **Inlämningsformat**: **Nätverksmeddelande-ID** (standard, med motsvarande värde i rutan **Nätverksmeddelande-ID)** eller **Arkiv** (bläddra till en lokal EML- eller MSG-fil). Observera att om du väljer **Arkiv** och sedan väljer **Nätverksmeddelande-ID**är det ursprungliga värdet borta.

  - **Mottagare**: Skriv vid lån en ursprunglig mottagare av meddelandet eller klicka på **Markera alla** för att identifiera alla mottagare. Du kan också klicka på **Markera alla** och sedan selektivt ta bort enskilda mottagare.

  - **Orsak till inlämning:** **Bör inte ha blockerats** (standard) eller **Bör ha blockerats**.

  När du är klar klickar du på **Skicka**.

Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Vidta åtgärder för flera e-postmeddelanden i karantän

När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:

- **Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.

- **Ta bort meddelanden**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort utan att skickas till de ursprungliga mottagarna.

Klicka på **Stäng** när du är klar.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Endast ATP: Använd Security & Compliance Center för att hantera filer i karantän

> [!NOTE]
> Procedurerna för filer i karantän i det här avsnittet är endast tillgängliga för ATP Plan 1- och Plan 2-prenumeranter.

I organisationer med ATP kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.

### <a name="view-quarantined-files"></a>Visa filer i karantän

1. I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.

2. Ändra **vy i karantän** till standardvärdefilerna . **files** Du kan sortera i ett fält genom att klicka på ett tillgängligt kolumnhuvud.

3. Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik. Klicka på **Ändra kolumner** för att visa högst sju kolumner. Standardkolumnerna är markerade med en asterisk ( <sup>\*</sup> ):

   - **Användaren**<sup>\*</sup>

   - **Plats**<sup>\*</sup>

   - **Filnamn**<sup>\*</sup>

   - **URL för filer**<sup>\*</sup>

   - **Filstorlek**<sup>\*</sup>

   - **Upphör**<sup>\*</sup>

   - **Släppt?**<sup>\*</sup>

   - **Detekteras av**

   - **Ändrad med tiden**

4. Om du vill filtrera resultaten klickar du på **Filter**. Följande filter är tillgängliga:

   - **Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:

     - **I dag**

     - **Kommande 2 dagarna**

     - **Kommande 7 dagarna**

     - Ett anpassat datum-/tidsintervall.

   - **Mottagen tid**

   - **Karantän orsak:** Det enda tillgängliga värdet är **Malware**.

När du har hittat en viss fil i karantän markerar du filen för att visa information om den och vidtar åtgärder för den (till exempel visa, släpp, hämta eller ta bort meddelandet).

#### <a name="export-file-results"></a>Exportera filresultat

1. Markera de filer du är intresserad av och klicka på **Exportera resultat**.

2. Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.

3. När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.

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

1. Logga in och [gå till Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)med hjälp av ett arbets- eller skolkonto som har globala administratörsbehörighet (eller lämpliga säkerhetsroller & Compliance Center) i organisationen .

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att visa och hantera meddelanden och filer i karantän

De cmdlets du använder för att visa och hantera meddelanden och filer i karantän är:

- [Ta bort karantänMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Exportera karantänMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Hämta karantänMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Observera att den här cmdleten endast är för meddelanden, inte skadliga programfiler från ATP för SharePoint Online, OneDrive för företag eller Teams.

- [Release-KarantänMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
