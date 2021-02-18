---
title: Skapa listor för betrodda avsändare
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om de tillgängliga och rekommenderade alternativen för att tillåta inkommande meddelanden i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ddcd6240cfc80350920999f9fc1e8ea188834553
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289717"
---
# <a name="create-safe-sender-lists-in-eop"></a>Skapa listor över betrodda avsändare i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Om du är Microsoft 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection-kund (EOP) utan Exchange Online-postlådor erbjuder EOP flera sätt att säkerställa att användarna får e-post från betrodda avsändare. De här alternativen omfattar Exchange-e-postflödesregler (kallas även transportregler), Betrodda avsändare i Outlook, listan över tillåtna IP-adresser (anslutningsfiltrering) och listor över tillåtna avsändare eller domänlistor som är tillåtna i principer för skydd mot skräppost. Sammantaget kan du tänka på de här alternativen som listor _över betrodda avsändare._

De tillgängliga listorna med betrodda avsändare beskrivs i följande lista, i den ordning som vi rekommenderar mest och minst:

1. E-postflödesregler
2. Betrodda avsändare i Outlook
3. IP-lista över tillåtna (anslutningsfiltrering)
4. Tillåtna avsändarlistor eller listor över tillåtna domäner (principer för skydd mot skräppost)

E-postflödesregler ger största flexibilitet för att säkerställa att endast rätt meddelanden tillåts. Listor med tillåtna avsändare och tillåtna domäner i principer för skydd mot skräppost är inte lika säkra som listan över tillåtna IP-adresser, eftersom avsändarens e-postdomän enkelt kapas. Men listan över tillåtna IP-adresser utgör  också en risk, eftersom e-post från en domän som skickas från den IP-adressen kringgår skräppostfiltrering.

> [!IMPORTANT]
>
> - Var noga med att övervaka *alla undantag* som du gör i skräppostfiltrering med hjälp av listor över betrodda avsändare.
>
> - Även om du kan använda listor över betrodda avsändare för att se till att e-postmeddelanden felaktigt markeras som felaktiga bör du överväga att använda listor över betrodda avsändare som en tillfällig lösning som om möjligt bör undvikas. Vi rekommenderar inte att du hanterar falska positiva meddelanden med hjälp av listor över betrodda avsändare, eftersom undantag från skräppostfiltrering kan öppna organisationen för förfalskning och andra attacker. Om du är försiktig med att använda listor över betrodda avsändare för att hantera falska positiva meddelanden, måste du vara uppmärksam och ha ämnet Rapportera meddelanden och filer till [Microsoft](report-junk-email-messages-to-microsoft.md) när de är klara.
>
> - Om du vill tillåta att en domän skickar oautisk e-post (kringgå skydd mot förfalskning) men inte kringgår kontroller av skräppost och skadlig programvara kan du lägga till den i listan Med [tillåtnaToSpoof](walkthrough-spoof-intelligence-insight.md) säkra avsändare
>
> - EOP och Outlook kontrollerar olika meddelandeegenskaper för att fastställa meddelandets avsändare. Mer information finns i avsnittet Att [tänka på vid massutskick](#considerations-for-bulk-email) senare i den här artikeln.

Däremot finns det flera alternativ för att blockera e-post från specifika källor med _hjälp av listor med spärrade avsändare._ Mer information finns i artikeln om att [skapa listor över blockerade avsändare i EOP](create-block-sender-lists-in-office-365.md).

## <a name="recommended-use-mail-flow-rules"></a>(Rekommenderas) Använda e-postflödesregler

E-postflödesregler i Exchange Online och fristående EOP använder villkor och undantag för att identifiera meddelanden och åtgärder för att ange vad som ska göras med dessa meddelanden. Mer information finns i [E-postflödesregler (transportregler) i Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

I följande exempel förutsätts att du behöver e-contoso.com att hoppa över skräppostfiltrering. Det gör du genom att konfigurera följande inställningar:

1. **Villkor:**  \> **Avsändardomänen** \> är contoso.com.

2. Konfigurera någon av följande inställningar:

   - **Villkor för e-postflödesregel:** **Ett meddelandehuvud** innehåller något av följande ord \>  \> **Rubriknamn:** `Authentication-Results` \> **Rubrikvärde**: `dmarc=pass` `dmarc=bestguesspass` eller.

     Det här villkoret kontrollerar e-postautentiseringsstatusen för den avsändande e-postdomänen för att säkerställa att den avsändande domänen inte kapas. Mer information om e-postautentisering finns [i SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC.](use-dmarc-to-validate-email.md)

   - **Lista över tillåtna** IP-adresser: Ange källans IP-adress eller adressintervall i anslutningsfilterprincipen.

     Använd den här inställningen om avsändardomänen inte använder e-postautentisering. Var så restriktiv som möjligt när det gäller käll-IP-adresserna i listan över tillåtna IP-adresser. Vi rekommenderar ett IP-adressintervall på /24 eller mindre (mindre är bättre). Använd inte IP-adressintervall som tillhör konsumenttjänster (till exempel outlook.com) eller delad infrastruktur.

   > [!IMPORTANT]
   >
   > - Konfigurera aldrig e-postflödesregler *med bara* avsändardomänen som villkor att hoppa över skräppostfiltrering. Då ökar  sannolikheten betydligt för att attacker kan förfalskning av avsändardomänen (eller personifiera den fullständiga e-postadressen), hoppa över all skräppostfiltrering och hoppa över autentiseringskontroller för avsändare så att meddelandet kommer till mottagarens inkorg.
   >
   > - Använd inte domäner du äger (kallas även godkända domäner) eller populära domäner (till exempel microsoft.com) som villkor i e-postflödesregler. Att göra det betraktas som hög risk eftersom det skapar möjligheter för attackerare att skicka e-post som annars skulle filtreras.
   >
   > - Om du tillåter en IP-adress som ligger bakom en NAT-gateway (network address translation) behöver du känna till servrarna som är inblandade i NAT-poolen för att ta reda på omfattningen av listan över tillåtna IP-adresser. IP-adresser och NAT-deltagare kan ändras. Du måste regelbundet kontrollera posterna för lista över tillåtna IP-adresser som en del av dina standardunderhåll.

3. **Valfria villkor:**

   - **Avsändaren** \> **är intern/extern** \> **Utanför organisationen:** Det här villkoret är implicit, men det är OK att använda det för att hantera lokala e-postservrar som kanske inte är korrekt konfigurerade.

   - **Ämne eller brödtext** \> **ämne eller brödtext innehåller något av dessa ord** \> : Om du kan begränsa meddelandena ytterligare efter nyckelord eller fraser i ämnesraden eller meddelandetexten kan du använda \<keywords\> de orden som ett villkor.

4. **Åtgärd:** Konfigurera båda dessa åtgärder i regeln:

   a. **Ändra meddelandeegenskaperna** \> **ange SCL (Spam Confidence Level)** \> **Kringgå skräppostfiltrering.**

   b. **Ändra meddelandeegenskaperna** \> **ange ett meddelandehuvud:** **Ställ in** \<CustomHeaderName\> **meddelanderubriken till** \<CustomHeaderValue\> värdet.

      Till exempel `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Om regeln innehåller mer än en domän kan du anpassa texten i sidhuvudet efter behov.

      Om ett meddelande hoppar över skräppostfiltreringen på grund av en e-postflödesregel märks värdet i rubriken `SFV:SKN` **X-Forefront-Antispam-Report.** Om meddelandet kommer från en källa på listan över tillåtna IP-adresser läggs `IPV:CAL` även värdet till. De här värdena kan hjälpa dig med felsökning.

![Inställningar för e-postflödesregel i EAC för att kringgå skräppostfiltrering.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Använda Betrodda avsändare i Outlook

> [!CAUTION]
> Den här metoden innebär en hög risk för att attacker ska leverera e-post till Inkorgen som annars skulle filtreras. Men listorna Betrodda avsändare och Betrodda domäner hindrar inte skadlig programvara eller betrodda nätfiskemeddelanden från att filtreras.

I stället för en organisationsinställning kan användare eller administratörer lägga till avsändaradresserna i listan Betrodda avsändare i postlådan. Instruktioner finns i Konfigurera [skräppostinställningar för Exchange Online-postlådor i Office 365.](configure-junk-email-settings-on-exo-mailboxes.md) Det här är inte ett bra sätt i de flesta situationer eftersom avsändare kringgår delar av filtreringsstacken. Även om du litar på avsändaren kan avsändaren fortfarande komprometteras och skicka skadligt innehåll. Det är bäst att du låter våra filter göra det som behövs för att kontrollera varje meddelande och sedan rapportera det falska [positiva/negativa](report-junk-email-messages-to-microsoft.md) till Microsoft om våra filter fick det fel. Förbikoppling av filtreringsstack stör även [ZAP.](zero-hour-auto-purge.md)

När meddelanden hoppar över skräppostfiltrering på grund av en användares lista över betrodda avsändare innehåller **rubrikfältet X-Forefront-Antispam-Report** värdet, vilket anger att filtrering av skräppost, förfalskning och nätfiske har `SFV:SFE` kringgåts.

## <a name="use-the-ip-allow-list"></a>Använd listan över tillåtna IP-adresser

Om du inte kan använda e-postflödesregler enligt beskrivningen ovan är det näst bästa alternativet att lägga till käll-e-postservern eller servrarna i listan över tillåtna IP-adresser i anslutningsfilterprincipen. Mer information finns i Konfigurera [anslutningsfiltrering i EOP.](configure-the-connection-filter-policy.md)

**Anmärkningar**:

- Det är viktigt att ha så få tillåtna IP-adresser som möjligt, så undvik att använda hela IP-adressintervall när det är möjligt.

- Använd inte IP-adressintervall som tillhör konsumenttjänster (till exempel outlook.com) eller delad infrastruktur.

- Regelbundet granska posterna i listan över tillåtna IP-adresser och ta bort poster som du inte längre behöver.

> [!CAUTION]
> Utan ytterligare verifiering, som e-postflödesregler, hoppar e-post från källor i listan över tillåtna IP-adresser över skräppostfiltrering och avsändarautentisering (SPF, DKIM, DMARC). Då skapas en hög risk för att attacker ska leverera e-post till Inkorgen som annars skulle filtreras. Men listan över tillåtna IP-adresser förhindrar inte att skadlig programvara eller nätfiskemeddelanden med hög konfidens filtreras.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Använda tillåtna avsändarlistor eller listor med tillåtna domäner

Det minst önskat alternativet är att använda listan med tillåtna avsändare eller listan över tillåtna domäner i principer för skydd mot skräppost. Du bör undvika det här alternativet om *det* är möjligt eftersom avsändare kringgår all skräppost, förfalskning och nätfiskeskydd och avsändarautentisering (SPF, DKIM, DMARC). Den här metoden används endast för tillfällig testning. De detaljerade anvisningarna finns i Konfigurera [principer för skydd mot skräppost i EOP-avsnittet.](configure-your-spam-filter-policies.md)

Maxgränsen för dessa listor är ungefär 1 000 poster. även om du bara kan ange 30 poster i portalen. Du måste använda PowerShell för att lägga till fler än 30 poster.

> [!CAUTION]
>
> - Den här metoden innebär en hög risk för att attacker ska leverera e-post till Inkorgen som annars skulle filtreras. Men listorna med tillåtna avsändare eller tillåtna domäner förhindrar inte skadlig programvara eller nätfiskemeddelanden med hög konfidens.
>
> - Använd inte domäner du äger (kallas även godkända domäner) eller populära domäner (till exempel microsoft.com) i listor över tillåtna domäner.

## <a name="considerations-for-bulk-email"></a>Att tänka på när det gäller massutskick

Ett vanligt SMTP-e-postmeddelande består av ett *meddelandekuvert* och meddelandeinnehåll. Meddelandekuvertet innehåller information som behövs för att överföra och leverera meddelandet mellan SMTP-servrar. Meddelandeinnehållet innehåller fält för meddelanderubriker (kallas gemensamt *för meddelanderubriken)* och meddelandets brödtext. Meddelandekuvertet beskrivs i RFC 5321 och meddelanderubriken beskrivs i RFC 5322. Mottagarna ser aldrig det faktiska meddelandekuvertet eftersom det genereras av meddelandeöverföringsprocessen och det är faktiskt inte en del av meddelandet.

- Adressen (kallas även MAIL `5321.MailFrom` **FROM-adress,** P1-avsändare eller kuvertavsändare) är den e-postadress som används vid meddelandets SMTP-överföring. Den här **e-postadressen** registreras vanligtvis i huvudfältet för retursökväg i meddelandehuvudet (även om det är möjligt för avsändaren att ange en annan **e-postadress** för retursökväg). Om meddelandet inte kan levereras är det mottagaren för rapporten om utebliven leverans (kallas även NDR-rapport eller icke-leveransk leverans).

- Den (kallas även från-adress eller P2-avsändare) är e-postadressen i fältet Från rubrik och är avsändarens e-postadress som visas i `5322.From` e-postklienter.  

Ofta är `5321.MailFrom` `5322.From` adresserna och adresserna desamma (kommunikation mellan två personer). Men när e-post skickas åt någon annan kan adresserna vara olika. Det här inträffar oftast vid massutskick av e-postmeddelanden.

Anta till exempel att Blue Yonder Airlines har anställt Margies Travel för att skicka ut sin e-postannonsering. Meddelandet du får i Inkorgen har följande egenskaper:

- Adressen `5321.MailFrom` är blueyonder.airlines@margiestravel.com.

- Adressen `5322.From` är blueyonder@news.blueyonderairlines.com, vilket är vad som visas i Outlook.

Listor över betrodda avsändare och listor över betrodda domäner i principer för skydd mot skräppost i EOP granskar endast adresserna. Det påminner om Betrodda avsändare `5322.From` i Outlook som använder `5322.From` adressen.

För att förhindra att det här meddelandet filtreras kan du göra följande:

- Lägg blueyonder@news.blueyonderairlines.com `5322.From` (adressen) som betrodd avsändare i Outlook.

- [Använd en e-postflödesregel](#recommended-use-mail-flow-rules) med ett villkor som söker efter meddelanden från blueyonder@news.blueyonderairlines.com `5322.From` (adress, e-blueyonder.airlines@margiestravel.com `5321.MailFrom` (), eller båda.

Mer information finns i Skapa [listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)
