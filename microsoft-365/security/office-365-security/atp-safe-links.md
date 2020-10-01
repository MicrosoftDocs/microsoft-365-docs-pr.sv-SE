---
title: Säkra länkar
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: I den här artikeln kan administratörer lära sig skydda länkar i Office 365 Avancerat skydd (ATP) för att skydda sin organisation från nätfiske och andra attacker som använder skadlig URL.
ms.openlocfilehash: 742ccc82fe5c6fafa4e6c3463cb471b674b77fa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326722"
---
# <a name="safe-links-in-office-365-atp"></a>Säkra länkar i Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Den här artikeln är avsedd för företags kunder som har Office 365-tjänsten för [Avancerat skydd (ATP)](office-365-atp.md). Om du använder Outlook.com, Microsoft 365 eller Microsoft 365 personal och du letar efter information om Safelinks i Outlook kan du läsa mer i [avancerad Outlook.com-säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Säkra länkar är en funktion i [Office 365 Avancerat skydd](office-365-atp.md) som tillhandahåller URL-genomsökning och omskrivning av inkommande e-postmeddelanden i e-postflöde och när du klickar på verifiering av URL: er och länkar i e-postmeddelanden och andra platser. Sökning efter säkra länkar sker utöver det vanliga [skyddet mot skräp post och skydd mot skadlig program vara](anti-spam-and-anti-malware-protection.md) i inkommande e-postmeddelanden i Exchange Online Protection (EOP). Sökning efter säkra länkar skyddar din organisation från illasinnade länkar som används i nätfiske och andra attacker.

Säkra länkar skyddar du på följande platser:

- **E-postmeddelanden**: skyddade länkar skydd för länkar i e-postmeddelanden styrs av principer för säkra länkar. Det finns ingen standard princip för säkra länkar, **så för att skydda säkra länkar i e-postmeddelanden måste du skapa en eller flera principer för säkra länkar**. Anvisningar finns i [Konfigurera principer för säkra länkar i ATP](set-up-atp-safe-links-policies.md).

  Mer information om säkra Länkar för e-postmeddelanden finns i avsnittet [Inställningar för säkra länkar i e-postmeddelanden](#safe-links-settings-for-email-messages) längre ned i den här artikeln.

- **Microsoft Teams** (för närvarande i tryck för hands version): säkra länkar skydd för länkar i Teams konversationer, gruppchattar eller från kanaler styrs också av principer för säkra länkar. Det finns ingen standard princip för Safe Links, **så för att skydda säkra länkar i Teams måste du skapa en eller flera principer för säkra länkar**.

  Mer information om skydd för säkra länkar i Teams finns i avsnittet [Inställningar för säkra Länkar för Microsoft Teams](#safe-links-settings-for-microsoft-teams) senare i det här avsnittet.

- **Office 365-appar**: säkra länkar skydd för Office 365-appar är tillgängliga i Skriv bords-, mobil-och webb åtkomst punkter som stöds. Du **konfigurerar** skydd för säkra Länkar för Office 365-appar i den globala inställningen **utanför** Safe Links-principer. Anvisningar finns i [Konfigurera globala inställningar för inställningar för säkra länkar i Office 365 ATP](configure-global-settings-for-safe-links.md).

  Men säkra länkar skyddar för Office 365- **appar endast för** användare som är inkluderade i principer för aktiva säkra länkar. Om en användare inte ingår i en princip för aktiva säkra länkar får användaren inte säkra länkar i Office 365-appar som stöds.

  Mer information om skydd för säkra länkar i Office 365-appar finns i avsnittet [Inställningar för säkra Länkar för office 365-appar](#safe-links-settings-for-office-365-apps) längre ned i den här artikeln.

Den här artikeln innehåller detaljerad information om följande typer av inställningar för säkra länkar:

- **Inställningar i principer för säkra länkar**: de här inställningarna gäller endast för användare som ingår i vissa principer och inställningarna kan skilja sig mellan principer. Dessa inställningar omfattar:

  - [Inställningar för säkra Länkar för e-postmeddelanden](#safe-links-settings-for-email-messages)
  - [Inställningar för säkra Länkar för Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - ["Skriv inte över följande URL-adresser" i principer för säkra länkar](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Inställningar för global Safe Links**: de här inställningarna är globalt konfigurerade, inte i principer för säkra länkar. Inställningarna gäller dock endast för användare som ingår i principer för aktiva säkra länkar. Dessa inställningar omfattar:

  - [Inställningar för säkra Länkar för Office 365-appar](#safe-links-settings-for-office-365-apps)
  - ["Blockera följande URL-adresser" för säkra länkar](#block-the-following-urls-list-for-safe-links)

I följande tabell beskrivs scenarier för säkra länkar i Microsoft 365 och Office 365 organisationer som innehåller ATP (med andra ord är brist på licensiering inte ett problem i exemplen).

****

|Ovanligt|Resultat|
|---|---|
|Jean är medlem i marknadsförings avdelningen. Säkra länkar skydd för Office 365-appar är aktiverat i de globala inställningarna för säkra länkar och en policy för säkra länkar som gäller för medlemmar i marknadsförings avdelningen finns. Jean öppnar en PowerPoint-presentation i ett e-postmeddelande och klickar sedan på en URL i presentationen.|Jean skyddas av säkra länkar. <br/><br/> Jean ingår i en policy för säkra länkar och skydd för säkra Länkar för Office 365-appar är aktiverat. <br/><br/> Mer information om kraven för skydd mot säkra länkar i Office 365-appar finns i avsnittet [Inställningar för säkra Länkar för Office 365-appar](#safe-links-settings-for-office-365-apps) längre ned i den här artikeln.|
|Chris Microsoft 365 E5-organisation har inga konfigurerade principer för säkra länkar. Chris får ett e-postmeddelande från en extern avsändare som innehåller en URL till en illvillig webbplats som han sedan klickar på.|Chris skyddas inte av säkra länkar. <br/><br/> En administratör måste skapa minst en princip för säkra Länkar för att alla ska få säkra länkar i inkommande e-postmeddelanden. Christer måste inkludera villkoren i policyn för att skydda skydd mot säkra länkar.|
|I Pat organisation har inga administratörer några principer för Safe Links, men säkra länkar skyddar Office 365-apparna. Pat öppnar ett Word-dokument och klickar på en URL i filen.|Pat skyddas inte av säkra länkar. <br/><br/> Även om skydd för säkra Länkar för Office 365-appar är aktiverat globalt är Pat inte inkluderat i några aktiva principer för säkert länkar, så skyddet kan inte tillämpas.|
|I Aaron Lee-organisationen `https://tailspintoys.com` konfigureras i **Blockera följande URL-adresser** i de globala inställningarna för säkra länkar. En princip för säkra länkar som innehåller Aaron Lee finns redan. Aaron Lee får ett e-postmeddelande som innehåller URL-adressen `https://tailspintoys.com/aboutus/trythispage` . Aaron Lee klickar på URL-adressen.|URL-adressen kanske blockeras automatiskt för Aaron Lee; Det beror på URL-posten i listan och e-postklienten Aaron Lee används. Mer information finns i avsnittet ["Blockera följande URL-adresser" för säkra länkar](#block-the-following-urls-list-for-safe-links) längre ned i det här avsnittet.|
|Janne och Julia är både arbete för contoso.com. För länge sedan, administratörer konfigurerade principer för säkra länkar som gäller för båda Janne och Julia. Janne skickar ett e-postmeddelande till Julia och vet inte att e-postmeddelandet innehåller en skadlig URL.|Julia skyddas av säkra länkar **om** den princip för säkra länkar som gäller för henne är konfigurerad för att tillämpas på meddelanden mellan interna mottagare. Mer information finns i avsnittet [Inställningar för säkra länkar i e-postmeddelanden](#safe-links-settings-for-email-messages) längre ned i det här avsnittet.|

## <a name="safe-links-settings-for-email-messages"></a>Inställningar för säkra Länkar för e-postmeddelanden

Säkra länkar söker efter kända hyperlänkar i inkommande e-post. Skannade URL-adresser skrivs om med Microsofts standard-URL-prefix: `https://nam01.safelinks.protection.outlook.com` . När länken har skrivits om analyseras den för potentiellt skadligt innehåll.

När du har skrivit om en URL-adress sparas URL-adressen om, även om meddelandet vidarebefordras eller besvaras. Ytterligare länkar som läggs till i meddelandet vidarebefordras eller besvaras inte.

Inställningarna i principer för säkra länkar som gäller för e-postmeddelanden beskrivs i följande lista:

- **Välj åtgärd för okända URL-adresser i meddelanden**: aktiverar eller inaktiverar sökning efter säkra länkar i e-postmeddelanden. Det rekommenderade värdet är **på**. Om du aktiverar den här inställningen får du följande åtgärder.

  - Sökning efter säkra länkar är aktiverat i Outlook (C2R) i Windows.
  - URL-adresser skrivs om och användare dirigeras genom skydd för säkra länkar när de klickar på URL-adresser i meddelanden.
  - När du klickar på det här alternativet kontrol leras URL-adresser mot en lista med kända skadliga URL-adresser och [listan Blockera följande URL](#block-the-following-urls-list-for-safe-links): er.
  - URL-adresser som inte har ett giltigt rykte är sprängade asynkront i bakgrunden.

- **Använda URL-genomsökning i real tid för misstänkta länkar och länkar som pekar på filer**: aktiverar genomsökning i real tid med länkar, inklusive länkar i e-postmeddelanden som pekar på nedladdnings Bart innehåll. Det rekommenderade värdet är aktiverat.

  - **Vänta på att URL-genomsökningen ska slutföras innan du levererar meddelandet**:

    - Aktive rad: meddelanden som innehåller URL: er sparas tills genomsökningen är klar. Meddelanden levereras först efter att URL-adresserna bekräftats. Det här är det rekommenderade värdet.
    - Disabled: om URL-genomsökning inte kan slutföras kan du leverera meddelandet ändå.

- **Använda säkra Länkar för e-postmeddelanden som skickas inom organisationen**: aktiverar eller inaktiverar sökningar efter säkra länkar på meddelanden som skickas mellan interna avsändare och interna mottagare i samma Exchange Online-organisation. Det rekommenderade värdet är aktiverat.

- **Spåra inte användare**: aktiverar eller inaktiverar lagring av säkra länkar Klicka på data för URL-adresser som visas i e-postmeddelanden. Rekommenderat värde är att lämna den här inställningen avmarkerad (för att spåra användares klickningar).

  URL-adress klicka på spårning för länkar i e-postmeddelanden som skickas mellan interna avsändare och interna mottagare stöds inte för närvarande.

- **Tillåt inte att användare klickar genom till ursprunglig URL**: tillåter eller blockerar användare från att klicka på [varnings sidan](#warning-pages-from-safe-links) till den ursprungliga URL-adressen. Rekommendation svärdet är aktiverat.

- **Skriv inte om följande webb adresser**: lämnar URL-adresser som de är. Behåller en anpassad lista med URL-adresser som inte behöver skannas. Listan är unik för varje princip för säkert länkar. Mer information om listan för att **inte skriva om följande URL-adresser** finns i [listorna "Skriv inte om följande URL: er" i avsnittet principer för säkra länkar](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) längre ned i den här artikeln.

Mer information om rekommenderade värden för princip inställningar för standard och Strict för principer för säkra länkar finns i [princip inställningar för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

- **Mottagar filter**: du måste ange de mottagar villkor och undantag som avgör vem principen gäller för. Du kan använda dessa egenskaper för villkor och undantag:

  - **Mottagaren är**
  - **Mottagar domänen är**
  - **Mottagaren är medlem i**

  Du kan bara använda ett villkor eller ett undantag, men villkoret eller undantaget kan innehålla flera värden. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

- **Prioritet**: om du skapar flera principer kan du ange i vilken ordning de används. Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

  För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

### <a name="how-safe-links-works-in-email-messages"></a>Så fungerar länkar i e-postmeddelanden

På en hög nivå finns här hur säkra länkar skyddar sig på URL-adresser i e-postmeddelanden:

1. All e-post går genom EOP, där IP (Internet Protocol) och kuvert filter, signaturbaserade skydd mot skadlig program vara, filter mot skräp post och skadlig program vara innan meddelandet skickas till mottagarens post låda.

2. Användaren öppnar meddelandet i post lådan och klickar på en URL i meddelandet.

3. Säkra länkar kontrollerar URL-adressen omedelbart innan webbplatsen öppnas:

   - Om URL-adressen ingår i listan **Blockera följande URL-adresser** öppnas en [blockerad URL-varning](#blocked-url-warning) .

   - Om URL: en pekar på en webbplats som har bedömts vara skadlig visas en [varnings sida för skadlig webbplats](#malicious-website-warning) (eller en annan varnings sida).

   - Om URL: en pekar på en nedladdnings bar fil och **Använd URL-genomsökning i real tid för att misstänkta länkar och länkar som pekar på filer** har Aktiver ATS i den princip som gäller för användaren, är nedladdnings bar fil markerad.

   - Om webb adressen är säker öppnas webbplatsen.

## <a name="safe-links-settings-for-microsoft-teams"></a>Inställningar för säkra Länkar för Microsoft Teams

> [!IMPORTANT]
> Från och med mars 2020 är den här funktionen i förhands granskning och är endast tillgänglig för medlemmar i Microsoft Teams-programmet (KNACKa).

Du aktiverar eller inaktiverar skydd för säkra Länkar för Microsoft Teams i principer för säkra länkar. Du använder specifikt **åtgärden Välj åtgärd för okända eller potentiellt skadliga URL-adresser i Microsoft Teams** . Det rekommenderade värdet är **på**.

Följande inställningar i principer för säkra länkar som gäller för länkar i e-postmeddelanden gäller även för länkar i Teams:

- **Använda URL-genomsökning i real tid för misstänkta länkar och länkar som pekar på filer**
- **Spåra inte användar klickningar**
- **Tillåt inte att användare klickar genom till ursprunglig URL**

De här inställningarna förklaras i tidigare [Inställningar för säkra länkar i e-postmeddelanden](#safe-links-settings-for-email-messages) .

När du har aktiverat Safe Links Protection för Microsoft Teams kontrol leras URL-adresser i Teams mot en lista med kända illasinnade länkar när den skyddade användaren klickar på länken (tids kontroll). URL-adresser skrivs inte över. Om en länk har visat sig vara skadlig kan användarna se följande:

- Om länken klickade i en grupp konversation, gruppchatt eller från kanaler visas varnings sidan som visas i skärm bilden nedan i standard webbläsaren.
- Om länken klickade på en Fäst flik visas varnings sidan i Teams-gränssnittet på den fliken. Alternativet att öppna länken i en webbläsare är avaktiverat av säkerhets skäl.
- Beroende på hur alternativet **Tillåt inte att användare klickar via till ursprunglig URL** i principen är konfigurerat, kommer användaren att tillåtas eller får inte klicka dig fram till den ursprungliga URL-adressen (**Fortsätt ändå (rekommenderas inte)** i skärm bilden. Vi rekommenderar att du aktiverar inställningen **Tillåt inte att användare klickar via till ursprunglig URL-adress** så att användarna inte kan klicka dig fram till den ursprungliga URL-adressen.

Om användaren som skickade länken inte är med i en princip för säkra länkar där team skydd är aktiverat kan användaren klicka dig fram till original-URL: en på deras dator eller enhet.

![Ett säkert länkar för Teams-sidan rapporterar en illasinnad länk.](../../media/tp-safe-links-for-teams-malicious.png)

Om du klickar på knappen **gå tillbaka** på varnings sidan kommer sidan att stängas (eller resultera i en tom sida som användarna kan stänga). Om du klickar på den ursprungliga länken igen kommer du att få säkra länkar att söka igenom URL-adressen igen, så att varnings sidan visas igen.

### <a name="how-safe-links-works-in-teams"></a>Hur säkra länkar fungerar i Teams

På en hög nivå finns här hur säkra länkar skyddar sig efter URL-adresser i Microsoft Teams:

1. En användare startar Teams-appen.

2. Microsoft 365 kontrollerar att användarens organisation innehåller Office 365 ATP och att användaren ingår i en Active Safe Links-princip där skyddet för Microsoft Teams är aktiverat.

3. URL-adresser verifieras vid tiden för användaren i chatt, gruppchatt, kanaler och flikar.

## <a name="safe-links-settings-for-office-365-apps"></a>Inställningar för säkra Länkar för Office 365-appar

Säkra länkar skydd för Office 365-appar kontrollerar länkar i Office-dokument, inte länkar i e-postmeddelanden (men den kan kontrol lera länkar i bifogade Office-dokument i e-postmeddelanden när dokumentet har öppnats).

Säkra länkar skydd för Office 365-appar har följande klient krav:

- Microsoft 365-appar eller Microsoft 365 Business Premium.
  - Aktuella versioner av Word, Excel och PowerPoint på Windows, Mac eller i en webbläsare.
  - Office-appar på iOS-eller Android-enheter.
  - Visio på Windows.
  - OneNote i en webbläsare.

- Office 365-apparna är konfigurerade för modern lösenordsautentisering. Mer information finns i [så här fungerar modern inloggningsautentisering för office 2013-, office 2016-och office 2019-klient program](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).

- Användarna loggas in med sina arbets-eller skol konton. Mer information finns i [Logga in på Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).

Du konfigurerar skydd för säkra Länkar för Office 365-appar i de globala inställningarna för säkra länkar, inte i principer för säkra länkar. Men för att skydda säkra Länkar för Office 365-appar ska användas, användaren som öppnar Office-dokumentet och klickar på länken, måste ingå i en aktiv säker länk-princip.

Följande inställningar för säkra länkar är tillgängliga för Office 365-appar:

- **Office 365-program**: aktiverar eller inaktiverar sökning efter säkra länkar i Office 365-appar som stöds. Standard och Rekommenderat värde är **på**.

- **Spåra inte när användare klickar på säkra länkar**: aktiverar eller inaktiverar lagring av säkra länkar Klicka på data för URL-adresser på Word, Excel, PowerPoint och Visio. Det rekommenderade värdet är **inaktiverat**, vilket innebär att användare spåras.

- **Tillåt inte att användare klickar via säkra länkar till original-URL**: tillåter eller blockerar användare från att klicka på [varnings sidan](#warning-pages-from-safe-links) till den ursprungliga URL-adressen i Skriv bords versionerna Word, Excel, PowerPoint och Visio. Standard och Rekommenderat värde är **på**.

Information om hur du konfigurerar inställningar för Safe Links för Office 365-appar finns i [Konfigurera skydd för säkra Länkar för office 365-appar](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).

Mer information om rekommenderade värden för standard-och strikta princip inställningar finns i [globala inställningar för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links).

### <a name="how-safe-links-works-in-office-365-apps"></a>Så fungerar säkra länkar i Office 365-appar

På en hög nivå finns här hur säkra länkar skyddar sig för URL-adresser i Office 365-appar. De Office 365-appar som stöds beskrivs i föregående avsnitt.

1. En användare loggar in med sitt arbets-eller skol konto i en organisation som innehåller Microsoft 365-appar eller Microsoft 365 Business Premium.

2. Användaren öppnar och klickar på en länk ett Office-dokument i en Office-app som stöds.

3. Säkra länkar kontrollerar URL-adressen omedelbart innan mål webbplatsen öppnas:

   - Om URL-adressen ingår i listan som hoppar över genomsökning av säkra länkar ( **blockera den här listan med** URL-adresser) öppnas [varnings sidan för blockerad URL](#blocked-url-warning) .

   - Om URL: en pekar på en webbplats som har bedömts vara skadlig visas en [varnings sida för skadlig webbplats](#malicious-website-warning) (eller en annan varnings sida).

   - Om URL: en pekar på en nedladdnings bar fil och den princip för säkra länkar som gäller för användaren är konfigurerad för att söka igenom länkar till nedladdnings Bart innehåll (**Använd URL-genomsökning i real tid för misstänkta länkar och länkar som pekar på filer**), är nedladdnings bar fil markerad.

   - Om URL: en anses vara säker kommer användaren till webbplatsen.

   - Om det inte går att slutföra sökning efter säkra länkar utlöses inte skydd mot säkra länkar. I Office-skrivbords klienter får användaren en varning innan de fortsätter till mål webbplatsen.

> [!NOTE]
> Det kan ta några sekunder i början av varje session att kontrol lera att användaren har säkra Länkar för Office aktiverat.

## <a name="block-the-following-urls-list-for-safe-links"></a>"Blockera följande URL-adresser" för säkra länkar

I listan **Blockera följande URL: er** definieras de länkar som alltid blockeras av genomsökning av Safe Links på följande platser.

- E-postmeddelanden.
- Dokument i Office 365-appar i Windows och Mac.
- Dokument i Office för iOS och Android.

När en användare i en Active Safe Link-princip klickar på en blockerad länk i ett program som stöds, tas de till den [blockerade varnings](#blocked-url-warning) sidan för URL-adressen.

Du konfigurerar listan med URL-adresser i de globala inställningarna för säkra länkar. Anvisningar finns i [Konfigurera listan "Blockera följande URL-adresser"](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).

**Anmärkningar**:

- En verklig universell lista med URL: er som blockeras överallt finns i [hantera URL-adresser i listan Tillåt/blockera för klient organisation](tenant-allow-block-list.md).

- Restriktioner
  - Det maximala antalet poster är 500.
  - Den maximala längden för en post är 128 tecken.
  - Alla poster får inte överstiga 10 000 tecken.

- Ta inte med snedstreck ( `/` ) i slutet av webb adressen. Till exempel Använd `https://www.contoso.com` , inte `https://www.contoso.com/` .

- Endast en domän-URL (till exempel `contoso.com` eller `tailspintoys.com` ) blockerar alla URL-adresser som innehåller domänen.

- Du kan blockera en under domän utan att blockera den fullständiga domänen. Om du till exempel `toys.contoso.com*` blockerar en URL som innehåller under domänen, men den blockerar inte URL-adresser som innehåller den fullständiga domänen `contoso.com` .

- Du kan ta med upp till tre jokertecken ( `*` ) per URL-post.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Syntax för listan "Blockera följande URL-adresser"

Exempel på vilka värden du kan ange och deras resultat finns beskrivna i följande tabell:

****

|Value|Resultat|
|---|---|
|`contoso.com` <br/> eller <br/> `*contoso.com*`|Blockerar domänen, under domäner och sökvägar. Till exempel, `https://www.contoso.com` , `https://sub.contoso.com` och `https://contoso.com/abc` blockeras.|
|`https://contoso.com/a`|Block `https://contoso.com/a` men inte ytterligare under banor som `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Blockerar `https://contoso.com/a` och ytterligare under Sök vägar som `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Blockerar en under domän ( `toys` i det här exemplet) men tillåter klickningar till andra domän-URL: er (gilla `https://contoso.com` eller `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>"Skriv inte över följande URL-adresser" i principer för säkra länkar

> [!NOTE]
> Om din organisation använder principer för säkra länkar är **inte Skriv om följande URL** -listor de enda tillgängliga metoderna för nät fiske test av tredje part.

Alla principer för säkra länkar innehåller en, **Skriv inte över följande URL** -lista som du kan använda för att ange URL: er som inte skrivs om efter en säker sökning. Med andra ord kan du använda listan för att komma åt de angivna URL-adresser som annars skulle blockeras av säkra länkar. Du kan konfigurera olika listor i olika principer för säkra länkar. Princip bearbetning slutar efter den första (sannolika, högsta prioritets principen) tillämpas på användaren. Det innebär att bara en **inte skriver om följande webb adress** lista används för en användare som ingår i flera aktiva principer för säkra länkar.

Information om hur du lägger till poster i listan i nya eller befintliga principer för säkra länkar finns i [skapa principer för säkra länkar](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) eller [ändra principer för säkra länkar](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).

**Anmärkningar**:

- Följande klienter känner inte igen listan " **Skriv inte om följande URL-adresser** i principer för säkra länkar". Användare som ingår i polisen kan blockeras från att komma åt URL-adresserna baserat på resultaten av sökning efter säkra länkar i följande klienter:

  - Microsoft Teams
  - Office Web Apps

  En verklig universell lista över webb adresser som tillåts överallt finns i [hantera URL-adresser i listan Tillåt/blockera för klient organisation](tenant-allow-block-list.md).

- Överväg att lägga till vanliga interna URL-adresser i listan för att förbättra användar upplevelsen. Om du till exempel har lokala tjänster, till exempel Skype för företag eller SharePoint, kan du lägga till dessa URL-adresser för att utesluta dem från genomsökningen.

- Om du redan har angett **följande URL** -poster i dina principer för säkra länkar måste du läsa listorna och lägga till jokertecken efter behov. Din lista har till exempel en post som `https://contoso.com/a` du bestämmer dig för att inkludera under Sök vägar som `https://contoso.com/a/b` . I stället för att lägga till en ny post lägger du till ett jokertecken i den befintliga posten så att den blir `https://contoso.com/a/*` .

- Du kan ta med upp till tre jokertecken ( `*` ) per URL-post. Jokertecken inkluderar uttryckligen prefix eller under domäner. Posten är till exempel `contoso.com` inte samma sak som `*.contoso.com/*` eftersom `*.contoso.com/*` tillåter personer att besöka under domäner och sökvägar i den angivna domänen.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Syntax för listan "Skriv inte om följande URL: er"

Exempel på vilka värden du kan ange och deras resultat finns beskrivna i följande tabell:

****

|Value|Resultat|
|---|---|
|`contoso.com`|Tillåter åtkomst till `https://contoso.com` men inte under domäner eller sökvägar.|
|`*.contoso.com/*`|Tillåter åtkomst till en domän, under domäner och sökvägar (till exempel, `https://www.contoso.com` ,, `https://www.contoso.com` `https://maps.contoso.com` eller `https://www.contoso.com/a` ). <br/><br/> Den här posten är mycket bättre än `*contoso.com*` , eftersom den inte tillåter falska webbplatser, till exempel `https://www.falsecontoso.com` eller `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Tillåter åtkomst till `https://contoso.com/a` , men inte under Sök vägar `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Tillåter åtkomst till `https://contoso.com/a` och under Sök vägar som `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Varnings sidor från säkra länkar

Det här avsnittet innehåller exempel på de olika varnings sidor som aktive ras av skydd mot säkra länkar när du klickar på en webb adress.

Observera att flera varnings sidor har uppdaterats. Om du inte redan ser de uppdaterade sidorna är det snart. De uppdaterade sidorna innehåller ett nytt färg schema, mer information och möjligheten att gå vidare till en webbplats trots den angivna varningen och rekommendationerna.

### <a name="scan-in-progress-notification"></a>Avisering om genomsökning pågår

URL-adressen skannas av Safe Links. Du kan behöva vänta en liten stund innan du försöker igen.

![Meddelandet "länken skannas"](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

Den ursprungliga meddelande sidan såg ut så här:

![Ursprunglig "länken skannas"](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Varning om misstänkt meddelande

URL-adressen fanns i ett e-postmeddelande som liknar andra misstänkta meddelanden. Vi rekommenderar att du dubbelklickar på e-postmeddelandet innan du fortsätter till webbplatsen.

!["En länk klickade på ett misstänkt meddelande"](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Varning om nät fiske försök

URL-adressen fanns i ett e-postmeddelande som har identifierats som nätfiske-attack. Därför blockeras alla URL-adresser i e-postmeddelandet. Vi rekommenderar att du inte fortsätter till webbplatsen.

!["Länken klickade på ett nät fiske meddelande" visas](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Varning om skadlig webbplats

URL: en till en webbplats som har identifierats som skadlig. Vi rekommenderar att du inte fortsätter till webbplatsen.

![Varnings meddelandet "den här webbplatsen klassificeras som skadlig"](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

Den ursprungliga varnings sidan såg ut så här:

![Original varningen "den här webbplatsen har klassificerats som skadlig"](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Blockerad URL-varning

URL-adressen har blockerats av en administratör i din organisation ( **Blockera följande URL-adresser** i de globala inställningarna för säkra länkar). Länken skannades inte av säkra länkar eftersom den blockerades manuellt.

Det finns flera orsaker till att en administratör manuellt blockerar specifika URL: er. Om du tror att webbplatsen inte ska blockeras kontaktar du din administratör.

![Varningen "webbplatsen har blockerats av din administratör"](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

Den ursprungliga varnings sidan såg ut så här:

![Ursprunglig "den här webbplatsen har blockerats per din organisations URL-princip"-varning](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Fel varning

En typ av fel har inträffat och URL: en kan inte öppnas.

![Varningen "sidan som du försöker komma åt går inte att läsa in"](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

Den ursprungliga varnings sidan såg ut så här:

![Ursprunglig "Det gick inte att läsa in den här webb sidan"](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
