---
title: Principer för skydd mot nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om vilka phishing-principer som är tillgängliga i Exchange Online Protection (EOP) och Microsoft Defender för Office 365.
ms.openlocfilehash: 9d3c8c0bf2b1c440892a1099d3d0812d95027156
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615774"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Anti-nätfiske-principer i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Principer för att konfigurera inställningar för skydd mot nätfiske är tillgängliga i Microsoft 365-organisationer med Exchange Online-postlådor, fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor och Microsoft Defender för Office 365-organisationer.

AntiPhishing-principer i Microsoft Defender för Office 365 är endast tillgängliga i organisationer som har Defender för Office 365. Till exempel:

- Microsoft 365 Enterprise, E5, Microsoft 365 Education A5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender för Office 365 som ett tillägg](https://products.office.com/exchange/advance-threat-protection)

De högre skillnaderna mellan anti-nätfiske-principer i EOP och anti-nätfiske-principer i Microsoft Defender för Office 365 beskrivs i följande tabell:

****

|Funktion|Skydd mot nätfiske i EOP|Skydd mot nätfiske i Microsoft Defender för Office 365|
|---|:---:|:---:|
|Automatiskt skapad standard policy|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Skapa anpassade principer|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Princip inställningar<sup>\*</sup>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Inställningar för personifiering||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Inställningar för förfalskning|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Avancerade nät fiske trösklar||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup> I standard principen är princip namnet och beskrivningen skrivskyddad (beskrivningen är tom) och du kan inte ange vem principen gäller för (standard policyn gäller för alla mottagare).

Information om hur du konfigurerar principer för nätfiske finns i följande artiklar:

- [Konfigurera AntiPhishing-principer i EOP](configure-anti-phishing-policies-eop.md)

- [Konfigurera AntiPhishing-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md)

I resten av den här artikeln beskrivs de inställningar som är tillgängliga i principer för nätfiske i EOP och Defender för Office 365.

## <a name="policy-settings"></a>Princip inställningar

Följande princip inställningar är tillgängliga i principer för nätfiske i EOP och Microsoft Defender för Office 365:

- **Namn**: det går inte att byta namn på standard policyn för anti-phishing, men du kan namnge och byta namn på anpassade principer som du skapar.

- **Beskrivning** Du kan inte lägga till en beskrivning av standard policyn för anti-nätfiske, men det går att lägga till och ändra beskrivningen för anpassade principer som du skapar.

- **Tillämpat på**: identifierar interna mottagare som antivirus policyn gäller för. Det här värdet är obligatoriskt i anpassade principer och är inte tillgängligt i standard principen (standard policyn gäller för alla mottagare).

  Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

  - **Mottagare**: en eller flera post lådor, e-postkonton eller e-postkontakter i din organisation.
  - **Mottagaren är medlem i** en eller flera grupper i din organisation.
  - **Mottagar domänen är**: en eller flera av de godkända domänerna i Microsoft 365.

  - **Förutom när**: undantag för regeln. Inställningarna och beteendet är exakt som villkor:

    - **Mottagaren är**
    - **Mottagaren är medlem i**
    - **Mottagar domänen är**

  > [!NOTE]
  > Inställningen **tillämpa på** är obligatorisk i anpassade principer för nätfiske **för att identifiera vilka meddelanden** <u>som principen gäller för</u>. Anti-nätfiske-principer i Microsoft Defender för Office 365 har också [personifieringsparametrar-inställningar](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) där du kan ange enskilda avsändare-e-postadresser eller avsändar domäner <u>som ska få personifieringsnivå</u> enligt beskrivningen längre ned i det här avsnittet.

## <a name="spoof-settings"></a>Inställningar för förfalskning

Förfalskning är när från-adressen i ett e-postmeddelande (avsändar adressen som visas i e-postklienter) inte stämmer överens med e-postkällans domän. Mer information om förfalskning finns i skydd mot [förfalskning i Microsoft 365](anti-spoofing-protection.md).

Följande inställningar för förfalskning är tillgängliga i principer för nätfiske i EOP och Microsoft Defender för Office 365:

- **Skydd mot förfalskning**: aktiverar eller inaktiverar skydd mot förfalskning. Vi rekommenderar att du låter den vara aktive rad. Du använder **principen för förfalsknings information** för att tillåta eller blockera viss falsk intern och extern avsändare. Mer information finns i [Konfigurera förfalskningsinformation i Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  >
  > - Skydd mot förfalskning är aktiverat som standard i standard AntiPhishing-principen och i alla nya anpassade Antivirus principer som du skapar.
  >
  > - Du behöver inte inaktivera skydd mot förfalskning om din MX-post inte pekar på Microsoft 365; du aktiverar bättre filtrering för kopplingar i stället. Anvisningar finns i [utökad filtrering för kopplingar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

  För meddelanden från blockerade avsändare som inte är falska kan du även ange vilken åtgärd som ska vidtas:

  - **Flytta meddelandet till mappen skräp post**: det här är standardvärdet. Meddelandet skickas till post lådan och flyttas till mappen skräp post. I Exchange Online flyttas meddelandet till mappen skräp post om skräp post regeln är aktive rad på post lådan (den är aktive rad som standard). Mer information finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Karantän meddelandet**: skickar meddelandet till karantän i stället för avsedda mottagare. Information om karantän finns i följande artiklar:

    - [Karantän i Microsoft 365](quarantine-email-messages.md)
    - [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Hitta och släppa meddelanden i karantän som en användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Oautentiserad avsändare**: se informationen i nästa avsnitt.

### <a name="unauthenticated-sender"></a>Overifierad avsändare

Overifierad avsändare är en del av de [förfalsknings inställningar](#spoof-settings) som är tillgängliga i principer för nätfiske i EOP och Microsoft Defender för Office 365 enligt beskrivningen i föregående avsnitt.

Inställningen **overifierad avsändare** aktiverar eller inaktiverar icke autentiserad avsändare i Outlook. Verkligen

- Ett frågetecken (?) läggs till avsändarens foto om meddelandet inte tillåter SPF-eller DKIM-kontroller **och** meddelandet klarar inte DMARC eller [sammansatt](email-validation-and-authentication.md#composite-authentication)behörighet. Om du inaktiverar overifierad avsändare hindrar du att frågetecknet läggs till i avsändarens bild.

- Via-taggen (chris@contoso.com <u>via</u> Michelle@fabrikam.com) läggs till om domänen i from-adressen (meddelande avsändaren som visas i e-postklienter) skiljer sig från domänen i DKIM-signaturen eller **e-** postadressen. Mer information om dessa adresser finns i [Översikt över e-poststandarder](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

  Inaktive ring av overifierad avsändare förhindrar inte att taggen via läggs till om domänen i från-adressen är annorlunda i DKIM-signaturen eller e-postadressen.

För att förhindra att frågetecknet eller via-tagg läggs till i meddelanden från specifika avsändare har du följande alternativ:

- Tillåt avsändaren till förfalskning i policyn för förfalsknings information. Med den här åtgärden kan du förhindra att via-märket visas i meddelanden från avsändaren när avsändaren av avsändar-ID är inaktive rad. Anvisningar finns i [Konfigurera förfalsknings intelligens i Microsoft 365](learn-about-spoof-intelligence.md).

- [Konfigurera e-postauktorisering](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) för avsändarens domän.
  - För frågetecknet i avsändarens foto, SPF eller DKIM är de viktigaste.
  - För via-taggen bekräftar du domänen i DKIM signatur eller **e-** postadressen matchar (eller är en under domän av) domänen i från-adressen.

Mer information finns i [identifiera misstänkta meddelanden i Outlook.com och Outlook på webben](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Exklusiva inställningar i policy mot nätfiske i Microsoft Defender för Office 365

I det här avsnittet beskrivs de princip inställningar som endast är tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365.

> [!NOTE]
> Standard policyn för anti-phishing i Microsoft Defender för Office 365 tillhandahåller [förfalsknings skydd](set-up-anti-phishing-policies.md#spoof-settings) och post lådans intelligens för alla mottagare. Men de andra tillgängliga funktionerna för [skydd mot personifiering](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) och [Avancerade inställningar](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) är inte konfigurerade eller aktiverade i standard principen. Om du vill aktivera alla skydds funktioner ändrar du standard policyn för anti-phishing eller skapar ytterligare skydd mot nätfiske.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Inställningar för personifiering i principer för nätfiske i Microsoft Defender för Office 365

Personifiering är den plats där avsändaren eller avsändarens e-postdomän i ett meddelande ser ut ungefär som en riktig avsändare eller domän:

- Ett exempel på personifiering av domänen contoso.com är ćóntoso.com.
- Ett exempel på personifiering av användaren michelle@contoso.com är michele@contoso.com.

En personifierad domän kan på annat sätt anses vara legitim (registrerad domän, konfigurerade e-postautentiseringsmetoder, etc.), förutom att det är bra att vilseleda mottagare.

Följande inställningar för personifiering är bara tillgängliga i policy mot nätfiske i Microsoft Defender för Office 365:

- **Användare att skydda**: förhindrar att angivna interna eller externa e-postadresser personifieras **som avsändare**. Om du till exempel får ett e-postmeddelande från ditt företags president ber du dig skicka lite intern företags information. Skulle du göra det? Många vill skicka svaret utan att tänka.

  Du kan använda skyddade användare för att lägga till e-postadresser för intern och extern avsändare för att skydda mot användning av personifiering. Den här listan över **avsändare** som skyddas från användarautentisering skiljer sig från listan över **mottagare** som principen gäller för (alla mottagare av standard principen, specifika mottagare **enligt inställningarna i avsnittet** [princip inställningar](#policy-settings) ).

  > [!NOTE]
  >
  > - I varje skydds princip kan du ange högst 60 skyddade användare (avsändarens e-postadress). Du kan inte ange samma skyddade användare i flera principer.
  >
  > - Användarautentisering fungerar inte om avsändaren och mottagaren tidigare kommunicerat via e-post. Om avsändaren och mottagaren aldrig har kommunicerat via e-post identifieras meddelandet som ett personifierings försök.

  Standardinställningen är att inga e-postadresser för avsändare har kon figurer ATS för personifieringsnivå för **användare att skydda**. Därför är inte e-postadresserna för avsändare täckta av personifiering, antingen i standard principen eller i anpassade principer.

  När du lägger till interna eller externa e-postadresser i listan **användare att skydda** lista, är meddelanden från dessa **avsändare** föremål för kontroll av integritets skydd. Meddelandet kontrol leras för personifiering **om** meddelandet skickas till en **mottagare** som policyn gäller för (alla mottagare för standard principen; **Tillämpas på** mottagare i anpassade principer). Om personifiering upptäcks i avsändarens e-postadress tillämpas åtgärdens skydds åtgärder för användare i meddelandet (vad du kan göra med meddelandet om du vill visa personifierade användares säkerhets tips osv.).

- **Domäner att skydda**: förhindrar att de angivna domänerna personifieras **i meddelandets avsändares domän**. Till exempel alla domäner som du äger ([godkända domäner](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) eller specifika domäner (domäner som du äger eller partner domäner). Den här listan över **avsändare** som skyddas mot personifiering skiljer sig från listan över **mottagare** som principen gäller för (alla mottagare av standard principen, specifika mottagare **enligt inställningarna i avsnittet** [princip inställningar](#policy-settings) ).

  > [!NOTE]
  > Det maximala antalet skyddade domäner som du kan definiera i alla anti-nätfiske-principer är 50.

  Som standard är inga avsändare konfigurerade för personifierings skydd i **domäner att skydda**. Därför täcks inte heller inga avsändare via personifiering, antingen i standard principen eller i anpassade principer.

  När du lägger till domäner i **domänen för att skydda** listan är meddelanden från **avsändare i dessa domäner** föremål för skydds kontroller för obehöriga. Meddelandet kontrol leras för personifiering **om** meddelandet skickas till en **mottagare** som policyn gäller för (alla mottagare för standard principen; **Tillämpas på** mottagare i anpassade principer). Om personifiering hittas i avsändarens domän tillämpas åtgärderna för skydd mot personifiering för domäner (vad du kan göra med meddelandet, om du vill visa personifierade användares säkerhets tips osv.).

- **Åtgärder för skyddade användare eller domäner**: Välj vilken åtgärd som ska vidtas i inkommande meddelanden som innehåller användnings försök mot de skyddade användarna och skyddade domäner i principen. Du kan ange olika åtgärder för personifiering av skyddade användare kontra personifiering av skyddade domäner:

  - **Tillämpa inte någon åtgärd**

  - **Omdirigera meddelande till andra e-postadresser**: skickar meddelandet till mottagarna i stället för avsedda mottagare.

  - **Flytta meddelandet till mappen skräp post**: meddelandet skickas till post lådan och flyttas till mappen skräp post. I Exchange Online flyttas meddelandet till mappen skräp post om skräp post regeln är aktive rad på post lådan (den är aktive rad som standard). Mer information finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - **Karantän meddelandet**: skickar meddelandet till karantän i stället för avsedda mottagare. Information om karantän finns i följande artiklar:

    - [Karantän i Microsoft 365](quarantine-email-messages.md)
    - [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Hitta och släppa meddelanden i karantän som en användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Leverera meddelandet och Lägg till andra adresser till raden Hemlig kopia**: skicka meddelandet till de avsedda mottagarna och tyst skicka meddelandet till mottagarna.

  - **Ta bort meddelandet innan det levereras**: det tar tyst bort hela meddelandet, inklusive alla bifogade filer.

- **Säkerhets tips**: aktiverar eller inaktiverar följande säkerhets tips som kommer att visas meddelanden som inte fungerar:

  - **Personifierade användare**: från-adressen innehåller en skyddad användare.
  - **Personifierade domäner**: från-adressen innehåller en skyddad domän.
  - **Ovanliga tecken**: från-adressen innehåller ovanliga tecken uppsättningar (till exempel matematiska symboler och text eller en blandning av versaler och gemener) i en skyddad avsändare eller domän.

  > [!IMPORTANT]
  >
  > Även när säkerhets tipset för personifiering är inaktiverat **rekommenderar vi** att du använder en regel för e-postflöde (kallas även en transport regel) för att lägga till ett meddelande som heter **X-MS-Exchange-EnableFirstContactSafetyTip** med värde **Aktivera** meddelanden. Ett säkerhets tips meddelar mottagarna första gången de får ett meddelande från avsändaren, eller om de inte får meddelanden från avsändaren ofta.
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="Texten i säkerhets tipset för personifiering med flera mottagare.":::

- **Post låda**: aktiverar eller inaktiverar artificiell intelligens (AI) som bestämmer användarnas e-postmönster med deras vanliga kontakter. Den här inställningen hjälper AI-åtskillnaden mellan legitim och falsk e-post från de kontakterna. Post låda-intelligens är bara tillgängligt för Exchange Online-postlådor.

- **Post låda baserat på postskydd**: aktiverar eller inaktiverar utökade personifieringsnivå utifrån användarens enskilda avsändare. Med den här intelligensen kan Microsoft 365 anpassa identifiering av användarautentisering och bättre bevarade falsk identifiering. När personifiering av användare identifieras kan du ange en specifik åtgärd att vidta i meddelandet:

  - **Tillämpa inte någon åtgärd**
  - **Omdirigera meddelanden till andra e-postadresser**
  - **Flytta meddelandet till mappen skräp post**
  - **Sätt i karantän meddelandet**
  - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
  - **Ta bort meddelandet innan det levereras**

- **Betrodda avsändare och domäner**: undantag till inställningarna för skydd mot obehörig person. Meddelanden från angivna avsändare och avsändare klassificeras aldrig som personifieringsnivå av principen. Med andra ord tillämpas inte åtgärden för skyddade avsändare, skyddade domäner eller post lådans informations skydd för dessa betrodda avsändare eller avsändare. Högsta tillåtna gräns för dessa listor är ungefär 1000 poster.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Avancerade gräns värden för nätfiske i principer för nätfiske i Microsoft Defender för Office 365

Följande avancerade nät fiske trösklar är bara tillgängliga i principer för nätfiske i Microsoft Defender för Office 365. Dessa tröskelvärden styr känsligheten för att använda dator utbildnings modeller på meddelanden för att fastställa ett nät fiske Verdict:

- **1-standard**: det här är standardvärdet. Allvarlighets graden för den åtgärd som tas i meddelandet beror på hur mycket du är säker på att meddelandet är nätfiske (Low, medium, High eller mycket hög exakthet). Meddelanden som identifieras som nätfiske med en mycket stor exakthet har de svåraste åtgärderna, medan meddelanden som identifieras som nätfiske med låg exakthet har färre omfattande åtgärder.

- **2 – aggressiv**: meddelanden som identifieras som nätfiske med en hög exakthet behandlas som om de identifierades med en mycket stor tillförlitlighet.

- **3-fler aggressiva**: meddelanden som identifieras som nätfiske med medelhög eller hög tillförlitlighet behandlas som om de har identifierats med mycket stor tillförlitlighet.

- **4 – de flesta aggressiva**: meddelanden som identifieras som nätfiske med en låg, medels Tor eller hög exakthet behandlas som om de identifierades med en mycket stor exakthet.

Chansen att falska positiva (negativa meddelanden är markerade som dåliga) ökar när du ökar den här inställningen. Information om de rekommenderade inställningarna finns i [principer för anti-nätfiske i inställningar för Microsoft Defender för Office 365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).
