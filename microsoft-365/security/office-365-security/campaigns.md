---
title: Kampanjmallar i Office 365 ATP-abonnemang
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Lär dig mer om kampanjmallar i Office 365 Avancerat skydd.
ms.openlocfilehash: 00af3f241bc1d9fd2cae9ebae0cdec7817679ed2
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430579"
---
# <a name="campaign-views-in-office-365-atp"></a>Kampanjvyer i Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Kampanjmallar är en funktion i abonnemanget Avancerat skydd (ATP) (till exempel Microsoft 365 E5 eller organisationer med ett ATP-abonnemang 2-tillägg). I vyn kampanjer i säkerhets & identifieras och kategoriseras nätfiske-attacker i tjänsten. Med hjälp av kampanjmallar kan du:

- Undersök och svara på nät fiske attacker effektivt.
- Bättre förståelse för attackens omfattning.
- Visa värde för besluts fattare.

Med kampanjmallar kan du se en stor bild av en attack snabbare och mer komplett än de som är på människa.

## <a name="what-is-a-campaign"></a>Vad är en kampanj?

En kampanj är en koordinerad e-postattack mot en eller flera organisationer. E-postattacker som stjälar uppgifter och företags data är en stor och Lucrative bransch. Eftersom teknikerna ökar för att förhindra attacker, ändrar angripare sina metoder för att säkerställa fortsatt framgång.

Microsoft utnyttjar de stora mängderna nätfiske, anti-spam och data mot skadlig program vara via hela tjänsten för att identifiera kampanjer. Vi analyserar och klassificerar angrepps informationen enligt flera faktorer. Till exempel:

- **Attack källa**: käll-IP-adresser och e-postdomäner.
- **Meddelande egenskaper**: innehåll, format och ton för meddelanden.
- **Mottagare**: hur mottagarna är relaterade. Till exempel mottagare och mottagare, arbets uppgifter (administratörer, chefer etc.), företags typer (stor, liten, offentlig, privat etc.) och branscher.
- **Attack-nyttolast**: illasinnade länkar, bifogade filer eller andra nytto laster i meddelanden.

En kampanj kan vara kort livs längd eller kunna omfatta flera dagar, veckor eller månader med aktiva och inaktiva perioder. En kampanj kan startas mot din specifika organisation, eller så kan din organisation vara en del av en större kampanj i flera företag.

## <a name="campaign-views-in-the-security--compliance-center"></a>Kampanjmallar i säkerhets & efterlevnad

Kampanjmallar är tillgängligt i [säkerhets & Compliance Center](https://protection.office.com) med kampanjer för **Threat Management** \> **Campaigns**eller direkt vid <https://protection.office.com/campaigns> .

![Översikt över kampanjer i säkerhets & Compliance Center](../../media/campaigns-overview.png)

Du kan också komma åt kampanjmallar från:

- **Threat Management** \> **Utforskaren** \> **Visa** \> **Kampanjer**

- **Threat Management** \> **Utforskaren** \> **Visa** \> **All e-post** \> Fliken **kampanj**

- **Threat Management** \> **Utforskaren** \> **Visa** \> **Phish** \> Fliken **kampanj**

- **Threat Management** \> **Utforskaren** \> **Visa** \> **Malware** \> Fliken **kampanj**

För att få åtkomst till kampanjmallar måste du vara medlem i roll grupperna **organisations hantering**, **säkerhets administratör**eller **säkerhets läsare** i säkerhets & efterlevnad. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

## <a name="campaigns-overview"></a>Översikt över kampanjer

Sidan översikt visar information om alla kampanjer.

På fliken standard **kampanj** visas ett stapeldiagram som visar antalet mottagare per dag i området **kampanj typ** . Som standard visar diagrammet både **Phish** och **malware** data.

> [!TIP]
> Om du inte ser några kampanj data kan du försöka ändra datum intervallet eller [filtren](#filters-and-settings).

På resten av översikts sidan visas följande information på fliken **kampanj** :

- **Namn**

- **Exempel ämne**: ämnes raden för ett av meddelandena i kampanjen. Observera att alla meddelanden i kampanjen inte nödvändigt vis har samma ämne.

- **Riktad**: den procents ATS som beräknas av: (antalet mottagare av kampanjen i organisationen)/(det totala antalet mottagare i kampanjen i alla organisationer i tjänsten). Det här värdet anger i vilken utsträckning kampanjen bara riktas in på din organisation (ett högre värde) kontra riktas till andra organisationer i tjänsten (ett lägre värde).

- **Typ**: det här värdet är antingen **Phish** eller **skadlig program vara**.

- **Undertyp**: det här värdet innehåller mer information om kampanjen. Till exempel:

  - **Phish**: där det är tillgängligt, det märke som phished av kampanjen. Till exempel, `Microsoft` ,,, `365` `Unknown` `Outlook` eller `DocuSign` .

  - **Skadlig kod**: till exempel `HTML/PHISH` eller `HTML/<MalwareFamilyName>` .

Där det är tillgängligt, det märke som phished av kampanjen. När identifieringen drivs av ATP-teknologin används prefixet **ATP-** och värdet för undertyp.

- **Mottagare**: antalet användare som är riktade till den här kampanjen.

- **Inkorgen**: antalet användare som fick meddelanden från den här kampanjen i sin inkorg (levereras inte till mappen skräp post).

- **Klickar**du på: antalet användare som klickade på URL-adressen eller öppnade den bifogade filen i nät fiske meddelandet.

- **Klicka på ränta**: procent satsen beräknat av "**klickade**på  /  **Inkorgen**". Detta värde är en indikator för kampanjens effektivitet. Med andra ord, om mottagarna kunde identifiera meddelandet som nätfiske, och om de inte klickade på nytto lastens URL.

  Observera att **Klicka på ränta** inte används i kampanjer med skadlig program vara.

- **Besökt**: hur många användare faktiskt gjorde det till nytto Last webbplatsen. Om du **klickade på** värden, men säkra länkar blockerade åtkomst till webbplatsen, är det här värdet noll.

På fliken **kampanj källa** visas meddelande källorna på en karta över hela världen.

### <a name="filters-and-settings"></a>Filter och inställningar

Högst upp på sidan kampanjmallar finns det flera filter-och frågeinställningar som hjälper dig att hitta och isolera specifika kampanjer.

![Kampanj filter](../../media/campaign-filters-and-settings.png)

Den mest grundläggande filtreringen du kan göra är start datum och slut tid.

Om du vill filtrera vyn ytterligare kan du utföra en enskild egenskap med filtrering av flera värden genom att klicka på knappen **kampanj typ** , välja och sedan klicka på **Uppdatera**.

De tillgängliga kampanj egenskaperna beskrivs i följande lista:

- Basic

  - **Kampanj typ**: Välj **skadlig** eller **Phish**. Om du avmarkerar valen är det samma resultat som att markera båda.
  - **Kampanj namn**
  - **Kampanj under typ**
  - **Avsändare**
  - **Mottagarna**
  - **Avsändningsdomän**
  - **Ämne**
  - **Namn på bifogad fil**
  - **Familjen skadlig program vara**
  - **Leverans åtgärd**
  - **Detekterings teknologi**
  - **Taggen**
  - **Systemåsidosättningar**

- Avancerat

  - **Internet meddelande-ID**: tillgängligt i fältet **meddelande-ID** i meddelande huvudet. Ett exempel värde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observera vinkelparenteser).
  
  - **ID för nätverks meddelande**: ett GUID-värde som är tillgängligt i huvudet **X-MS-Exchange-Organization-Network-meddelande-ID** i meddelande huvudet.
  
  - **Avsändarens IP**
  
  - **Bilaga SHA256**: om du vill hitta SHA256-hash-värdet för en fil i Windows kör du följande kommando i kommando tolken: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  
  - **Kluster-ID**
  
  - **ID för aviserings policy**

- Garanteras

  - **URL-domän**
  - **URL-domän och sökväg**
  - **:**
  - **URL-sökväg**
  - **Klicka på Verdict**

För mer avancerad filtrering, inklusive filtrering efter flera egenskaper, kan du klicka på knappen **Avancerat filter** för att skapa en fråga. Samma kampanj egenskaper är tillgängliga, men med följande förbättringar:

- Du kan klicka på **Lägg till ett villkor** för att välja flera villkor.
- Du kan välja operatorerna **och** eller **eller** mellan villkoren.
- Du kan markera **villkors gruppen** längst ned i listan villkor för att bilda komplexa sammansatta förhållanden.

När du är klar klickar du på knappen **fråga** .

När du har skapat ett grundläggande eller Avancerat filter kan du spara det genom att använda **Spara fråga** eller **Spara fråga som**. Senare när du återvänder till kampanjmallar kan du läsa in ett sparat filter genom att klicka på **Inställningar för sparade frågor**.

Om du vill exportera diagrammet eller listan med kampanjer klickar du på **Exportera** och väljer **Exportera diagram data** eller **Exportera kampanj lista**.

Om du har en Microsoft Defender ATP-prenumeration kan du klicka på **WDATP** för att koppla eller koppla bort kampanj informationen med Microsoft Defender ATP. Mer information finns i [integrera Office 365 ATP med Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).

## <a name="campaign-details"></a>Kampanj uppgifter

När du klickar på namnet på en kampanj visas kampanj informationen i en utfällbar lista.

### <a name="campaign-information"></a>Kampanj information

Högst upp i vyn kampanj information är följande kampanj information tillgänglig:

- **ID**: unika kampanj-ID.

- **Startat** och **avslutat**: start datum och slutdatum för kampanjen. Observera att dessa datum kanske sträcker sig längre än de filter datum som du valde på översikts sidan.

- **Effekt**: det här avsnittet innehåller följande data för det datum intervall som du valde (eller som du väljer i tids linjen):
  
  - Totalt antal mottagare.
  - Antalet meddelanden som "Inkorg" (det vill säga levereras till Inkorgen, inte till mappen skräp post).
  - Hur många användare klickar på URL-nyttolasten i nät fiske meddelandet.
  - Howe många användare besöker URL-adressen.

- **Riktad**: den procents ATS som beräknas av: (antalet mottagare av kampanjen i organisationen)/(det totala antalet mottagare i kampanjen i alla organisationer i tjänsten). Observera att det här värdet beräknas under hela kampanjens livstid och inte ändras utifrån datum filter.

- En interaktiv tids linje med kampanj aktivitet: tids linjen visar aktivitet under hela kampanjens livstid. Som standard innehåller det skuggade området det datum intervall som du valde i översikten. Du kan klicka och dra för att välja en specifik start punkt och slut punkt, <u>som ändrar informationen som visas i området **påverkan** och på resten av sidan enligt beskrivningen i nästa avsnitt</u>.

I namn listen kan du klicka på knappen **Hämta kampanjens uppskrivnings** ![ ikon för att hämta kampanj ](../../media/download-campaign-write-up-button.png) informationen till ett Word-dokument (som standard heter CampaignReport.docx). Observera att nedladdningen innehåller information under hela kampanjens livstid (inte bara valda filter datum).

![Kampanj information](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Kampanj flöde

I vyn kampanj information visas viktig information om kampanjen i **flödet** i ett vågrätt flödes diagram (kallas ett _Sankey_ -diagram). Dessa uppgifter hjälper dig att förstå vad som händer med kampanjen och hur de kan påverka din organisation.

> [!TIP]
> Informationen som visas i **flödes** diagrammet styrs av det skuggade datum intervallet på tids linjen enligt beskrivningen i föregående avsnitt.

![Kampanj uppgifter som inte innehåller användar-URL-musklick](../../media/campaign-details-no-recipient-actions.png)

Om du hovrar över ett vågrätt band i diagrammet visas antalet relaterade meddelanden (till exempel meddelanden från en viss käll-IP, meddelanden från käll-IP med den angivna avsändarens domän osv.).

Diagrammet innehåller följande information:

- **Avsändare**

- **Avsändare**

- **Filter verdicts**: Verdict-värden är relaterade till de tillgängliga phishing-och skräp post filtrerings verdicts som beskrivs i [meddelandehuvuden](anti-spam-message-headers.md). De tillgängliga värdena beskrivs i följande tabell:

  ****

  |Value|Skräp post filter Verdict|Beskrivning|
  |---|---|---|
  |**Möjlighet**|`SFV:SKN` <br/><br/> `SFV:SKI`|Meddelandet har marker ATS som icke skräp post och/eller ignorerade filtrering innan skräp post filtrering. Meddelandet markerades till exempel som inte skräp post av en regel för e-postflöde (kallas även transport regel).<br/><br/>Meddelandet ignorerade spam av andra orsaker. Avsändaren och mottagaren ser till exempel ut i samma organisation.|
  |**Blockering**|`SFV:SKS`|Meddelandet har marker ATS som skräp post innan det utvärderas av skräp post filtrering. Till exempel med en regel för e-postflöde.|
  |**Upptäckte**|`SFV:SPM`|Meddelandet markerades som skräppost av skräppostfiltret.|
  |**Identifieras inte**|`SFV:NSPM`|Meddelandet har marker ATS som inte skräp post av filtrering av skräp post.|
  |**Levereras**|`SFV:SKQ`|Meddelandet hoppade över skräp post filtrering eftersom det släpptes från karantän.|
  |**Tillåt klient organisation**<sup>\*</sup>|`SFV:SKA`|Meddelandet hoppade över skräp post filtrering på grund av inställningarna i en policy för skräp post. Avsändaren fanns till exempel i listan över tillåtna avsändare eller tillåtna domäner.|
  |**Klient blockering**<sup>\*\*</sup>|`SFV:SKA`|Meddelandet blockerades av filtrering av skräp post på grund av inställningarna i en policy för skräp post. Avsändaren fanns till exempel i listan över tillåtna avsändare eller tillåtna domäner.|
  |**Tillåt användare**<sup>\*</sup>|`SFV:SFE`|Meddelandet hoppade över skräp post filtrering eftersom avsändaren fanns i en användares lista med betrodda avsändare.|
  |**User block**<sup>\*\*</sup>|`SFV:BLK`|Meddelandet blockerades av skräp post filtrering eftersom avsändaren fanns i en användares lista över spärrade avsändare.|
  |**ZAP**|ej tillämpligt|[Automatisk rensning av Tom timme (Zap)](zero-hour-auto-purge.md) flyttade det levererade meddelandet till mappen skräp post eller karantän. Du konfigurerar åtgärden i policyn för skydd mot skräp post.|
  |

  <sup>\*</sup> Granska dina skydd mot skräp post eftersom det tillåtna meddelandet förmodligen har blockerats av tjänsten.

  <sup>\*\*</sup> Granska dina principer för skräp post, eftersom dessa meddelanden bör vara i karantän, inte levereras.

- **Leverans ställen**: du kommer troligen att behöva undersöka meddelanden som har levererats till mottagarna (antingen till Inkorgen eller mappen skräp post), även om användarna inte klickar på nytto lastens URL i meddelandet. Du kan också ta bort meddelanden i karantänen från karantänen. Mer information finns i [e-postmeddelanden i karantän i EOP](quarantine-email-messages.md).

  - **Borttagen mapp**
  - **Avbröts**
  - **Externt**: mottagaren finns i din lokala e-postorganisation i hybrid miljöer.
  - **Misslyckades**
  - **Vidarekopplas**
  - **Brevlåda**
  - **Skräppostmappen**
  - **Karantän**
  - **Okänd**

- **URL-musklick**: de här värdena beskrivs i nästa avsnitt.

> [!NOTE]
> I alla lager som innehåller fler än 10 objekt visas de 10 översta objekten, medan resten samlas samman i **andra**.

#### <a name="url-clicks"></a>URL-klickningar

När ett nät fiske meddelande levereras till en mottagares inkorg eller mapp för skräp post kan användaren klicka på nytto lastens URL-adress. Att klicka på URL-adressen är en liten mått på framgång, men du måste fastställa varför nät fiske meddelandet levererades till post lådan.

Om en användare klickar på nytto lastens URL i nät fiske meddelandet visas åtgärderna i området URL- **klickning** i diagrammet i vyn kampanj information.

- **Möjlighet**

- **BlockPage**: mottagaren klickade på nytto lastens URL, men deras åtkomst till den illasinnade webbplatsen blockerades av en princip för [säkra länkar](atp-safe-links.md) i organisationen.

- **BlockPageOverride**: mottagaren klickade på nytto lastens URL i meddelandet, men säkra länkar försökte stoppa dem, men de har kunnat åsidosätta blocket. Undersök dina [principer för säkra länkar](set-up-atp-safe-links-policies.md) för att se varför användare tillåts att åsidosätta Safe Links-Verdict och fortsätta till den illasinnade webbplatsen.

- **PendingDetonationPage**: säkra bilagor i Office 365 ATP är att öppna och undersöka nytto lastens URL i en virtuell dator miljö.

- **PendingDetonationPageOverride**: mottagaren har fått tillåtelse att åsidosätta nytto toner processen och öppna URL: en utan att vänta på resultaten.

### <a name="tabs"></a>TABB

Flikarna i vyn kampanj information gör att du kan undersöka kampanjen ytterligare.

> [!TIP]
> Informationen som visas på flikarna styrs av det skuggade datum intervallet i tids linjen enligt beskrivningen i avsnittet [kampanj information](#campaign-information) .

- **URL klickar**på: om användare inte klickar på nytto lastens URL i meddelandet är det här avsnittet tomt. Om en användare kunde klicka på URL-adressen fylls följande värden i:

  - **Användarläge**<sup>\*</sup>
  - **:**<sup>\*</sup>
  - **Klicka på tid**
  - **Klicka på Verdict**

- **Avsändare**

  - **Avsändarens IP**<sup>\*</sup>
  - **Totalt antal**
  - **Inkorgen**
  - **Inte i Inkorgen**
  - **SPF skickades**: avsändaren autentiserades av [SPF (avsändare Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md). En avsändare som inte skickar SPF-verifiering indikerar en oautentiserad avsändare eller meddelandet har falskats för en legitim avsändare.

- **Avsändare**

  - **Avsändare**: det här är den faktiska avsändar adressen i SMTP e-postmeddelandet, som inte nödvändigt vis är den e-postadress som användarna ser i sina e-postklienter.
  - **Totalt antal**
  - **Inkorgen**
  - **Inte i Inkorgen**
  - **DKIM lyckades**: avsändaren autentiserades av [domän nycklar som identifieras via e-post (DKIM)](support-for-validation-of-dkim-signed-messages.md). En avsändare som inte skickar DKIM verifiering indikerar en overifierad avsändare eller meddelandet har falskats för en legitim avsändare.
  - **DMARC skickades**: avsändaren autentiserades av [domänbaserad autentisering, rapportering och omslutande (DMARC)](use-dmarc-to-validate-email.md). En avsändare som inte skickar DMARC verifiering indikerar en overifierad avsändare eller meddelandet har falskats för en legitim avsändare.

- **Bifogade filer**

  - **Datafil**
  - **SHA256**
  - **Familjen skadlig program vara**
  - **Totalt antal**

- **:**

  - **:**<sup>\*</sup>
  - **Totalt antal**

<sup>\*</sup> Om du klickar på det här värdet öppnas en ny utfällare som innehåller mer information om det angivna objektet (användare, URL: er osv.). Om du vill gå tillbaka till vyn kampanj Detaljer klickar du på **klar** i den nya utfällbara menyn.

### <a name="buttons"></a>Pilknapp

Med knapparna i vyn kampanj information kan du använda privilegiet mot hot Explorer för att undersöka kampanjen.

- **Utforska kampanjen**: öppna en ny Threat Explorer-fliken Sök med hjälp av värdet för **kampanj-ID** som Sök filter.

- **Utforska meddelanden i Inkorgen**: öppnar en ny webbplats Sök-flik med **kampanj-ID** och **leverans plats: Inkorgen** som Sök filter.
