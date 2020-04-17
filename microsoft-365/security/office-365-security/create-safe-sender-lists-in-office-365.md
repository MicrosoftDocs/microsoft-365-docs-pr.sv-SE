---
title: Skapa listor över betrodda avsändare i Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Administratörer kan lära sig mer om tillgängliga alternativ i Office 365 och EOP som gör att inkommande meddelanden kan hoppa över skräppostfiltrering.
ms.openlocfilehash: 4b50a4b63377c0f3e7b12592c512449f1a3adc12
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528635"
---
# <a name="create-safe-sender-lists-in-office-365"></a>Skapa listor över betrodda avsändare i Office 365

Om du är en Office 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection -kund (EOP) utan Exchange Online-postlådor, erbjuder EOP flera sätt att se till att användarna får e-post från betrodda avsändare. Dessa alternativ omfattar regler för Exchange-e-postflöde (kallas även transportregler), outlook-betrodda avsändare, IP-listan (anslutningsfiltrering) och tillåtna avsänningslistor eller tillåtna domänlistor i principer mot skräppost. Tillsammans kan du se dessa alternativ som _säkra avsändarelistor_.

De tillgängliga listorna för säkra avsändare beskrivs i följande lista för att från de flesta rekommenderade till minst rekommenderade:

1. Regler för e-postflöde

2. Betrodda avsändare i Outlook

3. Lista över IP-tillåt (anslutningsfiltrering)

4. Tillåtna avsändarlistor eller tillåtna domänlistor (policyer mot skräppost)

Regler för e-postflöde ger mest flexibilitet för att säkerställa att endast rätt meddelanden tillåts. Tillåtna avsändare och tillåtna domänlistor i anti-spam-principer är inte lika säkra som IP-listan, eftersom avsändarens e-postdomän enkelt förfalskas. Men IP Allow List utgör också en risk, eftersom e-post från _en_ domän som skickas från den IP-adressen kommer att kringgå skräppostfiltrering.

> [!IMPORTANT]
> <ul><li>Var noga med att noga övervaka *eventuella* undantag som du till skräppostfiltrering med hjälp av säkra avsändande listor.</li><li>Även om du kan använda säkra avsänningslistor för att hjälpa till med falska positiva identifieringar (bra e-post markerad som skräppost), bör du betrakta användningen av säkra avsändarelistor som en tillfällig lösning som bör undvikas om möjligt. Vi rekommenderar inte att du hanterar falska positiva identifieringar med hjälp av säkra avsänningslistor, eftersom undantag från skräppostfiltrering kan öppna din organisation för förfalskning och andra attacker. Om du insisterar på att använda listor med betrodda avsändare för att hantera falska positiva identifieringar måste du vara vaksam och hålla ämnet [Rapportmeddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md) i redo.</li><li>Om du vill att en domän ska kunna skicka oautentiserade e-postmeddelanden (kringgå skydd mot förfalskning) men inte kringgå kontroller av skräppost och skadlig kod kan du lägga till den i [listan Tillåtentillbehållsbehåll för säker avsändare](walkthrough-spoof-intelligence-insight.md)</li><li>EOP och Outlook granskar olika meddelandeegenskaper för att fastställa meddelandets avsändare. Mer information finns i avsnittet [Överväganden för massutskick av e-post](#considerations-for-bulk-email) senare i det här avsnittet.</li></ul>

Däremot har du också flera alternativ för att blockera e-post från specifika källor med hjälp av _blockerade avsändarelistor_. Mer information finns i artikeln om att [skapa listor över blockerade avsändare i Office 365](create-block-sender-lists-in-office-365.md).

## <a name="recommended-use-mail-flow-rules"></a>(Rekommenderas) Använda regler för e-postflöde

Regler för e-postflöde i Exchange Online och fristående EOP använder villkor och undantag för att identifiera meddelanden och åtgärder för att ange vad som ska göras med dessa meddelanden. Mer information finns i [Regler för e-postflöde (transportregler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

I följande exempel förutsätts att du behöver e-post från contoso.com för att hoppa över skräppostfiltrering. Det gör du genom att konfigurera följande inställningar:

1. **Villkor**: **Avsändatordomänen** \> **är** \> contoso.com.

2. Konfigurera någon av följande inställningar:

   - **Villkor för e-postflödesregel:** **Ett meddelandehuvud** \> innehåller `dmarc=pass` något `dmarc=bestguesspass`av **följande ord** \> **Rubriknamn:** `Authentication-Results` \> **Rubrikvärde**: eller .

     Det här villkoret kontrollerar avsändarautentiseringsstatusen för den sändande e-postdomänen för att säkerställa att den sändande domänen inte förfalskas. Mer information om e-postautentisering finns i [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC](use-dmarc-to-validate-email.md).

   - **LISTA ÖVER IP-tillåta:** Ange källans IP-adress eller adressintervall i anslutningsfilterprincipen.
  
     Använd den här inställningen om den sändande domänen inte har autentisering. Var så restriktiv som möjligt när det gäller källans IP-adresser i IP-listan. Vi rekommenderar ett IP-adressintervall på /24 eller mindre (mindre är bättre). Använd inte IP-adressintervall som tillhör konsumenttjänster (till exempel outlook.com) eller delade infrastrukturer.

   > [!IMPORTANT]
   > <ul><li>Konfigurera aldrig konfigurera regler för e-postflöde med *endast* avsändatordomänen som villkor för att hoppa över skräppostfiltrering. Om du gör *det* ökar sannolikheten avsevärt för att angripare kan förfalska den sändande domänen (eller utge sig för att vara den fullständiga e-postadressen), hoppa över all skräppostfiltrering och hoppa över autentiseringskontroller för avsändare så att meddelandet kommer till mottagarens inkorg.</li><li>Använd inte domäner som du äger (kallas även godkända domäner) eller populära domäner (till exempel microsoft.com) som villkor i regler för e-postflöde. Detta anses vara hög risk eftersom det skapar möjligheter för angripare att skicka e-post som annars skulle filtreras.</li><li>Om du tillåter en IP-adress som ligger bakom en NAT-gateway (Network Address Translation) måste du känna till de servrar som ingår i NAT-poolen för att känna till omfattningen av ip-listan. IP-adresser och NAT-deltagare kan ändras. Du måste regelbundet kontrollera dina IP Allow List-poster som en del av dina standardunderhållsprocedurer.</li></ul>

3. **Valfria villkor:**

   - \> **Avsändaren** **är intern/extern** \> Utanför organisationen : Det här **villkoret**är implicit, men det är OK att använda den för att ta hänsyn till lokala e-postservrar som kanske inte är korrekt konfigurerade.

   - **Ämnet eller** \> **kroppsämnet eller brödtexten innehåller något av dessa ords** \> \<\>nyckelord: Om du ytterligare kan begränsa meddelandena med nyckelord eller fraser i ämnesraden eller meddelandetexten kan du använda dessa ord som ett villkor.

4. **Åtgärd**: Konfigurera båda dessa åtgärder i regeln:

   a. **Ändra meddelandeegenskaperna** \> **ange skräppostförtroendenivå (SCL)** \> **Bypass-skräppostfiltrering**.

   b. **Ett meddelandehuvud** \> innehåller något av \<dessa **ord** \> \> **Rubriknamn:** CustomHeaderName Header **värde:** \<CustomHeaderValue\>.

      Till exempel `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Om du har mer än en domän i regeln kan du anpassa rubriktexten efter behov.

      När ett meddelande hoppar över skräppostfiltrering på `SFV:SKN` grund av en regel för e-postflöde stämplas värdevärdet i **X-Forefront-Antispam-Report-huvudet.** Om meddelandet kommer från en källa som finns i `IPV:CAL` listan TILLÅT IP läggs värdet också till. Dessa värden kan hjälpa dig med felsökning.

![Inställningar för e-postflödesregel i EAC för förbikoppling av skräppostfiltrering.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Använda säkra avsändare i Outlook

I stället för en organisationsinställning kan användare eller administratörer lägga till avsändarens e-postadresser i listan Betrodda avsändare i postlådan. Instruktioner finns i [Konfigurera inställningar för skräppost på Exchange Online-postlådor i Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

När meddelanden hoppar över skräppostfiltrering på grund av en användares lista Betrodda avsändare innehåller `SFV:SFE`huvudfältet **X-Forefront-Antispam-Report** värdet , vilket indikerar att skräppost, parodi och phish-filtrering har kringgåts.

## <a name="use-the-ip-allow-list"></a>Använda listan TILLÅT IP

Om du inte kan använda e-postflödesregler som tidigare beskrivits är det näst bästa alternativet att lägga till källmeddelandeservern eller källservrarna i IP-listan tillåt i anslutningsfilterprincipen. Mer information finns [i Konfigurera anslutningsfiltrering i Office 365](configure-the-connection-filter-policy.md).

**Anmärkningar**:

- Det är viktigt att du håller antalet tillåtna IP-adresser till ett minimum, så undvik att använda hela IP-adressintervall när det är möjligt.

- Använd inte IP-adressintervall som tillhör konsumenttjänster (till exempel outlook.com) eller delade infrastrukturer.

- Granska regelbundet posterna i LISTAN TILLÅT IP och ta bort de poster som du inte längre behöver.

> [!CAUTION]
> Utan ytterligare verifiering som regler för e-postflöde hoppar e-post från källor i IP-listan över skräppostfiltrering och avsändandeautentisering (SPF, DKIM, DMARC). Detta skapar en hög risk för angripare som lyckas leverera e-post till Inkorgen som annars skulle filtreras.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Använda tillåtna avsänningslistor eller tillåtna domänlistor

Det minst önskvärda alternativet är att använda listan över tillåtna avsändare eller tillåtna domänlista i anti-spam-policyer. Du bör undvika det här alternativet *om det alls är möjligt* eftersom avsändare kringgår all skräppost, parodi och phish-skydd och avsändareautentisering (SPF, DKIM, DMARC). Den här metoden används endast bäst för tillfälliga tester. De detaljerade stegen finns i [Konfigurera principer mot skräppost i Office 365-avsnittet.](configure-your-spam-filter-policies.md)

Den maximala gränsen för dessa listor är cirka 1000 poster. även om du bara kan ange 30 poster i portalen. Du måste använda PowerShell för att lägga till fler än 30 poster.

> [!CAUTION]
> <ul><li>Den här metoden skapar en hög risk för att angripare lyckas leverera e-post till Inkorgen som annars skulle filtreras.</li><li>Använd inte domäner som du äger (kallas även godkända domäner) eller populära domäner (till exempel microsoft.com) i tillåtna domänlistor.</li></ul>

## <a name="considerations-for-bulk-email"></a>Överväganden för mass-e-post

Ett standardmeddelande för SMTP-meddelanden består av ett *meddelandekuvert* och meddelandeinnehåll. Meddelandekuvertet innehåller information som krävs för att överföra och leverera meddelandet mellan SMTP-servrar. Meddelandeinnehållet innehåller fält för meddelandehuvud (kallas gemensamt *meddelandehuvudet)* och meddelandetexten. Meddelandekuvertet beskrivs i RFC 5321 och meddelandehuvudet beskrivs i RFC 5322. Mottagarna ser aldrig det faktiska meddelandekuvertet eftersom det genereras av meddelandeöverföringsprocessen och det är faktiskt inte en del av meddelandet.

- Adressen `5321.MailFrom` (kallas även **MAIL FROM-adressen,** P1-avsändaren eller kuvertavsändaren) är den e-postadress som används i SMTP-överföringen av meddelandet. Den här e-postadressen registreras vanligtvis i fältet **Retursökväg** i meddelandehuvudet (även om avsändaren kan ange en annan **e-postadress för retursökväg).** Om meddelandet inte kan levereras är det mottagaren för rapporten om utebliven leverans (kallas även NDR eller avvisningsmeddelande).

- (även `5322.From` känd som **Från-adressen** eller P2-avsändaren) är e-postadressen i fältet **Från-huvud** och är avsändarens e-postadress som visas i e-postklienter.

Ofta är `5321.MailFrom` adresserna och `5322.From` desamma (kommunikation mellan person och person). Men när e-post skickas på uppdrag av någon annan, är adresserna ofta olika. Detta händer oftast oftast för massmeddelanden.

Anta till exempel att Blue Yonder Airlines har anlitat Margie's Travel för att skicka ut sin e-postreklam. Meddelandet du får i Inkorgen har följande egenskaper:

- Adressen `5321.MailFrom` är blueyonder.airlines@margiestravel.com.

- Adressen `5322.From` är blueyonder@news.blueyonderairlines.com, vilket är vad du ser i Outlook.

Säkra avsändarelistor och säkra domänlistor i anti-spam-policyer i EOP inspekterar både `5321.MailFrom` och `5322.From` adresser. Outlook Safe Avsändare `5322.From` använder bara adressen.

Om du vill förhindra att det här meddelandet filtreras kan du vidta följande åtgärder:

- Lägg till blueyonder@news.blueyonderairlines.com `5322.From` (adressen) som en säker avsändare i Outlook.

- Använd en regel för [e-postflöde](#recommended-use-mail-flow-rules) med ett villkor som `5322.From` söker efter meddelanden från `5321.MailFrom`blueyonder@news.blueyonderairlines.com (adressen, blueyonder.airlines@margiestravel.com (den ) eller båda.

Mer information finns [i Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md).
