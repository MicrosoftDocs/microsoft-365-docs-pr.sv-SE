---
title: Kampanjvyer i ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Läs mer om kampanjvyer i det avancerade hotskyddet i Office 365.
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039484"
---
# <a name="campaign-views-in-atp"></a>Kampanjvyer i ATP

Kampanjvyer är en funktion i Advanced Threat Protection (ATP) i Security & Compliance Center som identifierar och kategoriserar nätfiskeattacker i tjänsten. Kampanjvyer kan hjälpa dig att:

- Effektivt undersöka och svara på phishing-attacker.

- Bättre förstå omfattningen av attacken.

- Visa värde för beslutsfattare.

Med kampanjvyer kan du se helheten av en attack snabbare och mer komplett än någon människa.

## <a name="what-is-a-campaign"></a>Vad är en kampanj?

En kampanj är en samordnad e-postattack mot en eller flera organisationer. E-postattacker som stjäl referenser och företagsdata är en stor och lukrativ bransch. I takt med att tekniken ökar i ett försök att stoppa attacker ändrar angripare sina metoder i ett försök att säkerställa fortsatt framgång.

Microsoft utnyttjar de stora mängderna anti-phishing, anti-spam och anti-malware data över hela tjänsten för att identifiera kampanjer. Vi analyserar och klassificerar attackinformationen enligt flera faktorer. Till exempel:

- **Attack källa:** Källan IP-adresser och avsändare e-domäner.

- **Attack meddelandeegenskaper:** Innehållet, stilen och tonen i meddelandena.

- **Attackmottagare:** Mottagare, mottagarjobbsfunktioner (administratörer, chefer osv.), företagstyper (stora, små, offentliga, privata osv.) och branscher.

- **Attack nyttolast:** Skadliga länkar, bilagor eller andra nyttolaster i meddelandena.

En kampanj kan vara kortlivad eller sträcka sig över flera dagar, veckor eller månader med aktiva och inaktiva perioder. En kampanj kan startas mot din specifika organisation, eller så kan din organisation vara en del av en större kampanj för flera företag.

## <a name="campaign-views-the-security--compliance-center"></a>Kampanjvyer säkerhets- & compliance center

Kampanjvyer är tillgängliga i [Security & Compliance Center](https://protection.office.com) vid **hothanteringskampanjer** \> **Campaigns**eller direkt på <https://protection.office.com/campaigns> .

![Översikt över kampanjer i Security & Compliance Center](../../media/campaigns-overview.png)

Du kan också komma åt kampanjvyer från:

- **Hantering av** \> hot **Explorer** \> **Visa** \> **Kampanjer**

- **Hantering av** \> hot **Explorer** \> **Visa** \> **Alla e-postmeddelanden** \> **Fliken Kampanj**

- **Hantering av** \> hot **Explorer** \> **Visa** \> **Phish (phish)** \> **Fliken Kampanj**

- **Hantering av** \> hot **Explorer** \> **Visa** \> **Skadlig kod** \> **Fliken Kampanj**

För att komma åt kampanjvyer måste du vara medlem i rollgrupperna **Organisationshantering,** **Säkerhetsadministratör**eller **Säkerhetsläsare** i säkerhets- & Compliance Center. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

## <a name="campaigns-overview"></a>Översikt över kampanjer

Översiktssidan visar information om alla kampanjer.

På fliken **Kampanj** visar området **Kampanjtyp** ett stapeldiagram som visar antalet mottagare per dag. Som standard visar diagrammet både **Phish-** och **Malware-data.**

> [!TIP]
> Om du inte ser några kampanjdata kan du prova att ändra datumintervallet eller [filtren](#filters-and-settings).

På sidan Översikt visas följande information på fliken **Kampanj:**

- **Namn**

- **Exempelämne**: Ämnesraden för ett av meddelandena i kampanjen. Observera att alla meddelanden i kampanjen inte nödvändigtvis har samma ämne.

- **Riktad**: Procentsatsen som beräknat med: (antalet kampanjmottagare i organisationen) / (det totala antalet mottagare i kampanjen i alla organisationer i tjänsten). Det här värdet anger i vilken utsträckning kampanjen är specifikt riktad till din organisation (ett högre värde) jämfört med andra organisationer i tjänsten (ett lägre värde).

- **Typ:** Detta värde är antingen **Phish** eller **Malware**.

- **Undertyp**: Det här värdet innehåller mer information om kampanjen. Till exempel:

  - **Phish**: Om tillgängligt, det varumärke som phished av denna kampanj. Till exempel `Microsoft` `365` , , , eller `Unknown` `Outlook` `DocuSign` .

  - **Skadlig kod:** Till exempel, `HTML/PHISH` eller `HTML/<MalwareFamilyName>` .

Om det finns, det varumärke som phished av denna kampanj. När identifieringen drivs av **ATP-teknik** läggs prefixet ATP till undertypsvärdet.

- **Mottagare**: Antalet användare som har riktats mot kampanjen.

- **Inkorg**: Antalet användare som har fått meddelanden från den här kampanjen i inkorgen (inte levererat till mappen Skräppost).

- **Klickade på**: Antalet användare som klickade på webbadressen eller öppnade den bifogade filen i nätfiskemeddelandet.

- **Klickfrekvens**: Procentsatsen som beräknas av "**Klickad**  /  **inkorg**". Det här värdet är en indikator på kampanjens effektivitet och om mottagarna kunde identifiera meddelandet som nätfiske och undvika att klicka på nyttolast-url:en.

  Observera att det här värdet inte används i kampanjer för skadlig kod.

- **Besökt:** Hur många användare som faktiskt gjorde det genom att nyttolasten webbplats. Om det finns klickade värden, men säkra länkar **blockeras** åtkomst till webbplatsen, kommer detta värde att vara noll.

På fliken **Kampanjursprung** visas meddelandekällorna på en världskarta.

### <a name="filters-and-settings"></a>Filter och inställningar

Högst upp på sidan Kampanjvyer finns det flera filter- och frågeinställningar som hjälper dig att hitta och isolera specifika kampanjer.

![Kampanjfilter](../../media/campaign-filters-and-settings.png)

Den mest grundläggande filtrering som du kan göra är startdatum/tid och slutdatum/-tid.

Om du vill filtrera vyn ytterligare kan du göra en enda egenskap med flera värden som filtrerar genom att klicka på knappen **Kampanjtyp,** göra ditt val och sedan klicka på **Uppdatera**.

De tillgängliga kampanjegenskaperna beskrivs i följande lista:

- Grundläggande

  - **Kampanjtyp:** Välj **Skadlig kod** eller **Phish**. När du rensar markeringarna får du samma resultat som att välja båda.
  - **Kampanjnamn**
  - **Undertyp för kampanj**
  - **Avsändare**
  - **Mottagare**
  - **Avsändningsdomän**
  - **Ämne**
  - **Filnamn för bifogad fil**
  - **Malware familj**
  - **Leveransåtgärd**
  - **Detektionsteknik**
  - **Taggar**
  - **System åsidosättningar**

- Avancerade

  - **Internet-meddelande-ID:** Tillgängligt i fältet **Meddelande-ID-huvud** i meddelandehuvudet. Ett exempelvärde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (notera vinkelparenteserna).
  
  - **Nätverksmeddelande-ID:** Ett GUID-värde som är tillgängligt i huvudfältet **X-MS-Exchange-Organization-Network-Message-Id** i meddelandehuvudet.
  
  - **IP-adress för avsändare**
  
  - **BIFOGAD FIL SHA256**: Om du vill hitta SHA256-hash-värdet för en fil i Windows kör du följande kommando i en kommandotolk: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  
  - **Kluster-ID**
  
  - **Princip-ID för aviseringar**

- Webbadresser

  - **URL-domän**
  - **URL-domän och url-sökväg**
  - **Url**
  - **URL-sökväg**
  - **Klicka dom**

Om du vill ha mer avancerad filtrering, inklusive filtrering efter flera egenskaper, kan du klicka på knappen **Avancerat filter** för att skapa en fråga. Samma kampanjegenskaper är tillgängliga, men med följande förbättringar:

- Du kan klicka på **Lägg till ett villkor** för att välja flera villkor.
- Du kan välja operatorn **Och** **eller Eller** mellan villkoren.
- Du kan välja objektet **Villkorsgrupp** längst ned i villkorslistan för att skapa komplexa sammansatta villkor.

När du är klar klickar du på knappen **Fråga.**

När du har skapat ett grundläggande eller avancerat filter kan du spara det med hjälp av **Spara fråga** eller **Spara fråga som**. När du senare går tillbaka till kampanjvyer kan du läsa in ett sparat filter genom att klicka på **Sparade frågeinställningar**.

Om du vill exportera diagrammet eller listan över kampanjer klickar du på **Exportera** och väljer **Exportera diagramdata** eller **Exportkampanjlista**.

Om du har en Microsoft Defender ATP-prenumeration kan du klicka på **WDATP** för att ansluta eller koppla från kampanjinformationen med Microsoft Defender ATP. Mer information finns i [Integrera Office 365 ATP med Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).

## <a name="campaign-details"></a>Information om kampanj

När du klickar på namnet på en kampanj visas kampanjinformationen i ett utfällbart utfällbart.

### <a name="campaign-information"></a>Kampanjinformation

Högst upp i kampanjinformationsvyn finns följande kampanjinformation tillgänglig:

- **ID**: Den unika kampanjidentifieraren.

- **Startad** och **avslutad:** Kampanjens startdatum och slutdatum. Observera att dessa datum kan sträcka sig längre än dina filterdatum som du har valt på översiktssidan.

- **Effekt**: Det här avsnittet innehåller följande data för det datumintervallfilter du valt (eller som du väljer på tidslinjen):
  
  - Det totala antalet mottagare.
  - Antalet meddelanden som var "Inkorged" (det vill än levereras till Inkorgen, inte till mappen Skräppost).
  - Hur många användare klickade på webbadressens nyttolast i nätfiskemeddelandet.
  - Howe många användare besökte webbadressen.

- **Riktad**: Procentsatsen som beräknat med: (antalet kampanjmottagare i organisationen) / (det totala antalet mottagare i kampanjen i alla organisationer i tjänsten). Observera att det här värdet beräknas under kampanjens hela livstid och inte ändrar filterdatumen.

- En interaktiv tidslinje för kampanjaktivitet: Tidslinjen visar aktivitet under kampanjens hela livstid. Som standard innehåller det skuggade området det datumintervallfilter som du valde i översikten. Du kan klicka och dra för att välja en viss startpunkt och slutpunkt, <u>som ändrar de data som visas i **Impact-området** och på resten av sidan enligt beskrivningen i nästa avsnitt</u>.

I namnlisten kan du klicka på knappen Hämta **kampanjbildning** Av att ladda ![ ned ](../../media/download-campaign-write-up-button.png) kampanjskrivningen för att hämta kampanjinformationen till ett Word-dokument (som standard med namnet CampaignReport.docx). Observera att det här dokumentet innehåller information under kampanjens hela livstid (inte bara de filterdatum du har valt).

![Kampanjinformation](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Kampanjflöde

I mitten av vyn kampanjinformation presenteras viktiga detaljer om kampanjen i avsnittet **Flöde** i ett vågrätt flödesdiagram (ett så kallat _Sankey-diagram)._ Dessa uppgifter hjälper dig att förstå delarna av kampanjen och den potentiella effekten i din organisation.

> [!TIP]
> Informationen som visas i **flödesdiagrammet** styrs av det skuggade datumintervallet i tidslinjen enligt beskrivningen i föregående avsnitt.

![Kampanjinformation som inte innehåller klick på användarens WEBBADRESS](../../media/campaign-details-no-recipient-actions.png)

Om du hovrar över ett vågrätt band i diagrammet visas antalet relaterade meddelanden (till exempel meddelanden från en viss käll-IP, meddelanden från käll-IP med den angivna avsändarendomänen osv.).

Diagrammet innehåller följande information:

- **Avsändare-IPs**

- **Avsändaredomäner**

- **Filtrera domar:** Dessa värden är relaterade till tillgängliga phishing och spam filtrering domar som beskrivs i [Anti-spam meddelande rubriker](anti-spam-message-headers.md). De tillgängliga värdena beskrivs i följande tabell:

  ||||
  |---|---|---|
  |**Värde**|**Spam filter dom**|**Beskrivning**|
  |**Tillåtet**|`SFV:SKN` <br/><br/> `SFV:SKI`|Meddelandet markerades som inte skräppost och/eller överhoppade filtrering innan det utvärderades av skräppostfiltrering (till exempel av en regel för e-postflöde, även känd som en transportregel).<br/><br/>Meddelandet hoppade över skräppostfiltrering av andra skäl (till exempel verkar avsändaren och mottagaren vara i samma organisation).|
  |**Blockerade**|`SFV:SKS`|Meddelandet markerades som skräppost innan det utvärderades av skräppostfiltrering (till exempel av en regel för e-postflöde).|
  |**Upptäckt**|`SFV:SPM`|Meddelandet markerades som skräppost av skräppostfiltret.|
  |**Har inte identifierats**|`SFV:NSPM`|Meddelandet markerades som inte skräppost genom skräppostfiltrering.|
  |**Släppt**|`SFV:SKQ`|Meddelandet hoppade över skräppostfiltrering eftersom det släpptes från karantänen.|
  |**Klient tillåt**<sup>\*</sup>|`SFV:SKA`|Meddelandet hoppade över skräppostfiltrering på grund av policyinställningar mot skräppost (till exempel var avsändaren med i listan över tillåtna avsändare eller tillåtna domänlistan).|
  |**Hyresgästblock**<sup>\*\*</sup>|`SFV:SKA`|Meddelandet blockerades av skräppostfiltrering på grund av policyinställningar mot skräppost (till exempel var avsändaren i listan över tillåtna avsändare eller tillåtna domänlistan).|
  |**Tillåt användare**<sup>\*</sup>|`SFV:SFE`|Meddelandet hoppade över skräppostfiltrering eftersom avsändaren fanns i en användares lista över betrodda avsändare i Outlook.|
  |**Användarblock**<sup>\*\*</sup>|`SFV:BLK`|Meddelandet blockerades av skräppostfiltrering eftersom avsändaren fanns i en användares lista blockerade avsändare i Outlook.|
  |**Zap**|ej|[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) vidtog åtgärder på det levererade meddelandet enligt dina anti-spam-principinställningar (flyttade till mappen Skräppost eller karantän).|
  |

  <sup>\*</sup>Granska dina policyer mot skräppost, eftersom det tillåtna meddelandet sannolikt skulle ha blockerats av tjänsten.

  <sup>\*\*</sup>Granska dina policyer mot skräppost, eftersom dessa meddelanden ska sättas i karantän, inte levereras.

- **Leveransplatser**: Du vill förmodligen undersöka meddelanden som faktiskt levererades till mottagarna (antingen till inkorgen eller mappen Skräppost), även om användarna inte klickade på nyttolast-URL:en i meddelandet. Du kan också ta bort meddelandena i karantän från karantänen. Mer information finns [i EOP i karantän](quarantine-email-messages.md).

  - **Borttagen mapp**
  - **Tappade**
  - **Externt**: Mottagaren finns i din lokala e-postorganisation i hybridmiljöer.
  - **Misslyckades**
  - **Vidarebefordras**
  - **Inkorg**
  - **Skräppostmapp**
  - **Karantän**
  - **Okänd**

- **URL-klick**: Dessa beskrivs i nästa avsnitt.

> [!NOTE]
> I alla lager som innehåller fler än 10 objekt visas de 10 översta objekten, medan resten buntas ihop i **Andra**.

#### <a name="url-clicks"></a>URL-klick

När ett nätfiskemeddelande levereras till en mottagare (till inkorgen eller mappen Skräppost) finns det alltid en chans att användaren klickar på nyttolastadressen. Att inte klicka på webbadressen i ett levererat meddelande är ett litet mått på framgång, men du måste ta reda på varför nätfiskemeddelandet levererades till deras postlåda från början.

Om en användare klickade på nyttolast-URL:en i nätfiskemeddelandet visas åtgärderna i området **URL-klick** i diagrammet i kampanjinformationsvyn.

- **Tillåtet**

- **BlockPage**: Mottagaren klickade på nyttolastens URL, men deras åtkomst till den skadliga webbplatsen blockerades av [ATP Safe Links-principerna](atp-safe-links.md) i organisationen.

- **BlockPageOverride**: Mottagaren klickade på nyttolastens URL i meddelandet, ATP Safe Links försökte stoppa dem, men de fick åsidosätta blocket. Du måste undersöka dina principer för [säkra länkar](set-up-atp-safe-links-policies.md) för att se varför användare tillåts åsidosätta domen om säkra länkar och fortsätta till den skadliga webbplatsen.

- **PendingDetonationPage**: ATP Säkra bilagor håller på att öppna nyttolast-URL:en i en virtuell datormiljö och se vad som händer.

- **PendingDetonationPageOverride**: Mottagaren tilläts åsidosätta detonationsprocessen för nyttolasten och öppna URL:en utan att vänta på resultatet.

### <a name="tabs"></a>Flikar

Med flikarna i vyn kampanjinformation kan du undersöka kampanjen ytterligare.

> [!TIP]
> Informationen som visas på flikarna styrs av det skuggade datumintervallet i tidslinjen enligt beskrivningen i avsnittet [Kampanjinformation.](#campaign-information)

- **URL-klick**: Om användarna inte klickade på nyttolastadressen i nätfiskemeddelandet är det här avsnittet tomt. Om en användare kunde klicka på webbadressen fylls följande värden i:

  - **Användaren**<sup>\*</sup>
  - **Url**<sup>\*</sup>
  - **Klicka på tid**
  - **Klicka dom**

- **Avsändare-IPs**

  - **IP-adress för avsändare**<sup>\*</sup>
  - **Totalt antal**
  - **Inkorg**
  - **Inte inkorg**
  - **SPF passerade:** Avsändaren autentiserades av [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md). En avsändare som inte skickar SPF-validering anger att avsändaren inte autentiseras eller att meddelandet förfalskar en legitim avsändare.

- **Avsändare**

  - **Avsändare**: Det här är den faktiska avsändaradressen i kommandot SMTP MAIL FROM, vilket inte nödvändigtvis är den Från: e-postadress som användarna ser i sina e-postklienter.
  - **Totalt antal**
  - **Inkorg**
  - **Inte inkorg**
  - **DKIM-skickaded:** Avsändaren autentiserades av [DKIM (Domain Keys Identified Mail).](support-for-validation-of-dkim-signed-messages.md) En avsändare som inte klarar DKIM-validering anger att avsändaren inte autentiseras eller att meddelandet förfalskar en legitim avsändare.
  - **DMARC-godkänd:** Avsändaren autentiserades av [Domänbaserad meddelandeautentisering, rapportering och konformance (DMARC)](use-dmarc-to-validate-email.md). En avsändare som inte klarar DMARC-validering anger att avsändaren inte autentiseras eller att meddelandet förfalskar en legitim avsändare.

- **Bilagor**

  - **Filnamn**
  - **SHA256 (SHA256)**
  - **Malware familj**
  - **Totalt antal**

- **Url**

  - **Url**<sup>\*</sup>
  - **Totalt antal**

<sup>\*</sup>Om du klickar på det här värdet öppnas ett nytt utfällbart objekt som innehåller mer information om det angivna objektet (användare, URL osv.) ovanpå kampanjinformationsvyn. Om du vill återgå till kampanjinformationsvyn klickar du på **Klar** i det nya utfällbara resultatet.

### <a name="buttons"></a>Knappar

Med knapparna i vyn kampanjinformation kan du använda kraften i Threat Explorer för att undersöka kampanjen ytterligare.

- **Utforska kampanj**: Öppnar en ny sökflik för Threat Explorer med värdet **Kampanj-ID** som sökfilter.

- **Utforska inkorgsmeddelanden:** Öppnar en ny sökflik för Hot Explorer med **kampanj-ID** och **leveransplats: Inkorgen** som sökfilter.
