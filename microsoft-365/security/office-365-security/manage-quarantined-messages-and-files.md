---
title: Hantera meddelanden och filer i karantän som administratör
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Administratörer kan lära sig att visa och hantera meddelanden i karantän för alla användare i Exchange Online Protection (EOP). Administratörer i organisationer med Microsoft Defender för Office 365 kan också hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0515d610b38986c2b5339c1cb967a7b150914a2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405824"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Hantera meddelanden och filer i karantän som administratör i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden. Mer information finns i [e-postmeddelanden i karantän i EOP.](quarantine-email-messages.md)

Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare. Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig programvara, nätfiske med hög konfidens eller som ett resultat av e-postflödesregler (kallas även transportregler). Administratörer kan också rapportera falska positiva resultat till Microsoft.

Administratörer i organisationer med Microsoft Defender för Office 365 kan också visa, ladda ned och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.

Du visar och hanterar meddelanden i karantän i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter. Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online innan** du kan utföra procedurerna i den här artikeln:
  - Om du vill vidta åtgärder för meddelanden i karantän för alla användare måste du vara medlem i rollgrupperna Organisationshantering, Säkerhetsadministratör eller  <sup>\*</sup> Karantänadministratör.
  - För skrivskyddad åtkomst till meddelanden i karantän för alla användare måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Exchange Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)

  **Anmärkningar**:

  - Om du lägger till användare till motsvarande Azure Active Directory-roll i  administrationscentret för Microsoft 365 får användarna de behörigheter och behörigheter som krävs för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.
  - <sup>\*</sup>Medlemmar i **rollgruppen för** karantänadministratör måste  också vara medlemmar i rollgruppen Hantering avfrågas i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) för att kunna göra karantänprocedurer i Exchange Online PowerShell.

- Meddelanden i karantän behålls under en standardtid innan de tas bort automatiskt:
  - 30 dagar för meddelanden i karantän enligt principer mot skräppost (skräppost, nätfiske och massutskick). Det här är standardvärdet och det högsta värdet. Information om hur du konfigurerar (lägre) det här värdet [finns i Konfigurera principer för skydd mot skräppost.](configure-your-spam-filter-policies.md)
  - 15 dagar för meddelanden som innehåller skadlig programvara.
  - 15 dagar för filer i karantän efter Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams i Defender för Office 365.

  När ett meddelande förfaller från karantän kan du inte återställa det.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Använda Säkerhets- & för att hantera e-postmeddelanden i karantän

### <a name="view-quarantined-email"></a>Visa e-post i karantän

1. I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.

2. Kontrollera att **Visa i karantän är** inställt på standardvärdet för e-post. 

3. Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik. Klicka på **Ändra kolumner** för att visa högst sju kolumner. Standardvärdena är markerade med en asterisk (<sup>\*</sup>):

   - **Mottaget**<sup>\*</sup>
   - **Avsändare**<sup>\*</sup>
   - **Ämne**<sup>\*</sup>
   - **Orsak till karantän**<sup>\*</sup>
   - **Släppt?**<sup>\*</sup>
   - **Principtyp**<sup>\*</sup>
   - **Upphör**
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
     - **Princip:** Meddelandet matchade villkoren i en e-postflödesregel (kallas även transportregel).
     - **Bulk** (Massutskick)
     - **Nätfiske:** Skräppostfiltrets  bedömning var nätfiskeskydd eller skydd mot nätfiske i karantän för meddelandet [(förfalskningsinställningar](set-up-anti-phishing-policies.md#spoof-settings) eller [personifieringsskydd).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
     - **Skadlig programvara**
     - **Skräppost**
     - **Phish med hög konfidens**

   - **Principtyp**: filtrera meddelanden efter principtyp:
     - **Policy för skydd mot skadlig programvara**
     - **Princip för säkra bifogade filer**
     - **Princip för skydd mot nätfiske**
     - **Filterprincip för värdbaserat innehåll** (Skräppostprincip)
     - **Transportregel**

   - **E-postmottagare:** Alla användare eller endast meddelanden som skickats till dig. Slutanvändarna kan bara hantera meddelanden i karantän som skickas till dem.

   Tryck på **Rensa** om du vill ta bort filtret. Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.

5. Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden. Jokertecken stöds inte. Du kan söka efter följande värden:

   - **Meddelande-ID**: Meddelandets globalt unika identifierare.

     Du använde till exempel [meddelandespårning](message-trace-scc.md) för att leta efter ett meddelande som skickades till en användare i organisationen och du fastställer att meddelandet har satts i karantän i stället för att levereras. Se till att ta med det fullständiga id-värdet för meddelandet, vilket kan inkludera vinkelparenteser ( \<\> ). Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .

   - **Avsändarens e-postadress**: En enskild avsändarens e-postadress.

   - **Principnamn**: använd meddelandets hela principnamn. Sökningen är inte skiftlägeskänslig.

   - **Mottagarens e-postadress**: En enskild mottagares e-postadress.

   - **Ämne**: Använd meddelandets hela ämne. Sökningen är inte skiftlägeskänslig.

   - **Principnamn:** Namnet på principen som ansvarar för att kvartilen av meddelandet.

   När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.

När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).

#### <a name="view-quarantined-message-details"></a>Visa information om meddelanden i karantän

När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information**:

- **Meddelande-ID**: Meddelandets globalt unika identifierare.

- **Avsändarens adress**

- **Mottaget**: Datumet/tiden då meddelandet togs emot.

- **Ämne**

- **Orsak till** karantän: Visar om ett meddelande har identifierats som **skräppost,** massutskick,  **phish** matchat en e-postflödesregel **(transportregel)** eller identifierats som innehåller skadlig **programvara.**

- **Antal mottagare**

- **Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.

- **Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.

- **Släppt till**: Alla e-postadresser som meddelandet har släppts till.

- **Släppt till**: Alla e-postadresser som meddelandet har släppts till.

### <a name="take-action-on-quarantined-email"></a>Vidta åtgärder för e-post i karantän

När du har valt ett meddelande kan du välja mellan flera alternativ för vad du vill göra med meddelandena i den **utfällna** rutan Information:

- **Släpp meddelandet:** Välj följande alternativ i det utfällfönster som visas:

  - **Rapportera meddelanden till Microsoft för analys:** Det här är valt som standard och rapporterar det felaktiga meddelandet i karantän till Microsoft som felaktigt positivt. Om meddelandet har satts i karantän som skräppost, massutskick, nätfiske eller som innehåller skadlig programvara rapporteras meddelandet även till Microsofts team för skräppostanalys. Beroende på deras analys kan reglerna för skräppostfilter för hela tjänsten justeras så att meddelandet tillåts.

  - Välj något av följande alternativ:
    - **Släppa meddelanden till alla mottagare**
    - **Släppa meddelanden till specifika mottagare**
    - **Släpp meddelanden till andra personer:** Observera att det inte går att släppa skadlig programvara till andra personer än de ursprungliga mottagarna.

  Klicka på **Släpp meddelandet** när du är klar.

  Kommentarer om att släppa meddelanden:

  - Du kan inte släppa ett meddelande till samma mottagare flera gånger.
  - Endast mottagare som inte har fått meddelandet visas i listan med potentiella mottagare.

- **Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text. Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften). Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):

- **Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:

  - **Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.
  - **Textvy**: Visar meddelandetexten som oformaterad text.

- **Ta bort från karantän:** När du **klickar** på Ja i varningen som visas tas meddelandet bort omedelbart utan att skickas till de ursprungliga mottagarna.

- **Ladda ned meddelande**: Välj **Jag är medveten om riskerna om jag laddar ned meddelandet** i den utfällbara rutan som visas om du vill spara en lokal kopia av meddelandet i .eml-format.

- **Skicka ett** meddelande: Välj följande alternativ i det utfällfönster som visas:

  - **Objekttyp:** **E-post** (standard), **URL** eller **bifogad fil.**

  - **Överföringsformat:** **Nätverksmeddelande-ID** (standard med motsvarande värde i rutan **Nätverksmeddelande-ID)** eller Fil **(bläddra** till en lokal .eml- eller .msg-fil). Observera att om du väljer **Arkiv** och sedan **Nätverksmeddelande-ID** är det ursprungliga värdet borta.

  - **Mottagare:** Skriv vid leasa en ursprunglig mottagare av meddelandet eller klicka **på Markera alla** för att identifiera alla mottagare. Du kan också klicka **på Markera alla** och sedan selektivt ta bort enskilda mottagare.

  - **Orsak till** **inskickning: Borde inte ha blockerats** (standard) **eller borde ha blockerats.**

  Klicka på Skicka när du är **klar.**

Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Vidta åtgärder för flera e-postmeddelanden i karantän

När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:

- **Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.

  > [!NOTE]
  > Tänk dig följande scenario: john@gmail.com skickar ett meddelande till faith@contoso.com och john@subsidiary.contoso.com. Gmail delar upp det här meddelandet i två kopior som båda dirigeras till karantän som nätfiske i Microsoft. En administratör släpper båda dessa meddelanden till admin@contoso.com. Det första släppta meddelandet som når administratörspostlådan levereras. Det andra släppta meddelandet identifieras som dubblettleverans och hoppas över. Meddelandet identifieras som dubbletter om de har samma meddelande-ID och mottagen tid.

- **Ta bort** meddelanden: När du klickar på **Ja** i varningen som visas tas meddelandena bort omedelbart utan att skickas till de ursprungliga mottagarna.

Klicka på **Stäng** när du är klar.

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Endast Microsoft Defender för Office 365: Använd säkerhets- & för att hantera filer i karantän

> [!NOTE]
> Procedurerna för filer i karantän i det här avsnittet är endast tillgängliga för Microsoft Defender för Office 365 Abonnemang 1- och Abonnemang 2-prenumeranter.

I organisationer med Defender för Office 365 kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams. Information om hur du aktiverar skydd för dessa [filer finns i Aktivera Säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="view-quarantined-files"></a>Visa filer i karantän

1. I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.

2. Ändra **visa i karantän** till **värdefilerna.** Du kan sortera på ett fält genom att klicka på en tillgänglig kolumnrubrik.

3. Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik. Klicka på **Ändra kolumner** för att visa högst sju kolumner. Standardkolumnerna är markerade med en asterisk ( <sup>\*</sup> ):

   - **Användare**<sup>\*</sup>
   - **Plats**<sup>\*</sup>
   - **Filnamn**<sup>\*</sup>
   - **Fil-URL**<sup>\*</sup>
   - **Filstorlek**<sup>\*</sup>
   - **Upphör**<sup>\*</sup>
   - **Släppt?**<sup>\*</sup>
   - **Upptäckt av**
   - **Ändrad efter tid**

4. Om du vill filtrera resultaten klickar du på **Filter**. Följande filter är tillgängliga:

   - **Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:
     - **I dag**
     - **Kommande 2 dagarna**
     - **Kommande 7 dagarna**
     - Ett anpassat datum-/tidsintervall.
   - **Mottagen tid**
   - **Orsak till karantän:** Det enda tillgängliga värdet är skadlig **programvara.**
   - **Typ av princip**

När du har hittat en specifik fil i karantän väljer du filen för att visa information om den och för att vidta åtgärder på den (till exempel visa, släppa, ladda ned eller ta bort meddelandet).

#### <a name="view-quarantined-file-details"></a>Visa information om karantän

När du väljer en fil i listan visas  följande filinformation i den utfällopanelen Information:

- **Filnamn**
- **Fil-URL:** URL som definierar filens plats (till exempel i SharePoint Online).
- **Skadligt innehåll som upptäckts** Datum/tid då filen satt i karantän.
- **Går ut:** Datumet då filen tas bort från karantän.
- **Upptäckt av:** Defender för Office 365 eller Microsofts motor mot skadlig programvara.
- **Släppt?**
- **Malware Name**
- **Dokument-ID:** unik identifierare beskrivning av dokumentet.
- **Filstorlek:** I kilobyte (KB).
- **Organisation** Din organisations unika ID.
- **Senast ändrad**
- **Ändrad av:** Den användare som senast ändrade filen.
- **256-bitars algoritmen för säker hash-algoritm (SHA-256):** Du kan använda det här hash-värdet för att identifiera filen i andra rykteslager eller på andra platser i din miljö.

### <a name="take-action-on-quarantined-files"></a>Vidta åtgärder för filer i karantän

När du väljer en fil i listan kan du utföra  följande åtgärder på filen i den utfällopanelen Information:

- **Släpp filer:** Markera (standard) eller avmarkera **rapportfiler till Microsoft för** analys och klicka sedan på **Släpp filer.**
- **Ladda ned fil**
- **Ta bort en fil från karantän**

Om du inte släpper eller tar bort filerna tas de bort när standardlagringsperioden för karantän löper ut.

#### <a name="actions-on-multiple-quarantined-files"></a>Åtgärder för flera filer i karantän

När du markerar flera filer i karantän i listan (upp till 100) visas den utfällda rutan Massåtgärder där du kan utföra följande åtgärder: 

- **Släppa filer**
- **Ta bort** filer: När **du klickar** på Ja i varningen som visas tas filerna bort direkt.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att visa och hantera meddelanden och filer i karantän

De cmdlets du använder för att visa och hantera meddelanden och filer i karantän är:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)Observera att den här cmdleten endast är till för meddelanden, inte för skadlig programvara från säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
