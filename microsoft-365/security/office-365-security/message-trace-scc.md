---
title: Meddelandespårning i Säkerhets- och efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan använda meddelande spårning i säkerhets & efterlevnad för att ta reda på vad som hände med meddelanden.
ms.openlocfilehash: 1e9f5e21655e55f711997defcb7ace0319ff4be6
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197543"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Meddelandespårning i Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="message-trace-features"></a>Funktioner för meddelande spårning

Meddelande spårning i säkerhets & Compliance Center följer e-postmeddelanden när de reser genom Exchange Online-organisationen. Du kan bestämma om ett meddelande har tagits emot, nekats, uppskjuts eller levererats av tjänsten. Det visar också vilka åtgärder som vidtogs innan meddelandet nådde sin slutliga status.

Meddelande spårning i säkerhets & uppfyller kraven på den ursprungliga meddelande spårningen i administrations centret för Exchange (UK). Du kan använda informationen från meddelande spårning för att effektivt besvara användar frågor om vad som hände med meddelanden, felsöka e-postflöden och validera princip ändringar.

> [!NOTE]
>
> - Om du vill göra en meddelande spårning måste du vara medlem i roll grupperna organisations hantering eller supportavdelning. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
>
> - Det maximala antalet meddelanden som visas i resultaten beror på vilken typ av rapport du valde (se avsnittet [Välj rapport typ](#choose-report-type) för detaljer). Cmdleten [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) i Exchange Online PowerShell eller fristående EOP PowerShell returnerar alla meddelanden i resultatet.

## <a name="open-message-trace"></a>Öppna meddelande spårning

1. Öppna säkerhets & Compliance Center på <https://protection.office.com> .

2. Expandera **e-postflödet**och välj sedan **meddelande spårning**.

## <a name="message-trace-page"></a>Sidan meddelande spårning

Härifrån kan du starta en ny standard spårning genom att klicka på knappen **starta en spårning** . Detta söker efter alla meddelanden för alla avsändare och mottagare under de senaste två dagarna. Eller så kan du använda en av de lagrade frågorna från de tillgängliga kategorierna för frågor och antingen köra dem som de är eller använda dem som utgångs punkt för dina egna frågor:

- **Standard frågor**: inbyggda frågor som tillhandahålls av Microsoft 365.

- **Anpassade frågor**: frågor som sparats av administratörer i organisationen för framtida användning.

- **Automatiskt sparade frågor**: de senaste tio vanligaste frågorna. Den här listan gör det enkelt att fortsätta där du slutade.

Även på den här sidan finns ett område med **hämtnings bara rapporter** för de förfrågningar som du har skickat, samt själva rapporterna när det finns att ladda ner.

## <a name="options-for-a-new-message-trace"></a>Alternativ för en ny meddelande spårning

### <a name="filter-by-senders-and-recipients"></a>Filtrera efter avsändare och mottagare

Standardvärdena är **alla avsändare** och **alla mottagare**, men du kan använda följande fält för att filtrera resultat:

- **Av de här personerna**: Klicka i det här fältet för att välja en eller flera avsändare från din organisation. Du kan också börja skriva ett namn och objekten i listan filtreras efter vad du har skrivit, till exempel hur en Sök sida beter sig.

- **Till de här personerna**: Klicka i det här fältet för att välja en eller flera användare i organisationen.

> [!NOTE]
> Du kan också skriva e-postadresserna för externa avsändare och mottagare. Jokertecken stöds (till exempel `*@contoso.com` ), men du kan inte använda flera jokertecken i samma fält samtidigt. <br/><br/> Du kan klistra in flera avsändare eller mottagar listor avgränsade med semikolon ( `;` ). blank steg ( `\s` ), rad matningar ( `\r` ) eller Next-line ( `\n` ).

### <a name="time-range"></a>Tidsintervall

Standardvärdet är **2 dagar**, men du kan ange datum-och tidsintervall på upp till 90 dagar. Tänk på följande när du använder datum-och tidsintervall:

- Som standard väljer du tidsintervall i vyn i **skjutreglaget** med en tids linje. Du kan bara välja de datum-och tids inställningar som visas. Om du försöker markera ett värde mellan två fäster du Start-och slut bubblan till den närmaste visade inställningen.

  ![Ett tidsintervall i en ny meddelande spårning i säkerhets & Compliance Center](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  Men du kan också växla till den **anpassade** vyn där du kan ange värdena **start datum** och **slutdatum** (inklusive tid) och du kan också välja **tids zonen** för datum/tid-intervallet. Observera att inställningen för **tids zoner** gäller för både frågeresultatet och frågeresultaten.

  ![Ett anpassat tidsintervall i en ny meddelande spårning i säkerhets & Compliance Center](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  I 10 dagar eller färre blir resultaten omedelbart tillgängliga som en **sammanfattnings** rapport. Om du anger ett tidsintervall som är ännu något mer än 10 dagar försenas resultatet eftersom det bara är tillgängligt som en CSV-fil som hämtas ( **utökad Sammanfattning** eller **utökade** rapporter).

  Mer information om de olika rapport typerna finns i avsnittet [välja rapport typ](#choose-report-type) i det här avsnittet.

  **Obs!** förbättrad Sammanfattning och utökade rapporter är avsedda med arkiverade meddelanden och kan ta upp till flera timmar innan rapporten kan laddas ner. Beroende på hur många andra administratörer som också har lämnat rapport förfrågningar samtidigt kan du också få en fördröjning innan bearbetningen påbörjas för din kö.

- Om du sparar en fråga i vyn **Slider** sparas det relativa tidsintervallet (till exempel 3 dagar från idag). När du sparar en fråga i en **anpassad** vy sparas det absoluta datum-och tidsintervallet (till exempel 2018-05-06 13:00 till 2018-05-08 18:00).

### <a name="more-search-options"></a>Fler sökalternativ

#### <a name="delivery-status"></a>Leverans status

Du kan lämna standardvärdet **alla** markerat, eller så kan du välja ett av följande värden för att filtrera resultaten:

- **Levererat**: meddelandet skickades till destinationen.

- **Förestående**: meddelandets leverans försök pågår eller försök igen.

- **Expanderat**: en distributions grupp mottagare expanderades innan de köpte till de enskilda medlemmarna i gruppen.

- **Misslyckades**: meddelandet levererades inte.

- I **karantän**: meddelandet sattes i karantän (som skräp post, Mass utskick eller nätfiske). Mer information finns i [e-postmeddelanden i karantän i EOP](quarantine-email-messages.md).

- **Filtrerad som skräp post**: meddelandet identifierades som skräp post och avvisades eller blockerades (inte i karantän).

- **Status:** Meddelandet togs nyligen emot av Microsoft 365, men inga andra status data är tillgängliga ännu. Kom tillbaka om några minuter.

**Obs!** de värden som **väntar,** **satts i karantän**och **filtreras som skräp post** är bara tillgängliga för sökningar som är mindre än 10 dagar. Det kan också finnas en 5-till-10 minuters fördröjning mellan den faktiska och rapporterade leverans statusen.

#### <a name="message-id"></a>Meddelande-ID

Det här är Internet meddelande-ID (kallas även klient-ID) som finns i fältet **meddelande-ID:** rubrik i meddelande huvudet. Användarna kan ge dig det här värdet för att undersöka specifika meddelanden.

Det här värdet är konstant för meddelandets livstid. För meddelanden som har skapats i Microsoft 365 eller Exchange är värdet i formatet `<GUID@ServerFQDN>` , inklusive vinkelparenteser ( \< \> ). Till exempel `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Andra meddelande system kan använda olika syntax och värden. Det här värdet ska vara unikt, men inte alla e-postsystem följer det här kravet. Om fältet **meddelande-ID:** inte finns eller är tomt för inkommande meddelanden från externa källor tilldelas ett godtyckligt värde.

När du använder **meddelande-ID** för att filtrera resultaten måste du ta med hela strängen, inklusive alla vinkelparenteser.

#### <a name="direction"></a>Riktning

Du kan lämna standardvärdet **alla** markerat, eller så kan du välja **inkommande** (meddelanden som skickas till mottagarna i organisationen) eller **utgående** (meddelanden som skickas från användare i organisationen) för att filtrera resultaten.

#### <a name="original-client-ip-address"></a>Ursprunglig klient-IP-adress

Du kan skicka in resultaten efter klient-IP-adress för att undersöka hackade datorer som skickar stora mängder skräp post eller skadlig program vara. Även om meddelandena kan verka komma från flera avsändare beror det troligt vis på att samma dator genererar alla meddelanden.

**Obs!** klient-IP-adress-informationen är bara tillgänglig i 10 dagar och är endast tillgänglig i **utökad Sammanfattning** eller **utökade** rapporter (nedladdnings bara CSV-filer).

### <a name="choose-report-type"></a>Välj rapport typ

Tillgängliga rapport typer är:

- **Sammanfattning**: tillgänglig om tidsintervallet är mindre än 10 dagar och kräver inga ytterligare filtrerings alternativ. Resultaten är tillgängliga nästan direkt efter att du klickat på **Sök**. Rapporten returnerar upp till 20000 resultat.

- **Förbättrad Sammanfattning** eller **utökad**: dessa rapporter är bara tillgängliga som nedladdnings bara CSV-filer och kräver ett eller flera av följande filtrerings alternativ oavsett tidsintervallet: **av dessa personer**, **till dessa personer**eller **meddelande-ID**. Du kan använda jokertecken för avsändare eller mottagare (till exempel \* @contoso. com). Den förbättrade sammanfattnings rapporten returnerar upp till 50000 resultat. Den utökade rapporten returnerar upp till 1000 resultat.

**Anmärkningar**:

- Förbättrad Sammanfattning och utökade rapporter är avsedda med arkiverade meddelanden och det kan ta upp till flera timmar innan rapporten kan laddas ner. Beroende på hur många andra administratörer som också har lämnat rapport förfrågningar samtidigt kan du också få en fördröjning innan den köade begäran börjar behandlas.

- Du kan välja en utökad Sammanfattning eller utökad rapport för ett datum-och tidsintervall, vanligt vis är de fyra sista timmarna av arkiverade data inte tillgängliga för dessa två typer av rapporter.

När du klickar på **Nästa**visas en sammanfattnings sida med de filtrerings alternativ som du har valt, en unik (redigerbar) rubrik för rapporten och e-postadressen som tar emot meddelandet när meddelande spårningen har slutförts (även redigerbart) och måste finnas i en av organisationens godkända domäner. Klicka på **Förbered rapport** för att skicka meddelande spårningen. På sidan för huvud **meddelande spårning** visas rapportens status i avsnittet **nedladdnings bara rapporter** .

Mer information om informationen som returneras i olika rapport typer finns i nästa avsnitt.

## <a name="message-trace-results"></a>Resultat för meddelande spårning

De olika rapport typerna returnerar olika informations nivåer. Informationen som är tillgänglig i de olika rapporterna beskrivs i följande avsnitt.

### <a name="summary-report-output"></a>Sammanfattnings rapport

När du har kört meddelande spårningen kommer resultatet att visas sorterade efter fallande datum/tid (senaste först).

![Sammanfattnings rapport resultat för meddelande spårning i säkerhets & efterlevnad](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Sammanfattnings rapporten innehåller följande information:

- **Date**: det datum och den tid då meddelandet togs emot av tjänsten, med den konfigurerade tids zonen för UTC.

- **Avsändare**: avsändarens e-postadress (*Ali Ask* @ *Domain*).

- **Mottagare**: mottagarens eller mottagarens e-postadress. Det finns en rad per mottagare för ett meddelande som skickas till flera mottagare. Om mottagaren är en distributions grupp, dynamisk distributions grupp eller en e-postaktive rad säkerhets grupp, blir gruppen den första mottagaren och sedan är varje medlem i gruppen en separat rad.

- **Ämne** **: fältets** första 256 tecken.

- **Status**: de här värdena beskrivs i avsnittet [leverans status](#delivery-status) .

Normalt är de första 250-resultaten inlästa och lättillgängliga. När du rullar nedåt är det en liten paus när nästa resultat uppsättning laddas. I stället för att bläddra kan du klicka på **Läs in alla** om du vill att alla resultaten ska laddas upp till maximalt 10 000.

Du kan klicka på kolumn rubrikerna för att sortera resultaten efter värdena i den kolumnen i stigande eller fallande ordning.

Du kan klicka på **filtrera resultat** för att filtrera resultatet efter en eller flera kolumner.

Du kan exportera resultaten när du har markerat en eller flera rader genom att klicka på **Exportera resultat** och sedan välja **Exportera alla resultat**, **Exportera inlästa resultat**eller **Exportera markerade**.

#### <a name="find-related-records-for-this-message"></a>Hitta relaterade poster för det här meddelandet

Relaterade meddelande poster är poster som har samma meddelande-ID. Kom ihåg att även ett enskilt meddelande som skickas mellan två personer kan generera flera poster. Antalet poster ökar när meddelandet påverkas av distributions grupp ökning, vidarebefordring, regler för e-postflöde (kallas även transport regler) osv.

När du har markerat kryss rutan för en rad kan du söka efter relaterade poster för meddelandet genom att klicka på knappen **Sök relaterad** som visas, eller genom att välja **fler alternativ** ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **för att hitta relaterade poster för detta meddelande**.

Mer information om meddelande-ID finns i avsnittet meddelande-ID ovan i det här avsnittet.

#### <a name="message-trace-details"></a>Information om meddelande spårning

I sammanfattnings rapportens utdata kan du Visa information om ett meddelande på något av följande sätt:

- Markera raden (klicka någonstans på raden förutom kryss rutan).

- Markera kryss rutan för raden och klicka på **fler alternativ** ![ mer ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **information om meddelanden**.

   ![Information efter att du dubbelklickar på en rad i sammanfattnings rapportens meddelande spårning resulterar i säkerhets & Compliance Center](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

Meddelande spårnings informationen innehåller följande ytterligare information som inte finns i sammanfattnings rapporten:

- **Meddelande händelser**: det här avsnittet innehåller klassificeringar som hjälper till att kategorisera åtgärderna som tjänsten utför på meddelanden. **Några av de mer intressanta händelser** som du kan stöta på är:

  - **Mottagning**: meddelandet togs emot av tjänsten.

  - **Skicka**: meddelandet skickades av tjänsten.

  - **Misslyckades**: det gick inte att leverera meddelandet.

  - **Leverera**: meddelandet skickades till en post låda.

  - **Expandera**: meddelandet skickades till en distributions grupp som har expanderats.

  - **Överföring**: mottagarna har flyttats till ett förgrenat meddelande på grund av innehålls konvertering, meddelande mottagarens gränser eller agenter.

  - **Skjut**upp: meddelande leveransen uppskjuts och kan försöka igen senare.

  - **Åtgärdat**: meddelandet har omdirigerats till en ny mottagar adress baserat på en Active Directory-uppkoppling. När detta inträffar visas den ursprungliga mottagar adressen på en separat rad i meddelande spårningen tillsammans med meddelandets slutliga leverans status.

  Kommentarer:

  - Ett fel meddelande som skickas genererar flera **händelse** poster i meddelande spårningen.

  - Denna lista är inte avsedd att vara uttömmande. Beskrivningar av fler händelser finns i [händelse typer i meddelande spårnings loggen](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log). Observera att den här länken är ett Exchange Server-avsnitt (lokalt Exchange).

- **Mer information**: det här avsnittet innehåller följande information:

  - **Meddelande-ID**: det här värdet beskrivs i avsnittet [meddelande-ID](#message-id) tidigare i det här avsnittet. Till exempel `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Meddelande storlek**

  - **Från IP**: IP-adressen till den dator som skickade meddelandet. För utgående meddelanden som skickas från Exchange Online är det här värdet tomt.

  - **IP**-adress eller adresser där tjänsten försökte leverera meddelandet. Om meddelandet har flera mottagare visas dessa. Det här värdet är tomt för inkommande meddelanden som skickas till Exchange Online.

### <a name="enhanced-summary-reports"></a>Förbättrade sammanfattnings rapporter

Tillgängliga (slutförda) förbättrade sammanfattnings rapporter finns i avsnittet **nedladdnings rapporter** i den inledande meddelande spårningen. Följande information är tillgänglig i rapporten:

- **origin_timestamp** <sup>*</sup> : det datum och den tid då meddelandet ursprungligen togs emot av tjänsten med den konfigurerade tids zonen för UTC.

- **sender_address**: avsändarens e-postadress (*Ali* @ *Domain*).

- **Recipient_status**: leveransens status till mottagaren. Om meddelandet skickades till flera mottagare kommer det att visa alla mottagare och motsvarande status för varje, i formatet: \<*email address*\> ## \<*status*\> . Till exempel:

  - **# #Receive** innebär att meddelandet togs emot av tjänsten och skickats till den avsedda platsen.

  - **# #Receive** betyder att meddelandet togs emot av tjänsten men leverans till den avsedda platsen misslyckades.

  - **# #Receive** betyder att meddelandet togs emot av tjänsten och att det levererades till mottagarens post låda.

- **message_subject**: de första 256 tecknen i meddelandets **ämnes** fält.

- **total_bytes**: meddelandets storlek i byte, inklusive bifogade filer.

- **message_id**: det här värdet beskrivs i avsnittet [meddelande-ID](#message-id) tidigare i det här avsnittet. Till exempel `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id**: ett unikt meddelande-ID som finns kvar i alla kopior av meddelandet som kan skapas på grund av bifurcation eller distributions grupp. Ett exempel värde är `1341ac7b13fb42ab4d4408cf7f55890f` .

- **original_client_ip**: avsändarens klientens IP-adress.

- **riktning**: anger om meddelandet skickades inkommande (1) till din organisation, eller om det skickades utgående (2) från din organisation.

- **connector_id**: namnet på käll-eller destinations kopplingen. Mer information om anslutningar i Exchange Online finns i [Konfigurera e-postflöde med kopplingar i Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

- **delivery_priority** <sup>*</sup> : om meddelandet skickades med **hög**, **lägre**eller **Normal** prioritet.

<sup>*</sup>Dessa egenskaper är bara tillgängliga i förbättrade sammanfattnings rapporter.

### <a name="extended-reports"></a>Utökade rapporter

Tillgängliga (slutförda) utökade rapporter finns i avsnittet **nedladdnings rapporter** i början av meddelande spårning. Praktiskt taget all information från en förbättrad sammanfattnings rapport finns i en utökad rapport (med undantag för **origin_timestamp** och **delivery_priority**). Följande ytterligare information är bara tillgänglig i en utökad rapport:

- **client_ip**: IP-adressen för e-postservern eller meddelande klienten som skickade meddelandet.

- **client_hostname**: värd namnet eller FQDN för e-postservern eller meddelande klienten som skickade meddelandet.

- **server_ip**: käll-eller mål serverns IP-adress.

- **server_hostname**: värd namnet eller FQDN för mål servern.

- **source_context**: Mer information om fältet **källa** . Till exempel:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **källa**: den Exchange Online-komponent som är ansvarig för händelsen. Till exempel:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**: de motsvarar de händelse värden för **meddelanden** som förklaras i avsnittet [hitta relaterade poster för det här meddelandet](#find-related-records-for-this-message) .

- **internal_message_id**: ett meddelande som är kopplat till Exchange Online-servern som för tillfället bearbetar meddelandet.

- **recipient_address**: e-postadresserna till meddelandets mottagare. Flera e-postadresser avgränsas med semikolon (;).

- **recipient_count**: det totala antalet mottagare i meddelandet.

- **related_recipient_address**: används med `EXPAND` , `REDIRECT` och `RESOLVE` händelser för att visa andra mottagares e-postadresser som är kopplade till meddelandet.

- **referens**: det här fältet innehåller ytterligare information om specifika typer av händelser. Till exempel:

  - **DSN**: innehåller rapport länken, vilket är **message_id** värdet för den associerade leverans status aviseringen (kallas även DSN, rapport om utebliven leverans, NDR eller studs meddelande) om en DSN genereras efter den här händelsen. Om det är ett DSN-meddelande innehåller det här fältet **message_id** värdet för det ursprungliga meddelandet som DSN genererades för.

  - **Expand**: innehåller **related_recipient_address** svärdet för de relaterade meddelandena.

  - **Ta emot**: kan innehålla **message_id** -värdet för det relaterade meddelandet om meddelandet genererades av andra processer (till exempel regler för Inkorgen).

  - **Send**: innehåller **INTERNAL_MESSAGE_ID** värdet för DSN-meddelanden.

  - **Överföring**: innehåller **internal_message_id** värdet för det meddelande som används för grenar sig (till exempel genom innehålls konvertering, begränsningar för meddelande mottagare eller agenter).

  - **MAILBOXRULE**: innehåller **internal_message_id** värdet för det inkommande meddelandet som orsakade att regeln om utgående meddelanden skapades.

    För andra typer av händelser är det här fältet normalt tomt.

- **return_path**: den returnerade e-postadressen som anges av kommandot **e-post** som skickade meddelandet. Även om det här fältet aldrig är tomt kan värdet för null avsändar adress visas som `<>` .

- **message_info**: ytterligare information om meddelandet. Till exempel:

  - Meddelandets ursprungs datum-tid i UTC för `DELIVER` och `SEND` events. Ursprungs datum-tid är den tid då meddelandet först registrerade Exchange Online-organisationen. UTC-datum-tiden visas i ISO 8601 datum-och tids format: `yyyy-mm-ddThh:mm:ss.fffZ` , där `yyyy` = år, `mm` = månad, `dd` = dag, `T` anger början av Time-komponenten, `hh` = timme, `mm` = minut, `ss` = Second, `fff` = bråktal för en sekund och `Z` betyder `Zulu` , vilket är ett annat sätt att beteckna UTC.

  - Autentiseringsfel. Du kan till exempel se värdet `11a` och typen av verifikation som användes när autentiseringsfel inträffade.

- **tenant_id**: ett GUID-värde som representerar Exchange Online-organisationen (till exempel `39238e87-b5ab-4ef6-a559-af54c6b07b42` ).

- **original_server_ip**: den ursprungliga SERVERns IP-adress.

- **custom_data**: innehåller data som är relaterade till specifika händelse typer. Mer information finns i följande avsnitt.

#### <a name="custom_data-values"></a>custom_data värden

**Custom_data** fältet för en `AGENTINFO` händelse används av en mängd olika Exchange Online-agenter för att logga information om meddelanden. Vissa av de mer intressanta agenterna beskrivs i följande avsnitt.

#### <a name="spam-filter-agent"></a>Skräp post filter Agent

Ett **custom_data** värde som börjar med `S:SFA` kommer från agenten för skräp post filter. Informationen finns i följande tabell:

****

|Value|Beskrivning|
|---|---|
|`SFV=NSPM`|Meddelandet har markerats som icke skräppost och skickats till avsedda mottagare.|
|`SFV=SPM`|Meddelandet har marker ATS som skräp post av filtrering av skräp post (kallas även innehålls filtrering).|
|`SFV=BLK`|Filtreringen hoppades över och meddelandet blockerades eftersom det kom från en blockerad avsändare.|
|`SFV=SKS`|Meddelandet har marker ATS som skräp post innan den bearbetas av skräp post filtrering. Detta inkluderar meddelanden där meddelandet har matchat en e-postflödesregel (även känt som transportregel) som automatiskt markerat det som skräppost och förbigått all ytterligare filtrering.|
|`SCL=<number>`|Mer information om de olika SCL-värdena och vad de innebär finns i [säkerhets nivåer för skräp post](spam-confidence-levels.md).|
|`PCL=<number>`|Meddelandets värde för nätfiske konfidensnivå (PCL). De här kan tolkas på samma sätt som de SCL värdena i [skräp post nivåer](spam-confidence-levels.md).|
|`DI=SB`|Meddelandets avsändare blockerades.|
|`DI=SQ`|Meddelandet sattes i karantän.|
|`DI=SD`|Meddelandet har tagits bort.|
|`DI=SJ`|Meddelandet skickades till mottagarens mapp för skräp post.|
|`DI=SN`|Meddelandet dirigerades via den vanliga utgående leverans-poolen.|
|`DI=SO`|Meddelandet dirigerades via poolen med högre risk. Mer information finns i [poolen högrisk leveranser för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md).|
|`SFS=[a]|SFS=[b]`|Detta anger att skräp post regler matchades.|
|`IPV=CAL`|Meddelandet släpptes igenom skräppostfiltret då IP-adressen specificerades i en lista över tillåtna IP-adresser i anslutningsfiltret.|
|`H=<EHLOstring>`|En anslutande e-mailservers HELO- eller OEHLO-sträng.|
|`PTR=<ReverseDNS>`|PTR-posten för den sändande IP-adressen, som även kallas omvänd DNS-adress.|
|

Ett exempel **custom_data** värde för ett meddelande som filtrerats för skräp post så här:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Filter Agent för skadlig program vara

Ett **custom_data** värde som börjar med `S:AMA` kommer från filter agenten för skadlig program vara. Informationen finns i följande tabell:

****

|Value|Beskrivning|
|---|---|
|`AMA=SUM|v=1|` respektive `AMA=EV|v=1`|Meddelandet fastställdes att det innehåller skadlig program vara. `SUM` anger att den skadliga program varan kunde identifieras av ett antal motorer. `EV` anger att den skadliga program varan upptäcktes av en viss motor. När skadlig program vara identifieras av en motor utlöses följande åtgärder.|
|`Action=r`|Meddelandet har ersatts.|
|`Action=p`|Meddelandet har hoppats över.|
|`Action=d`|Meddelandet skjuts upp.|
|`Action=s`|Meddelandet har tagits bort.|
|`Action=st`|Meddelandet har hoppats över.|
|`Action=sy`|Meddelandet har hoppats över.|
|`Action=ni`|Meddelandet nekades.|
|`Action=ne`|Meddelandet nekades.|
|`Action=b`|Meddelandet blockerades.|
|`Name=<malware>`|Namnet på den skadliga program varan som upptäcktes.|
|`File=<filename>`|Namnet på den fil som innehåller den skadliga program varan.|
|

Ett exempel **custom_data** värde för ett meddelande som innehåller skadlig kod ser ut så här:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Transport regel agent

Ett **custom_data** värde som börjar med `S:TRA` är från transport regel agenten för regler för e-postflöde (kallas även transport regler). Informationen finns i följande tabell:

****

|Value|Beskrivning|
|---|---|
|`ETR|ruleId=<guid>`|Regel-ID som matchades.|
|`St=<datetime>`|Datum och tid i UTC när regeln matchar.|
|`Action=<ActionDefinition>`|Åtgärden som användes. En lista över tillgängliga åtgärder finns i [åtgärder för e-postflödes regler i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|`Mode=<Mode>`|Regelns läge. Giltiga värden är:<ul><li>**Påtvinga**: alla åtgärder i regeln tillämpas.</li><li>**Testa med princip Tips:**: alla princip Tips åtgärder skickas, men andra tvingande åtgärder kommer inte att genomföras.</li><li>**Testa utan princip Tips**: åtgärder visas i en loggfil, men avsändare kommer inte att meddelas på något sätt, och tvingande åtgärder kommer inte att genomföras.</li></ul>|
|

Ett exempel **custom_data** värde för ett meddelande som matchar villkoren för en regel för e-postflöde ser ut så här:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
