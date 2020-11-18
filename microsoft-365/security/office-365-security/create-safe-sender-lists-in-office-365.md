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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa om tillgängliga och önskade alternativ för att tillåta inkommande meddelanden i Exchange Online Protection (EOP).
ms.openlocfilehash: 6d862f0ed6d6bbea56cb2bb79fee69a044e4fede
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130799"
---
# <a name="create-safe-sender-lists-in-eop"></a>Skapa listor med säkra avsändare i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Om du är Microsoft 365-kund med post lådor i Exchange Online eller på en fristående Exchange Online Protection (EOP)-kund utan Exchange Online-postlådor, erbjuder EOP flera olika sätt att säkerställa att användarna får e-post från betrodda avsändare. Dessa alternativ inkluderar regler för Exchange-postflöde (kallas även transport regler), Outlook Safe avsändare, listan över tillåtna IP-adresser (anslutnings filter) och tillåtna avsändar listor eller tillåtna domän listor i principer för skräp post. Tillsammans kan du se dessa alternativ som _listor med säkra avsändare_.

Tillgängliga listor över betrodda avsändare beskrivs i följande lista, i den ordning de rekommenderas till minst Rekommenderad:

1. Regler för e-postflöde
2. Säkra avsändare i Outlook
3. Lista över tillåtna IP-adresser (anslutnings filter)
4. Listan Tillåtna avsändare eller tillåtna domän listor (principer för skräp post)

Reglerna för e-postflöden gör det möjligt att se till att endast rätt meddelanden är tillåtna. Tillåtna avsändare och tillåtna domän listor i principer för skräp post är inte så säkra som listan över tillåtna IP-adresser eftersom avsändarens e-postdomän är lätt att falska. Men i listan över tillåtna IP-adresser visas också en risk, eftersom e-post från vilken domän som _helst_ som skickas från den IP-adressen åsidosätter filtrering av skräp post.

> [!IMPORTANT]
>
> - Se till att noggrant övervaka *eventuella* undantag som du kan använda för att filtrera meddelanden med säkra avsändare.
>
> - Du kan använda listor med säkra avsändare för att få hjälp med falsk identifiering (god e-post markerat som spam), men du bör överväga att använda säkra avsändar listor som en tillfällig lösning som bör undvikas om möjligt. Vi rekommenderar inte att du hanterar falsk identifiering genom att använda listor med säkra avsändare, eftersom undantag för skräp post filtrering kan öppna din organisation för förfalskning och andra attacker. Om du måste med hjälp av säkra avsändar listor för att hantera falska positiva identifieringar måste du vara vigilant och hålla koll på [meddelandena och filerna till Microsoft](report-junk-email-messages-to-microsoft.md) när du är redo.
>
> - Om du vill tillåta att en domän skickar overifierad e-post (kringgå skydd mot förfalskning) men inte kringgår kontroll av skräp post och skadlig program vara, kan du lägga till den i [AllowedToSpoof Safe Sender List](walkthrough-spoof-intelligence-insight.md)
>
> - EOP och Outlook inspekterar olika meddelande egenskaper för att bestämma meddelandets avsändare. Mer information finns i avsnittet [om att skicka e-post](#considerations-for-bulk-email) längre ned i det här avsnittet.

Däremot har du flera alternativ för att blockera e-post från specifika källor med _spärrade avsändare_. Mer information finns i artikeln om att [skapa listor över blockerade avsändare i EOP](create-block-sender-lists-in-office-365.md).

## <a name="recommended-use-mail-flow-rules"></a>Lämpligt Använda regler för e-postflöde

Regler för e-postflöden i Exchange Online och fristående EOP användnings villkor och undantag för att identifiera meddelanden och åtgärder för att ange vad som ska göras i dessa meddelanden. Mer information finns i [regler för e-postflöde (transport regler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

I följande exempel förutsätts att du behöver e-post från contoso.com för att hoppa över skräp post filtrering. Gör det genom att konfigurera följande inställningar:

1. **Villkor**: **avsändarens** \> **domän är** \> contoso.com.

2. Konfigurera någon av följande inställningar:

   - **Regel villkor för e-postflöde**: **ett meddelande huvud** \> **innehåller något av följande ord** \> **rubrik namn**: `Authentication-Results` \> **header-värde**: `dmarc=pass` eller `dmarc=bestguesspass` .

     Det här villkoret kontrollerar statusen för e-poststatus för den sändande e-postdomänen för att säkerställa att den sändande domänen inte är falsk. Mer information om e-postauktorisering finns i [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC](use-dmarc-to-validate-email.md).

   - **Lista över tillåtna IP-** adresser: Ange käll-IP-adressen eller adress intervallet i anslutnings filter principen.
  
     Använd den här inställningen om den sändande domänen inte använder e-postauktorisering. Var så restriktiv som möjligt när det kommer till käll-IP-adresserna i listan över tillåtna IP-adresser. Vi rekommenderar ett IP-adressintervall på/eller mindre (mindre är bättre). Använd inte IP-adressintervall som tillhör konsument tjänster (till exempel outlook.com) eller delade infrastrukturer.

   > [!IMPORTANT]
   >
   > - Konfigurera aldrig regler för e-postflöden med *endast* avsändarens domän som villkor för att hoppa över filtrering av skräp post. Om du gör *det ökar* sannolikheten för att angripare kan falska den sändande domänen (eller personifiera den fullständiga e-postadressen), hoppa över alla skräp post filter och hoppa över avsändare av verifikations kontroll så att meddelandet kommer till mottagarens inkorg.
   >
   > - Använd inte domäner som du äger (kallas även godkända domäner) eller vanliga domäner (till exempel microsoft.com) som villkor i regler för e-postflöde. Det betraktas som en hög risk eftersom det skapar möjligheter för angripare att skicka e-post som annars skulle filtreras.
   >
   > - Om du tillåter en IP-adress som ligger bakom en NAT-gateway (Network Address Translation) måste du känna till de servrar som ingår i NAT-poolen för att kunna veta omfattningen av listan över tillåtna IP-adresser. IP-adresser och NAT-deltagare kan ändra. Du måste regelbundet kontrol lera listan över tillåtna IP-poster som en del av dina standard underhålls procedurer.

3. **Valfria villkor**:

   - **Avsändaren** \> **är intern/extern** \> **Utanför organisationen**: det här villkoret är implicit, men det är OK att använda det för att logga in på lokala e-postservrar som kanske inte är korrekt konfigurerade.

   - **Ämne eller brödtext** \> **ämne eller brödtext innehåller något av dessa ord** \> \<keywords\>: Om du kan begränsa meddelandena ytterligare med nyckelord eller fraser i ämnes raden eller meddelande texten kan du använda dessa ord som villkor.

4. **Åtgärd**: Konfigurera båda de här åtgärderna i regeln:

   a. **Ändra meddelande egenskaper** \> **Ställ in nivån för skräp post (SCL)** \> **Kringgå filtrering av skräp post**.

   b. **Ändra meddelande egenskaper** \> **Ange ett meddelande huvud**: **Ange meddelande huvudet** \<CustomHeaderName\> **till värdet** \<CustomHeaderValue\> .

      Till exempel `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Om du har fler än en domän i regeln kan du anpassa sidhuvud texten efter behov.

      När ett meddelande hoppar över skräp post filtrering på grund av en regel för e-postflöde stämplas värdet värde av `SFV:SKN` i huvudet **X-antispam-Report** . Om meddelandet kommer från en källa som är med i listan över tillåtna IP-adresser `IPV:CAL` läggs värdet också till. Dessa värden kan hjälpa dig med fel sökning.

![Inställningar för regel för e-postflöde i UK för att hoppa över filtrering av skräp post.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Använda betrodda avsändare i Outlook

I stället för en organisations inställning kan användare eller administratörer lägga till avsändarens e-postadresser i listan Betrodda avsändare i post lådan. Anvisningar finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Office 365](configure-junk-email-settings-on-exo-mailboxes.md). Detta är inte önskvärt i de flesta fall eftersom avsändare kringgår delar av filtrerings stacken. Trots att du litar på avsändaren kan avsändaren ändå vara angripen och skicka skadligt innehåll. Det är bäst att låta våra filter göra vad som behövs för att kontrol lera alla meddelanden och sedan [rapportera falskt positiv/negativ till Microsoft](report-junk-email-messages-to-microsoft.md) om våra filter har fel. Om du kringgår filtrerings stacken påverkas också inte med [ZAP](zero-hour-auto-purge.md).

När meddelanden hoppar över filtrering av skräp post på grund av en användares lista med betrodda avsändare kommer fältet **X-antispam – rapport** huvud att innehålla värdet `SFV:SFE` , vilket betyder att filtrering av skräp post, förfalskning och nätfiske hoppades över.

## <a name="use-the-ip-allow-list"></a>Använd listan över tillåtna IP-adresser

Om du inte kan använda regler för e-postflöde enligt beskrivningen ovan är nästa bästa alternativet att lägga till käll-e-postservern eller servrar i listan över tillåtna IP-adresser för anslutnings filter. Mer information finns i [Konfigurera anslutnings filtrering i EOP](configure-the-connection-filter-policy.md).

**Anmärkningar**:

- Det är viktigt att du behåller det minsta antalet tillåtna IP-adresser, så undvik att använda hela IP-adressintervallet när så är möjligt.

- Använd inte IP-adressintervall som tillhör konsument tjänster (till exempel outlook.com) eller delade infrastrukturer.

- Granska posterna i listan över tillåtna IP-adresser och ta bort de uppgifter som du inte längre behöver.

> [!CAUTION]
> Utan extra verifiering som regler för e-postflöde hoppar e-post från källor i listan över tillåtna IP-adresser över skräp post och avsändare (SPF, DKIM, DMARC). Detta skapar en stor risk för att attackerare skickar e-post till Inkorgen som annars skulle filtrerats.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Använda listor med tillåtna avsändare eller tillåtna domän listor

Det minst önskvärda alternativet är att använda listan med tillåtna avsändare eller tillåtna domäner i principer för skräp post. Du bör undvika det här alternativet om det är *möjligt* eftersom avsändarna kringgår all skräp post, falskheten och nätfiske-skyddet (SPF, DKIM, DMARC). Den här metoden är bäst för tillfälliga tester. Detaljerade anvisningar finns i [Konfigurera principer för skydd mot skräp post i EOP](configure-your-spam-filter-policies.md) avsnitt.

Högsta tillåtna gräns för dessa listor är ungefär 1000 poster; Du kan dock bara ange 30 poster i portalen. Du måste använda PowerShell för att lägga till fler än 30 poster.

> [!CAUTION]
>
> - Med den här metoden skapas en stor risk för att attackerare skickar e-post till Inkorgen som annars skulle filtreras.
>
> - Använd inte domäner som du äger (kallas även godkända domäner) eller vanliga domäner (till exempel microsoft.com) i listan över tillåtna domän rapporter.

## <a name="considerations-for-bulk-email"></a>Att tänka på för Mass utskick

Ett SMTP-standard-e-postmeddelande består av ett *meddelandes kuvert* och meddelande innehåll. Meddelandets kuvert innehåller information som krävs för överföring och leverans av meddelandet mellan SMTP-servrar. Meddelandets innehåll innehåller fält för meddelande rubrik (gemensamt kallat *meddelande huvudet*) och meddelande texten. Meddelandets kuvert beskrivs i RFC 5321 och meddelande huvudet beskrivs i RFC 5322. Mottagarna kan aldrig se det faktiska meddelandets kuvert eftersom det är genererat av meddelande överföringen och egentligen inte ingår i meddelandet.

- `5321.MailFrom`Adressen (kallas även för **e-post från** adress, P1 avsändare eller kuvert avsändare) är den e-postadress som används i SMTP-överföringen av meddelandet. Den här e-postadressen lagras normalt i huvud fältet för **RETUR-sökväg** i meddelande huvudet (även om det är möjligt för avsändaren att ange en annan e-postadress för **RETUR-sökvägen** ). Om det inte går att leverera meddelandet är det mottagaren för rapporten om utebliven leverans (kallas även för en NDR eller ett studs meddelande).

- `5322.From`(Kallas även **från** -adressen eller P2-avsändaren) är e-postadressen i fältet **från** huvud och är avsändarens e-postadress som visas i e-postklienter.

Ofta är de `5321.MailFrom` och `5322.From` adresserna samma (person-till-person-kommunikation). Men när e-post skickas åt någon annan kan adresser vara olika. Detta gäller oftast för Mass utskick av e-postmeddelanden.

Anta till exempel att Blue Yonder-flyg bolag har hyrt Margie ' s Travel för att skicka ut sin e-postannonsering. Meddelandet som du får i Inkorgen har följande egenskaper:

- `5321.MailFrom`Adressen är blueyonder.Airlines@margiestravel.com.

- `5322.From`Adressen är blueyonder@news.blueyonderairlines.com, som du kommer att se i Outlook.

Listorna Betrodda avsändare och betrodda domäner i en policy för borttagning av skräp post i EOP inspektera bara `5322.From` adresserna, det fungerar ungefär som betrodda avsändare med Outlook `5322.From` .

Om du inte vill filtrera meddelandet kan du utföra följande steg:

- Lägg till blueyonder@news.blueyonderairlines.com ( `5322.From` adressen) som en Outlook Safe-avsändare.

- [Använd en regel för e-postflöde](#recommended-use-mail-flow-rules) med ett villkor som letar efter meddelanden från blueyonder@news.blueyonderairlines.com ( `5322.From` adress, blueyonder.Airlines@margiestravel.com (det `5321.MailFrom` ) eller båda.

Mer information finns i [skapa säkra avsändare i EOP](create-safe-sender-lists-in-office-365.md).
