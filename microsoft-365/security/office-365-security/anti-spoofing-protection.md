---
title: Skydd mot förfalskning
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
description: Administratörer kan läsa mer om de skydd mot förfalskning som finns tillgängliga i Exchange Online Protection (EOP) och som kan hjälpa dig att minska riskerna för nätfiske från falska avsändare och domäner.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 17228f634dc4aee9cfd416ca676920a5b4e0fba2
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779500"
---
# <a name="anti-spoofing-protection-in-eop"></a>Skydd mot förfalskning i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

För Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor, ingår det funktioner i EOP som hjälper till att skydda organisationen mot falska (förfalskade) avsändare.

När det gäller att skydda sina användare tar Microsoft hot om nätfiske på allvar. Förfalskning är en vanlig teknik som används av angripare. **Falska meddelanden ser ut att komma från en person eller plats som inte är den verkliga källan**. Metoden används ofta i nätfiskekampanjer som är utformade för att få tag på användaruppgifter. Metoden för förfalskningsskydd i EOP undersöker särskilt förfalskningar av Från-rubriken i meddelandetexten (används för att visa meddelandets avsändare i e-postklienter). När EOP är övertygat om att huvudraden Från är förfalskad identifieras meddelandet som förfalskat.

Här följer de förfalskningsskyddsmetoder som finns tillgängliga i EOP:

- **E-postautentisering**: en integrerad del av allt förfalskningsskydd är användningen av e-postautentisering (även kallat e-postverifiering) genom SPF-, DKIM- och DMARC-poster i DNS. Du kan konfigurera dessa poster för dina domäner så att mål-e-postsystemen kan kontrollera giltigheten i meddelanden som gör anspråk på att komma från avsändare i dina domäner. För inkommande meddelanden kräver Microsoft 365 autentisering av e-post för avsändardomäner. Mer information finns i [E-postautentisering i Microsoft 365](email-validation-and-authentication.md).

  EOP analyserar och blockerar meddelanden som inte kan autentiseras med kombinationen av standardmetoder för e-postautentisering och metoder för avsändaromdöme.

  ![EOP-kontroller för förfalskningsskydd](../../media/eop-anti-spoofing-protection.png)

- **Insikt om förfalskningsinformation**: granska falska meddelanden från avsändare i interna och externa domäner under de senaste 7 dagarna samt tillåt eller blockera avsändarna. Mer information finns i [Insikt om förfalskningsinformation i EOP](learn-about-spoof-intelligence.md).

- **Tillåt eller blockera falska avsändare i Tillåten av klient/blockeringslista**: När du åsidosätter domen i Insikt om förfalskningsinformation blir den falska avsändaren en manuell tillåtelse eller blockera posten som bara visas på fliken **Falska** i Tillåten av klient/blockeringslistan. Du kan också skapa tillåtna eller blockera poster manuellt för falska avsändare innan de upptäcks av förfalskningsinformation. För mer information se [Hantera Tillåten av klient/blockeringslista i EOP](tenant-allow-block-list.md).

- **Skydd mot nätfiske**: I EOP och Microsoft Defender för Office 365 innehåller principer för skydd mot nätfiske följande inställningar för funktioner mot förfalskning:
  - Aktivera eller inaktivera förfalskningsinformation.
  - Aktivera eller inaktivera identifiering av oautentiserad avsändare i Outlook.
  - Ange åtgärd för blockerade falska avsändare.

  Mer information finns i [Principer för skydd mot nätfiske](set-up-anti-phishing-policies.md#spoof-settings).

  **Obs!** Principer för skydd mot nätfiske i Defender för Office 365 innehåller ytterligare skydd, inklusive **imitationsskydd**. Mer information finns på [Exklusiva inställningar i principer för skydd mot nätfiske i Microsoft Defender för Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

- **Rapport över identifierad förfalskning**: Mer information finns i [Rapport över identifierad förfalskning](view-email-security-reports.md#spoof-detections-report).

  **Obs!** Defender för Office 365-organisationer kan även använda Identifieringar i realtid (abonnemang 1) eller Hotutforskaren (abonnemang 2) för att visa information om försök till nätfiske. Mer information finns i [Undersökning av hot och svar i Microsoft 365](office-365-ti.md).

## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Hur förfalskning används i nätfiskeattacker

Förfalskade meddelanden har följande två negativa konsekvenser för användare:

- **Falska meddelanden lurar användare**: Ett falskt meddelande kan lura en användare att klicka på en länk och lämna ut sina autentiseringsuppgifter, ladda ned skadlig kod eller svara på ett meddelande med känsligt innehåll (även kallat för business email compromise (BEC) – kompromettering av företags-e-post).

  Följande är ett exempel på ett nätfiskemeddelande med den falska avsändaren msoutlook94@service.outlook.com:

  ![Nätfiskemeddelande som imiterar service.outlook.com](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  Det här meddelandet kom inte från service.outlook.com, men rubrikfältet **Från** förfalskades så att det ger intryck av att göra det. Det här var ett försök att lura mottagaren att klicka på **Ändra lösenords**-länken och uppge sina autentiseringsuppgifter.

  Följande meddelande är ett exempel på BEC (business email compromise) som använder den falska e-postdomänen contoso.com:

  ![Nätfiskemeddelande – kompromettering av företags-e-post](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  Meddelandet ser äkta ut men avsändaren är i själva verket falsk.

- **Användare förväxlar riktiga meddelanden med falska**: även användare som känner till nätfiske kan ha svårt att se skillnaderna mellan riktiga och falska meddelanden.

  Följande meddelande är ett exempel på en faktisk lösenordsåterställning från Microsofts säkerhetskonto:

  ![Legitim lösenordsåterställning från Microsoft](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  Meddelandet kom faktiskt från Microsoft, men användarna har lärt sig att vara misstänksamma. Det är nämligen svårt att se skillnad på ett riktigt och ett falskt meddelande om lösenordsåterställning. Därför ignorerar många användare dessa meddelanden, rapporterar dem som skräppost eller rapporterar dem i onödan till Microsoft som nätfiskebedrägerier.

## <a name="different-types-of-spoofing"></a>Olika typer av förfalskning

Microsoft skiljer mellan två olika typer av falska meddelanden:

- **Förfalskning inom organisationen (“intra-org”)**: kallas även för _“self-to-self”_-förfalskning. Till exempel:

  - Avsändaren och mottagaren finns i samma domän:
    > Från: chris@contoso.com <br> Till: michelle@contoso.com

  - Avsändaren och mottagaren finns i underdomäner till samma domän:
    > Från: laura@marketing.fabrikam.com <br> Till: julia@engineering.fabrikam.com

  - Avsändaren och mottagaren finns i olika domäner som tillhör samma organisation (d.v.s. båda domänerna är konfigurerade som [godkända domäner](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i samma organisation):
    > Från: avsändare @ microsoft.com <br> Till: mottagare @ bing.com

    Mellanslag används i e-postadresserna för att förhindra spambot-insamling.

  Meddelanden som inte klarar [sammansatt autentisering](email-validation-and-authentication.md#composite-authentication) på grund av förfalskning inom organisationen innehåller följande värden i meddelandehuvudet:

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - `reason=6xx` tyder på förfalskning inom organisationen.

  - SFTY är meddelandets säkerhetsnivå. 9 anger nätfiske, .11 anger förfalskning inom organisationen.

- **Förfalskningar mellan domäner**: avsändarens och mottagarens domäner skiljer sig åt och har ingen relation sinsemellan (kallas även externa domäner). Till exempel:
    > Från: chris@contoso.com <br> Till: michelle@tailspintoys.com

  Meddelanden som inte klarar [sammansatt autentisering](email-validation-and-authentication.md#composite-authentication) på grund av förfalskning mellan domäner innehåller följande värden i meddelandehuvudet:

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - `reason=000` betyder att meddelandet inte har klarat explicit e-postautentisering. `reason=001` betyder att meddelandet inte har klarat implicit e-postautentisering.

  - `SFTY`är meddelandets säkerhetsnivå. 9 anger nätfiske, .22 anger förfalskning mellan domäner.

> [!NOTE]
> Om du har fått ett meddelande som ***compauth=fail reason=###** _ och behöver veta om sammansatt autentisering (compauth) och värdena relaterade till förfalskning kan du läsa mer under meddelanderubriker för [_Anti-skräppost i Microsoft 365*](anti-spam-message-headers.md). Eller gå direkt till koderna för [*orsak*](anti-spam-message-headers.md).

Mer information om DMARC finns i [Använda DMARC för att validera e-post i Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="problems-with-anti-spoofing-protection"></a>Problem med förfalskningsskydd

E-postlistor (även kallade diskussionslistor) är kända för att ha problem med förfalskning på grund av det sätt de vidarebefordrar meddelanden och ändrar innehållet i dem.

Anta till exempel att Gabriela Laureano (glaureano@contoso.com) är intresserad av fågelskådning och går med i diskussionslistan fagelskadare@fabrikam.com. och skickar följande meddelande till listan:

> **From:** "Gabriela Laureano" \<glaureano@contoso.com\> <br> **Till:** Birdwatcherens diskussions lista \<birdwatchers@fabrikam.com\> <br> **Ämne:** Fantastiska bilder av blåskrika på Mt. Rainier denna vecka <p> Vem vill kolla in bilderna från Mt. Rainier den här veckan?

E-postlistans server tar emot meddelandet, ändrar innehållet och skickar tillbaka det till medlemmarna i listan. Det återgivna meddelandet har samma Från:-adress (glaureano@contoso.com) men en tagg har lagts till i ämnesraden och en sidfot har lagts till längst ned i meddelandet. Den här typen av ändringar är vanliga i distributionslistor och kan leda till falska positiva identifieringar av förfalskning.

> **From:** "Gabriela Laureano" \<glaureano@contoso.com\> <br> **Till:** Birdwatcherens diskussions lista \<birdwatchers@fabrikam.com\> <br> **Ämne:** [FÅGELSKÅDARE] Fantastiska bilder av blåskrika på Mt. Rainier denna vecka <p> Vem vill kolla in bilderna från Mt. Rainier den här veckan? <p> Meddelandet skickades till diskussionslistan Fågelskådare. Du kan avbryta prenumerationen när du vill.

Om du vill se till att e-post från distributionslistor klarar förfalskningskontroller, följer du dessa anvisningar beroende på om du har kontroll över distributionslistan:

- Din organisation äger distributionslistan:

  - Ta en titt på vanliga frågor och svar på DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F) (Jag driver en distributionslista och vill samverka med DMARC, vad ska jag göra?).

  - Läs anvisningarna i det här blogginlägget: [A tip for mailing list operators to interoperate with DMARC to avoid failures](/archive/blogs/tzink/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures) (Ett tips för dem som driver distributionslistor att samverka med DMARC för att undvika fel).

  - Överväg att installera uppdateringar på distributionslistans server som stöder ARC, se <http://arc-spec.org>.

- Din organisation äger inte distributionslistan:

  - Be personen som hanterar distributionslistan att konfigurera e-postautentisering för den domän som distributionslistan vidarebefordras från.

    När tillräckligt många avsändare svarar tillbaka till domänägare om att de bör konfigurera poster för e-postautentisering motiveras de att vidta åtgärder. Microsoft samarbetar också med domänägare i att publicera de nödvändiga posterna men det hjälper ännu mer när enskilda användare begär det.

  - Du kan skapa regler för Inkorgen i e-postklienten för att flytta meddelanden till Inkorgen. Du kan också be dina administratörer att konfigurera åsidosättningar enligt beskrivningen i [Insikt om förfalskningsinformation i EOP](learn-about-spoof-intelligence.md) och [Hantera Tillåten av klient/blockeringslista](tenant-allow-block-list.md).

  - Du kan skapa ett supportärende med Microsoft 365 för att skapa en åsidosättning för distributionslistan för att behandla den som legitim. Mer information finns i [Kontakta supporten för företagsprodukter – hjälp för administratörer](../../business-video/get-help-support.md).

Om ingenting annat fungerar kan du rapportera meddelandet som en falsk positiv identifiering till Microsoft. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

Du kan också kontakta din administratör som kan skapa ett supportärende hos Microsoft. Microsofts tekniska team undersöker varför meddelandet har markerats som förfalskning.

## <a name="considerations-for-anti-spoofing-protection"></a>Överväganden för skydd mot förfalskning

Om du är en administratör som för närvarande skickar meddelanden till Microsoft 365 måste du se till att e-postmeddelandet autentiseras på rätt sätt. Annars kan det markeras som skräppost eller nätfiske. Mer information finns i [Lösningar för legitima avsändare som skickar icke autentiserad e-post](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).

Avsändare i en enskild användares (eller administratörs) lista över säkra avsändare kommer att kringgå delar av filtreringsstacken, inklusive falskt skydd. Mer information finns i [Outlook Safe avsändare](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders).

Administratörer bör (om möjligt) undvika att använda tillåtna avsändarlistor eller tillåtna domänlistor. Dessa avsändare övergår allt skräppost, förfalskning och nätfiskningsskydd och även avsändarautentisering (SPF, DKIM, DMARC). Mer information finns i [Använd tillåtna avsändarlistor eller tillåtna domänlistor](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists).
