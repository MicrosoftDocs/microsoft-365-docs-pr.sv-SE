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
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om principer för nätfiske som finns i Exchange Online Protection (EOP) och Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 083fd4ae7e5564f2affeca73dd3d78a52657c5a7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287323"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Principer för skydd mot nätfiske i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Principer för att konfigurera inställningar för skydd mot nätfiske är tillgängliga i Microsoft 365-organisationer med Exchange Online-postlådor, fristående Exchange Online Protection (EOP) organisationer utan Exchange Online-postlådor och Microsoft Defender för Office 365-organisationer.

Principer för skydd mot nätfiske i Microsoft Defender för Office 365 är endast tillgängliga i organisationer som har Defender för Office 365. Till exempel:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5 osv.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender för Office 365 som ett tillägg](https://products.office.com/exchange/advance-threat-protection)

De stora skillnaderna mellan principer för skydd mot nätfiske i EOP och principer för skydd mot nätfiske i Microsoft Defender för Office 365 beskrivs i följande tabell:

****

|Funktion|Principer för skydd mot nätfiske i EOP|Principer mot nätfiske i Microsoft Defender för Office 365|
|---|:---:|:---:|
|Standardprincip skapad automatiskt|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|Skapa anpassade principer|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|Principinställningar<sup>\*</sup>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|Inställningar för personifiering||![Bockmarkering](../../media/checkmark.png)|
|Inställningar för förfalskning|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|Avancerade tröskelvärden för nätfiske||![Bockmarkering](../../media/checkmark.png)|
|

<sup>\*</sup> I standardprincipen är principnamnet och beskrivningen skrivskyddade (beskrivningen är tom) och du kan inte ange vem principen ska gälla för (standardprincipen gäller för alla mottagare).

Information om hur du konfigurerar principer mot nätfiske finns i följande artiklar:

- [Konfigurera principer för skydd mot nätfiske i EOP](configure-anti-phishing-policies-eop.md)

- [Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md)

I resten av den här artikeln beskrivs de inställningar som är tillgängliga i principer mot nätfiske i EOP och Defender för Office 365.

## <a name="policy-settings"></a>Principinställningar

Följande principinställningar är tillgängliga i principer för skydd mot nätfiske i EOP och Microsoft Defender för Office 365:

- **Namn:** Du kan inte byta namn på standardprincipen för nätfiske, men du kan namnge och byta namn på anpassade principer som du skapar.

- **Beskrivning** Du kan inte lägga till en beskrivning i standardprincipen för nätfiske, men du kan lägga till och ändra beskrivningen för anpassade principer som du skapar.

- **Används för:** Identifierar interna mottagare som principen mot nätfiske gäller för. Det här värdet krävs i anpassade principer och är inte tillgängligt i standardprincipen (standardprincipen gäller för alla mottagare).

  Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

  - **Mottagaren är:** En eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.
  - **Mottagaren är medlem i**: En eller flera grupper i organisationen.
  - **Mottagardomänen är:** En eller flera av de konfigurerade godkända domänerna i Microsoft 365.

  - **Förutom när**: Undantag för regeln. Inställningarna och beteendet är exakt som villkoren:

    - **Mottagaren**
    - **Mottagaren är medlem i**
    - **Mottagardomänen är**

  > [!NOTE]
  > Inställningen **Används för** krävs i anpassade principer för nätfiske för att identifiera vilka mottagare av **meddelandet** <u>som principen gäller för.</u> Principer för skydd mot nätfiske i Microsoft [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Defender för Office 365 har också <u></u> personifieringsinställningar där du kan ange enskilda avsändares e-postadresser eller avsändardomäner som får personifieringsskydd enligt beskrivningen längre fram i den här artikeln.

## <a name="spoof-settings"></a>Inställningar för förfalskning

Förfalskning är när avsändaradressen i ett e-postmeddelande (den avsändaradress som visas i e-postklienter) inte matchar domänen för e-postkällan. Mer information om förfalskning finns i Skydd mot [förfalskning i Microsoft 365.](anti-spoofing-protection.md)

Följande inställningar för förfalskning finns i principer för skydd mot nätfiske i EOP och Microsoft Defender för Office 365:

- **Skydd mot förfalskning:** Aktiverar eller inaktiverar skydd mot förfalskning. Vi rekommenderar att du låter det vara aktiverat. Du använder **förfalskningsinformationsprincipen för** att tillåta eller blockera specifika falska interna och externa avsändare. Mer information finns i [Konfigurera förfalskningsinformation i Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  >
  > - Skydd mot förfalskning är aktiverat som standard i standardprincipen för skydd mot nätfiske och i alla nya anpassade principer för skydd mot nätfiske som du skapar.
  >
  > - Du behöver inte inaktivera skydd mot förfalskning om MX-posten inte pekar på Microsoft 365. aktiverar du Utökad filtrering för kopplingar i stället. Instruktioner finns i Utökad [filtrering för kopplingar i Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)
  >
  > - Om du inaktiverar skydd mot förfalskning inaktiveras bara implicit förfalskningsskydd från [sammansatta](email-validation-and-authentication.md#composite-authentication) autentiseringskontroller. Om avsändaren inte klarar av [en uttrycklig DMARC-kontroll](use-dmarc-to-validate-email.md) där principen sätts i karantän eller avvisas, sätts meddelandet fortfarande i karantän eller avvisas.

  För meddelanden från spärrade förfalskningsavsändare kan du också ange vilken åtgärd som ska vidtas på meddelandena:

  - **Flytta meddelandet till mappen Skräppost:** det här är standardvärdet. Meddelandet levereras till postlådan och flyttas till mappen Skräppost. I Exchange Online flyttas meddelandet till mappen Skräppost om skräppostregeln är aktiverad för postlådan (den är aktiverad som standard). Mer information finns i Konfigurera [skräppostinställningar för Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

  - **Sätt meddelandet i karantän:** Skickar meddelandet till karantän i stället för de avsedda mottagarna. Mer information om karantän finns i följande artiklar:

    - [Karantän i Microsoft 365](quarantine-email-messages.md)
    - [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Hitta och släppa meddelanden i karantän som användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Oauthiskt avsändare:** Se informationen i nästa avsnitt.

### <a name="unauthenticated-sender"></a>Oauthenticerad avsändare

Oauthiskt identifiering av avsändare är [](#spoof-settings) en del av inställningarna för förfalskning som är tillgängliga i principer för skydd mot nätfiske i EOP och Microsoft Defender för Office 365 enligt beskrivningen i föregående avsnitt.

Inställningen **Oauthenticated sender** enables or disables unauthenticated sender identification in Outlook. Mer specifikt:

- Ett frågetecken (?) läggs till på avsändarens foto om meddelandet inte  klarar SPF- eller DKIM-kontroller och meddelandet inte klarar DMARC eller [sammansatt autentisering.](email-validation-and-authentication.md#composite-authentication) Om du inaktiverar ett oauenticerat avsändar-ID förhindrar du att frågetecknet läggs till på avsändarens foto.

- Via-taggen (chris@contoso.com <u>via</u> fabrikam.com) läggs till om domänen i från-adressen (meddelandeavsändaren som visas i e-postklienter) skiljer sig från domänen i DKIM-signaturen eller **MAIL FROM-adressen.** Mer information om de här adresserna finns i [En översikt över standarder för e-postmeddelanden.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  Att inaktivera oauthenticerad avsändar-ID hindrar inte via-taggen från att läggas till om domänen i från-adressen skiljer sig från domänen i DKIM-signaturen eller MAIL FROM-adressen.

Om du vill förhindra att frågetecknet eller taggen läggs till i meddelanden från specifika avsändare har du följande alternativ:

- Tillåt att avsändaren förfalskning i förfalskningsinformationsprincipen. Den här åtgärden förhindrar att via-taggen visas i meddelanden från avsändaren när oauticerad avsändar-ID inaktiveras. Instruktioner finns i [Konfigurera förfalskningsinformation i Microsoft 365.](learn-about-spoof-intelligence.md)

- [Konfigurera e-postautentisering](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) för avsändardomänen.
  - För frågetecknet på avsändarens foto är SPF eller DKIM det viktigaste.
  - För via-taggen bekräftar du domänen i signaturen DKIM eller så matchar **MAIL FROM-adressen** (eller är en underdomän till) domänen i från-adressen.

Mer information finns i [Identifiera misstänkta meddelanden i Outlook.com och Outlook på webben](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Exklusiva inställningar i principer för skydd mot nätfiske i Microsoft Defender för Office 365

I det här avsnittet beskrivs de principinställningar som bara är tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365.

> [!NOTE]
> Standardprincipen för skydd mot nätfiske i Microsoft Defender för Office 365 ger skydd mot [förfalskning](set-up-anti-phishing-policies.md#spoof-settings) och postlådeinformation för alla mottagare. Men andra tillgängliga funktioner [för personifieringsskydd](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) och [avancerade inställningar är](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) inte konfigurerade eller aktiverade i standardprincipen. Om du vill aktivera alla skyddsfunktioner ändrar du standardprincipen för skydd mot nätfiske eller skapar ytterligare principer mot nätfiske.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Inställningar för personifiering i principer för skydd mot nätfiske i Microsoft Defender för Office 365

Personifiering är när avsändaren eller avsändarens e-postdomän i ett meddelande liknar en verklig avsändare eller domän:

- Ett exempel på personifiering av domänens contoso.com är ćóntoso.com.
- En exempelpersonifiering av användarens michelle@contoso.com är michele@contoso.com.

En imiterad domän kan annars anses legitim (registrerad domän, konfigurerade e-postautentiseringsposter) med undantag för avsikten att lura mottagarna.

Följande inställningar för personifiering är endast tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365:

- **Användare att skydda:** Förhindrar att de angivna interna eller externa e-postadresserna **imiteras som meddelandeavsändare.** Du får till exempel ett e-postmeddelande från företagets vice vd där du ber dig att skicka information till hennes interna företag. Skulle du göra det? Många skulle skicka svaret utan att tänka efter.

  Du kan använda skyddade användare för att lägga till interna och externa avsändares e-postadresser för att skydda mot personifiering. Den här listan med avsändare som skyddas från användarpersonifiering  skiljer sig från listan över mottagare som principen gäller för  (alla mottagare [](#policy-settings) för standardprincipen, specifika mottagare som **konfigurerats** i inställningen Tillämpas på i avsnittet Principinställningar).

  > [!NOTE]
  >
  > - I varje princip mot nätfiske kan du ange högst 60 skyddade användare (avsändar-e-postadresser). Du kan inte ange samma skyddade användare i flera principer. Oavsett hur många principer som gäller för en mottagare är det maximala antalet skyddade användare (avsändar-e-postadresser) för varje enskild mottagare 60. Mer information om principprioritet och hur principbearbetningen stannar efter att den första principen har tillämpats finns i Ordningen och [prioriteten för e-postskydd.](how-policies-and-protections-are-combined.md)
  >
  > - Skydd för användarpersonifiering fungerar inte om avsändaren och mottagaren tidigare har kommunicerat via e-post. Om avsändaren och mottagaren aldrig har kommunicerat via e-post identifieras meddelandet som ett personifieringsförsök.

  Som standard är inga avsändar-e-postadresser konfigurerade för personifieringsskydd i **Användare för att skydda.** Som standard omfattas inga avsändar-e-postadresser av personifieringsskydd, antingen i standardprincipen eller i anpassade principer.

  När du lägger till interna  eller externa e-postadresser  i listan Användare för att skydda, kontrolleras meddelanden från dessa avsändare av personifieringsskydd. Meddelandet kontrolleras för personifiering om **meddelandet** skickas  till en mottagare som principen gäller för (alla mottagare för standardprincipen; **Tillämpas på** mottagare i anpassade principer). Om personifiering identifieras i avsändarens e-postadress tillämpas åtgärder för personifieringsskydd för användare på meddelandet (vad du ska göra med meddelandet, om du vill visa säkerhetstips för imiterade användare osv.).

- **Domäner som ska** skyddas: Förhindrar att de angivna domänerna personifieras **i meddelandets avsändares domän.** Till exempel alla domäner du äger (godkända[domäner) eller](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)specifika domäner (domäner du äger eller partnerdomäner). Den här  listan med avsändardomäner som skyddas från personifiering skiljer sig från listan över mottagare som principen  gäller för (alla mottagare för standardprincipen, specifika mottagare som konfigurerats i inställningen Tillämpas på i avsnittet Principinställningar).  [](#policy-settings)

  > [!NOTE]
  > Det maximala antalet skyddade domäner som du kan definiera i alla principer för skydd mot nätfiske är 50.

  Som standard är inga avsändardomäner konfigurerade för personifieringsskydd i **Domäner som ska skyddas.** Som standard omfattas inga avsändardomäner av personifieringsskydd, antingen i standardprincipen eller i anpassade principer.

  När du lägger till domäner i listan  **Domäner** för att skydda, kontrolleras meddelanden från avsändare på dessa domäner av personifieringsskydd. Meddelandet kontrolleras för personifiering om **meddelandet** skickas  till en mottagare som principen gäller för (alla mottagare för standardprincipen; **Tillämpas på** mottagare i anpassade principer). Om personifiering identifieras i avsändarens domän tillämpas åtgärder för personifieringsskydd för domäner på meddelandet (vad du ska göra med meddelandet, om du vill visa säkerhetstips för imiterade användare osv.).

- **Åtgärder för skyddade användare eller domäner:** Välj den åtgärd som ska vidtas för inkommande meddelanden som innehåller personifieringsförsök mot skyddade användare och skyddade domäner i principen. Du kan ange olika åtgärder för personifiering av skyddade användare och personifiering av skyddade domäner:

  - **Använd ingen åtgärd**

  - **Omdirigera meddelandet till andra e-postadresser:** Skickar meddelandet till de angivna mottagarna i stället för de avsedda mottagarna.

  - **Flytta meddelandet till mappen Skräppost:** Meddelandet levereras till postlådan och flyttas till mappen Skräppost. I Exchange Online flyttas meddelandet till mappen Skräppost om skräppostregeln är aktiverad för postlådan (den är aktiverad som standard). Mer information finns i Konfigurera [skräppostinställningar för Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

    - **Sätt meddelandet i karantän:** Skickar meddelandet till karantän i stället för de avsedda mottagarna. Mer information om karantän finns i följande artiklar:

    - [Karantän i Microsoft 365](quarantine-email-messages.md)
    - [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Hitta och släppa meddelanden i karantän som användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Leverera meddelandet och lägg till andra** adresser på raden Hemlig kopia: Leverera meddelandet till de avsedda mottagarna och skicka meddelandet i tyst meddelande till de angivna mottagarna.

  - **Ta bort meddelandet innan det levereras:** Ta bort hela meddelandet utan att ta bort det, inklusive alla bifogade filer.

- **Säkerhetstips:** Aktiverar eller inaktiverar följande säkerhetstips för personifiering som visar meddelanden som inte kan personifiera kontroller:

  - **Imiterade användare:** Från-adressen innehåller en skyddad användare.
  - **Imiterade domäner:** Från-adressen innehåller en skyddad domän.
  - **Ovanliga tecken:** Från-adressen innehåller ovanliga teckenuppsättningar (till exempel matematiska symboler och text eller en blandning av versaler och gemener) i en skyddad avsändare eller domän.


  > [!IMPORTANT]
  >
  > Rekommendation för att aktivera ett säkerhetstips som visas under första gången kontakten mellan avsändaren och mottagaren/mottagarna: Även när säkerhetstips för personifiering är avstängda **rekommenderar** vi att du använder en **e-postflödesregel**(kallas även transportregel) för att lägga till meddelanderubriken **X-MS-Exchange-EnableFirstContactSafetyTip** med värde aktiverad för meddelanden.  Ett säkerhetstips informerar mottagarna första gången de får ett meddelande från avsändaren eller om de inte ofta får meddelanden från avsändaren. Den här funktionen ger ett extra säkerhetsskydd mot potentiella personifieringsattacker. 
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="Texten i säkerhetstipset för personifieringsskydd med flera mottagare.":::

- **Postlådeinformation:** Aktiverar eller inaktiverar artificiell intelligens (AI) som bestämmer användarnas e-postmönster med vanliga kontakter. Den här inställningen hjälper AI att skilja mellan legitima och falska e-postmeddelanden från dessa kontakter. Postlådeinformation är bara tillgängligt för Exchange Online-postlådor.

- **Postlådebaserat personifieringsskydd:** Aktiverar eller inaktiverar utökade personifieringsresultat baserat på varje användares enskilda avsändarkarta. Med den här informationen kan Microsoft 365 anpassa identifiering av användarpersonifiering och hantera falska positiva identifieringar bättre. När användarpersonifiering identifieras kan du definiera en specifik åtgärd som ska vidtas på meddelandet:

  - **Använd ingen åtgärd**
  - **Omdirigera meddelandet till andra e-postadresser**
  - **Flytta meddelandet till mappen Skräppost**
  - **Sätt meddelandet i karantän**
  - **Leverera meddelandet och lägga till andra adresser i raden Hemlig kopia**
  - **Ta bort meddelandet innan det levereras**

- **Betrodda avsändare och domäner:** Undantag för inställningarna för personifieringsskydd. Meddelanden från angivna avsändare och avsändardomäner klassificeras aldrig som personifieringsbaserade attacker av principen. Med andra ord tillämpas inte åtgärden för skyddade avsändare, skyddade domäner eller postlådeinformationsskydd på dessa betrodda avsändare eller avsändardomäner. Maxgränsen för dessa listor är ungefär 1 000 poster.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Avancerade tröskelvärden för nätfiske i principer för nätfiske i Microsoft Defender för Office 365

Följande avancerade tröskelvärden för nätfiske är endast tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365. Dessa tröskelvärden styr känsligheten för användning av modeller för maskininlärning på meddelanden för att fastställa nätfiskeförsök:

- **1 – Standard:** Det här är standardvärdet. Hur allvarlig åtgärden är för meddelandet beror på hur allvarligt meddelandet är är nätfiske (låg, medel, hög eller mycket hög konfidens). Exempelvis har meddelanden som identifieras som nätfiske med mycket hög förtroendegrad de mest allvarliga åtgärderna, medan meddelanden som identifieras som nätfiske med låg konfidensgrad har mindre allvarliga åtgärder tillämpade.

- **2 – Aggressivt:** Meddelanden som identifieras som nätfiske behandlas som om de identifierades med mycket stort förtroende.

- **3 –** Mer aggressiva: Meddelanden som identifieras som nätfiske behandlas med medelhög eller hög förtroendegrad som om de identifierades med mycket stort förtroende.

- **4 –** Mest aggressiva: Meddelanden som identifieras som nätfiske med ett lågt, medelstort eller högt förtroende behandlas som om de identifierades med mycket hög förtroendegrad.

Risken för falska positiva meddelanden (bra meddelanden som markeras som dåliga) ökar när du ökar den här inställningen. Mer information om de rekommenderade inställningarna finns i [principen mot nätfiske i inställningarna för Microsoft Defender för Office 365.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)
