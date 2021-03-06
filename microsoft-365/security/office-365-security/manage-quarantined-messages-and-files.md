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
ms.openlocfilehash: 59bdfdaddbc091467bfd2ccddc2c40377955fab3
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028997"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Hantera meddelanden och filer i karantän som administratör i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden. Mer information finns i [EOP i karantän.](quarantine-email-messages.md)

Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare. Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig programvara, nätfiske med hög säkerhet eller som ett resultat av e-postflödesregler (kallas även transportregler). Administratörer kan också rapportera falska positiva resultat till Microsoft.

Administratörer i organisationer med Microsoft Defender för Office 365 kan också visa, ladda ned och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.

Du visar och hanterar meddelanden i karantän i Microsoft 365 Defender-portalen eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>. Om du vill öppna karantänsidan direkt går du till <https://security.microsoft.com/quarantine>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill vidta åtgärder för meddelanden i karantän för alla användare måste du vara medlem i rollgrupperna Organisationshantering, Säkerhetsadministratör eller  <sup>\*</sup> Karantänadministratör.
  - För skrivskyddad åtkomst till meddelanden i karantän för alla användare måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Anteckningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.
  - <sup>\*</sup>Medlemmar i rollgruppen **Karantänadministratör** måste också  vara medlemmar i rollgruppen Hantering av servergrupp [i Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) för att kunna göra karantänprocedurer i Exchange Online PowerShell.

- Meddelanden i karantän behålls under en standardtid innan de tas bort automatiskt:
  - 30 dagar för meddelanden som i karantän omfattas av principer mot skräppost (skräppost, nätfiske och massutskick). Det här är standardvärdet och maxvärdet. Information om hur du konfigurerar (lägre) det här värdet [finns i Konfigurera principer för skydd mot skräppost.](configure-your-spam-filter-policies.md)
  - 15 dagar för meddelanden som innehåller skadlig programvara.
  - 15 dagar för filer som satts i karantän av Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams i Defender för Office 365.

  När ett meddelande förfaller från karantän kan du inte återställa det.

## <a name="use-the-microsoft-365-defender-portal-to-manage-quarantined-email-messages"></a>Använda Microsoft 365 Defender för att hantera e-postmeddelanden i karantän

### <a name="view-quarantined-email"></a>Visa e-post i karantän

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Granska** \> **Karantän**.

2. På sidan **Karantän** kontrollerar du att Visa **i karantän är** inställt på standardvärdet för e-post. 

3. Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik. Klicka på **Ändra kolumner** för att visa högst sju kolumner. Standardvärdena är markerade med en asterisk (<sup>\*</sup>):

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

4. Om du vill filtrera resultaten klickar du på **Filter**. Följande filter är tillgängliga:
   - **Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:
     - **I dag**
     - **Kommande 2 dagarna**
     - **Kommande 7 dagarna**
     - **Anpassad**: Ange ett **Startdatum** och **Slutdatum**.
   - **Togs emot**: Ange ett **Startdatum** och **Slutdatum**.
   - **Orsak till karantän**:
     - **Princip:** Meddelandet matchade villkoren i en e-postflödesregel (kallas även transportregel).
     - **Massutskick**
     - **Phish:** Skräppostfiltrets  bedömning var nätfiskeskydd eller skydd mot nätfiske i karantän för meddelandet [(förfalskningsinställningar](set-up-anti-phishing-policies.md#spoof-settings) eller [personifieringsskydd).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
     - **Skadlig programvara**
     - **Skräppost**
     - **Hög konfidensfras**
   - **Principtyp**: filtrera meddelanden efter principtyp:
     - **Princip för skydd mot skadlig programvara**
     - **Valv Princip för bifogade filer**
     - **Princip för skydd mot nätfiske**
     - **Filterprincip för värdbaserat innehåll** (Skräppostprincip)
     - **Transportregel**
   - **E-postmottagare:** Alla användare eller bara meddelanden som skickats till dig. Slutanvändarna kan bara hantera meddelanden i karantän som skickas till dem.

   Tryck på **Rensa** om du vill ta bort filtret. Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.

5. Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden. Jokertecken stöds inte. Du kan söka efter följande värden:
   - **Meddelande-ID**: Meddelandets globalt unika identifierare.

     Du använde till exempel [meddelandespårning](message-trace-scc.md) för att leta efter ett meddelande som har skickats till en användare i organisationen och du anser att meddelandet har satts i karantän i stället för att levereras. Se till att ta med det fullständiga värdet för meddelande-ID, vilket kan inkludera vinkelparenteser ( \<\> ). Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .

   - **Avsändarens e-postadress**: En enskild avsändarens e-postadress.
   - **Principnamn**: använd meddelandets hela principnamn. Sökningen är inte skiftlägeskänslig.
   - **Mottagarens e-postadress**: En enskild mottagares e-postadress.
   - **Ämne**: Använd meddelandets hela ämne. Sökningen är inte skiftlägeskänslig.
   - **Principnamn:** Namnet på principen som ansvarar för att kvartilen av meddelandet.

   När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.

När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).

#### <a name="view-quarantined-message-details"></a>Visa information om meddelanden i karantän

När du markerar ett e-postmeddelande i listan är följande meddelandeinformation tillgänglig i den utfällade informationen som visas:

- **Meddelande-ID**: Meddelandets globalt unika identifierare.
- **Avsändarens adress**
- **Mottaget**: Datumet/tiden då meddelandet togs emot.
- **Ämne**
- **Orsak till karantän:** Visar om ett meddelande har identifierats som **skräppost**, **massutskick,** **phish**, matchat en e-postflödesregel **(transportregel)** eller identifierats som innehåller skadlig **programvara.**
- **Antal mottagare**
- **Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.
- **Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.
- **Släppt till**: Alla e-postadresser som meddelandet har släppts till.
- **Släppt till**: Alla e-postadresser som meddelandet har släppts till.

### <a name="take-action-on-quarantined-email"></a>Vidta åtgärder för e-post i karantän

När du har valt ett meddelande kan du välja mellan flera alternativ för vad du vill göra med meddelandena i den utfällade informationen:

- **Släpp meddelandet:** Välj följande alternativ i den utfäll plats som visas:
  - **Rapportera meddelanden till Microsoft för analys:** Det här är valt som standard och rapporterar det felaktiga meddelandet till Microsoft som felaktigt positivt. Om meddelandet har satts i karantän som skräppost, massutskick, nätfiske eller som innehåller skadlig programvara, rapporteras meddelandet även till Microsofts team för skräppostanalys. Beroende på deras analys kan reglerna för skräppostfilter för hela tjänsten justeras så att meddelandet tillåts.
  - Välj något av följande alternativ:
    - **Släppa meddelanden till alla mottagare**
    - **Släppa meddelanden till specifika mottagare**
    - **Släpp meddelanden till andra:** Observera att det inte går att släppa skadlig programvara till andra personer än de ursprungliga mottagarna.

  Klicka på **Släpp meddelandet** när du är klar.

  Kommentarer om att släppa meddelanden:

  - Du kan inte släppa ett meddelande till samma mottagare mer än en gång.
  - Endast mottagare som inte har fått meddelandet visas i listan över möjliga mottagare.

- **Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text. Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften). Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):
- **Förhandsgranskningsmeddelande:** Välj något av följande alternativ i den utfäll plats som visas:
  - **Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.
  - **Textvy**: Visar meddelandetexten som oformaterad text.
- **Ta bort från karantän:** När du **klickar** på Ja i den varning som visas tas meddelandet bort omedelbart utan att skickas till de ursprungliga mottagarna.
- **Ladda ned meddelandet:** I den  utfällbara menyn som visas väljer du Jag förstår riskerna med att ladda ned det här meddelandet om du vill spara en lokal kopia av meddelandet i EML-format.
- **Spärra avsändare**: Lägg till avsändaren i listan Spärrade avsändare i din postlåda. Mer information finns i [Spärra e-postavsändare](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).
- **Skicka ett** meddelande: Välj följande alternativ i den utfäll plats som visas:
  - **Objekttyp:** **E-post** (standard), **URL** eller **Bifogad fil**.
  - **Överföringsformat:** **Nätverksmeddelande-ID** (standard med motsvarande värde i rutan Nätverksmeddelande-ID) eller Fil **(bläddra** till en lokal .eml- eller .msg-fil).  Observera att om du väljer **Arkiv** och sedan **Nätverksmeddelande-ID** är det ursprungliga värdet borta.
  - **Mottagare:** Ange vid leasa en ursprunglig mottagare av meddelandet eller klicka på **Markera alla om** du vill identifiera alla mottagare. Du kan också klicka **på Markera alla** och sedan selektivt ta bort enskilda mottagare.
  - **Orsak till inskickning:** **Ska inte ha blockerats** (standard) eller Borde **ha blockerats.**

  När du är klar klickar du på **Skicka.**

Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Vidta åtgärder för flera e-postmeddelanden i karantän

När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällade listan Massåtgärder där du kan utföra följande åtgärder: 

- **Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.

  > [!NOTE]
  > Tänk dig följande scenario: john@gmail.com skickar ett meddelande till faith@contoso.com och john@subsidiary.contoso.com. Gmail delar upp meddelandet i två kopior som båda skickas till karantän som nätfiske i Microsoft. En administratör släpper båda dessa meddelanden till admin@contoso.com. Det första släppta meddelandet som når administratörspostlådan levereras. Det andra utgivna meddelandet identifieras som dubblettleverans och hoppas över. Meddelandet identifieras som dubbletter om de har samma meddelande-ID och har fått tid.

- **Ta bort** meddelanden: När du **klickar** på Ja i den varning som visas tas meddelandena bort omedelbart utan att skickas till de ursprungliga mottagarna.

Klicka på **Stäng** när du är klar.

## <a name="use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365"></a>Använd Microsoft 365 Defender för att hantera filer i karantän i Defender för Office 365
> [!NOTE]
> Procedurerna för filer i karantän i det här avsnittet är endast tillgängliga för Microsoft Defender för Office 365 abonnemang 1- och abonnemang 2-prenumeranter.

I organisationer med Defender för Office 365 kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams. Om du vill aktivera skydd för dessa filer kan du [gå till Aktivera Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

### <a name="view-quarantined-files"></a>Visa filer i karantän

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Granska** \> **Karantän**.


2. På sidan **Karantän** ändrar du **Visa i karantän** till värdefilerna.  Du kan sortera på ett fält genom att klicka på en tillgänglig kolumnrubrik.

3. Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik. Klicka på **Ändra kolumner** för att visa högst sju kolumner. Standardkolumnerna är markerade med en asterisk ( <sup>\*</sup> ):
   - **Användare**<sup>\*</sup>
   - **Plats**<sup>\*</sup>
   - **Filnamn**<sup>\*</sup>
   - **Fil-URL**<sup>\*</sup>
   - **Filstorlek**<sup>\*</sup>
   - **Upphör**<sup>\*</sup>
   - **Släppt?**<sup>\*</sup>
   - **Upptäckt av**
   - **Ändrad av tid**

4. Om du vill filtrera resultaten klickar du på **Filter**. Följande filter är tillgängliga:
   - **Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:
     - **I dag**
     - **Kommande 2 dagarna**
     - **Kommande 7 dagarna**
     - Ett anpassat datum-/tidsintervall.
   - **Mottagen tid**
   - **Orsak till karantän:** Det enda tillgängliga värdet är skadlig **programvara.**
   - **Typ av princip**

När du har hittat en viss fil i karantän väljer du filen för att visa information om den och för att vidta åtgärder för den (till exempel visa, släppa, ladda ned eller ta bort meddelandet).

#### <a name="view-quarantined-file-details"></a>Visa information om karantänfiler

När du väljer en fil i listan är följande filinformation tillgänglig i den utfällade informationen som öppnas:

- **Filnamn**
- **Fil-URL:** URL som definierar platsen för filen (till exempel i SharePoint Online).
- **Skadligt innehåll som upptäckts** Datum/tid då filen satt i karantän.
- **Går ut:** Det datum då filen tas bort från karantän.
- **Upptäckt av**: Defender för Office 365 eller Microsofts motor mot skadlig programvara.
- **Släppt?**
- **Malware Name**
- **Dokument-ID:** En unik identifierare för dokumentet.
- **Filstorlek:** i kilobyte (KB).
- **Organisation** Organisationens unika ID.
- **Senast ändrad**
- **Ändrad av:** Den användare som senast ändrade filen.
- **256-bitars algoritmen för säker hashalgoritm (SHA-256):** Du kan använda det här hashvärdet för att identifiera filen i andra rykteslager eller på andra platser i din miljö.

### <a name="take-action-on-quarantined-files"></a>Vidta åtgärder för filer i karantän

När du väljer en fil i listan kan du utföra följande åtgärder på filen i den utfällade informationen:

- **Släpp filer:** Markera (standard) eller avmarkera **Rapportfiler till Microsoft för analys** och klicka sedan på Släpp **filer.**
- **Ladda ned fil**
- **Ta bort en fil från karantän**

Om du inte släpper eller tar bort filerna tas de bort när standardlagringsperioden för karantän löper ut.

#### <a name="actions-on-multiple-quarantined-files"></a>Åtgärder för flera filer i karantän

När du markerar flera filer i karantän i listan (upp till 100) visas den utfällade listan Massåtgärder där du kan utföra följande åtgärder: 

- **Släpp filer**
- **Ta bort** filer: När **du klickar** på Ja i den varning som visas tas filerna bort omedelbart.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att visa och hantera meddelanden och filer i karantän

De cmdlets du använder för att visa och hantera meddelanden och filer i karantän är:

- [Delete-QuarantineMessage](/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage:](/powershell/module/exchange/preview-quarantinemessage)Observera att den här cmdleten endast används för meddelanden, inte filer i karantän från Valv Bifogade filer för SharePoint, OneDrive och Microsoft Teams.

- [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
