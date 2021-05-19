---
title: De 10 bästa sätten att skydda Microsoft 365 för företag-abonnemang
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: 'Skydda din affärs-e-post och data från cyberhot, inklusive utpressningstrojaner, nätfiske och skadliga bifogade filer. '
ms.openlocfilehash: dcaeb9588f50d1e12bdff5164f5f41a0beee2e47
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535884"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>De 10 bästa sätten att skydda Microsoft 365 för företag-abonnemang

Om du är en liten eller medelstor organisation som använder en av Microsofts affärsplaner och din typ av organisation är riktad mot cyberbrottsligheter och hackare kan du använda vägledning i den här artikeln för att öka säkerheten för din organisation. Den här vägledningen hjälper din organisation att uppnå de mål som beskrivs i Harvard Harvard School [Cybersecurity Campaign Handbook.](https://go.microsoft.com/fwlink/p/?linkid=2015598)

Microsoft rekommenderar att du utför de uppgifter som listas i följande tabell som gäller för ditt abonnemang.

||Uppgift|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|---|
|1|[Konfigurera multifaktorautentisering](secure-your-business-data.md#setup)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[Utbilda dina användare](secure-your-business-data.md#train)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Använda dedikerade administratörskonton](secure-your-business-data.md#admin)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4|[Höja skyddsnivån för skadlig programvara i e-post](secure-your-business-data.md#malware)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5|[Skydda mot utpressningstrojaner](secure-your-business-data.md#ransomware)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6|[Stoppa automatisk vidarebefordran av e-post](secure-your-business-data.md#forwarding)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7|[Använda Office meddelandekryptering](secure-your-business-data.md#encryption)||![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8|[Skydda din e-post från nätfiskeattacker](secure-your-business-data.md#phishing)||![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9|[Skydda mot skadliga bilagor och filer med Valv bilagor](secure-your-business-data.md#atp)||![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10|[Skydda mot nätfiskeattacker med Valv länkar](secure-your-business-data.md#phishingatp)||![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

Det snabbaste sättetföretag att konfigurera säkerhet och börja samarbeta säkert för dig med Microsoft Business Premium är att följa vägledningen i det här biblioteket: [Microsoft 365 för mindre företag och kampanjer](../../campaigns/index.md). Den här vägledningen har utvecklats i samarbete med teamet för Microsoft Defending Democracy för att skydda alla kunder med småföretag mot cyberhot från avancerade hackare.

Innan du börjar kontrollerar du [Microsoft 365 Secure Score](../../security/defender/microsoft-secure-score.md) i Microsoft 365 säkerhetscenter. Från en centraliserad instrumentpanel kan du övervaka och förbättra säkerheten för Microsoft 365 identiteter, data, appar, enheter och infrastruktur. Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter (till exempel visa rapporter) eller åtgärda rekommendationer med ett program eller en programvara från tredje part. Med ytterligare insikter och mer insyn i en bredare uppsättning av Microsofts produkter och tjänster kan du känna dig säker på att du rapporterar om organisationens säkerhetshälsa.

![Skärmbild av Microsoft Secure Score](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: Konfigurera multifaktorautentisering
<a name="setup"> </a>

Att använda multifaktorautentisering är ett av de enklaste och mest effektiva sätten att öka säkerheten i organisationen. Det är enklare än det låter – när du loggar in innebär multifaktorautentisering att du skriver en kod från telefonen för att få åtkomst till Microsoft 365. Det kan förhindra att hackare tar över om de känner till ditt lösenord. Multifaktorautentisering kallas även tvåstegsverifiering. Personer kan enkelt lägga till tvåstegsverifiering i de flesta konton, till exempel i sina Google- eller Microsoft-konton. Så här lägger du till [tvåstegsverifiering för ditt personliga Microsoft-konto.](https://go.microsoft.com/fwlink/p/?linkid=2016403)

För företag som använder Microsoft 365 lägger du till en inställning som kräver att användarna loggar in med multifaktorautentisering. När du gör den här ändringen uppmanas användarna att konfigurera sin telefon för tvåfaktorautentisering nästa gång de loggar in.
Om du vill se en utbildningsvideo om hur du konfigurerar MFA och hur användarna slutför konfigurerat går du till Konfigurera [MFA](../../business-video/turn-on-mfa.md) och [användaruppsättning.](../../business-video/set-up-mfa.md)

Om du vill konfigurera multifaktorautentisering aktiverar du Standardinställningar för säkerhet:

För de flesta organisationer tillhandahåller standardinställningar för säkerhet en god nivå av ytterligare inloggningssäkerhet. Mer information finns i [Vad är standardinställningar för säkerhet?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Om prenumerationen är ny kan standardinställningar för säkerhet redan vara aktiverat för dig automatiskt.

Du aktiverar eller inaktiverar säkerhetsinställningar för Azure Active Directory (Azure AD) i Microsoft Azure-portalen från fönstret **Egenskaper**.

1. Logga in som global administratör på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).
2. I det vänstra navigeringsfältet väljer du **Visa alla** och under **Administratörscenter** väljer du **Azure Active Directory**.
3. I **Azure Active Directory administratörscenter** väljer du **Azure Active Directory** > **Egenskaper**.
4. Längst ner på sidan väljer du **Hantera standardinställningar för säkerhet**.
5. Välj **Ja** för att aktivera standardinställningar för säkerhet eller **Nej** för att inaktivera dem och välj sedan **Spara**.

När du har konfigurerat multifaktorautentisering för din organisation måste dina användare konfigurera tvåstegsverifiering på sina enheter. Mer information finns i [Konfigurera tvåstegsverifiering för Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

Fullständig information och fullständiga rekommendationer finns i [Konfigurera multifaktorautentisering för användare.](set-up-multi-factor-authentication.md)

## <a name="2-train-your-users"></a>2: Utbilda dina användare
<a name="train"> </a>

Nu finns en handbok om [cybersäkerhet från](https://go.microsoft.com/fwlink/p/?linkid=2015598) Harvard School som ger utmärkt vägledning om att etablera en stark säkerhetskultur inom organisationen, bland annat utbildningsanvändare för att identifiera nätfiskeattacker.

Förutom den här vägledningen rekommenderar Microsoft att dina användare gör som beskrivs i den här artikeln: Skydda ditt konto och dina enheter [från hackare och skadlig programvara.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Dessa åtgärder omfattar:

- Använda starka lösenord

- Skydda enheter

- Aktivera säkerhetsfunktioner på Windows 10 Mac-datorer

Microsoft rekommenderar även att användare skyddar sina personliga e-postkonton genom att vidta de åtgärder som rekommenderas i följande artiklar:

- [Skydda ditt Outlook.com-konto](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Skydda ditt Gmail-konto med tvåstegsverifiering](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: Använd dedikerade administratörskonton
<a name="admin"> </a>

De administratörskonton du använder för att administrera Microsoft 365-miljön inkluderar förhöjda behörigheter. Det här är värdefulla mål för hackare och cyberbrottsligheter. Använd endast administratörskonton för administration. Administratörer bör ha ett separat användarkonto för normal, icke-administrativ användning och bara använda sitt administratörskonto när det behövs för att slutföra en uppgift som är kopplad till jobbfunktionen. Ytterligare rekommendationer:

- Se till att administratörskonton också har ställts in för multifaktorautentisering.

- Stäng alla orelaterade webbläsarsessioner och appar, inklusive personliga e-postkonton, innan du använder administratörskonton.

- Se till att logga ut från webbläsarsessionen när du har slutfört administratörsuppgifter.

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: Höj skyddsnivån för skadlig programvara i e-post
<a name="malware"> </a>

Din Microsoft 365 innehåller skydd mot skadlig programvara, men du kan öka skyddet genom att blockera bifogade filer med filtyper som ofta används för skadlig programvara. Om du vill få bättre skydd mot skadlig programvara i e-post [kan du titta på en](../../business-video/anti-malware.md)kort utbildningsvideo eller följa de här stegen:

1. Gå till <https://protection.office.com> och logga in med autentiseringsuppgifterna för ditt administratörskonto.

2. Välj Policy Anti-Malware & i det vänstra navigeringsfönstret, under **Hothantering,** i säkerhets- och **efterlevnadscentret.** \> 

3. Dubbelklicka på standardprincipen om du vill redigera den här företagsövergripande principen.

4. Välj **Inställningar**.

5. Under **Vanliga typer av bifogade filer väljer** du **På**. De filtyper som är blockerade visas i fönstret direkt nedanför den här kontrollen. Du kan lägga till eller ta bort filtyper senare om det behövs.

6. Välj **Spara.**

Mer information finns i Skydd [mot skadlig programvara i EOP.](../../security/office-365-security/anti-malware-protection.md)

## <a name="5-protect-against-ransomware"></a>5: Skydda mot utpressningstrojaner
<a name="ransomware"> </a>

Utpressningstrojaner begränsar åtkomsten till data genom att kryptera filer eller låsa datorskärmar. Sedan försöker den utkbjälja pengar från en leverantör genom att begära "utpressningstrojan" i form av cryptocurrencies som Bitcoin, i utbyte mot åtkomst till data.

Du kan skydda mot utpressningstrojaner genom att skapa en eller flera e-postflödesregler för att blockera filnamnstillägg som ofta används för utpressningstrojaner, eller för att varna användare som får dessa bifogade filer i e-postmeddelanden. En bra utgångspunkt är att skapa två regler:

- Varna användare innan de Office bifogade filer som innehåller makron. Utpressningstrojaner kan vara dolda i makron, så vi varnar användarna för att inte öppna dessa filer från personer de inte känner.

- Blockera filtyper som kan innehålla utpressningstrojaner eller annan skadlig kod. Vi börjar med en gemensam lista över körbara filer (som anges i tabellen nedan). Om din organisation använder någon av de här körbara typerna och du förväntar dig att de ska skickas med e-post, lägger du till dem i föregående regel (varna användare).

Om du vill skapa en e-posttransportregel visar [du en kort utbildningsvideo](../../business-video/prevent-ransom-in-email.md)eller följer anvisningarna nedan:

1. Gå till [administrationscentret för Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Välj regler i kategorin E-postflöde.  

3. Välj **+** och sedan Skapa en ny **regel.**

4. Välj **** längst ned i dialogrutan om du vill se alla alternativ.

5. Använd inställningarna i följande tabell för varje regel. Låt resten av inställningarna vara som standard, såvida du inte vill ändra dessa.

6. Välj **Spara**.
    
| Inställning | Varna användare innan de öppnar bifogade filer Office filer | Blockera filtyper som kan innehålla utpressningstrojaner eller annan skadlig kod |
|:-----|:-----|:-----|
|Namn  <br/> |Regel för utpressningstrojaner: varna användare  <br/> |Regel för utpressningstrojaner: blockera filtyper  <br/> |
|Tillämpa den här regeln om . . .  <br/> |En bifogad fil . . . filtillägg matchar . . .  <br/> |En bifogad fil . . . filtillägg matchar . . .  <br/> |
|Ange ord eller fraser  <br/> |Lägg till följande filtyper:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |Lägg till följande filtyper:  <br/> ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> |
|Gör följande. . .  <br/> |Förbereda en ansvarsfriskrivning  <br/> |Blockera meddelandet . . . avvisa meddelandet och inkludera en förklaring  <br/> |
|Ange meddelandetext  <br/> |Öppna inte den här typen av filer – om du inte hade väntat dig dem – eftersom filerna kan innehålla skadlig kod och veta att avsändaren inte är en säkerhetsgaranti.  <br/> ||
   
> [!TIP]
> Du kan också lägga till de filer du vill blockera i listan mot skadlig programvara i [steg 4.](#4-raise-the-level-of-protection-against-malware-in-mail)

Mer information finns i:

- [Utpressningstrojaner: minska riskerna](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Återställa OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: Stoppa automatisk vidarebefordran av e-post
<a name="forwarding"> </a>

Hackare som får åtkomst till en användares postlåda kan föra ut e-post genom att konfigurera postlådan så att den automatiskt vidarebefordrar e-post. Det här kan inträffa även utan användarens uppmärksamhet. Du kan förhindra detta genom att konfigurera en e-postflödesregel.

Så här skapar du en regel för e-posttransport:

1. Gå till [administrationscentret för Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Välj regler i kategorin E-postflöde.  

3. Välj **+** och sedan Skapa en ny **regel.**

4. Välj **Fler alternativ** längst ned i dialogrutan om du vill se alla alternativ.

5. Använd inställningarna i följande tabell. Låt resten av inställningarna vara som standard, såvida du inte vill ändra dessa.

6. Välj **Spara**.

|Inställning|Avvisa e-postmeddelanden om att vidarebefordra automatiskt till externa domäner|
|---|---|
|Namn|Förhindra automatisk vidarebefordran av e-post till externa domäner|
|Tillämpa den här regeln om ...|Avsändaren . . . är extern/intern . . . Inom organisationen|
|Lägg till villkor|Mottagaren . . . är extern/intern . . . Utanför organisationen|
|Lägg till villkor|Meddelandeegenskaperna . . . ange meddelandetypen . . . Vidarebefordra automatiskt|
|Gör följande ...|Blockera meddelandet . . . avvisa meddelandet och ge en förklaring.|
|Ange meddelandetext|Automatisk vidarebefordran av e-post utanför organisationen förhindras av säkerhetsskäl.|

## <a name="7-use-office-message-encryption"></a>7: Använda Office meddelandekryptering
<a name="encryption"> </a>

Office Meddelandekryptering ingår i Microsoft 365. Den är redan konfigurerad. Med Office krypterade meddelanden kan din organisation skicka och ta emot krypterade e-postmeddelanden mellan personer inom och utanför organisationen. Meddelandekryptering i Office 365 fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster. Kryptering av e-postmeddelanden säkerställer att endast tilltänkta mottagare kan visa meddelandeinnehållet.

Office Meddelandekryptering ger två skyddsalternativ när du skickar e-post:

- Vidarebefordra inte

- Kryptera

Din organisation kan ha konfigurerat ytterligare alternativ som använder en etikett för e-post, till exempel Konfidentiellt.

### <a name="to-send-protected-email"></a>Skicka skyddade e-postmeddelanden

I Outlook för PC väljer du **Alternativ i** e-postmeddelandet och väljer sedan **Behörigheter**.

![Kryptering av e-postmeddelanden i Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

I Outlook.com väljer du Skydda i e-postmeddelandet.  Standardskyddet är **Vidarebefordra inte**. Om du vill ändra detta till att kryptera väljer **du Ändra behörighetskryptera** \> .

![Kryptering av e-postmeddelanden på Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>Ta emot krypterad e-post

Om mottagaren har Outlook 2013 eller Outlook 2016 och ett Microsoft-e-postkonto visas ett meddelande om objektets begränsade behörigheter i läsfönstret. När mottagaren har öppnat meddelandet kan det visas precis som andra meddelanden.

Om mottagaren använder en annan e-postklient eller ett annat e-postkonto, till exempel Gmail eller Yahoo, visas en länk som gör att mottagaren antingen kan logga in för att läsa e-postmeddelandet eller begära ett lösenord för att visa meddelandet i en webbläsare. Om användarna inte får e-postmeddelandet kan du be dem kontrollera mappen Skräppost.

Mer information finns i [Skicka, visa och svara på krypterade meddelanden i Outlook för PC.](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. Skydda din e-post från nätfiskeattacker
<a name="phishing"> </a>

Om du har konfigurerat en eller flera egna domäner i Microsoft 365-miljön kan du konfigurera riktad skydd mot nätfiske. Skydd mot nätfiske, en del av Microsoft Defender för Office 365, kan skydda organisationen från skadliga personifieringsbaserade nätfiskeattacker och andra nätfiskeattacker. Om du inte har konfigurerat en egen domän behöver du inte göra det.

Vi rekommenderar att du kommer igång med det här skyddet genom att skapa en princip för att skydda dina viktigaste användare och din anpassade domän.

![Skapa en princip mot nätfiske i Microsoft Defender för Office 365](../../media/security-and-compliance-center.png)

Om du vill skapa en policy mot nätfiske i Defender för Office 365 du en [kort utbildningsvideo](../../business-video/setup-anti-phishing.md)eller följer anvisningarna nedan:

1. Gå till <https://protection.office.com>.

2. I det vänstra & säkerhets- och efterlevnadscentret under Hothantering i det vänstra **navigeringsfönstret** väljer du **Princip.**

3. På sidan Princip väljer du **Skydd mot nätfiske.**

4. På sidan mot nätfiske väljer du **+ Skapa.** En guide startar stegen för att definiera din policy mot nätfiske.

5. Ange namn, beskrivning och inställningar för principen enligt rekommenderade inställningar i diagrammet nedan. Mer [information finns i Läs mer om nätfiskeprincip i Microsoft Defender Office 365 alternativ.](../../security/office-365-security/set-up-anti-phishing-policies.md)

6. När du har granskat inställningarna väljer du Skapa **den här principen** eller **Spara** efter behov.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Domän och mest värdefull kampanjpersonal|
|Beskrivning|Se till att den viktigaste personalen och vår domän inte utger sig för att vara.|
|Lägga till användare att skydda|Välj **+ Lägg till ett villkor, mottagaren är**. Skriv användarnamn eller ange e-postadressen till kandidaten, kampanjhanteraren och andra viktiga personalmedlemmar. Du kan lägga till upp till 20 interna och externa adresser som du vill skydda från personifiering.|
|Lägga till domäner att skydda|Välj **+ Lägg till ett villkor, mottagarens domän är**. Ange den anpassade domän som är kopplad till Microsoft 365-prenumerationen, om du har definierat en sådan. Du kan ange mer än en domän.|
|Välja åtgärder|Om e-post skickas av en imiterad användare: välj Omdirigera meddelande till en annan e-postadress och skriv sedan e-postadressen till säkerhetsadministratören. till exempel securityadmin@contoso.com. <br/> Om e-post skickas av en imiterad domän: välj **Sätt meddelande i karantän.**|
|Postlådeintelligens|Postlådeintelligens är valt som standard när du skapar en ny princip mot nätfiske. Lämna den här inställningen **På** för bästa resultat.|
|Lägga till betrodda avsändare och domäner|I det här exemplet ska du inte definiera några åsidosättningar.|
|Tillämpas på|Välj **Mottagarens domän är**. Under **Valfri av dessa** väljer du **Välj**. Välj **+ Lägg till.** Markera kryssrutan bredvid namnet på domänen, till exempel markera contoso.com, i listan och välj sedan Lägg **till**. Välj **Klar**.|
|

Mer information finns i [Konfigurera principer för skydd mot nätfiske i Defender för Office 365](../../security/office-365-security/configure-atp-anti-phishing-policies.md).

## <a name="9-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>9: Skydda mot skadliga bifogade filer och filer Valv bilagor
<a name="atp"> </a>

Personer skickar, tar emot och delar regelbundet bifogade filer, till exempel dokument, presentationer, kalkylblad med mera. Det är inte alltid lätt att avgöra om en bifogad fil är säker eller skadlig bara genom att titta på ett e-postmeddelande. Microsoft Defender för Office 365 innehåller Valv skydd för bifogade filer, men det här skyddet är inte aktiverat som standard. Vi rekommenderar att du skapar en ny regel för att börja använda det här skyddet. Skyddet omfattar filer i SharePoint, OneDrive och Microsoft Teams.

Om du vill Valv en princip för bifogade filer, [visar du en kort utbildningsvideo](../../business-video/safe-attachments.md)eller följer anvisningarna nedan:

1. Gå till <https://protection.office.com> och logga in med ditt administratörskonto.

2. I det vänstra & säkerhets- och efterlevnadscentret under Hothantering i det vänstra **navigeringsfönstret** väljer du **Princip.**

3. På sidan Princip väljer du Välj **Valv Bifogade filer**.

4. På sidan Valv bifogade filer tillämpar du det här skyddet brett genom att markera kryssrutan Aktivera ATP för **SharePoint, OneDrive** och Microsoft Teams.

5. Välj **+** för att skapa en ny princip.

6. Använd inställningarna i följande tabell.

7. När du har granskat inställningarna väljer du Skapa **den här principen** eller **Spara** efter behov.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Blockera aktuella och framtida e-postmeddelanden med upptäckt skadlig programvara.|
|Beskrivning|Blockera aktuella och framtida e-postmeddelanden och bifogade filer med identifierade skadlig programvara.|
|Spara bifogade filer – okänd skadlig kod|Välj **Blockera – blockera aktuella och framtida e-postmeddelanden och bifogade filer med upptäckt skadlig kod.**|
|Omdirigera bifogad fil vid identifiering|Aktivera omdirigering (markera den här rutan) <br/> Ange administratörskontot eller en postlådekonfiguration för karantän. <br/> Använd alternativet ovan om genomsökning efter bifogade filer på tider eller fel inträffar (markera den här rutan).|
|Tillämpas på|Mottagarens domän är . . . väljer du din domän.|
|

Mer information finns i [Konfigurera principer för skydd mot nätfiske i Defender för Office 365](../../security/office-365-security/configure-atp-anti-phishing-policies.md).

## <a name="10-protect-against-phishing-attacks-with-safe-links"></a>10: Skydda mot nätfiskeattacker med Valv länkar
<a name="phishingatp"> </a>

Hackare döljer ibland skadliga webbplatser i länkar i e-postmeddelanden och andra filer. Valv Länkar, som är en del av Microsoft Defender för Office 365, kan skydda organisationen genom att tillhandahålla snabb verifiering av webbadresser (URL:er) i e-postmeddelanden och Office dokument. Skydd definieras via Valv principer för länkar.

Vi rekommenderar att du gör följande:

- Ändra standardprincipen för att öka skyddet.

- Lägg till en ny princip som är riktad för alla mottagare i din domän.

Om du vill Valv du på Länkar kan du [titta på en kort utbildningsvideo](../../business-video/safe-links.md)eller utföra följande steg:

1. Gå till <https://protection.office.com> och logga in med ditt administratörskonto.

2. I det vänstra & säkerhets- och efterlevnadscentret under Hothantering i det vänstra **navigeringsfönstret** väljer du **Princip.**

3. På sidan Princip väljer du **Valv Länkar**.

Så här ändrar du standardprincipen:

1. På Valv, under **Principer som gäller för hela organisationen,** dubbelklickar du på **Standardprincip.**

2. Under **Inställningar som gäller** för innehåll i Office 365 anger du en URL som ska blockeras, till exempel _example.com_ och väljer **+** .

3. Under **Inställningar** som gäller för innehåll utom e-post markerar du **Office 365-program** **,** Spåra inte när användare klickar på säkra länkar och Låt inte användare klicka sig fram genom säkra länkar till den **ursprungliga URL:en.**

4. Välj **Spara**.

Så här skapar du en ny princip som är riktad till alla mottagare i din domän:

1. På sidan Valv, under Principer som gäller för **specifika mottagare, väljer** du för **+** att skapa en ny princip.

2. Använd inställningarna i följande tabell.

3. Välj **Spara**.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Valv länkar för alla mottagare i domänen|
|Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden|Välj **På – URL:er skrivs om och kontrolleras mot en lista med kända skadliga länkar när användaren klickar på länken.**|
|Använd URL-skanning i realtid för misstänkta länkar och länkar som pekar på filer|Markera den här rutan.|
|Tillämpas på|Mottagarens domän är . . . väljer du din domän.|
|

Mer information finns i artikeln [Valv i Microsoft Defender för Office 365](../../security/office-365-security/atp-safe-links.md).
