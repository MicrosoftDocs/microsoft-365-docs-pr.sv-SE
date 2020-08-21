---
title: Hantera meddelanden och filer i karantän som administratör
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Administratörer kan lära sig att visa och hantera meddelanden i karantän för alla användare i Exchange Online Protection (EOP). Administratörer i organisationer med Office 365 Avancerat skydd (Office 365 ATP) kan även hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.openlocfilehash: 5da67f15a933694c1aef059ff18945122e3ee2e8
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827069"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Hantera meddelanden och filer i karantän som administratör i EOP

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden. Mer information finns i [e-postmeddelanden i karantän i EOP](quarantine-email-messages.md).

Administratörer kan visa, frigöra och ta bort alla typer av meddelanden i karantän för alla användare. Endast administratörer kan hantera meddelanden som satts i karantän som skadlig program vara, högsäker nät fiske eller resultat av regler för e-postflöden (kallas även transport regler). Administratörer kan också rapportera falsk identifiering till Microsoft.

Administratörer i organisationer med Office 365 Avancerat skydd (Office 365 ATP) kan även Visa, ladda ned och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.

Du visar och hanterar meddelanden i karantän i säkerhets & efterföljandekrav eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter. Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste tilldelas behörigheter innan du kan hantera karantänen som administratör. Behörigheterna styrs av **karantän** rollen i säkerhets & Compliance Center. Som standard tilldelas den här rollen **organisations hantering** (globala administratörer), **karantän administratören**och **säkerhets administratörs** rollerna för säkerhets &. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

- Meddelanden i karantän bevaras under en standard tids period innan de tas bort automatiskt:

  - Meddelanden i karantän med principer för skräp post (spam, nätfiske och Mass utskick): 30 dagar. Det här är standardvärdet och Max värdet. Information om hur du konfigurerar det här värdet finns i [Konfigurera principer för skräp post](configure-your-spam-filter-policies.md).

  - Meddelanden som innehåller skadlig kod: 15 dagar.

  När ett meddelande utgår från karantän kan du inte återställa det.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Hantera e-postmeddelanden med hjälp av säkerhets &

### <a name="view-quarantined-email"></a>Visa e-post i karantän

1. I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.

2. Kontrol lera att **Visa karantän** är inställt på standardvärdet för **e-post**.

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

     - **Princip**: meddelandet överensstämde med villkoren i en regel för e-postflöde (kallas även för transport regel).

     - **Bulk** (Massutskick)

     - **Nätfiske**

     - **Program**

     - **Skräppost**

     - **Hög exakthet Phish**

   - **E-postmottagare**: alla användare eller bara meddelanden som skickas till dig. Slutanvändare kan bara hantera skickade meddelanden till dem.

   Tryck på **Rensa** om du vill ta bort filtret. Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.

5. Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden. Jokertecken stöds inte. Du kan söka efter följande värden:

   - **Meddelande-ID**: Meddelandets globalt unika identifierare.

     Du använde exempelvis [meddelande spårning](message-trace-scc.md) för att leta efter ett meddelande som skickades till en användare i din organisation, och du fastställer att meddelandet satts i stället för att levereras. Se till att du inkluderar fullständigt meddelande-ID, som kan innehålla vinkelparenteser ( \<\> ). Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .

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

- **Karantän orsak**: visar om ett meddelande har identifierats som **skräp post**, **bulk**, **Phish**, matchade en e-postregel (**Transport regel**) eller som innehåller **skadlig program vara**.

- **Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.

- **Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.

- **Släppt till**: Alla e-postadresser som meddelandet har släppts till.

- **Släppt till**: Alla e-postadresser som meddelandet har släppts till.

### <a name="take-action-on-quarantined-email"></a>Vidta åtgärder för e-post i karantän

När du har valt ett meddelande har du flera alternativ för vad du kan göra med meddelandena i fönstret utfällda **Detaljer** :

- **Släpp meddelande**: i fönstret som visas väljer du följande alternativ:

  - **Rapportera meddelanden till Microsoft för analys**: det här är markerat som standard och rapporterar det felaktiga meddelandet till Microsoft som ett falskt positivt tal. Om meddelandet sattes i karantän som skräp post, bulk, nätfiske eller innehåller skadlig program vara, rapporteras meddelandet också till Microsoft spam-gruppen. Beroende på vilken analys de har, kan de globala skräp post filter reglerna justeras så att de tillåter meddelandet.

  - Välj något av följande alternativ:

    - **Släpp meddelanden till alla mottagare**

    - **Släpp meddelanden till specifika mottagare**

    - **Släppa meddelanden till andra personer**

  Klicka på **Släpp meddelandet** när du är klar.

  Anmärkningar om att frigöra meddelanden:

  - Du kan inte frigöra ett meddelande till samma mottagare flera gånger.

  - Endast mottagare som inte har fått meddelandet visas i listan över potentiella mottagare.

- **Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text. Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften). Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):

- **Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:

  - **Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.
  
  - **Textvy**: Visar meddelandetexten som oformaterad text.

- **Ta bort från karantän**: när du klickar på **Ja** i den varning som visas, tas meddelandet omedelbart bort utan att skickas till de ursprungliga mottagarna.

- **Ladda ned meddelande**: Välj **Jag är medveten om riskerna om jag laddar ned meddelandet** i den utfällbara rutan som visas om du vill spara en lokal kopia av meddelandet i .eml-format.

- **Skicka meddelande**: i fönstret som visas väljer du följande alternativ:

  - **Objekt typ**: **e-post** (standard), **URL**eller **bifogad fil**.

  - **Sändnings format**: **ID för nätverks meddelanden** (standard, med motsvarande värde i fältet för **nätverks meddelande-ID** ) eller **filen** (Bläddra till en lokal. eml-eller. msg-fil). Observera att om du väljer **Arkiv** och sedan **nätverks meddelande-ID**är värdet från från början borta.

  - **Mottagare**: Ange en ursprunglig mottagare för meddelandet eller klicka på **Markera alla** för att identifiera alla mottagare. Du kan också klicka på **Markera alla** och sedan ta bort enskilda mottagare.

  - **Orsak för inlämning**: **ska inte vara blockerat** (standard) eller **ha blockerats**.

  När du är klar klickar du på **Skicka**.

Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Vidta åtgärder för flera e-postmeddelanden i karantän

När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:

- **Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.

  > [!NOTE]
  > Tänk på följande: john@gmail.com skickar ett meddelande till faith@contoso.com och john@subsidiary.contoso.com. Gmail bifurcates det här meddelandet i två kopior som båda dirigeras till karantän som nätfiske i Microsoft. En administratör frigör båda dessa meddelanden till admin@contoso.com. Det första meddelandet som når administratörs post lådan levereras. Det andra publicerade meddelandet identifieras som dubbel leverans och hoppas över. Meddelandet identifieras som dubbletter om de har samma meddelande-ID och tid.

- **Ta bort meddelanden**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort utan att skickas till de ursprungliga mottagarna.

Klicka på **Stäng** när du är klar.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Endast ATP: Använd säkerhets & Compliance Center för att hantera filer i karantän

> [!NOTE]
> Procedurerna för filer i karantän i det här avsnittet är bara tillgängliga för ATP-abonnemang 1 och abonnemang 2.

I organisationer med ATP kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.

### <a name="view-quarantined-files"></a>Visa filer i karantän

1. I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.

2. Ändra **vyn i karantän** till standardvärdena **.** Du kan sortera efter ett fält genom att klicka på en tillgänglig kolumn rubrik.

3. Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik. Klicka på **Ändra kolumner** för att visa högst sju kolumner. Standard kolumnerna är markerade med en asterisk ( <sup>\*</sup> ):

   - **Användarläge**<sup>\*</sup>

   - **Plats**<sup>\*</sup>

   - **Fil namn**<sup>\*</sup>

   - **Fil-URL**<sup>\*</sup>

   - **Fil storlek**<sup>\*</sup>

   - **Upphör**<sup>\*</sup>

   - **Släppt?**<sup>\*</sup>

   - **Identifieras av**

   - **Ändrad efter tid**

4. Om du vill filtrera resultaten klickar du på **Filter**. Följande filter är tillgängliga:

   - **Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:

     - **I dag**

     - **Kommande 2 dagarna**

     - **Kommande 7 dagarna**

     - Ett anpassat datum-och tidsintervall.

   - **Mottaget**

   - **Karantän orsak**: det enda tillgängliga värdet är **skadlig program vara**.

När du har hittat en viss fil i karantän väljer du filen för att visa information om den och för att utföra en åtgärd på den (till exempel Visa, släppa, ladda ned eller ta bort meddelandet).

#### <a name="export-file-results"></a>Exportera fil resultat

1. Välj de filer du är intresse rad av och klicka på **Exportera resultat**.

2. Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.

3. När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.

#### <a name="view-quarantined-file-details"></a>Visa fil information i karantän

När du väljer en fil i listan visas följande fil information i fönstret **detaljerad information** :

- **Fil namn**

- **URL: URL**som definierar filens plats (till exempel i SharePoint Online).

- **Skadligt innehåll upptäcktes på** Det datum/den tid då filen sattes i karantän.

- **Upphör**: det datum då filen ska tas bort från karantänen.

- **Identifierat av**: ATP (avancerat skydd) eller Microsoft-programmet mot skadlig program vara.

- **Släppt?**

- **Namn på skadlig kod**

- **Dokument-ID**: ett unikt ID för dokumentet.

- **Fil storlek**: i KILOBYTE (KB).

- **Organisation** Organisationens unika ID.

- **Senast ändrad**

- **Ändrad av**: den användare som senast ändrade filen.

- **Secure Hash Algorithm 256-bit (SHA-256) värde**: du kan använda det här hashvärdet för att identifiera filen i andra ryktes butiker eller på andra platser i miljön.

### <a name="take-action-on-quarantined-files"></a>Vidta en åtgärd för filer i karantän

När du väljer en fil i listan kan du utföra följande åtgärder på filen i fönstret **detaljerad information** :

- **Släpp filer**: Välj (standard) eller avmarkera **rapportera filer till Microsoft för analys**och klicka sedan på **släpp filer**.

- **Ladda ner fil**

- **Ta bort fil från karantän**

Om du inte släpper eller tar bort filerna tas de bort när standard perioden för karantän lagring upphör.

#### <a name="actions-on-multiple-quarantined-files"></a>Åtgärder på flera filer i karantän

När du markerar flera filer i karantän i listan (upp till 100) visas utfällda **Mass åtgärder** -fönstret där du kan vidta följande åtgärder:

- **Släpp filer**

- **Ta bort filer**: när du har klickat på **Ja** i varningen som visas tas filerna bort omedelbart.

1. Använd ett arbets-eller skol konto som har global administratörs behörighet (eller lämpliga roller för säkerhets & efterlevnadsprinciper) i din organisation, logga in och [gå till säkerhets & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att visa och hantera meddelanden och filer i karantänen

De cmdlets som du använder för att visa och hantera meddelanden och filer i karantänen är:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Exportera-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- För [hands version – QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Observera att denna cmdlet endast gäller för meddelanden, inte malware-filer från ATP för SharePoint Online, OneDrive för företag eller teams.

- [Utgivning-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
