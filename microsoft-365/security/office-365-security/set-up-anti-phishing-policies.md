---
title: Principer för skydd mot nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
description: Lär dig mer om den grundläggande anti-phishing-principen i Exchange Online Protection (EOP) och de avancerade ATP-principerna mot nätfiske i Office 365 Advanced Threat Protection.
ms.openlocfilehash: 32214d24c7ed030b3bc7aad36bf3ac99f68a17fb
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949387"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Principer för bekämpning av nätfiske i Microsoft 365

Principer för att konfigurera inställningar för skydd mot nätfiske är tillgängliga i Microsoft 365-organisationer med Exchange Online-postlådor, fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor och ATP-organisationer (Office 365 Advanced Threat Protection).

ATP:s principer för nätfiske är endast tillgängliga i organisationer som har Office 365 ATP. Till exempel:

- Microsoft 365 Enterprise E5, Microsoft 365 Utbildning A5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Office 365 ATP som tillägg](https://products.office.com/exchange/advance-threat-protection)

Alla andra organisationer har policyer mot nätfiske.

Skillnaderna på hög nivå mellan anti-phishing-policyer och ATP-principer mot nätfiske beskrivs i följande tabell:

||||
|---|:---:|:---:|
|**Funktion**|**Principer för skydd mot nätfiske**|**ATP:s policyer för phishing-phishing**|
|Skapas automatiskt standardprincip|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Skapa anpassade principer|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Principinställningar<sup>\*</sup>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Inställningar för personifiering||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Spoof-inställningar|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Avancerade tröskelvärden för nätfiske||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup>I standardprincipen är principnamnet och beskrivningen skrivskyddade (beskrivningen är tom) och du kan inte ange vem principen ska gälla för (standardprincipen gäller för alla mottagare).

Information om hur du konfigurerar principer mot nätfiske finns i följande avsnitt:

- [Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md)

- [Konfigurera ATP-principer för phishing i Microsoft 365](configure-atp-anti-phishing-policies.md)

I resten av det här avsnittet beskrivs de inställningar som är tillgängliga i anti-phishing-principer och ATP-principer för nätfiske.

## <a name="spoof-settings"></a>Spoof-inställningar

Förfalskning är när Från-adressen i ett e-postmeddelande (avsändarens adress som visas i e-postklienter) inte matchar e-postkällans domän. Mer information om förfalskning finns i Skydd mot förfalskning [i Microsoft 365](anti-spoofing-protection.md).

Följande falska inställningar är tillgängliga i anti-phishing-policyer och ATP-principer mot nätfiske:

- **Skydd mot spoofing**: Aktiverar eller inaktiverar skydd mot förfalskning. Vi rekommenderar att du lämnar det aktiverat. Du använder **falska underrättelsepolicy för** att tillåta eller blockera specifika förfalskade interna och externa avsändare. Mer information finns i [Konfigurera förfalskningsinformation i Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  > Spoof-inställningar är aktiverade som standard i standardpolicyn mot nätfiske i EOP, standardprincipen för ATP-phishing och i nya anpassade anti-phishing-principer eller ATP-principer mot nätfiske som du skapar. <br/><br/> Du behöver inte inaktivera förfalskningsskydd om MX-posten inte pekar på Microsoft 365. du aktiverar utökad filtrering för kopplingar i stället. Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

  För meddelanden från blockerade förfalskade avsändare kan du också ange vilken åtgärd som ska vidtas för meddelandena:

  - **Flytta meddelande till mappen Skräppost:** Det här är standardvärdet. Meddelandet levereras till postlådan och flyttas till mappen Skräppost. I Exchange Online flyttas meddelandet till mappen Skräppost om skräppostregeln är aktiverad i postlådan (det är aktiverat som standard). Mer information finns i [Konfigurera inställningar för skräppost på Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Karantän meddelandet**: Skickar meddelandet till karantän i stället för de avsedda mottagarna. Mer information om karantän finns i artiklarna om följande ämnen:

    - [Karantän i Microsoft 365](quarantine-email-messages.md)
    - [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Söka efter och släppa meddelanden i karantän som användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Oautentiserade avsändaren**: Aktiverar eller inaktiverar oidentifierad avsändande-identifiering i Outlook. Specifikt:

  - Ett frågetecken (?) läggs till i avsändarens foto om meddelandet inte skickar SPF- eller DKIM-kontroller **och** meddelandet inte skickar DMARC eller [sammansatt autentisering](email-validation-and-authentication.md#composite-authentication).

  - Via-taggen (chris@contoso.com <u>via</u> michelle@fabrikam.com) läggs till om domänen i från-adressen (meddelandeavsändaren som visas i e-postklienter) skiljer sig från domänen i DKIM-signaturen eller **MAIL FROM-adressen.** Mer information om dessa adresser finns i [En översikt över e-postmeddelandenstandarder](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  Om du vill förhindra att dessa identifierare läggs till i meddelanden från specifika avsändare har du följande alternativ:

  - Låt avsändaren förfalska i falska underrättelsepolicyn. Instruktioner finns [i Konfigurera falska underrättelser i Microsoft 365](learn-about-spoof-intelligence.md).

  - [Konfigurera e-postautentisering](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) för avsändarendomänen.
  
    - För frågetecknet i avsändarens foto är SPF eller DKIM de viktigaste.
    - För via-taggen bekräftar du domänen i DKIM-signaturen eller **e-post från-adressen** matchar (eller är en underdomän till) domänen i Från-adressen.

  Mer information finns [i Identifiera misstänkta meddelanden i Outlook.com och Outlook på webben](https://support.office.com/article/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>Exklusiva inställningar i ATP:s principer för phishing-phishing

I det här avsnittet beskrivs de principinställningar som bara är tillgängliga i ATP:s principer för nätfiske.

> [!NOTE]
> Som standard är de exklusiva ATP-inställningarna inte konfigurerade eller aktiverade, inte ens i standardprincipen. Om du vill dra nytta av dessa funktioner måste du aktivera och konfigurera dem i standardprincipen för ATP-phishing, eller skapa och konfigurera anpassade ATP-principer för phishing.

### <a name="policy-settings-in-atp-anti-phishing-policies"></a>Principinställningar i ATP:s principer för nätfiske

Följande principinställningar är endast tillgängliga i ATP:s principer för nätfiske:

- **Namn**: Du kan inte byta namn på standardpolicyn mot nätfiske, men du kan namnge och byta namn på anpassade principer som du skapar.

- **Beskrivning** Du kan inte lägga till en beskrivning i standardpolicyn mot nätfiske, men du kan lägga till och ändra beskrivningen för anpassade principer som du skapar.

- **Används på**: Identifierar interna mottagare som ATP:s anti-phishing-policy gäller för. Det här värdet krävs i anpassade principer och inte tillgängligt i standardprincipen (standardprincipen gäller för alla mottagare).

    Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<mottagare1\>_ eller _\<mottagare2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<mottagare1\>_ och _\<medlem i grupp 1\>_).

  - **Mottagaren är**: En eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.
  - **Mottagaren är medlem i**: En eller flera grupper i organisationen.
  - **Mottagardomänen är**: En eller flera av de konfigurerade godkända domänerna i Microsoft 365.

  - **Utom när**: Undantag för regeln. Inställningarna och beteendet är exakt som villkoren:

    - **Mottagaren är**
    - **Mottagaren är medlem i**
    - **Mottagardomänen är**

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Inställningar för personifiering i ATP:s principer för phishing-phishing

Personifiering är där avsändaren eller avsändarens e-postdomän i ett meddelande ser mycket lik en riktig avsändare eller domän:

- Ett exempel på personifiering av domänen contoso.com är ćóntoso.com.

- Ett exempel personifiering av användaren michelle@contoso.com är michele@contoso.com.

En personifierad domän kan annars betraktas som legitim (registrerad domän, konfigurerade e-postautentiseringsposter osv.), förutom att dess avsikt är att vilseleda mottagare.

Följande inställningar för personifiering är endast tillgängliga i ATP:s principer för nätfiske:

- **Användare att skydda:** Förhindrar att angivna interna eller externa användare personifieras. Till exempel chefer (interna) och styrelseledamöter (externa). Du kan lägga till upp till 60 interna och externa adresser. Den här listan över skyddade användare skiljer sig från listan över mottagare som principen gäller för i inställningen **Tillämpad** på.

  Du kan till exempel ange Felipe Apodaca (felipea@contoso.com) som en skyddad användare i en princip som gäller för gruppen Chefer. Inkommande meddelanden som skickas till medlemmar i gruppen Chefer där där Felipe Apodaca personifieras kommer att hanteras av principen (den åtgärd som du konfigurerar för personifierade användare).

- **Domäner som ska skyddas**: Förhindra att de angivna domänerna personifieras. Till exempel alla domäner som du äger[(godkända domäner)](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)eller specifika domäner (domäner som du äger eller partnerdomäner). Den här listan över skyddade domäner skiljer sig från listan över domäner som principen gäller för i inställningen **Tillämpad** på.

  Du kan till exempel ange tailspintoys.com som en skyddad domän i en princip som gäller för medlemmar i gruppen Chefer. Inkommande meddelanden som skickas till medlemmar i gruppen Chefer där var tailspintoys.com personifieras kommer att utföras av principen (den åtgärd som du konfigurerar för personifierade domäner).

- **Åtgärder för skyddade användare eller domäner**: Välj vilken åtgärd som ska vidtas för inkommande meddelanden som innehåller personifieringsförsök mot skyddade användare och skyddade domäner i principen. Du kan ange olika åtgärder för personifiering av skyddade användare jämfört med personifiering av skyddade domäner:

  - **Använd inga åtgärder**

  - **Omdirigera meddelande till andra e-postadresser**: Skickar meddelandet till de angivna mottagarna i stället för de avsedda mottagarna.

  - **Flytta meddelande till mappen Skräppost:** Meddelandet levereras till postlådan och flyttas till mappen Skräppost. I Exchange Online flyttas meddelandet till mappen Skräppost om skräppostregeln är aktiverad i postlådan (det är aktiverat som standard). Mer information finns i [Konfigurera inställningar för skräppost på Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - **Karantän meddelandet**: Skickar meddelandet till karantän i stället för de avsedda mottagarna. Mer information om karantän finns i artiklarna om följande ämnen:

    - [Karantän i Microsoft 365](quarantine-email-messages.md)
    - [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Söka efter och släppa meddelanden i karantän som användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Leverera meddelandet och lägg till andra adresser på raden Hemlig kopia:** Leverera meddelandet till de avsedda mottagarna och leverera meddelandet tyst till de angivna mottagarna.

  - **Ta bort meddelandet innan det levereras:** Tar tyst bort hela meddelandet, inklusive alla bifogade filer.

- **Säkerhetstips**: Aktiverar eller inaktiverar följande säkerhetstips för personifiering som visas meddelanden som misslyckas med personifieringskontroller:

  - **Personifierade användare**: Från-adressen innehåller en skyddad användare.
  - **Personifierade domäner**: Från-adressen innehåller en skyddad domän.
  - **Ovanliga tecken**: Från-adressen innehåller ovanliga teckenuppsättningar (till exempel matematiska symboler och text eller en blandning av versaler och gemener) i en skyddad avsändare eller domän.

- **Mailbox intelligence**: Aktiverar eller inaktiverar artificiell intelligens (AI) som bestämmer användarnas e-postmönster med sina frekventa kontakter. Den här inställningen hjälper AI att skilja mellan legitim och förfalskad e-post från dessa kontakter. Postlådeinformation är endast tillgänglig för Exchange Online-postlådor.

- **Informationsskydd för postlådans intelligens:** Aktiverar eller inaktiverar förbättrade personifieringsresultat baserat på varje användares individuella avsändarekarta. Den här intelligensen gör det möjligt för Microsoft 365 att anpassa identifiering av användarens personifiering och bättre hantera falska positiva identifieringar. När användaren personifiering upptäcks, kan du definiera en specifik åtgärd att vidta på meddelandet:

  - **Använd inga åtgärder**
  - **Omdirigera meddelande till andra e-postadresser**
  - **Flytta meddelande till mappen Skräppost**
  - **Karantän meddelandet**
  - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
  - **Ta bort meddelandet innan det levereras**

- **Betrodda avsändare och domäner**: Undantag från inställningarna för personifieringsskydd. Meddelanden från angivna avsändare och avsändande domäner klassificeras aldrig som personifieringsbaserade attacker av principen. Med andra ord tillämpas inte åtgärden för skyddade avsändare, skyddade domäner eller postlådeinformationsskydd på dessa betrodda avsändare eller avsändande domäner. Den maximala gränsen för dessa listor är cirka 1000 poster.

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>Avancerade tröskelvärden för nätfiske i ATP:s principer för phishing

Följande avancerade tröskelvärden för nätfiske är endast tillgängliga i ATP:s principer för nätfiske för att ange hur identifierade nätfiskemeddelanden ska behandlas:

- **1 - Standard:** Detta är standardvärdet. Hur allvarlig åtgärden som vidtas på meddelandet är beror på graden av förtroende för att meddelandet är nätfiske (lågt, medel, högt eller mycket högt förtroende). Till exempel har meddelanden som identifieras som nätfiske med mycket hög grad av förtroende de allvarligaste åtgärderna, medan meddelanden som identifieras som nätfiske med låg grad av förtroende har mindre allvarliga åtgärder.

- **2 - Aggressiv**: Meddelanden som identifieras som nätfiske med en hög grad av förtroende behandlas som om de identifierades med en mycket hög grad av förtroende.

- **3 - Mer aggressiva:** Meddelanden som identifieras som nätfiske med en medelhög eller hög grad av förtroende behandlas som om de identifierades med en mycket hög grad av förtroende.

- **4 - Mest aggressiva:** Meddelanden som identifieras som nätfiske med låg, medel eller hög grad av förtroende behandlas som om de identifierades med en mycket hög grad av förtroende.

Risken för falska positiva identifieringar (bra meddelanden markerade som dåliga) ökar när du ökar den här inställningen. Information om de rekommenderade inställningarna finns i [Office ATP:s inställningar för phishing-phishing.](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)