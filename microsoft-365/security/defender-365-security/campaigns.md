---
title: Kampanjvyer i Microsoft Defender för Office 365-abonnemang
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Läs mer om kampanjvyer i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3c84b9e6253dd813ff930314fc2c1d0a947e94e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073473"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a>Kampanjvyer i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)

Kampanjvyer är en funktion i Microsoft Defender för Office 365 abonnemang 2 (till exempel Microsoft 365 E5 eller organisationer med tillägget Defender för Office 365 abonnemang 2). Kampanjvyer i säkerhets- & säkerhets- och efterlevnadscenter identifierar och kategoriserar nätfiskeattacker i tjänsten. Kampanjvyer kan hjälpa dig att:

- Undersök effektivt och svara på nätfiskeattacker.
- Bättre förståelse för attackens omfattning.
- Visa värde för beslutsfattare.

I kampanjvyer kan du se en helhetsbild av en attack snabbare och mer fullständig än en person.

## <a name="what-is-a-campaign"></a>Vad är en kampanj?

En kampanj är en koordinerad e-postattack mot en eller flera organisationer. E-postattacker som stjäl autentiseringsuppgifter och företagsdata är en stor och lucrativ bransch. När tekniken ökar i ett försök att stoppa attacker, ändrar attacker deras metoder i ett försök att säkerställa fortsatt framgång.

Microsoft använder sig av de omfattande mängder information om skydd mot nätfiske, skräppost och skadlig programvara som finns i hela tjänsten för att identifiera kampanjer. Vi analyserar och klassificerar attackinformationen utifrån flera faktorer. Ett exempel:

- **Attackkälla:** Käll-IP-adresser och avsändardomäner.
- **Meddelandeegenskaper:** Meddelandens innehåll, format och ton.
- **Meddelandemottagare:** Hur mottagare är relaterade. Till exempel mottagardomäner, funktioner för mottagarjobb (administratörer, chefer osv.), företagstyper (stora, små, offentliga, privata osv.) och branscher.
- **Attack av nyttolast:** Skadliga länkar, bifogade filer eller andra nyttolaster i meddelandena.

En kampanj kan vara kortlivad eller kan omfatta flera dagar, veckor eller månader med aktiva och inaktiva perioder. En kampanj kan startas mot din specifika organisation eller din organisation kan vara en del av en större kampanj i flera företag.

## <a name="campaign-views-in-the-security--compliance-center"></a>Kampanjvyer i Säkerhets- & Säkerhets- och efterlevnadscenter

Kampanjvyer finns i [Säkerhets- & Säkerhets- och efterlevnadscenter](https://protection.office.com) på **kampanjer för** \> **hothantering** eller direkt på <https://protection.office.com/campaigns> .

![Översikt över kampanjer i Säkerhets- & Efterlevnadscenter](../../media/campaigns-overview.png)

Du kan också komma åt kampanjvyer från:

- **Hothantering** \> **Utforskaren** \> **Visa** \> **Kampanjer**
- **Hothantering** \> **Utforskaren** \> **Visa** \> **All e-post** \> **Fliken** Kampanj
- **Hothantering** \> **Utforskaren** \> **Visa** \> **Phish** \> **Fliken** Kampanj
- **Hothantering** \> **Utforskaren** \> **Visa** \> **Skadlig programvara** \> **Fliken** Kampanj

För att komma åt kampanjvyer måste du vara medlem  i rollgrupperna Organisationshantering, Säkerhetsadministratör eller Säkerhetsläsare i Säkerhets- & Efterlevnadscenter. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

## <a name="campaigns-overview"></a>Översikt över kampanjer

På översiktssidan finns information om alla kampanjer.

På **standardfliken** Kampanj visar **området Kampanjtyp** ett stapeldiagram som visar antalet mottagare per dag. Som standard visas både **Phish- och Malware-data** **i** diagrammet.

> [!TIP]
> Om du inte ser några kampanjdata kan du prova att ändra datumintervallet eller [filtren](#filters-and-settings).

På resten av översiktssidan visas följande information på **fliken** Kampanj:

- **Namn**

- **Exempel på** ämne: Ämnesraden i ett av meddelandena i kampanjen. Observera att alla meddelanden i kampanjen inte nödvändigtvis har samma ämne.

- **Riktad**: Procentandelen som beräknas av: (antalet kampanjmottagare i organisationen) / (det totala antalet mottagare i kampanjen i alla organisationer i tjänsten). Det här värdet anger i vilken grad kampanjen endast dirigeras till din organisation (ett högre värde) jämfört med när den även riktar sig till andra organisationer i tjänsten (ett lägre värde).

- **Typ:** Det här värdet är **antingen phish** eller **skadlig kod.**

- **Undertyp:** Det här värdet innehåller mer information om kampanjen. Ett exempel:
  - **Phish**: Där det finns ett märke som phished av den här kampanjen. Till exempel `Microsoft` , , eller `365` `Unknown` `Outlook` `DocuSign` .
  - **Skadlig** programvara: till exempel `HTML/PHISH` eller `HTML/<MalwareFamilyName>` .

  Om det finns tillgängligt är det märke som används av den här kampanjen. När identifieringen drivs av Defender för Office 365-teknik läggs prefixet **ATP-** till i undertypsvärdet.

- **Mottagare:** Antalet användare som har riktats av den här kampanjen.

- **Inkorg:** Antalet användare som har fått meddelanden från den här kampanjen i Inkorgen (levereras inte till mappen Skräppost).

- **Klickade:** Antalet användare som klickade på URL-adressen eller öppnade den bifogade filen i nätfiskemeddelandet.

- **Klicka på** ränta: Procentandelen som beräknas med "**Klickad**  /  **inkorg**". Det här värdet är en indikator på kampanjens effektivitet. Med andra ord, om mottagarna kunde identifiera meddelandet som nätfiske och om de inte klickade på webbadressen för nyttolasten.

  Observera att **Click rate inte** används i skadlig programvara.

- **Besökt:** Hur många användare som faktiskt tog sig fram till nyttolastwebbplatsen. Om det finns **klickade** värden, men säkra länkar blockerade åtkomsten till webbplatsen, är det här värdet noll.

På **fliken Kampanjens** ursprung visas meddelandekällorna på en världskarta.

### <a name="filters-and-settings"></a>Filter och inställningar

Längst upp på sidan Kampanjvyer finns det flera filter- och frågeinställningar som hjälper dig att hitta och isolera specifika kampanjer.

![Kampanjfilter](../../media/campaign-filters-and-settings.png)

Den mest grundläggande filtreringen du kan göra är startdatum/starttid och slutdatum/-tid.

Om du vill filtrera vyn ytterligare kan du göra  en egenskap med flera värden genom att klicka på knappen Kampanjtyp, göra ditt val och sedan klicka **på Uppdatera**.

De filtrerbara kampanjegenskaper som är tillgängliga **i** knappen Kampanjtyp beskrivs i följande lista:

- **Grundläggande:**
  - **Kampanjtyp:** Välj **Skadlig programvara** **eller Phish**. Om du avmarkerar markeringarna får du samma resultat som om du markerar båda.
  - **Kampanjnamn**
  - **Kampanjundertyp**
  - **Avsändare**
  - **Mottagare**
  - **Avsändningsdomän**
  - **Ämne**
  - **Filnamn på bifogad fil**
  - **Familj för skadlig programvara**
  - **Taggar:** Användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton). Mer information om användartaggar finns i [Användartaggar.](user-tags.md)
  - **System åsidosättningar**
  - **Leveransåtgärd**
  - **Ytterligare åtgärd**
  - **Directionality**
  - **Identifieringsteknik**
  - **Ursprunglig leveransplats**
  - **Senaste leveransplats**
  - **System åsidosättningar**

- **Avancerat:**
  - **Internetmeddelande-ID:** Tillgängligt i **meddelande-ID-sidhuvudet** i meddelandehuvudet. Ett exempelvärde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observera vinkelparenteserna).
  - **Nätverksmeddelande-ID:** Ett GUID-värde som är tillgängligt i huvudfältet **X-MS-Exchange-Organization-Network-Message-Id** i meddelandehuvudet.
  - **Sender IP**
  - **SHA256 för bifogade** filer: Om du vill hitta HASH-värdet för SHA256 för en fil i Windows kör du följande kommando i kommandotolken: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  - **Kluster-ID**
  - **Aviseringsprincip-ID**
  - **ZAP URL-signal**

- **URL:er:**
  - **URL-domän**
  - **URL-domän och sökväg**
  - **URL**
  - **URL-sökväg**
  - **Klicka på bedömning**

Om du vill använda mer avancerad filtrering, t.ex. filtrering efter flera egenskaper, kan du **skapa** en fråga genom att klicka på knappen Avancerat filter. Samma kampanjegenskaper är tillgängliga men med följande förbättringar:

- Du kan klicka på **Lägg till ett villkor** för att välja flera villkor.
- Du kan välja **operatorn Och** **eller** Eller mellan villkoren.
- Du kan välja **gruppobjektet Villkor** längst ned i villkorslistan om du vill skapa komplexa sammansatta villkor.

När du är klar klickar du på **knappen** Fråga.

När du har skapat ett grundläggande eller avancerat filter kan du spara det med hjälp **av Spara fråga** eller Spara fråga **som**. När du senare återgår till kampanjvyer kan du läsa in ett sparat filter genom att klicka **på Sparade frågeinställningar.**

Om du vill exportera diagrammet eller listan med kampanjer klickar du på **Exportera** och väljer **Exportera diagramdata** eller **Exportera kampanjlista**.

Om du har en Microsoft Defender för slutpunkt-prenumeration kan du klicka på **MDE-inställningar** för att ansluta till eller koppla bort kampanjerna med Microsoft Defender för Slutpunkt. Mer information finns i Integrera [Microsoft Defender för Office 365 med Microsoft Defender för slutpunkt.](integrate-office-365-ti-with-mde.md)

## <a name="campaign-details"></a>Kampanjinformation

När du klickar på namnet på en kampanj visas kampanjinformationen i en utfällbladstext.

### <a name="campaign-information"></a>Kampanjinformation

Högst upp i vyn med kampanjinformation finns följande kampanjinformation:

- **ID**: Unikt kampanj-ID.

- **Startade** **och avslutades:** Startdatum och slutdatum för kampanjen. Observera att de här datumen kan utökas ytterligare än de filterdatum du valde på översiktssidan.

- **Påverkan:** Det här avsnittet innehåller följande data för det datumintervallfilter du valde (eller som du valde i tidslinjen):
  - Det totala antalet mottagare.
  - Antalet meddelanden som har "Inkorgen" (det vill säga levererats till Inkorgen, inte till mappen Skräppost).
  - Hur många användare som klickade på URL-nyttolasten i nätfiskemeddelandet.
  - Hur många användare som besökt URL:en.

- **Riktad**: Procentandelen som beräknas av: (antalet kampanjmottagare i organisationen) / (det totala antalet mottagare i kampanjen i alla organisationer i tjänsten). Observera att det här värdet beräknas över hela kampanjens livslängd och ändras inte baserat på datumfilter.

- En interaktiv tidslinje med kampanjaktivitet: Tidslinjen visar aktiviteten under hela kampanjens livstid. Som standard innehåller det skuggade området filtret för datumintervall som du valde i översikten. Du kan klicka och dra för att välja en specifik startpunkt och ändpunkt, vilket ändrar <u>de data  </u>som visas i effektområdet och på resten av sidan enligt beskrivningen i nästa avsnitt .

I namnlisten kan du klicka på nedskrivningsikonen Ladda ned kampanj och ladda ned kampanjinformationen till ett **Word-dokument** ![ (standardnamnet ](../../media/download-campaign-write-up-button.png) CampaignReport.docx). Observera att nedladdningen innehåller information om hela kampanjens livslängd (inte bara de filterdatum du valde).

![Kampanjinformation](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Kampanjflöde

I mitten av vyn med kampanjinformation visas viktig information om kampanjen i avsnittet **Flöde** i ett vågrätt flödesdiagram (kallas _Sankey-diagram)._ Den här informationen hjälper dig att förstå kampanjens element och hur de kan påverka din organisation.

> [!TIP]
> Informationen som visas i **flödesschemat** styrs av det skuggade datumintervallet på tidslinjen enligt beskrivningen i föregående avsnitt.

![Kampanjinformation som inte innehåller klick på användar-URL](../../media/campaign-details-no-recipient-actions.png)

Om du hovrar över ett vågrätt band i diagrammet visas antalet relaterade meddelanden (till exempel meddelanden från en viss käll-IP, meddelanden från käll-IP med den angivna avsändardomänen osv.).

Diagrammet innehåller följande information:

- **Avsändar-IP**
- **Avsändardomäner**
- **Filtrera omdömen: Bedömningsvärden** är relaterade till tillgängliga filterutskick av nätfiske och skräppost enligt beskrivningen i [Skräppostskyddsrubriker.](anti-spam-message-headers.md) De tillgängliga värdena beskrivs i följande tabell:

  ****

  |Value|Skräppostfilter för bedömning|Beskrivning|
  |---|---|---|
  |**Tillåten**|`SFV:SKN` <p> `SFV:SKI`|Meddelandet har markerats som inte skräppost och/eller hoppats över filtrering innan det utvärderas av skräppostfiltrering. Meddelandet har till exempel markerats som inte skräppost av en e-postflödesregel (kallas även transportregel). <p> Meddelandet hoppade över skräppostfiltrering av andra orsaker. Till exempel ser avsändaren och mottagaren ut att vara i samma organisation.|
  |**Blockerad**|`SFV:SKS`|Meddelandet markerades som skräppost innan det utvärderades av skräppostfiltrering. Till exempel efter en e-postflödesregel.|
  |**Upptäckt**|`SFV:SPM`|Meddelandet markerades som skräppost av skräppostfiltret.|
  |**Inte upptäckt**|`SFV:NSPM`|Meddelandet har markerats som inte skräppost genom filtrering av skräppost.|
  |**Släppt**|`SFV:SKQ`|Meddelandet hoppade över skräppostfiltreringen eftersom det släpptes från karantän.|
  |**Tillåt klientorganisation**<sup>\*</sup>|`SFV:SKA`|Meddelandet hoppade över skräppostfiltrering på grund av inställningarna i en princip som är skräppostskyddad. Till exempel finns avsändaren i listan med tillåtna avsändare eller domänlistor med tillåtna avsändare.|
  |**Klientorganisationsblock**<sup>\*\*</sup>|`SFV:SKA`|Meddelandet blockerades av skräppostfiltrering på grund av inställningarna i en princip mot skräppost. Till exempel finns avsändaren i listan med tillåtna avsändare eller domänlistor med tillåtna avsändare.|
  |**Tillåt för användare**<sup>\*</sup>|`SFV:SFE`|Meddelandet hoppade över skräppostfiltreringen eftersom avsändaren fanns med på en användares lista över betrodda avsändare.|
  |**Användarblock**<sup>\*\*</sup>|`SFV:BLK`|Meddelandet blockerades av skräppostfiltrering eftersom avsändaren fanns med på en användares lista över spärrade avsändare.|
  |**ZAP**|Ej a|[Zap (Zero-hour auto purge)](zero-hour-auto-purge.md) flyttade det skickade meddelandet till mappen Skräppost eller karantän. Du konfigurerar åtgärden i principen mot skräppost.|
  |

  <sup>\*</sup> Gå igenom dina principer för skydd mot skräppost eftersom det tillåtna meddelandet sannolikt har blockerats av tjänsten.

  <sup>\*\*</sup> Läs igenom dina principer för skydd mot skräppost, eftersom dessa meddelanden ska ha karantän och inte levereras.

- Leveransplatser: Du bör troligtvis undersöka meddelanden som har **levererats** till mottagare (antingen till Inkorgen eller mappen Skräppost), även om användarna inte klickade på webbadressen för nyttolasten i meddelandet. Du kan också ta bort meddelanden i karantän. Mer information finns i [EOP i karantän.](quarantine-email-messages.md)
  - **Borttaget mapp**
  - **Nedsnad**
  - **Extern:** Mottagaren finns i din lokala e-postorganisation i hybridmiljöer.
  - **Misslyckades**
  - **Vidarebefordrad**
  - **Inkorgen**
  - **Skräppostmapp**
  - **Karantän**
  - **Okänd**

- **URL-klick:** Dessa värden beskrivs i nästa avsnitt.

> [!NOTE]
> I alla lager som innehåller fler än 10 objekt visas de 10 översta objekten, medan resten samlas i **Andra**.

#### <a name="url-clicks"></a>URL-klick

När ett nätfiskemeddelande levereras till mottagarens inkorg eller mappen Skräppost är det alltid en chans att användaren klickar på payload-URL:en. Att inte klicka på URL:en är ett litet mått på framgång, men du måste avgöra varför nätfiskemeddelandet ens levererades till postlådan.

Om en användare har klickat på betalningsadressen i nätfiskemeddelandet visas åtgärderna i **området URL-klickningar** i diagrammet i vyn med kampanjinformation.

- **Tillåten**
- **BlockPage:** Mottagaren har klickat på webbadressen för nyttolasten, men åtkomsten till den skadliga webbplatsen har blockerats av en princip [för](safe-links.md) säkra länkar i organisationen.
- **BlockPageOverride:** Mottagaren klickade på payload-URL:en i meddelandet, säkra länkar försökte stoppa dem, men fick åsidosätta blockeringen. Kontrollera principerna [för säkra länkar](set-up-safe-links-policies.md) och se varför användarna tillåts åsidosätta safe Links-bedömningen och fortsätta till den skadliga webbplatsen.
- **VäntandeDetonationPage:** Säkra bifogade filer i Microsoft Defender för Office 365 arbetar med att öppna och undersöka nyttolast-URL:en i en virtuell datormiljö.
- **VäntandeDetonationPageOverride**: Mottagaren tillåts åsidosätta processen för nyttolast detonation och öppna URL-adressen utan att vänta på resultaten.

### <a name="tabs"></a>Flikar

Med flikarna i vyn kampanjinformation kan du undersöka kampanjen ytterligare.

> [!TIP]
> Informationen som visas på flikarna styrs av det skuggade datumintervallet på tidslinjen enligt beskrivningen i [avsnittet Kampanjinformation.](#campaign-information)

- **URL-klick:** Om användarna inte klickade på webbadressen för nyttolasten i meddelandet är det här avsnittet tomt. Om en användare kunde klicka på URL:en fylls följande värden i:
  - **Användare**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Klicktid**
  - **Klicka på bedömning**

- **Avsändar-IP**
  - **Sender IP**<sup>\*</sup>
  - **Totalt antal**
  - **Inkorg**
  - **Inte inkorg**
  - **SPF godkänd:** Avsändaren autentiserades av [Sender Policy Framework (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md) En avsändare som inte klarar SPF-verifieringen anger en oauthenticerad avsändare eller att meddelandet kapar en äkta avsändare.

- **Avsändare**
  - **Avsändare:** Det här är den faktiska avsändaradressen i kommandot SMTP MAIL FROM, som inte nödvändigtvis är från: e-postadressen som användarna ser i sina e-postklienter.
  - **Totalt antal**
  - **Inkorg**
  - **Inte inkorg**
  - **DKIM godkänd:** Avsändaren autentiserades av [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md). En avsändare som inte klarar DKIM-verifiering anger en oautherad avsändare eller att meddelandet förfalskning av en äkta avsändare.
  - **DMARC godkänd:** Avsändaren autentiserades med domänbaserad meddelandeautentisering, rapportering och [överensstämmelse (DMARC).](use-dmarc-to-validate-email.md) En avsändare som inte klarar DMARC-verifieringen anger en oaugen avsändare eller att meddelandet kapar en äkta avsändare.

- **Bifogade filer**
  - **Filnamn**
  - **SHA256**
  - **Familj för skadlig programvara**
  - **Totalt antal**

- **URL**
  - **URL**<sup>\*</sup>
  - **Totalt antal**

<sup>\*</sup> Om du klickar på det här värdet öppnas en ny utfällsida som innehåller mer information om det angivna objektet (användare, URL osv.) överst i vyn med kampanjinformation. Om du vill gå tillbaka till vyn med kampanjinformation klickar du **på Klar** i den nya utfällvyn.

### <a name="buttons"></a>Knappar

Med knapparna i vyn med kampanjinformation kan du använda kraften i HotUtforskaren för att undersöka kampanjen ytterligare.

- **Utforska kampanj:** Öppnar en ny sökflik i Hotutforskaren med **värdet kampanj-ID** som sökfilter.
- **Utforska inkorgar:** Öppnar en ny sökflik för Hotutforskaren med hjälp av **kampanj-ID** och **leveransplats: Inkorgen** som sökfilter.
