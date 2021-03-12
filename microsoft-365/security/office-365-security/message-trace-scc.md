---
title: Meddelandespårning i Säkerhets- och efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan använda meddelandespårning i Säkerhets- och & för att ta reda på vad som har hänt med meddelanden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c3f7e4bc9624b9fae48074203da525d7a504a12
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741581"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Meddelandespårning i Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="message-trace-features"></a>Funktioner för meddelandespårning

Meddelandespårning i säkerhets- & efterlevnadscenter följer e-postmeddelanden när de färdas genom din Exchange Online-organisation. Du kan avgöra om ett meddelande har tagits emot, avvisats, skjutits upp eller levererats av tjänsten. Det visar också vilka åtgärder som har vidtagits för meddelandet innan det nått sin slutgiltiga status.

Meddelandespårning i Säkerhets- & kompatibilitetscenter förbättrar den ursprungliga meddelandespårningen som var tillgänglig i Exchange admin center (EAC). Du kan använda informationen från meddelandespårning för att effektivt svara på användarfrågor om vad som har hänt med meddelanden, felsöka problem i e-postflödet och verifiera principändringar.

> [!NOTE]
>
> - För att kunna göra en meddelandespårning måste du vara medlem i rollgrupperna Organisationshantering, Efterlevnadshantering eller Support. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
>
> - Det maximala antalet meddelanden som visas i resultatet beror på vilken rapporttyp du har valt (mer information finns [i](#choose-report-type) avsnittet Välj rapporttyp). [Cmdlet:en Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) i Exchange Online PowerShell eller fristående EOP PowerShell returnerar alla meddelanden i resultatet.

## <a name="open-message-trace"></a>Öppna meddelandespårning

1. Öppna Säkerhets- & efterlevnadscenter på <https://protection.office.com> .

2. Expandera **e-postflödet** och välj sedan **Meddelandespårning**.

## <a name="message-trace-page"></a>Sidan Meddelandespårning

Härifrån kan du starta en ny standardspårning genom att klicka på **knappen Starta en** spårning. Då söker du efter alla meddelanden för alla avsändare och mottagare under de senaste två dagarna. Du kan också använda en av de lagrade frågorna från tillgängliga frågekategorier och antingen köra dem som de är eller använda dem som utgångspunkt för dina egna frågor:

- **Standardfrågor:** Inbyggda frågor från Microsoft 365.

- **Anpassade frågor:** Frågor som sparas av administratörer i organisationen för framtida bruk.

- **Automatisktsparade frågor**: De senaste tio senaste körningsfrågorna. I den här listan är det enkelt att fortsätta där du slutade.

På den här sidan finns **även ett avsnitt** med nedladdningsbara rapporter för de begäranden du har skickat in, samt själva rapporterna när det finns tillgängliga för nedladdning.

## <a name="options-for-a-new-message-trace"></a>Alternativ för en ny meddelandespårning

### <a name="filter-by-senders-and-recipients"></a>Filtrera efter avsändare och mottagare

Standardvärdena är **Alla avsändare och** Alla **mottagare,** men du kan använda följande fält för att filtrera resultatet:

- **Av de här personerna:** Klicka i det här fältet om du vill välja en eller flera avsändare från organisationen. Du kan också börja skriva ett namn så filtreras objekten i listan efter vad du har skrivit, ungefär som en söksida fungerar.

- **Till de här** personerna: Klicka i det här fältet för att välja en eller flera mottagare i organisationen.

> [!NOTE]
>
> - Du kan också skriva e-postadresserna till externa avsändare och mottagare. Jokertecken stöds (till exempel ), men du kan inte använda flera jokerteckenposter i samma `*@contoso.com` fält på samma gång.
>
> - Du kan klistra in flera avsändare eller mottagare, avgränsade med semikolon ( `;` ). blanksteg ( `\s` ), vagnreturer ( `\r` ) eller nästa rader ( `\n` ).

### <a name="time-range"></a>Tidsperiod

Standardvärdet är **2 dagar,** men du kan ange datum-/tidsintervall på upp till 90 dagar. När du använder datum-/tidsintervall bör du tänka på följande:

- Som standard kan du välja tidsintervallet i **skjutreglaget** i en tidslinje. Du kan bara välja de dag- eller tidsinställningar som visas. Om du försöker välja ett värde mellan kommer start-/slutbubblan att fästas mot den närmaste visade inställningen.

  ![Ett skjutreglage med ett tidsintervall i en ny meddelandespårning i & Säkerhets- och efterlevnadscenter](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  Men du kan också  växla till vyn Anpassad där  du kan ange värden för Startdatum  och Slutdatum (inklusive tider), och du kan också välja Tidszon för datum/tidsintervall.  Observera att **tidszonsinställningen** gäller både för frågeindata och frågeresultatet.

  ![Ett anpassat tidintervall i en ny meddelandespårning i säkerhets- & säkerhets- och efterlevnadscenter](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  I mindre än 10 dagar visas resultaten  direkt som en sammanfattningsrapport. Om du anger ett tidsperiod som är ännu något större än 10 dagar fördröjs resultatet eftersom det bara är tillgängligt som en nedladdningsbar CSV-fil **(Utökad** sammanfattning eller **Utökade** rapporter).

  Mer information om de olika rapporttyperna finns i avsnittet [Välj rapporttyp](#choose-report-type) i den här artikeln.

  > [!NOTE]
  > Förbättrad sammanfattning och utökade rapporter förbereds med arkiverade meddelandespårningsdata och det kan ta flera timmar innan rapporten är tillgänglig för nedladdning. Beroende på hur många andra administratörer som också har skickat rapportförfrågningar samtidigt kan du också märka en fördröjning innan bearbetningen startar för din i köade begäran.

- När du sparar en fråga **i** skjutreglagevyn sparas det relativa tidsperioden (till exempel tre dagar från i dag). När du  sparar en fråga i vyn Anpassad sparas absolut datum-/tidsintervall (t.ex. 2018-05-06 13:00 till 2018-05-08 18:00).

### <a name="more-search-options"></a>Fler sökalternativ

#### <a name="delivery-status"></a>Leveransstatus

Du kan låta standardvärdet **Alla vara** markerat eller så kan du välja något av följande värden för att filtrera resultatet:

- **Levererad**: Meddelandet levererades till den avsedda destinationen.

- **Väntande:** Leverans av meddelandet försöker eller försöker på nytt.

- **Expanderat:** En mottagare i distributionsgruppen expanderades innan den levereras till de enskilda medlemmarna i gruppen.

- **Misslyckades:** Meddelandet levererades inte.

- **I karantän:** Meddelandet har satts i karantän (som skräppost, massutskick eller nätfiske). Mer information finns i [EOP i karantän.](quarantine-email-messages.md)

- **Filtrerad som skräppost:** Meddelandet identifierades som skräppost och avvisades eller blockerades (inte i karantän).

- **Hämtar status:** Meddelandet togs nyligen emot av Microsoft 365, men inga andra statusdata är ännu tillgängliga. Titta in igen om några minuter.

> [!NOTE]
> Värdena **Väntande, I** **karantän och** Filter som **skräppost** är bara tillgängliga för sökningar som är mindre än 10 dagar. Det kan också finnas en fördröjning på 5 till 10 minuter mellan den faktiska och rapporterade leveransstatusen.

#### <a name="message-id"></a>Meddelande-ID

Det här är det Internetmeddelande-ID (kallas även klient-ID) som finns i fältet **Meddelande-ID:** sidhuvud i meddelandehuvudet. Användarna kan ge dig det här värdet för att undersöka specifika meddelanden.

Det här värdet är konstant under meddelandets livslängd. För meddelanden som skapas i Microsoft 365 eller Exchange är värdet i formatet , inklusive `<GUID@ServerFQDN>` vinkelparenteser ( \< \> ). Till exempel `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Andra meddelandesystem kan använda andra syntax eller värden. Detta värde ska vara unikt, men inte alla e-postsystem strikt följer detta krav. Om fältet **Meddelande-ID:** rubrik inte finns eller är tomt för inkommande meddelanden från externa källor tilldelas ett godtyckligt värde.

När du **filtrerar resultatet med meddelande-ID** ska du inkludera hela strängen inklusive vinkelparenteser.

#### <a name="direction"></a>Riktning

Du kan lämna  standardvärdet Alla markerat eller välja **Inkommande** (meddelanden som skickas till mottagare i organisationen) eller Utgående **(meddelanden** som skickas från användare i organisationen) om du vill filtrera resultaten.

#### <a name="original-client-ip-address"></a>Ursprungliga klientens IP-adress

Du kan filer resultaten efter klientens IP-adress för att undersöka hackade datorer som skickar stora mängder skräppost eller skadlig programvara. Även om meddelandena ser ut att komma från flera avsändare är det troligt att samma dator genererar alla meddelanden.

> [!NOTE]
> Informationen om klientens IP-adress är endast tillgänglig i 10  dagar och finns bara tillgänglig i rapporterna Utökad sammanfattning eller Utökade rapporter (nedladdningsbara CSV-filer). 

### <a name="choose-report-type"></a>Välj rapporttyp

De tillgängliga rapporttyperna är:

- **Sammanfattning**: Tillgängligt om tidsperioden är mindre än 10 dagar och inte kräver några ytterligare filtreringsalternativ. Resultatet blir nästan tillgängligt direkt när du klickar på **Sök**. Rapporten returnerar upp till 2 000 resultat.

- **Förbättrad sammanfattning** eller Utökad: De här rapporterna är endast tillgängliga som nedladdningsbara CSV-filer och kräver ett eller flera av följande filtreringsalternativ oavsett **tidsperiod:** För dessa personer , Till dessa personer eller **Meddelande-ID**.  Du kan använda jokertecken för avsändare eller mottagare (till exempel \* @contoso.com). Den förbättrade sammanfattningsrapporten returnerar upp till 5 000 resultat. Den utökade rapporten returnerar upp till 1 000 resultat.

> [!NOTE]
>
> - Förbättrad sammanfattning och utökade rapporter förbereds med arkiverade meddelandespårningsdata och det kan ta flera timmar innan rapporten kan laddas ned. Beroende på hur många andra administratörer som också har skickat rapportförfrågningar samtidigt kan du också märka en fördröjning innan den i köde begäran börjar bearbetas.
>
> - Du kan välja en Utökad sammanfattning eller Utökad rapport för ett datum-/tidsintervall, men vanligtvis är de sista fyra timmarna med arkiverade data ännu inte tillgängliga för dessa två typer av rapporter.
>
> - Den maximala storleken för en nedladdningsbar rapport är 500 MB. Om en nedladdningsbar rapport överskrider 500 MB kan du inte öppna rapporten i Excel eller Anteckningar.

När du klickar på Nästa visas en sammanfattningssida med de filtreringsalternativ som du har valt, en unik (redigerbar) rubrik för rapporten och den e-postadress som får meddelandet när meddelandespårningen har slutförts (också redigerbara och måste finnas i någon av organisationens godkända domäner). Klicka **på Förbered rapport** för att skicka meddelandespårningen. På **huvudsidan Meddelandespårning** kan du se status för rapporten i avsnittet **Nedladdningsbara** rapporter.

Mer information om den information som returneras i de olika rapporttyperna finns i nästa avsnitt.

## <a name="message-trace-results"></a>Resultat från meddelandespårning

De olika rapporttyperna returnerar olika informationsnivåer. Den information som är tillgänglig i de olika rapporterna beskrivs i följande avsnitt.

### <a name="summary-report-output"></a>Sammanfattningsrapportresultat

När du har kört meddelandespårningen visas resultatet, sorterat efter fallande datum/tid (senaste först).

![Sammanfattningsrapportresultat för meddelandespårning i Säkerhets- & Säkerhets- och efterlevnadscenter](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Sammanfattningsrapporten innehåller följande information:

- **Datum:** Datum och tid då meddelandet togs emot av tjänsten med hjälp av den konfigurerade UTC-tidszonen.

- **Avsändare**: E-postadressen till avsändaren ( @ *aliasdomän*).

- **Mottagare**: Mottagarens eller mottagarnas e-postadress. Ett meddelande som skickas till flera mottagare visas på en rad per mottagare. Om mottagaren är en distributionsgrupp, dynamisk distributionsgrupp eller e-postaktiverad säkerhetsgrupp blir gruppen den första mottagaren och sedan varje medlem i gruppen på en separat rad.

- **Ämne**: De första 256 tecknen i meddelandets **Ämne: fält.**

- **Status:** Dessa värden beskrivs i [avsnittet Leveransstatus.](#delivery-status)

Som standard läses de första 250 resultaten in och är tillgängliga. När du rullar nedåt finns det en liten paus när nästa uppsättning resultat läses in. I stället för att  rulla kan du klicka på Läs in alla för att läsa in alla resultat upp till maximalt 10 000.

Du kan klicka på kolumnrubrikerna för att sortera resultatet efter värdena i kolumnen i stigande eller fallande ordning.

Du kan klicka **på Filtrera** resultat om du vill filtrera resultatet med en eller flera kolumner.

Du kan exportera resultaten när du har markerat  en eller flera rader genom att klicka på Exportera resultat och sedan välja Exportera alla **resultat,** **Exportera** inlästa resultat eller **Exportera markerat**.

#### <a name="find-related-records-for-this-message"></a>Hitta relaterade poster för det här meddelandet

Relaterade meddelandeposter är poster som delar samma meddelande-ID. Kom ihåg att även ett enskilt meddelande som skickas mellan två personer kan generera flera poster. Antalet poster ökar när meddelandet påverkas av distributionsgruppsexpansion, vidarebefordran, e-postflödesregler (kallas även transportregler), osv.

När du har markerat en rads kryssruta kan du  hitta relaterade poster för  meddelandet genom att klicka på knappen Sök relaterat som visas eller genom att välja Fler alternativ Fler alternativ Hitta relaterade poster för det ![ här ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **meddelandet**).

Mer information om meddelande-ID finns i avsnittet Meddelande-ID tidigare i den här artikeln.

#### <a name="message-trace-details"></a>Information om meddelandespårning

I sammanfattningsrapportens utdata kan du visa information om ett meddelande med någon av följande metoder:

- Markera raden (klicka någonstans på raden utom kryssrutan).

- Markera radens kryssruta och klicka på **Fler alternativ** Mer ![ visa ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **meddelandeinformation**.

   ![Information när du dubbelklickar på en rad i meddelandespårningen för sammanfattningsrapporten visas i & säkerhets- och efterlevnadscenter](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

Informationen om meddelandespårningen innehåller ytterligare information som inte finns med i sammanfattningsrapporten:

- **Meddelandehändelser:** Det här avsnittet innehåller klassificeringar som hjälper till att kategorisera de åtgärder som tjänsten vidtar för meddelanden. **Här är några av de mest intressanta** händelser som du kan stöta på:

  - **Ta** emot: Meddelandet togs emot av tjänsten.

  - **Skicka:** Meddelandet skickades av tjänsten.

  - **Fel:** Meddelandet kunde inte levereras.

  - **Leverera:** Meddelandet levererades till en postlåda.

  - **Expandera**: Meddelandet skickades till en distributionsgrupp som expanderats.

  - **Överföring:** Mottagare har flyttats till ett nytt meddelande på grund av innehållskonvertering, begränsningar för meddelandemottagare eller representanter.

  - **Skjut upp:** Meddelandeleveransen har skjutits upp och kan försökas igen senare.

  - **Löst:** Meddelandet omdirigerades till en ny mottagaradress baserat på ett active directory-upp slå upp. När detta händer visas den ursprungliga mottagaradressen på en separat rad i meddelandespårningen tillsammans med meddelandets slutgiltiga leveransstatus.

  > [!NOTE]
  > 
  > - Ett ojämnt meddelande som har levererats genererar flera **händelseposter** i meddelandespårningen.
  > 
  > - Listan är inte uttömmande. Beskrivningar av fler händelser finns i [Händelsetyper i meddelandespårningsloggen](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log). Observera att den här länken är ett ämne för Exchange Server (lokal Exchange).

- **Mer information:** Det här avsnittet innehåller följande information:

  - **Meddelande-ID:** Det här värdet beskrivs i [avsnittet Meddelande-ID](#message-id) tidigare i den här artikeln. Till exempel `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Meddelandestorlek**

  - **Från IP:** IP-adressen för den dator som skickade meddelandet. För utgående meddelanden som skickas från Exchange Online är det här värdet tomt.

  - **Till IP:** IP-adressen eller adresserna där tjänsten försökte leverera meddelandet. Om meddelandet har flera mottagare visas de. För inkommande meddelanden som skickas till Exchange Online är det här värdet tomt.

### <a name="enhanced-summary-reports"></a>Förbättrade sammanfattningsrapporter

Tillgängliga (slutförda) utökade sammanfattningsrapporter är tillgängliga **i avsnittet Hämtningsbara rapporter** i början av meddelandespårningen. Följande information är tillgänglig i rapporten:

- **origin_timestamp:** Datum och tid då meddelandet ursprungligen togs emot av tjänsten med hjälp av <sup>*</sup> den konfigurerade UTC-tidszonen.

- **sender_address:** Avsändarens e-postadress ( @ *aliasdomän*).

- **Recipient_status:** Status för leveransen av meddelandet till mottagaren. Om meddelandet skickades till flera mottagare visas alla mottagare och motsvarande status för dem i formatet: \<*email address*\> ## \<*status*\> . Ett exempel:

  - **##Receive innebär Skicka** att meddelandet togs emot av tjänsten och skickades till den avsedda destinationen.

  - **##Receive, Fail** innebär att meddelandet togs emot av tjänsten men leveransen till den avsedda destinationen misslyckades.

  - **##Receive, Deliver** innebär att meddelandet togs emot av tjänsten och levererades till mottagarens postlåda.

- **message_subject:** De första 256 tecknen i meddelandets **Ämnesfält.**

- **total_bytes:** Storleken på meddelandet i byte, inklusive bifogade filer.

- **message_id:** Det här värdet beskrivs i avsnittet [Meddelande-ID](#message-id) tidigare i den här artikeln. Till exempel `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id:** Ett unikt värde för meddelande-ID som finns kvar i alla kopior av meddelandet som kan skapas på grund av expandering eller distributionsgruppsexpansion. Ett exempelvärde är `1341ac7b13fb42ab4d4408cf7f55890f` .

- **original_client_ip:** IP-adressen för avsändarens klient.

- **riktning :** Anger om meddelandet skickades inkommande (1) till din organisation eller om det skickades utgående (2) från din organisation.

- **connector_id**: Namnet på källan eller målkopplingen. Mer information om kopplingar i Exchange Online finns i Konfigurera [e-postflöde med kopplingar i Office 365.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- **delivery_priority** <sup>*</sup> : Om meddelandet skickades med **hög,** **låg** eller **normal** prioritet.

<sup>*</sup> De här egenskaperna är endast tillgängliga i rapporter med utökade sammanfattningar.

### <a name="extended-reports"></a>Utökade rapporter

Tillgängliga (slutförda) utökade rapporter är tillgängliga **i avsnittet Nedladdningsbara rapporter** i början av meddelandespårningen. Praktiskt taget all information från en utökad sammanfattningsrapport är tillgänglig i en utökad rapport (med undantag **för** origin_timestamp och **delivery_priority**). Följande ytterligare information är endast tillgänglig i en utökad rapport:

- **client_ip:** IP-adressen för den e-postserver eller meddelandeklient som skickade meddelandet.

- **client_hostname:** Värdnamnet eller FQDN för e-postservern eller meddelandeklienten som skickade meddelandet.

- **server_ip:** IP-adressen för källan eller målservern.

- **server_hostname:** Målserverns värdnamn eller FQDN.

- **source_context**: Extra information associerad med **källfältet.** Ett exempel:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **källa:** Exchange Online-komponenten som ansvarar för händelsen. Ett exempel:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id:** De motsvarar de **händelsevärden för meddelanden** som förklaras i avsnittet Hitta relaterade poster för det [här](#find-related-records-for-this-message) meddelandet.

- **internal_message_id**: En meddelandeidentifierare som har tilldelats av Exchange Online-servern som för närvarande bearbetar meddelandet.

- **recipient_address:** E-postadresserna till meddelandets mottagare. Flera e-postadresser avgränsas med semikolontecken (;).

- **recipient_count**: Det totala antalet mottagare i meddelandet.

- **related_recipient_address:** Används med `EXPAND` `REDIRECT` , och händelser för att visa `RESOLVE` andra mottagares e-postadresser som är kopplade till meddelandet.

- **referens:** Det här fältet innehåller ytterligare information för specifika typer av händelser. Ett exempel:

  - **DSN:** Innehåller rapportlänken, som är **message_id-värdet** för det associerade leveransstatusmeddelandet (kallas även DSN, rapport om utebliven leverans, NDR eller icke-leveranskavisering) om ett DSN genereras senare för den här händelsen. Om det här är ett DSN-meddelande innehåller det **message_id** värdet för det ursprungliga meddelandet som DSN skapades för.

  - **EXPAND**: Innehåller **related_recipient_address** värdet för relaterade meddelanden.

  - **RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).

  - **SKICKA:** Innehåller **det internal_message_id** värdet för DSN-meddelanden.

  - **ÖVERFÖRING:** Innehåller **internal_message_id** värdet för meddelandet som delars upp (till exempel genom innehållskonvertering, begränsningar för meddelandemottagare eller representanter).

  - **MAILBOXRULE:** Innehåller **det internal_message_id** värdet för det inkommande meddelandet som orsakade att inkorgsregeln skulle generera det utgående meddelandet.

    För andra typer av händelser är det här fältet vanligtvis tomt.

- **return_path:** Den avsändar-e-postadress som anges av **kommandot MAIL FROM** som skickade meddelandet. Även om fältet aldrig är tomt kan värdet för null-avsändaradressen representeras som `<>` .

- **message_info:** Ytterligare information om meddelandet. Ett exempel:

  - Datum-tid för meddelande originering i UTC för `DELIVER` och `SEND` händelser. Datum-tid för ursprung är tidpunkten när meddelandet först angav Exchange Online-organisationen. DATUM-tid i UTC representeras i ISO 8601-datum/tid-format: , där = år, = månad, = dag, anger början av `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` `mm` `dd` `T` `hh` tidskomponenten, = timme, `mm` = minut, = sekund, `ss` `fff` = `Z` `Zulu` bråktal för en sekund och betecknar , vilket är ett annat sätt att ange UTC.

  - Autentiseringsfel. Du kan till exempel se värdet och `11a` typen av autentisering som användes när autentiseringsfelet inträffade.

- **tenant_id**: Ett GUID-värde som representerar Exchange Online-organisationen (t.ex. `39238e87-b5ab-4ef6-a559-af54c6b07b42` ).

- **original_server_ip:** IP-adressen till den ursprungliga servern.

- **custom_data**: Innehåller data som är relaterade till specifika händelsetyper. Mer information finns i följande avsnitt.

#### <a name="custom_data-values"></a>custom_data värden

Fältet **custom_data** för en `AGENTINFO` händelse används av olika Exchange Online-agenter för att logga information om meddelandebearbetningen. Några av de mer intressanta representanterna beskrivs i följande avsnitt.

#### <a name="spam-filter-agent"></a>Filteragent för skräppost

Ett **custom_data** som börjar med `S:SFA` kommer från skräppostfilteragenten. Den viktigaste informationen beskrivs i följande tabell:

****

|Value|Beskrivning|
|---|---|
|`SFV=NSPM`|Meddelandet har markerats som icke skräppost och skickats till avsedda mottagare.|
|`SFV=SPM`|Meddelandet markerades som skräppost genom skräppostfiltrering (kallas även innehållsfiltrering).|
|`SFV=BLK`|Filtrering hoppades över och meddelandet blockerades eftersom det kommer från en blockerad avsändare.|
|`SFV=SKS`|Meddelandet markerades som skräppost innan det hanterades av skräppostfiltrering. Detta inkluderar meddelanden där meddelandet har matchat en e-postflödesregel (även känt som transportregel) som automatiskt markerat det som skräppost och förbigått all ytterligare filtrering.|
|`SCL=<number>`|Mer information om de olika SCL-värdena och vad de betyder finns i [Konfidensnivåer för skräppost.](spam-confidence-levels.md)|
|`PCL=<number>`|PCL-värdet (Phishing Confidence Level) för meddelandet. De kan tolkas på samma sätt som SCL-värdena som beskrivs i [konfidensnivåer för skräppost.](spam-confidence-levels.md)|
|`DI=SB`|Meddelandets avsändare blockerades.|
|`DI=SQ`|Meddelandet har satts i karantän.|
|`DI=SD`|Meddelandet togs bort.|
|`DI=SJ`|Meddelandet skickades till mottagarens skräppostmapp.|
|`DI=SN`|Meddelandet skickades via den vanliga utgående leveranspoolen.|
|`DI=SO`|Meddelandet skickades via högriskleveranspoolen. Mer information finns i [Högriskleveranspool för utgående meddelanden.](high-risk-delivery-pool-for-outbound-messages.md)|
|`SFS=[a]|SFS=[b]`|Det betyder att reglerna för skräppost har matchats.|
|`IPV=CAL`|Meddelandet släpptes igenom skräppostfiltret då IP-adressen specificerades i en lista över tillåtna IP-adresser i anslutningsfiltret.|
|`H=<EHLOstring>`|En anslutande e-mailservers HELO- eller OEHLO-sträng.|
|`PTR=<ReverseDNS>`|PTR-posten för den avsändande IP-adressen, som även kallas omvänd DNS-adress.|
|

Ett exempel **custom_data** värde för ett meddelande som filtreras efter skräppost så här:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Filteragent för skadlig programvara

Ett **custom_data** som börjar med är `S:AMA` från filteragenten för skadlig programvara. Den viktigaste informationen beskrivs i följande tabell:

****

|Value|Beskrivning|
|---|---|
|`AMA=SUM|v=1|` eller `AMA=EV|v=1`|Meddelandet innehöll skadlig programvara. `SUM` anger att skadlig programvara kan ha upptäckts av ett antal motorer. `EV` anger att skadlig programvara identifierades av en specifik motor. När skadlig programvara identifieras av en motor utlöser detta efterföljande åtgärder.|
|`Action=r`|Meddelandet har ersatts.|
|`Action=p`|Meddelandet har kringgåts.|
|`Action=d`|Meddelandet har skjutits upp.|
|`Action=s`|Meddelandet togs bort.|
|`Action=st`|Meddelandet har kringgåts.|
|`Action=sy`|Meddelandet har kringgåts.|
|`Action=ni`|Meddelandet avvisades.|
|`Action=ne`|Meddelandet avvisades.|
|`Action=b`|Meddelandet blockerades.|
|`Name=<malware>`|Namnet på den skadlig programvara som identifierades.|
|`File=<filename>`|Namnet på filen som innehöll den skadliga programvaran.|
|

Ett exempel **custom_data** ett meddelande som innehåller skadlig programvara ser ut så här:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Transportregelagent

Ett **custom_data** som börjar med `S:TRA` kommer från transportregelagenten för e-postflödesregler (kallas även transportregler). Den viktigaste informationen beskrivs i följande tabell:

****

|Value|Beskrivning|
|---|---|
|`ETR|ruleId=<guid>`|Detta är det regel-ID som matchades.|
|`St=<datetime>`|Datum och tid i UTC när regelmatchning inträffade.|
|`Action=<ActionDefinition>`|Den åtgärd som tillämpats. En lista över tillgängliga åtgärder finns i Åtgärder [för e-postflödesregel i Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|`Mode=<Mode>`|Läget för regeln. Giltiga värden är:<ul><li>Framtvinga: Alla åtgärder för regeln tillämpas.</li><li>**Test med policytips: Alla** policytipsåtgärder skickas, men inga åtgärder vidtas.</li><li>**Testa utan principtips:** Åtgärder visas i en loggfil, men avsändarna meddelas inte på något sätt och inga åtgärder vidtas.</li></ul>|
|

Ett exempel **custom_data** för ett meddelande som matchar villkoren i en e-postflödesregel ser ut så här:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
