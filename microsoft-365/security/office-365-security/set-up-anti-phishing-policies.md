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
ms.openlocfilehash: d20d9c3839cf72d1e99a185186d0716d9a513c5f
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537865"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Principer mot nätfiske i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Principer för att konfigurera inställningar för skydd mot nätfiske är tillgängliga i Microsoft 365-organisationer med Exchange Online-postlådor, fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor och Microsoft Defender för Office 365 organisationer.

Principer för skydd mot nätfiske i Microsoft Defender Office 365 bara tillgängliga i organisationer som har Defender för Office 365. Till exempel:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5 osv.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender Office 365 tillägg som ett tillägg](https://products.office.com/exchange/advance-threat-protection)

De stora skillnaderna mellan principer för skydd mot nätfiske i EOP och principer för skydd mot nätfiske i Microsoft Defender Office 365 nätfiske beskrivs i följande tabell:

****

|Funktion|Principer mot nätfiske i EOP|Principer mot nätfiske i Microsoft Defender för Office 365|
|---|:---:|:---:|
|Standardprincip skapad automatiskt|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|Skapa anpassade principer|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|Principinställningar<sup>\*</sup>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|Inställningar för personifiering||![Bockmarkering](../../media/checkmark.png)|
|Inställningar för förfalskning|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|Avancerade tröskelvärden för nätfiske||![Bockmarkering](../../media/checkmark.png)|
|

<sup>\*</sup> I standardprincipen är principnamnet och beskrivningen skrivskyddade (beskrivningen är tom) och du kan inte ange vem principen gäller för (standardprincipen gäller för alla mottagare).

Information om hur du konfigurerar principer mot nätfiske finns i följande artiklar:

- [Konfigurera principer för skydd mot nätfiske i EOP](configure-anti-phishing-policies-eop.md)

- [Konfigurera principer mot nätfiske i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md)

I resten av den här artikeln beskrivs de inställningar som är tillgängliga i principer mot nätfiske i EOP och Defender för Office 365.

## <a name="policy-settings"></a>Principinställningar

Följande principinställningar är tillgängliga i principer för skydd mot nätfiske i EOP och Microsoft Defender för Office 365:

- **Namn:** Du kan inte byta namn på standardprincipen för skydd mot nätfiske. När du har skapat en anpassad princip mot nätfiske kan du inte byta namn på principen i Säkerhets- & efterlevnadscenter.

- **Beskrivning** Du kan inte lägga till en beskrivning i standardprincipen för nätfiske, men du kan lägga till och ändra beskrivningen för anpassade principer som du skapar.

- **Används för:** Identifierar interna mottagare som principen mot nätfiske gäller för. Det här värdet krävs i anpassade principer och är inte tillgängligt i standardprincipen (standardprincipen gäller för alla mottagare).

  Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

  - **Mottagaren är:** En eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.
  - **Mottagaren är medlem i**: En eller flera grupper i organisationen.
  - **Mottagarens domän är:** En eller flera av de konfigurerade godkända domänerna i Microsoft 365.

  - **Förutom när**: Undantag för regeln. Inställningarna och beteendet är exakt som villkoren:

    - **Mottagaren är**
    - **Mottagaren är medlem i**
    - **Mottagarens domän är**

  > [!NOTE]
  > Inställningen **Används för** krävs i anpassade principer för nätfiske för att identifiera vilka mottagare av **meddelandet** <u>som principen gäller för.</u> Principer för skydd mot nätfiske i Microsoft [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Defender för Office 365 har också personifieringsinställningar där du kan ange enskilda e-postadresser eller avsändardomäner som ska få <u>personifieringsskydd</u> enligt beskrivningen längre fram i den här artikeln.

## <a name="spoof-settings"></a>Inställningar för förfalskning

Förfalskning är när avsändarens adress i ett e-postmeddelande (den avsändaradress som visas i e-postklienterna) inte matchar e-postkällans domän. Mer information om förfalskning finns i [Skydd mot förfalskning i Microsoft 365.](anti-spoofing-protection.md)

Följande inställningar för förfalskning finns i principer för skydd mot nätfiske i EOP och Microsoft Defender för Office 365:

- **Aktivera förfalskningsinformation?**: Aktiverar eller inaktiverar förfalskningsinformation. Vi rekommenderar att du lämnar det aktiverat.

  När förfalskningsinformation har aktiverats visar förfalskningsinformation förfalskningsavsändare som automatiskt identifierats och tillåts eller blockerats av förfalskningsinformation.  Du kan manuellt åsidosätta förfalskningsinformationstestet för att tillåta eller blockera identifierade förfalskningsavsändare inifrån insikten. Men när du gör det försvinner den falska avsändaren från förfalskningsinformation, och visas nu bara på fliken **Förfalskning** i listan Tillåt/blockera klientorganisation. Du kan också manuellt skapa tillåta eller blockera poster för förfalskningsavsändare i klientorganisationens lista över tillåtna/blockerade avsändare. Mer information finns i följande avsnitt:

  - [Falska intelligensinsikter i EOP](learn-about-spoof-intelligence.md)
  - [Hantera klientorganisationens lista över tillåtna/blockerade klienter i EOP](tenant-allow-block-list.md)

  > [!NOTE]
  >
  > - Skydd mot förfalskning är aktiverat som standard i standardprincipen för skydd mot nätfiske och i alla nya anpassade principer mot nätfiske som du skapar.
  >
  > - Du behöver inte inaktivera skydd mot förfalskning om MX-posten inte pekar på Microsoft 365. aktiverar du Utökad filtrering för kopplingar i stället. Instruktioner finns i [Utökad filtrering för kopplingar i Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
  >
  > - Om du inaktiverar skydd mot förfalskning inaktiveras bara implicit förfalskningsskydd från [sammansatta autentiseringskontroller.](email-validation-and-authentication.md#composite-authentication) Om avsändaren misslyckas med ett [explicit DMARC-kontroller](use-dmarc-to-validate-email.md) där principen är inställd på att sätta i karantän eller avvisas meddelandet fortfarande i karantän eller avvisas.

- **Inställningar för oautherade avsändare**: Se informationen i nästa avsnitt.

- **Åtgärder:** För meddelanden från spärrade förfalskningsavsändare (blockeras automatiskt av förfalskningsinformation eller manuellt blockeras i listan Tillåt/blockera klientorganisation) kan du också ange vilken åtgärd som ska vidtas på meddelanden:

  - **Flytta meddelanden till mottagarnas skräppostmappar:** Det här är standardvärdet. Meddelandet levereras till postlådan och flyttas till mappen Skräppost. I Exchange Online flyttas meddelandet till mappen Skräppost om skräppostregeln är aktiverad för postlådan (den är aktiverad som standard). Mer information finns i [Konfigurera inställningar för skräppost Exchange Online postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Sätt meddelandet i karantän:** Skickar meddelandet till karantän i stället för de avsedda mottagarna. Mer information om karantän finns i följande artiklar:

    - [Karantän i Microsoft 365](quarantine-email-messages.md)
    - [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Hitta och släppa meddelanden i karantän som en användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

### <a name="unauthenticated-sender"></a>Oauthenticerad avsändare

Inställningar för oautherade avsändare är [](#spoof-settings) en del av inställningarna för förfalskning som är tillgängliga i principer för skydd mot nätfiske i EOP och Microsoft Defender för Office 365 enligt beskrivningen i föregående avsnitt.

- Aktivera oautentiserade avsändares frågetecken **(?)-symbol?**: När den här inställningen är aktiverad läggs ett frågetecken till på avsändarens foto  i rutan Från om meddelandet inte klarar SPF- eller DKIM-kontroller och meddelandet inte klarar DMARC eller sammansatt [autentisering.](email-validation-and-authentication.md#composite-authentication) När den här inställningen är inaktiverad läggs frågetecknet inte till på avsändarens foto.

- Aktivera **via-taggen?**: När den här inställningen är aktiverad läggs via-taggen (chris@contoso.com via fabrikam.com) till i rutan Från om domänen i från-adressen (meddelandets avsändare som visas i e-postklienter) skiljer sig från domänen i DKIM-signaturen eller <sup>\*</sup> MAIL <u></u> **FROM-adressen.** Mer information om de här adresserna finns i [En översikt över e-poststandarder.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

> [!NOTE]
> För närvarande är **inställningen Aktivera via-taggen inte** tillgänglig i alla organisationer. Om du inte har inställningen Enable **"via"?** styrs  både frågetecknet och via-taggen av inställningen Enable **unauthenticated sender frågetecken (?)** i organisationen.

Om du vill förhindra att frågetecknet eller via taggen läggs till i meddelanden från specifika avsändare har du följande alternativ:

- Tillåt förfalskningsavsändare i [förfalskningsinformation eller manuellt](learn-about-spoof-intelligence.md) i klientorganisationens lista över tillåtna/blockerade [avsändare.](tenant-allow-block-list.md) Om du tillåter den falska avsändaren förhindras via-taggen att visas i meddelanden från avsändaren när oauthenticerad avsändaridentifiering inaktiveras.

- [Konfigurera e-postautentisering](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) för avsändardomänen.
  - För frågetecken på avsändarens foto är SPF eller DKIM det viktigaste.
  - För via-taggen bekräftar du domänen i signaturen DKIM eller **mail FROM** address matches (eller är en underdomän till) domänen i Från-adressen.

Mer information finns i [Identifiera misstänkta meddelanden på Outlook.com och Outlook på webben](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Exklusiva inställningar i principer för skydd mot nätfiske i Microsoft Defender för Office 365

I det här avsnittet beskrivs de principinställningar som bara är tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365.

> [!NOTE]
> Standardprincipen för skydd mot nätfiske i Microsoft Defender för Office 365 tillhandahåller [förfalskningsskydd och](set-up-anti-phishing-policies.md#spoof-settings) postlådeinformation för alla mottagare. De andra funktionerna för [personifieringsskydd och](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) avancerade [inställningar är](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) dock inte konfigurerade eller aktiverade i standardprincipen. Om du vill aktivera alla skyddsfunktioner ändrar du standardprincipen för skydd mot nätfiske eller skapar ytterligare principer mot nätfiske.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Inställningar för personifiering i principer för skydd mot nätfiske i Microsoft Defender för Office 365

Personifiering är när avsändarens eller avsändarens e-postdomän i ett meddelande ser ut ungefär som en verklig avsändare eller domän:

- En exempelpersonifiering av domänens contoso.com är ćóntoso.com.
- En person som utger sig för att vara michelle@contoso.com är michele@contoso.com.

En imiterad domän kan i annat fall anses legitim (registrerad domän, konfigurerade e-postautentiseringsposter osv.), förutom avsikten att lura mottagarna.

Följande inställningar för personifiering är endast tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365:

- **Lägg till användare som ska** skydda: Förhindrar att de angivna interna eller externa e-postadresserna **utger sig för att vara avsändare.** Du får till exempel ett e-postmeddelande från företagets vice vd och ber dig skicka information inom företaget. Skulle du göra det? Många skickade svaret utan att tänka efter.

  Du kan använda skyddade användare för att lägga till interna och externa avsändares e-postadresser för att skydda mot personifiering. Den här listan med avsändare som skyddas från användarpersonifiering  skiljer sig från den lista över mottagare som principen gäller  för (alla mottagare för standardprincipen, specifika mottagare som **konfigurerats** i inställningen Tillämpas på i avsnittet [Principinställningar).](#policy-settings)

  > [!NOTE]
  >
  > - I varje princip mot nätfiske kan du ange högst 60 skyddade användare (avsändar-e-postadresser). Du kan inte ange samma skyddade användare i flera principer. Oavsett hur många principer som gäller för en mottagare är det maximala antalet skyddade användare (avsändar-e-postadresser) för varje enskild mottagare 60. Mer information om principprioritet och hur principbearbetningen avbryts efter att den första principen har tillämpats finns i Ordning och [prioritet för e-postskydd.](how-policies-and-protections-are-combined.md)
  >
  > - Skydd för användarpersonifiering fungerar inte om avsändaren och mottagaren tidigare har kommunicerat via e-post. Om avsändaren och mottagaren aldrig har kommunicerat via e-post identifieras meddelandet som ett personifieringsförsök.

  Som standard är inga avsändar-e-postadresser konfigurerade för personifieringsskydd i **Användare som ska skydda**. Som standard omfattas därför inga avsändar-e-postadresser av personifieringsskydd, antingen i standardprincipen eller i anpassade principer.

  När du lägger till interna  eller externa e-postadresser i listan Användare som ska **skyddas** kontrolleras meddelanden från dessa avsändare av personifieringsskydd. Meddelandet kontrolleras för personifiering om **meddelandet** skickas  till en mottagare som principen gäller för (alla mottagare för standardprincipen; **Tillämpas på** mottagare i anpassade principer). Om personifiering identifieras i avsändarens e-postadress tillämpas åtgärder för personifieringsskydd för användare på meddelandet (vad du ska göra med meddelandet, om du vill visa säkerhetstips för imiterade användare osv.).

- **Lägg till domäner att** skydda: Förhindrar att de angivna domänerna utger **sig för att vara i meddelandets domän.** Till exempel alla domäner du äger (godkända[domäner) eller specifika](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)domäner (domäner du äger eller partnerdomäner). Den här listan med avsändardomäner som skyddas  från personifiering skiljer sig från listan över mottagare som principen  gäller för (alla mottagare för standardprincipen, specifika mottagare som konfigurerats i inställningen Används för i avsnittet [Principinställningar).](#policy-settings) 

  > [!NOTE]
  > Det maximala antalet skyddade domäner som du kan definiera i alla principer mot nätfiske är 50.

  Som standard är inga avsändardomäner konfigurerade för personifieringsskydd i **Domäner att skydda**. Som standard omfattas inga avsändardomäner av personifieringsskydd, antingen i standardprincipen eller i anpassade principer.

  När du lägger till domäner **i** listan  Domäner för att skydda, kontrolleras meddelanden från avsändare i dessa domäner av personifieringsskydd. Meddelandet kontrolleras för personifiering om **meddelandet** skickas  till en mottagare som principen gäller för (alla mottagare för standardprincipen; **Tillämpas på** mottagare i anpassade principer). Om personifiering identifieras i avsändarens domän tillämpas åtgärder för personifieringsskydd för domäner på meddelandet (vad du ska göra med meddelandet, om du vill visa säkerhetstips för imiterade användare osv.).

- **Åtgärder:** Välj vilken åtgärd som ska vidtas på inkommande meddelanden som innehåller personifieringsförsök mot skyddade användare och skyddade domäner i principen. Du kan ange olika åtgärder för personifiering av skyddade användare och personifiering av skyddade domäner:

  - **Använd inte någon åtgärd**

  - **Omdirigera meddelandet till andra e-postadresser**: Skickar meddelandet till de angivna mottagarna i stället för de avsedda mottagarna.

  - **Flytta meddelanden till mottagarnas skräppostmappar:** Meddelandet levereras till postlådan och flyttas till mappen Skräppost. I Exchange Online flyttas meddelandet till mappen Skräppost om skräppostregeln är aktiverad för postlådan (den är aktiverad som standard). Mer information finns i [Konfigurera inställningar för skräppost Exchange Online postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Sätt meddelandet i karantän:** Skickar meddelandet till karantän i stället för de avsedda mottagarna. Mer information om karantän finns i följande artiklar:
    - [Karantän i Microsoft 365](quarantine-email-messages.md)
    - [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Hitta och släppa meddelanden i karantän som en användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Leverera meddelandet och lägg till andra adresser** på raden Hemlig kopia: Skicka meddelandet till de avsedda mottagarna och skicka meddelandet utan meddelande till de angivna mottagarna.

  - **Ta bort meddelandet innan det levereras:** Tyst tar bort hela meddelandet, inklusive alla bifogade filer.

- **Aktivera säkerhetstips för personifiering**: Aktivera eller inaktivera följande säkerhetstips för personifiering som visar meddelanden som inte kan personifiera kontroller:
  - **Visa tips för imiterade användare:** Från-adressen innehåller en skyddad användare.
  - **Visa tips för imiterade domäner**: Från-adressen innehåller en skyddad domän.
  - **Visa tips för ovanliga tecken:** Från-adressen innehåller ovanliga teckenuppsättningar (till exempel matematiska symboler och text eller en blandning av versaler och gemener) i en skyddad avsändare eller domän.

  > [!IMPORTANT]
  >
  > Även när säkerhetstips för personifiering  är avstängda rekommenderar vi att du använder en e-postflödesregel (kallas även transportregel) för att lägga till ett meddelandehuvud med namnet **X-MS-Exchange-EnableFirstContactSafetyTip** med värde **enable** i meddelanden. En säkerhetstips meddelande informerar mottagarna första gången de får ett meddelande från avsändaren eller om de inte ofta får meddelanden från avsändaren. Den här funktionen ger ett extra säkerhetsskydd mot potentiella personifieringsattacker.
  >
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="Texten i meddelandet säkerhetstips personifieringsskydd med flera mottagare.":::

- Postlådeintelligens: Aktiverar eller inaktiverar artificiell intelligens (AI) som bestämmer användar-e-postmönster med vanliga kontakter. Den här inställningen hjälper AI att skilja mellan meddelanden från legitima och imiterade avsändare.

  Till exempel är Gabriela Laureano (glaureano@contoso.com) företagets VD, så du lägger till henne  som skyddad avsändare i inställningar för användare som ska skydda principen. Men vissa mottagare, som principen gäller, kan regelbundet kommunicera med en leverantör som även heter Gabriela Laureano (glaureano@fabrikam.com). Eftersom de mottagarna har en kommunikationshistorik med glaureano@fabrikam.com identifierar inte postlådeinformation meddelanden från glaureano@fabrikam.com som ett personifieringsförsök för glaureano@contoso.com för de mottagarna.

  Om du vill använda vanliga kontakter som har lärts av postlådeintelligens (och brist på därav) för att  skydda användare från personifieringsattacker kan du aktivera postlådeintelligensbaserat **personifieringsskydd** och ange vilken åtgärd som ska vidtas om du även aktiverar postlådeintelligens. 

- **Postlådeintelligensbaserat** personifieringsskydd: Aktivera den här inställningen om du vill ange vilken åtgärd som ska vidtas på meddelanden för personifieringsidentifiering från postlådeintelligensresultat:

  - **Använd inte någon åtgärd**: Observera att det här  värdet har samma resultat som att aktivera postlådeintelligens men inaktivera postlådeintelligensbaserat **personifieringsskydd.**
  - **Omdirigera meddelandet till andra e-postadresser**
  - **Flytta meddelandet till mottagarnas skräppostmappar**
  - **Sätt meddelandet i karantän**
  - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
  - **Ta bort meddelandet innan det levereras**

- **Lägg till betrodda avsändare och** domäner : Undantag till inställningarna för personifieringsskydd. Meddelanden från angivna avsändare och avsändardomäner klassificeras aldrig som personifieringsbaserade attacker av principen. Med andra ord tillämpas inte åtgärden för skyddade avsändare, skyddade domäner eller postlådeintelligensskydd på dessa betrodda avsändare eller avsändardomäner. Maxgränsen för dessa listor är cirka 1 000 poster.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Avancerade tröskelvärden för nätfiske i principer mot nätfiske i Microsoft Defender för Office 365

Följande avancerade tröskelvärden för nätfiske är endast tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365. Dessa tröskelvärden styr känsligheten för användning av maskininlärningsmodeller i meddelanden för att fastställa en nätfiskebedrägeri:

- **1 – Standard:** Det här är standardvärdet. Hur allvarlig åtgärden som vidtas på meddelandet beror på hur väl meddelandet är nätfiske (låg, medium, hög eller mycket hög konfidens). Exempelvis har meddelanden som identifieras som nätfiske med mycket hög grad av förtroende de viktigaste åtgärderna tillämpade, medan meddelanden som identifieras som nätfiske med låg konfidensgrad har mindre allvarliga åtgärder tillämpade.

- **2 – Aggressivt:** Meddelanden som identifieras som nätfiske med hög grad av förtroende behandlas som om de identifierades med mycket hög förtroendegrad.

- **3 – Mer** aggressiva: Meddelanden som identifieras som nätfiske med medelhög eller hög grad av förtroende behandlas som om de identifierades med mycket hög förtroendegrad.

- **4 –** Mest aggressiva : Meddelanden som identifieras som nätfiske med låg, medel eller hög grad av förtroende behandlas som om de identifierades med mycket hög konfidensgrad.

Risken för falska positiva resultat (bra meddelanden som markerats som dåliga) ökar när du ökar den här inställningen. Mer information om de rekommenderade inställningarna finns i [principen för skydd mot nätfiske i Microsoft Defender Office 365 inställningar.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)
