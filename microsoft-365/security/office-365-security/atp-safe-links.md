---
title: Säkra länkar
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
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
description: I den här artikeln kan administratörer läsa mer om skydd mot säkra länkar i Defender för Office 365 för att skydda organisationen från nätfiske och andra attacker som använder skadliga URL:er.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 15168f2fff5ce1e4afbef5ff71a780de896f0bbf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288699"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Säkra länkar i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](office-365-atp.md). Om du använder Outlook.com, Microsoft 365 Family eller Microsoft 365 Personal och letar efter information om säkra länkar i Outlook, se [Avancerad Outlook.com säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Säkra länkar är en funktion i Defender för [Office 365](office-365-atp.md) som ger URL-sökning och omskrivning av inkommande e-postmeddelanden i e-postflödet samt tids för klick-verifiering av URL:er och länkar i e-postmeddelanden och andra platser. Genomsökning av säkra länkar sker utöver det vanliga skyddet mot skräppost och skadlig programvara för inkommande [e-postmeddelanden](anti-spam-and-anti-malware-protection.md) i Exchange Online Protection (EOP). Genomsökning av säkra länkar kan skydda organisationen från skadliga länkar som används vid nätfiske och andra attacker.

Skydd mot säkra länkar är tillgängligt på följande platser:

- **E-postmeddelanden:** Skydd mot säkra länkar för länkar i e-postmeddelanden styrs av principer för säkra länkar. Det finns ingen standardprincip för säkra länkar, så för att skydda säkra länkar i e-postmeddelanden måste du skapa en eller flera principer för **säkra länkar.** Instruktioner finns i Konfigurera [principer för säkra länkar i Microsoft Defender för Office 365.](set-up-atp-safe-links-policies.md)

  Mer information om skydd mot säkra länkar för e-postmeddelanden finns i inställningarna för säkra länkar för [e-postmeddelanden](#safe-links-settings-for-email-messages) längre fram i den här artikeln.

- **Microsoft Teams** (för närvarande i förhandsversionen av TAP): Skydd av säkra länkar för länkar i Teams-konversationer, gruppchattar eller från kanaler styrs också av principer för säkra länkar. Det finns ingen standardprincip för säkra länkar, så för att få skydd av säkra länkar i Teams måste du skapa en **eller flera principer för säkra länkar.**

  Mer information om skydd mot säkra länkar i Teams finns i inställningarna [för säkra länkar för Microsoft Teams](#safe-links-settings-for-microsoft-teams) senare i den här artikeln.

- **Office 365-program:** Skydd mot säkra länkar för Office 365-program är tillgängligt i skrivbords-, mobil- och webb-APS som stöds. Du **konfigurerar** skydd mot säkra länkar för Office 365-program i den globala inställning som ligger **utanför** principerna för säkra länkar. Instruktioner finns i Konfigurera [globala inställningar för inställningar för säkra länkar i Microsoft Defender för Office 365.](configure-global-settings-for-safe-links.md)

  Skydd av säkra länkar för Office 365-program tillämpas dock bara på användare som ingår i aktiva principer för säkra länkar.  Om en användare inte ingår i en aktiv princip för säkra länkar får användaren inte skydd mot säkra länkar i Office 365-program som stöds.

  Mer information om skydd mot säkra länkar i Office 365-program finns i inställningarna för Säkra länkar för [Office 365-program](#safe-links-settings-for-office-365-apps) senare i den här artikeln.

Den här artikeln innehåller detaljerade beskrivningar av följande typer av inställningar för säkra länkar:

- **Inställningar i principer för säkra** länkar: De här inställningarna gäller endast för de användare som ingår i specifika principer och inställningarna kan skilja sig åt mellan principer. Dessa inställningar omfattar:

  - [Inställningar för säkra länkar för e-postmeddelanden](#safe-links-settings-for-email-messages)
  - [Inställningar för säkra länkar för Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - ["Skriva inte om följande URL:er" i principer för säkra länkar](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Globala inställningar för säkra** länkar: De här inställningarna konfigureras globalt, inte i principer för säkra länkar. Inställningarna gäller dock endast för användare som ingår i aktiva principer för säkra länkar. Dessa inställningar omfattar:

  - [Inställningar för säkra länkar för Office 365-appar](#safe-links-settings-for-office-365-apps)
  - [Listan "Blockera följande URL:er" för Säkra länkar](#block-the-following-urls-list-for-safe-links)

I följande tabell beskrivs scenarier för säkra länkar i Microsoft 365- och Office 365-organisationer där Defender för Office 365 ingår (brist på licensiering är alltså aldrig ett problem i exemplen).

****

|Scenario|Resultat|
|---|---|
|Han är medlem i marknadsföringsavdelningen. Skydd mot säkra länkar för Office 365-program aktiveras i de globala inställningarna för Säkra länkar, och det finns en princip för säkra länkar som gäller för medlemmar i marknadsföringsavdelningen. Han öppnar en PowerPoint-presentation i ett e-postmeddelande och klickar sedan på en URL i presentationen.|Han är skyddad av Säkra länkar. <p> Ingår i en princip för säkra länkar och skydd mot säkra länkar för Office 365-appar är aktiverat. <p> Mer information om kraven för skydd mot säkra länkar i Office 365-program finns i avsnittet Säkra länkar för [Office 365-program](#safe-links-settings-for-office-365-apps) senare i den här artikeln.|
|Chris Microsoft 365 E5-organisation har inga principer för säkra länkar konfigurerade. Chris får ett e-postmeddelande från en extern avsändare som innehåller en URL till en skadlig webbplats som han slutligen klickar på.|Chris skyddas inte av Säkra länkar. <p> En administratör måste skapa minst en princip för säkra länkar för att alla ska kunna få skydd mot säkra länkar i inkommande e-postmeddelanden. Chris måste omfattas av policyvillkoren för att skydda säkra länkar.|
|I Pats organisation har inga administratörer skapat några principer för säkra länkar, men skydd mot säkra länkar för Office 365-program är aktiverat. Pat öppnar ett Word-dokument och klickar på en URL i filen.|Pat skyddas inte av Säkra länkar. <p> Även om skydd mot säkra länkar för Office 365-program är aktiverat globalt ingår Pat inte i några aktiva principer för säkra länkar, så skyddet kan inte tillämpas.|
|I Lees organisation är `https://tailspintoys.com` den konfigurerad i listan **Spärra följande URL-adresser** i de globala inställningarna för Säkra länkar. En princip för säkra länkar som innehåller Lee redan finns. Lee får ett e-postmeddelande som innehåller `https://tailspintoys.com/aboutus/trythispage` WEBBADRESSen. Lee klickar på WEBBADRESSen.|URL-adressen kan blockeras automatiskt för Lee. Det beror på URL-posten i listan och vilken e-postklient Lee använde. Mer information finns i listan ["Blockera följande URL:er" för avsnittet Säkra](#block-the-following-urls-list-for-safe-links) länkar senare i den här artikeln.|
|Både Johan och Julia arbetar för contoso.com. För länge sedan konfigurerade administratörer principer för säkra länkar som gäller för både Janne och Julia. Johan skickar ett e-postmeddelande till Julia, utan att veta att e-postmeddelandet innehåller en skadlig URL.|Julia skyddas av säkra länkar **om principen** för säkra länkar som gäller för henne är konfigurerad att gälla meddelanden mellan interna mottagare. Mer information finns i inställningarna för [Säkra länkar för e-postmeddelanden](#safe-links-settings-for-email-messages) längre fram i den här artikeln.|

## <a name="safe-links-settings-for-email-messages"></a>Inställningar för säkra länkar för e-postmeddelanden

Säkra länkar söker igenom inkommande e-postmeddelanden efter kända skadliga hyperlänkar. Skannade URL:er skrivs om med Microsofts standard-URL-prefix: `https://nam01.safelinks.protection.outlook.com` . När länken har skrivits om analyseras den för potentiellt skadligt innehåll.

När säkra länkar har skrivit om en URL förblir URL:en omskriven även om meddelandet vidarebefordras manuellt eller besvaras (både till interna och externa mottagare).  Ytterligare länkar som läggs till i det vidarebefordrade eller besvarade meddelandet skrivs inte om. När det gäller  automatisk vidarebefordran via inkorgsregler eller SMTP-vidarebefordran skrivs dock inte URL-adressen om  i meddelandet som är avsedd för den slutliga mottagaren om inte mottagaren också skyddas av Säkra länkar eller om URL-adressen redan har skrivits om i ett tidigare meddelande. 

Inställningarna i principer för säkra länkar som gäller för e-postmeddelanden beskrivs i följande lista:

- **Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden:** Aktiverar eller inaktiverar sökning med säkra länkar i e-postmeddelanden. Det rekommenderade värdet är **På.** Om du slår på den här inställningen resulterar det i följande åtgärder.

  - Genomsökning av säkra länkar är aktiverat i Outlook (C2R) i Windows.
  - URL:er skrivs om och användare dirigeras genom skydd mot säkra länkar när de klickar på URL-adresser i meddelanden.
  - Vid klickning kontrolleras URL:er mot en lista med kända skadliga URL:er och listan ["Blockera följande URL:er".](#block-the-following-urls-list-for-safe-links)
  - URL:er som inte har ett giltigt rykte detoneras asynkront i bakgrunden.

- **Använd URL-skanning** i realtid för misstänkta länkar och länkar som pekar på filer: Möjliggör genomsökning av länkar i realtid, inklusive länkar i e-postmeddelanden som pekar på hämtningsbart innehåll. Det rekommenderade värdet aktiveras.

  - **Vänta tills URL-skanningen har slutförts innan du levererar meddelandet:**

    - Aktiverad: Meddelanden som innehåller URL:er hålls kvar tills genomsökning har slutförts. Meddelanden levereras endast när URL:erna har bekräftats vara säkra. Det här är det rekommenderade värdet.
    - Inaktiverat: Om URL-skanningen inte kan slutföra levereras meddelandet ändå.

- **Tillämpa säkra länkar på e-postmeddelanden** som skickas inom organisationen: Aktiverar eller inaktiverar säker länkskanning för meddelanden som skickas mellan interna avsändare och interna mottagare inom samma Exchange Online-organisation. Det rekommenderade värdet aktiveras.

- **Spåra inte användarklick: Aktiverar** eller inaktiverar lagring av data för säkra länkar klickdata för URL:er som klickas i e-postmeddelanden. Rekommenderad inställning är att låta den här inställningen vara avmarkerad (för att spåra användarklick).

  URL-klickspårning för länkar i e-postmeddelanden som skickas mellan interna avsändare och interna mottagare stöds för närvarande inte.

- **Tillåt inte att användare klickar till den ursprungliga** URL:en: Tillåter eller blockerar användare från att klicka på [varningssidan](#warning-pages-from-safe-links) till den ursprungliga URL:en. Rekommenderad värde är aktiverat.

- **Skriva inte om följande URL:er:** Lämnar URL:er som de är. Med den här listan ser du till att en anpassad lista med säkra webbadresser som inte behöver skannas visas. Listan är unik för varje princip för säkra länkar. Mer information om  listan Ange inte om följande URL-adresser finns i listorna "Skriva inte om följande URL:er" i avsnittet om principer för säkra länkar längre fram i den här artikeln. [](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

Mer information om rekommenderade värden för standard- och strikt-principinställningar för principer för säkra länkar finns i [principinställningarna för Säkra länkar.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- **Mottagarfilter:** Du måste ange mottagarens villkor och undantag som bestämmer vem principen gäller för. Du kan använda de här egenskaperna för villkor och undantag:

  - **Mottagaren**
  - **Mottagardomänen är**
  - **Mottagaren är medlem i**

  Du kan bara använda ett villkor eller undantag en gång, men villkoret eller undantaget kan innehålla flera värden. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

- **Prioritet:** Om du skapar flera principer kan du ange i vilken ordning de ska tillämpas. Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

  För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

### <a name="how-safe-links-works-in-email-messages"></a>Hur säkra länkar fungerar i e-postmeddelanden

Så här fungerar skydd mot säkra länkar på en hög nivå med URL-adresser i e-postmeddelanden:

1. All e-post går via EOP, där INTERNETPROTOKOLL (IP) och kuvertfilter, signaturbaserat skydd mot skadlig programvara, skydd mot skräppost och skadlig programvara filtreras innan meddelandet levereras till mottagarens postlåda.

2. Användaren öppnar meddelandet i sin postlåda och klickar på en URL i meddelandet.

3. Med Säkra länkar kontrolleras url:en omedelbart innan webbplatsen öppnas:

   - Om URL:en finns i **listan Blockera följande URL:er** öppnas en varning [om blockerad](#blocked-url-warning) URL.

   - Om URL:en pekar på en webbplats som [](#malicious-website-warning) har fastställt att den är skadlig, öppnas en varningssida för skadlig webbplats (eller en annan varningssida).

   - Om **URL:en** pekar på en hämtningsbar fil och använd URL-genomsökning i realtid för misstänkta länkar och länkar som pekar på filer har aktiverats i principen som gäller för användaren, är den hämtningsbara filen markerad.

   - Om URL:en är säker öppnas webbplatsen.

## <a name="safe-links-settings-for-microsoft-teams"></a>Inställningar för säkra länkar för Microsoft Teams

> [!IMPORTANT]
> Från och med mars 2020 är den här funktionen i förhandsversion och är endast tillgänglig för medlemmar i Microsoft Teams Technology Adoption Program (TAP). Mer information om versionsschemat finns i Microsoft [365-översikten.](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)

Du aktiverar eller inaktiverar skydd mot säkra länkar för Microsoft Teams i principer för säkra länkar. Mer specifikt använder du åtgärden **Markera för okända eller potentiellt skadliga URL-adresser i Microsoft Teams-inställningen.** Det rekommenderade värdet är **På.**

Följande inställningar i principer för säkra länkar som gäller för länkar i e-postmeddelanden gäller även för länkar i Teams:

- **Använda URL-sökning i realtid för misstänkta länkar och länkar som pekar på filer**
- **Spåra inte användarklick**
- **Tillåt inte att användare klickar till den ursprungliga URL:en**

De här inställningarna förklaras i tidigare [inställningar för säkra länkar för e-postmeddelanden.](#safe-links-settings-for-email-messages)

När du aktiverar skydd mot säkra länkar för Microsoft Teams kontrolleras URL:er i Teams mot en lista med kända skadliga länkar när den skyddade användaren klickar på länken (tids för klickningsskydd). URL:er skrivs inte om. Om en länk visas som skadlig har användarna följande funktioner:

- Om länken klickades i en Teams-konversation, gruppchatt eller från kanaler visas varningssidan som visas i skärmbilden nedan i standardwebbläsaren.
- Om du klickade på länken från en fäst flik visas varningssidan i Teams-gränssnittet på den fliken. Alternativet att öppna länken i en webbläsare är inaktiverat av säkerhetsskäl.
- Beroende på hur tillåt inte användare att klicka sig fram till den ursprungliga **URL-inställningen** i principen har konfigurerats tillåts eller tillåts användaren inte att klicka till den ursprungliga URL:en (Fortsätt ändå **(rekommenderas inte)** på skärmbilden. Vi rekommenderar att du aktiverar Tillåt inte att användare klickar sig fram till den ursprungliga **URL-inställningen** så att användarna inte kan klicka till den ursprungliga URL:en.

Om användaren som skickade länken inte finns med i en princip för säkra länkar där Teams-skydd är aktiverat kan användaren klicka sig fram till den ursprungliga URL:en på sin dator eller enhet.

![En sida med säkra länkar för Teams som rapporterar en skadlig länk.](../../media/tp-safe-links-for-teams-malicious.png)

Om du **klickar på knappen** Gå tillbaka på varningssidan återgår användaren till sin ursprungliga kontext eller URL-plats. Om du klickar på den ursprungliga länken igen får dock Felsäkert länkar att ändra webbadressen, så att varningssidan visas igen.

### <a name="how-safe-links-works-in-teams"></a>Hur säkra länkar fungerar i Teams

På en hög nivå fungerar skydd av säkra länkar för URL:er i Microsoft Teams så här:

1. En användare startar Teams-appen.

2. Microsoft 365 verifierar att användarens organisation inkluderar Microsoft Defender för Office 365 och att användaren ingår i en aktiv princip för säkra länkar där skydd för Microsoft Teams är aktiverat.

3. URL:er valideras när användaren klickar i chattar, gruppchattar, kanaler och flikar.

## <a name="safe-links-settings-for-office-365-apps"></a>Inställningar för säkra länkar för Office 365-appar

Skydd mot säkra länkar för Office 365-program kontrollerar länkar i Office-dokument, inte länkar i e-postmeddelanden (men det kan kontrollera länkar i bifogade Office-dokument i e-postmeddelanden när dokumentet har öppnats).

Skydd mot säkra länkar för Office 365-program har följande klientkrav:

- Microsoft 365 Apps eller Microsoft 365 Business Premium.
  - Aktuella versioner av Word, Excel och PowerPoint på Windows, Mac eller i en webbläsare.
  - Office-appar på iOS- eller Android-enheter.
  - Visio i Windows.
  - OneNote i en webbläsare.

- Office 365-program är konfigurerade för modern autentisering. Mer information finns i Hur modern autentisering fungerar för [Office 2013-, Office 2016- och Office 2019-klientprogram.](../../enterprise/modern-auth-for-office-2013-and-2016.md)

- Användarna loggas in med sina arbets- eller skolkonton. Mer information finns i [Logga in på Office.](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)

Du konfigurerar skydd mot säkra länkar för Office 365-program i de globala inställningarna för Säkra länkar, inte i principer för säkra länkar. Men för att skydd mot säkra länkar för Office 365-program ska tillämpas måste användaren som öppnar Office-dokumentet och klickar på länken inkluderas i en aktiv princip för säkra länkar.

Följande inställningar för Säkra länkar är tillgängliga för Office 365-program:

- **Office 365-program:** Aktiverar eller inaktiverar säker sökning med länkar i Office 365-program som stöds. Standardvärdet och det rekommenderade värdet är **På.**

- **Spåra inte när användare** klickar på Säkra länkar: Aktiverar eller inaktiverar data för säker länkklick på data för URL-adresser som klickas i skrivbordsversionerna av Word, Excel, PowerPoint och Visio. Det rekommenderade värdet är **Av,** vilket innebär att användarens klick spåras.

- **Låt inte användare** klicka igenom säkra länkar till den ursprungliga [](#warning-pages-from-safe-links) URL:en: Tillåter eller blockerar användare från att klicka på varningssidan till den ursprungliga URL-adressen i skrivbordsversionerna av Word, Excel, PowerPoint och Visio. Standardvärdet och det rekommenderade värdet är **På.**

Information om hur du konfigurerar inställningarna för säkra länkar för Office 365-program finns i Konfigurera skydd mot säkra länkar för [Office 365-program.](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)

Mer information om rekommenderade värden för principinställningarna Standard och Strikt finns i [Globala inställningar för Säkra länkar.](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)

### <a name="how-safe-links-works-in-office-365-apps"></a>Hur säkra länkar fungerar i Office 365-appar

Så här fungerar säkert länkskydd för URL:er i Office 365-program på en hög nivå. De Office 365-program som stöds beskrivs i föregående avsnitt.

1. En användare loggar in med sitt arbets- eller skolkonto i en organisation som innehåller Microsoft 365 Apps eller Microsoft 365 Business Premium.

2. Användaren öppnas och klickar på en länk till ett Office-dokument i ett Office-program som stöds.

3. Säkra länkar kontrollerar omedelbart WEBBADRESSen innan målwebbplatsen öppnas:

   - Om URL:en finns med i listan som  hoppar över skanning av säkra länkar (listan Blockera följande URL-adresser) öppnas en varningssida för [blockerade](#blocked-url-warning) URL:er.

   - Om URL:en pekar på en webbplats som [](#malicious-website-warning) har fastställt att den är skadlig, öppnas en varningssida för skadlig webbplats (eller en annan varningssida).

   - Om **URL-adressen** pekar på en hämtningsbar fil och principen för säkra länkar som gäller för användaren är konfigurerad att söka igenom länkar till hämtningsbart innehåll (använd URL-genomsökning i realtid för misstänkta länkar och länkar som pekar på filer) är den nedladdningsbara filen markerad.

   - Om URL:en anses vara säker tas användaren till webbplatsen.

   - Om genomsökning av säkra länkar inte kan slutföras utlöses inte skyddet för säkra länkar. I Office-skrivbordsklienter får användaren en varning innan han eller hon går vidare till målwebbplatsen.

> [!NOTE]
> Det kan ta flera sekunder i början av varje session att verifiera att användaren har säkra länkar för Office aktiverat.

## <a name="block-the-following-urls-list-for-safe-links"></a>Listan "Blockera följande URL:er" för Säkra länkar

Listan **Blockera följande URL-adresser** definierar de länkar som alltid blockeras genom genomsökning av säkra länkar på följande platser:

- E-postmeddelanden.
- Dokument i Office 365-program i Windows och Mac.
- Dokument i Office för iOS och Android.

När en användare i en aktiv princip för säkra länkar klickar på en blockerad länk i ett program som stöds kommer de till varningssidan [blockerad](#blocked-url-warning) URL.

Du konfigurerar listan med URL-adresser i de globala inställningarna för Säkra länkar. Instruktioner finns i [Konfigurera listan "Blockera följande URL:er".](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)

**Anmärkningar**:

- En verkligt universell lista över URL-adresser som blockeras överallt finns i [Hantera klientorganisationens lista över tillåtna/blockerade adresser.](tenant-allow-block-list.md)

- Begränsningar:
  - Det maximala antalet poster är 500.
  - Den maximala längden på en post är 128 tecken.
  - Alla poster får högst vara 10 000 tecken.

- Inkludera inte ett snedstreck `/` () i slutet av URL:en. Du kan till exempel `https://www.contoso.com` använda , inte `https://www.contoso.com/` .

- En URL med endast domän (till `contoso.com` `tailspintoys.com` exempel) blockerar alla URL-adresser som innehåller domänen.

- Du kan blockera en underdomän utan att blockera hela domänen. Spärrar `toys.contoso.com*` till exempel URL-adresser som innehåller underdomänen, men url-adresser som innehåller den fullständiga domänen blockeras `contoso.com` inte.

- Du kan ta med upp till tre jokertecken ( `*` ) per URL-post.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Postsyntaxen för listan "Blockera följande URL:er"

Exempel på värden som du kan ange och deras resultat beskrivs i följande tabell:

****

|Value|Resultat|
|---|---|
|`contoso.com` <p> eller <p> `*contoso.com*`|Spärrar domäner, underdomäner och sökvägar. Till `https://www.contoso.com` `https://sub.contoso.com` exempel, och `https://contoso.com/abc` blockeras.|
|`https://contoso.com/a`|Spärrar `https://contoso.com/a` men inte ytterligare undervägar `https://contoso.com/a/b` som.|
|`https://contoso.com/a*`|Blockerar `https://contoso.com/a` och ytterligare undervägar `https://contoso.com/a/b` som.|
|`https://toys.contoso.com*`|Spärrar en underdomän `toys` (i det här exemplet) men tillåter klick till andra domän-URL:er (t.ex. `https://contoso.com` `https://home.contoso.com` eller).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>"Skriva inte om följande URL:er" i principer för säkra länkar

> [!NOTE]
> Om organisationen använder principer för  säkra länkar är följande URL-listor inte omskrivningar den enda metod som stöds för nätfisketester från tredje part.

Varje princip för  säkra länkar innehåller en Omskrivning av inte följande URL-lista som du kan använda för att ange URL-adresser som inte skrivs om vid genomsökning av säkra länkar. Med andra ord gör listan att användare som ingår i principen kan komma åt angivna URL:er som annars skulle blockeras av säkra länkar. Du kan konfigurera olika listor i olika principer för säkra länkar. Principbearbetningen avbryts efter att den första principen (förmodligen högsta prioritet) tillämpas på användaren. Därför är det bara **en som inte** skriver om följande URL-lista och tillämpas på en användare som ingår i flera aktiva principer för säkra länkar.

Information om hur du lägger till poster i listan i nya eller befintliga principer för säkra länkar finns i Skapa principer för säkra [länkar](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) [eller Ändra principer för säkra länkar.](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)

**Anmärkningar**:

- Följande klienter känner inte igen följande **URL-listor** i principer för säkra länkar. Användare som omfattas av de här säkerheterna kan blockeras från att komma åt webbadresserna baserat på resultatet av genomsökning av Säkra länkar i dessa klienter:

  - Microsoft Teams
  - Office-webbappar

  En verkligt universell lista över URL-adresser som är tillåtna överallt finns i [Hantera klientorganisationens lista över tillåtna/blockerade adresser.](tenant-allow-block-list.md)

- Överväg att lägga till ofta använda interna URL:er i listan för att förbättra användarupplevelsen. Om du till exempel har lokala tjänster, till exempel Skype för företag eller SharePoint, kan du lägga till de URL-adresser som undantar dem från genomsökning.

- Om du redan har Skriver inte om följande **URL-adresser** i principerna för säkra länkar bör du granska listorna och lägga till jokertecken efter behov. Listan har till exempel en post som du senare `https://contoso.com/a` bestämmer dig för att ta med undervägar `https://contoso.com/a/b` som. I stället för att lägga till en ny post kan du lägga till ett jokertecken för den befintliga posten så att det blir `https://contoso.com/a/*` det.

- Du kan ta med upp till tre jokertecken ( `*` ) per URL-post. Jokertecken innehåller uttryckligen prefix eller underdomäner. Posten är till exempel inte samma som , eftersom den tillåter att personer besöker underdomäner `contoso.com` `*.contoso.com/*` och `*.contoso.com/*` sökvägar i den angivna domänen.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Postsyntaxen för listan "Ange inte följande URL:er"

Exempel på värden som du kan ange och deras resultat beskrivs i följande tabell:

****

|Value|Resultat|
|---|---|
|`contoso.com`|Tillåter åtkomst till `https://contoso.com` men inte underdomäner eller sökvägar.|
|`*.contoso.com/*`|Tillåter åtkomst till en domän, underdomäner och sökvägar (till `https://www.contoso.com` `https://www.contoso.com` exempel, `https://maps.contoso.com` `https://www.contoso.com/a` eller). <p> Den här posten är bättre än den, eftersom den inte tillåter potentiellt falska `*contoso.com*` webbplatser, som `https://www.falsecontoso.com` eller `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Tillåter åtkomst `https://contoso.com/a` till, men inte undervägar som `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Tillåter åtkomst till `https://contoso.com/a` och undervägar som `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Varningssidor från Säkra länkar

Det här avsnittet innehåller exempel på de olika varningssidor som utlöses av skydd mot säkra länkar när du klickar på en URL.

Observera att flera varningssidor har uppdaterats. Om du inte redan ser de uppdaterade sidorna kommer du snart att göra det. De uppdaterade sidorna innehåller ett nytt färgschema, mer detaljerad information och möjligheten att gå vidare till en webbplats trots den angivna varningen och rekommendationerna.

### <a name="scan-in-progress-notification"></a>Avisering om pågående sökning

Url:en som du klickar på genomsöks av Säkra länkar. Det kan ta en liten stund innan du provar länken igen.

![Meddelandet "Länken genomsöks"](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

Den ursprungliga aviseringssidan såg ut så här:

![Ursprungliga meddelandet "Länken genomsöks"](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Varning om misstänkt meddelande

Den klickade URL-adressen fanns i ett e-postmeddelande som liknar andra misstänkta meddelanden. Vi rekommenderar att du dubbelkollar e-postmeddelandet innan du fortsätter till webbplatsen.

![Varningsmeddelandet "En länk klickades från ett misstänkt meddelande"](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Varning om försök till nätfiske

Den klickade URL:en fanns i ett e-postmeddelande som identifierats som en nätfiskeattack. Därför blockeras alla URL:er i e-postmeddelandet. Vi rekommenderar att du inte fortsätter till webbplatsen.

![Varningen "Länken klickades från ett nätfiskemeddelande"](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Varning om skadlig webbplats

Den klickade URL-adressen pekar på en webbplats som har identifierats som skadlig. Vi rekommenderar att du inte fortsätter till webbplatsen.

![Varningsmeddelandet "Den här webbplatsen klassificeras som skadlig"](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

Den ursprungliga varningssidan såg ut så här:

![Den ursprungliga varningen "Den här webbplatsen har klassificerats som skadlig"](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Varning om blockerad URL

Url-adressen som du har klickat på har  blockerats manuellt av en administratör i din organisation (listan Blockera följande URL-adresser i de globala inställningarna för säkra länkar). Länken genomsökdes inte av Säkra länkar eftersom den blockerades manuellt.

Det finns flera orsaker till varför en administratör manuellt skulle blockera specifika URL:er. Kontakta administratören om du tror att webbplatsen inte ska blockeras.

![Varningen "Den här webbplatsen blockerades av din administratör"](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

Den ursprungliga varningssidan såg ut så här:

![Den ursprungliga varningen "Den här webbplatsen har blockerats enligt organisationens URL-princip"](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Felvarning

Någon typ av fel har inträffat och URL-adressen kan inte öppnas.

![Varningsmeddelandet "Sidan du försöker komma åt kan inte läsas in"](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

Den ursprungliga varningssidan såg ut så här:

![Varning om att den här webbsidan inte kunde läsas in](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
