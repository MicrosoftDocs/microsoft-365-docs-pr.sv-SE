---
title: Skicka e-postaviseringar och visa principtips för DLP-principer
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Lär dig hur du lägger till ett principtips i en DLP-princip (Data Loss Prevention) för att informera användarna om att de arbetar med innehåll som står i konflikt med en DLP-princip.
ms.openlocfilehash: 53a4db6cfc37f35422a1efffaeac052370cd5988
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228657"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a>Skicka e-postaviseringar och visa principtips för DLP-principer

Du kan använda en DLP-princip (Data Loss Prevention) för att identifiera, övervaka och skydda känslig information Office 365. Du vill att alla organisationen som arbetar med den här känsliga informationen ska uppfylla reglerna som följer DLP-principerna, men du vill heller inte skapa blockeringar i onödan som gör att de inte får jobbet gjort. Det är här e-postaviseringar och principtips kan vara till hjälp.

![Meddelandefältet visar principtips i Excel 2016](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

Ett principtips är ett meddelande eller en varning som visas när någon arbetar med innehåll som står i konflikt med en DLP-princip – till exempel innehåll som en Excel-arbetsbok på en OneDrive för företag-webbplats som innehåller personligt identifierbar information och delas med en extern användare.

Du kan använda e-postaviseringar och policytips för att öka medvetenheten hos människor om organisationens principer. Du kan också ge användare möjlighet att åsidosätta principen, så att de inte blockeras om de har giltigt affärs behov eller om principen identifierar en felaktig positiv identifiering.

När du skapar en DLP-princip i efterlevnadscentret kan du konfigurera användarmeddelanden till följande:

- Skicka en e-postavisering till de personer som du väljer som beskriver problemet.
> [!NOTE]
> E-postmeddelanden skickas oskyddade.

- Visa ett principtips för innehåll som står i konflikt med DLP-principen:

  - För e-Outlook på webben och Outlook 2013 och senare visas principtipset högst upp i meddelandet ovanför mottagarna medan meddelandet består.

  - För dokument i OneDrive för företag-konto SharePoint onlinewebbplats visas principtipset med en varningsikon som visas för objektet. Om du vill visa mer information kan  du markera ett objekt och sedan välja ikonen för informationsfönstret i det övre högra hörnet på sidan för ![ att öppna ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) informationsfönstret.

  - För Excel-, PowerPoint- och Word-dokument som lagras på en OneDrive för företag-webbplats eller SharePoint Online-webbplats som ingår i DLP-principen visas principtipset i meddelandefältet och Backstage-vyn (Arkiv-menyn \> **Info).**

## <a name="add-user-notifications-to-a-dlp-policy"></a>Lägga till användarmeddelanden i en DLP-princip

När du skapar en DLP-princip kan du aktivera **användarmeddelanden.** När användarmeddelanden är aktiverade skickar Microsoft 365 både e-postaviseringar och principtips. Du kan anpassa vilka aviseringar som skickas till, e-posttexten och policytipstexten.

1. Gå till [https://protection.office.com](https://protection.office.com).

2. Logga in med ditt arbets- eller skolkonto. Nu är du i &amp; säkerhetsefterlevnadscentret.

3. I det vänstra &amp; \> navigeringscentret för \> **säkerhetsefterlevnad finns Policy för** \> **dataförlustskydd** + Skapa en \> **princip.**

    ![Knappen Skapa en princip](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)

4. Välj den DLP-principmall som skyddar de typer av känslig information som du behöver \> **.**

    Om du vill börja med en tom mall väljer **du Anpassad** \> **anpassad princip** – \> **Nästa.**

5. Namnge principen \> **Nästa.**

6. Välj platser som du vill att DLP-principen ska skydda genom att göra något av följande:

   - Välj **Alla platser i Office 365** \> **Nästa.**

   - Välj **Let me choose specific locations** \> **Next**.

   Om du vill inkludera eller exkludera en hel plats, till exempel all e Exchange post eller alla OneDrive-konton, ska du slå på eller stänga av **statusen** för den platsen.

   Om du bara vill SharePoint specifika webbplatser eller konton  OneDrive-konton, växlar du status till på och klickar sedan på länkarna **under** Inkludera för att välja specifika webbplatser eller konton.

7. Välj **Använd avancerade inställningar** \> **Nästa.**

8. Välj **+ Ny regel**.

9. I regelredigeraren, under **Användarmeddelanden,** slår du på statusen.

    ![Avsnittet Användarmeddelanden i regelredigeraren](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> DLP-principer gäller för alla dokument som matchar principen, oavsett om de är nya eller befintliga. Men en e-postavisering skapas bara när nytt innehåll matchar en befintlig DLP-princip. Befintligt innehåll är skyddat, men genererar inte ett användarmeddelande via e-post.

## <a name="options-for-configuring-email-notifications"></a>Alternativ för konfigurering av e-postaviseringar

För varje regel i en DLP-princip kan du:

- Skicka aviseringen till de personer du väljer. De här personerna kan inkludera ägaren av innehållet, den person som senast ändrade innehållet, ägaren av webbplatsen där innehållet lagras eller en viss användare.

- Anpassa texten som tas med i meddelandet med hjälp av HTML eller token. Mer information finns i avsnittet nedan.

> [!NOTE]
>  E-postaviseringar kan endast skickas till enskilda mottagare, inte till grupper eller distributionslistor. Endast nytt innehåll utlöser en e-postavisering. När du redigerar befintligt innehåll utlöses principtips, men inte ett e-postmeddelande.

![Alternativ för e-postaviseringar](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)

### <a name="default-email-notification"></a>Standardavisering om e-post

Aviseringar har en ämnesrad som börjar med den åtgärd som vidtas, till exempel "Meddelande", "Meddelande blockerat" för e-post eller "Åtkomst blockerad" för dokument. Om meddelandet handlar om ett dokument innehåller meddelandetexten en länk som tar dig till den webbplats där dokumentet lagras och öppnar principtipset för dokumentet, där du kan lösa eventuella problem (se avsnittet nedan om principtips). Om meddelandet handlar om ett meddelande innehåller meddelandet som en bifogad fil det meddelande som matchar en DLP-princip.

![Aviseringsmeddelande](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)

Som standard visar meddelanden text som liknar följande för ett objekt på en webbplats. Meddelandetexten konfigureras separat för varje regel, så texten som visas varierar beroende på vilken regel som matchas.

|**Om DLP-principregeln gör det här...**|**Standardmeddelandet för en SharePoint eller OneDrive för företag det här ...**|**Standardmeddelandet för meddelandena Outlook det här ...**|
|:-----|:-----|:-----|
|Skickar ett meddelande men tillåter inte åsidosättning  <br/> |Det här objektet står i konflikt med en princip i din organisation.  <br/> |Ditt e-postmeddelande står i konflikt med en princip i din organisation.  <br/> |
|Blockerar åtkomst, skickar ett meddelande och tillåter åsidosättning  <br/> |Det här objektet står i konflikt med en princip i din organisation. Om du inte löser konflikten kan åtkomsten till den här filen blockeras.  <br/> |Ditt e-postmeddelande står i konflikt med en princip i din organisation. Meddelandet levererades inte till alla mottagare.  <br/> |
|Blockerar åtkomst och skickar ett meddelande  <br/> |Det här objektet står i konflikt med en princip i din organisation. Åtkomst till det här objektet blockeras för alla utom ägaren, den senaste modifieringen och den primära administratören för webbplatssamlingen.  <br/> |Ditt e-postmeddelande står i konflikt med en princip i din organisation. Meddelandet levererades inte till alla mottagare.  <br/> |

### <a name="custom-email-notification"></a>Anpassad e-postavisering

Du kan skapa en anpassad e-postavisering i stället för att skicka standardaviseringen för e-post till slutanvändarna eller administratörerna. Det anpassade e-postmeddelandet har stöd för HTML och har en gräns på 5 000 tecken. Du kan använda HTML för att ta med bilder, formatering och annan profilering i meddelandet.

Du kan också använda följande tokens för att anpassa e-postaviseringen. Dessa tokens är variabler som ersätts med specifik information i meddelandet som skickas.

|**Token**|**Beskrivning**|
|:-----|:-----|
|%%AppliedActions%%  <br/> |Åtgärderna som tillämpas på innehållet.  <br/> |
|%%ContentURL%%  <br/> |URL-adressen till dokumentet på webbplatsen SharePoint online eller OneDrive för företag webbplatsen.  <br/> |
|%%MatchedConditions%%  <br/> |Villkoren som matchades av innehållet. Använd den här token för att informera personer om möjliga problem med innehållet.  <br/> |

![Meddelande som visar var tokens visas](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)

## <a name="options-for-configuring-policy-tips"></a>Alternativ för konfigurering av principtips

För varje regel i en DLP-princip kan du konfigurera principtips så att de:

- Informera bara personen om att innehållet står i konflikt med en DLP-princip, så att de kan vidta åtgärder för att lösa konflikten. Du kan använda standardtexten (se tabellerna nedan) eller ange anpassad text om organisationens specifika principer.

- Tillåt personen att åsidosätta DLP-principen. Om du vill kan du:

  - Kräv att personen anger en affärs justering för att åsidosätta principen. Den här informationen loggas och du kan visa den i DLP-rapporter i **avsnittet** Rapporter i &amp; Säkerhetsefterlevnad.

  - Tillåt att personen rapporterar en felaktig spärr och åsidosätter DLP-principen. Den här informationen loggas även för rapportering, så att du kan använda falska positiva resultat för att finjustera dina regler.

![Alternativ för principtips](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)

Du kan till exempel tillämpa en DLP-princip på OneDrive för företag webbplatser som identifierar personligt identifierbar information (PII), och denna princip har tre regler:

1. Första regeln: Om färre än fem instanser av den här känsliga informationen identifieras i ett dokument  och dokumentet delas med personer inom organisationen visas ett principtips i åtgärden Skicka ett meddelande. För principtips krävs inga åsidosättningsalternativ eftersom den här regeln bara informerar användarna och inte blockerar åtkomsten.

2. Andra regeln: Om fler än fem instanser av den här känsliga informationen identifieras i ett dokument  och dokumentet delas med personer inom organisationen  begränsar åtgärden Blockera åtkomst till innehåll filens behörigheter och med åtgärden Skicka ett meddelande kan andra åsidosätta åtgärderna i den här regeln genom att ange en affärsre justering. Ibland kräver organisationens företag att interna användare delar pii-data och du inte vill att DLP-principen ska blockera det här arbetet.

3. Tredje regeln: Om större än fem instanser av den här känsliga informationen identifieras i ett dokument  och dokumentet delas med personer utanför organisationen  begränsar åtgärden Blockera åtkomst till innehåll filens behörigheter och åtgärden Skicka ett meddelande tillåter inte att personer åsidosätter åtgärderna i den här regeln eftersom informationen delas externt. Under inga omständigheter ska personer i organisationen tillåtas att dela PII-data utanför organisationen.

Här är några bra saker att förstå om att använda ett principtips för att åsidosätta en regel:

- Alternativet att åsidosätta är per regel och det åsidosätter alla åtgärder i regeln (förutom att skicka ett meddelande, vilket inte kan åsidosättas).

- Innehållet kan matcha flera regler i en DLP-princip, men endast principtipset från den högst prioriterade regeln visas. Till exempel kommer ett principtips från en regel som blockerar åtkomst till innehåll att visas över ett principtips från en regel som helt enkelt skickar ett meddelande. Det gör att det inte går att se en störtlapp av principtips.

- Om principtipset i den mest restriktiva regeln tillåter att användare åsidosätter regeln åsidosätter den här regeln även eventuella andra regler som det matchade innehållet.

## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a>Principtips för OneDrive för företag webbplatser och SharePoint onlinewebbplatser

När ett dokument på en OneDrive för företag-webbplats eller SharePoint Online-webbplats matchar en regel i en DLP-princip och den regeln använder principtips, visar principtipsen särskilda ikoner i dokumentet:

1. Om regeln skickar ett meddelande om filen visas varningsikonen.

2. Om regeln blockerar åtkomsten till dokumentet visas den blockerade ikonen.

   ![Principtipsikoner för dokument i ett OneDrive konto](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)

Om du vill vidta åtgärder för ett dokument kan du markera ett objekt genom att välja ikonen för fönstret Informationsinformation i det övre högra hörnet på sidan för att öppna informationsfönstret \>  ![ Visa ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **principtips.**

Principtipset innehåller alla problem med innehållet och om principtipsen har konfigurerats med  de här alternativen  kan du välja Lös och sedan Åsidosätta principtipset eller Rapportera en felaktig positiv inställning. 

![Informationsfönstret med principtips](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)

![Principtips med alternativ för att åsidosätta](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)

DLP-principer synkroniseras med webbplatser och innehåll utvärderas mot dem med jämna mellanrum och asynkront, så det kan uppstå en kort fördröjning mellan det att du skapar DLP-principen och den tid då du börjar se principtips. Det kan uppstå en liknande fördröjning från när du löser eller åsidosätter ett principtips till när ikonen i dokumentet på webbplatsen försvinner.

### <a name="default-text-for-policy-tips-on-sites"></a>Standardtext för principtips på webbplatser

Som standard visar principtips text som liknar följande för ett objekt på en webbplats. Meddelandetexten konfigureras separat för varje regel, så texten som visas varierar beroende på vilken regel som matchas.

|**Om DLP-principregeln gör det här...**|**Då står det i standardprinciptipset här ...**|
|:-----|:-----|
|Skickar ett meddelande men tillåter inte åsidosättning  <br/> |Det här objektet står i konflikt med en princip i din organisation.  <br/> |
|Blockerar åtkomst, skickar ett meddelande och tillåter åsidosättning  <br/> |Det här objektet står i konflikt med en princip i din organisation. Om du inte löser konflikten kan åtkomsten till den här filen blockeras.  <br/> |
|Blockerar åtkomst och skickar ett meddelande  <br/> |Det här objektet står i konflikt med en princip i din organisation. Åtkomst till det här objektet blockeras för alla utom ägaren, den senaste modifieringen och den primära administratören för webbplatssamlingen.  <br/> |

### <a name="custom-text-for-policy-tips-on-sites"></a>Anpassad text för principtips på webbplatser

Du kan anpassa texten för principtips separat från e-postaviseringen. Till skillnad från anpassad text för e-postaviseringar (se avsnittet ovan) accepterar inte anpassad text för principtips HTML eller token. I stället är anpassad text för principtips oformaterad text endast med en begränsning på 256 tecken.

## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a>Principtips i Outlook på webben och Outlook 2013 och senare

När du skriver ett nytt e-postmeddelande i Outlook på webben och Outlook 2013 och senare visas ett principtips om du lägger till innehåll som matchar en regel i en DLP-princip och den regeln använder principtips. Principtipset visas högst upp i meddelandet, ovanför mottagarna, medan meddelandet består.

![Principtips högst upp i ett meddelande som består](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)

Principtips fungerar oavsett om känslig information visas i meddelandets brödtext, på ämnesraden eller i ett meddelande som visas här.

![Principtips som visar att en bifogad fil står i konflikt med en DLP-princip](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)

Om principtipsen har konfigurerats för att  tillåta åsidosättning kan du välja Visa åsidosättning av detaljer och ange en justering för ett företag eller rapportera \>  \> en felaktig \> **åsidosättning** av principen.

![Principtips i meddelandet expanderat för att visa alternativet Åsidosätt](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)

![Dialogruta med principtips där du kan åsidosätta principtipset](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)

Observera att när du lägger till känslig information i ett e-postmeddelande kan det uppstå fördröjningar mellan när känslig information läggs till och när principtipset visas.

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a>Outlook 2013 och senare har stöd för att visa principtips endast för vissa villkor

För närvarande stöds Outlook 2013 och senare med policytips endast för dessa villkor:

- Innehållet innehåller
- Innehåll delas

Observera att undantag anses vara villkor och att alla dessa villkor fungerar i Outlook, där de matchar innehåll och tillämpar skyddsåtgärder för innehåll. Men det finns ännu inte stöd för att visa principtips för användare.

### <a name="policy-tips-in-the-exchange-admin-center-vs-the-security-amp-compliance-center"></a>Principtips i Exchange administrationscenter och &amp; Säkerhetsefterlevnadscenter

Principtips kan antingen fungera med DLP-principer och e-postflödesregler som skapats i Exchange-administrationscentret eller med DLP-principer som skapats i Säkerhetsefterlevnadscenter, men inte &amp; båda. Det beror på att dessa principer lagras på olika platser, men principtips kan endast ritas från en enda plats.

Om du har konfigurerat principtips i administrationscentret för Exchange visas inte principtips som du konfigurerar i säkerhetsefterlevnadscentret för användare i Outlook på webben och Outlook 2013 eller senare förrän du inaktiverar tipsen i administrationscentret för &amp; Exchange. Det säkerställer att Exchange för e-postflödesregler (kallas även transportregler) fortsätter att fungera tills du väljer att växla över till &amp; Säkerhetsefterlevnadscenter.

Observera att även om principtips bara kan ritas från en enda plats skickas alltid e-postmeddelanden, även om du använder DLP-principer i både säkerhets- och Exchange &amp; administrationscenter.

### <a name="default-text-for-policy-tips-in-email"></a>Standardtext för principtips i e-post

Som standard visar principtips text som liknar följande för e-post.

|**Om DLP-principregeln gör det här...**|**Då står det i standardprinciptipset här ...**|
|:-----|:-----|
|Skickar ett meddelande men tillåter inte åsidosättning  <br/> |Din e-post står i konflikt med en princip i din organisation.  <br/> |
|Blockerar åtkomst, skickar ett meddelande och tillåter åsidosättning  <br/> |Din e-post står i konflikt med en princip i din organisation.  <br/> |
|Blockerar åtkomst och skickar ett meddelande  <br/> |Din e-post står i konflikt med en princip i din organisation.  <br/> |

## <a name="policy-tips-in-excel-powerpoint-and-word"></a>Principtips i Excel, PowerPoint och Word

När personer arbetar med känsligt innehåll i skrivbordsversionerna av Excel, PowerPoint och Word kan principtips informera dem i realtid om att innehållet står i konflikt med en DLP-princip. Detta kräver att:

- Dokumentet Office lagras på en webbplats OneDrive för företag eller på en SharePoint Online-webbplats.

- Webbplatsen ingår i en DLP-princip som är konfigurerad för att använda principtips.

Office synkroniserar automatiskt DLP-principerna direkt från Office 365 och skannar sedan dokumenten för att säkerställa att de inte står i konflikt med DLP-principerna och visa principtips i realtid.

> [!NOTE]
> Office genom dokument i programmen för att avgöra om tips för DLP-principen ska visas. De visar inte principtips som SharePoint onlinewebbplatser eller OneDrive för företag webbplatser redan har fastställt ska visas i en fil. Därför kanske du inte alltid ser ett tips för DLP-principen i skrivbordsapparna som visas på SharePoint Online-webbplatserna OneDrive för företag webbplatser. Däremot visar Office-programmen på webben endast DLP-principtips som SharePoint Online-webbplatser eller OneDrive för företag-webbplatser redan har fastställt bör visas.

Beroende på hur du konfigurerar principtipsen i DLP-principen kan andra välja att helt enkelt ignorera principtipset, åsidosätta principen med eller utan en affärsre justering eller rapportera en felaktig positiv.

Principtips visas i meddelandefältet.

![Meddelandefältet visar principtips i Excel 2016](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

Dessutom visas principtips i Backstage-vyn (på **fliken** Arkiv).

![Backstage visar principtips i Excel 2016](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)

Om principtipsen i DLP-principen är konfigurerade  med  de här alternativen kan du välja Lös om du vill åsidosätta ett principtips eller **Rapportera** en felaktig positiv inställning.

![Alternativ för principtips i Backstage-vyn i Excel 2016](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)

I alla Office datorprogram kan man välja att inaktivera principtips. Om de är inaktiverade visas inte principtips som är enkla meddelanden i meddelandefältet eller Backstage-vyn (på **fliken** Arkiv). Principtips om blockering och åsidosättning visas dock fortfarande, och de kommer fortfarande att få e-postaviseringen. När principtips inaktiveras undantas inte dokumentet från de DLP-principer som har tillämpats på det.

### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Standardtext för principtips i Excel 2016, PowerPoint 2016 och Word 2016

Som standard visar principtips text som liknar följande i meddelandefältet och Backstage-vyn i ett öppet dokument. Meddelandetexten konfigureras separat för varje regel, så texten som visas varierar beroende på vilken regel som matchas.

|**Om DLP-principregeln gör det här...**|**Då står det i standardprinciptipset här ...**|
|:-----|:-----|
|Skickar ett meddelande men tillåter inte åsidosättning  <br/> |Den här filen står i konflikt med en princip i din organisation. Gå till **Arkiv-menyn** för mer information.  <br/> |
|Blockerar åtkomst, skickar ett meddelande och tillåter åsidosättning  <br/> |Den här filen står i konflikt med en princip i din organisation. Om du inte löser konflikten kan åtkomsten till den här filen blockeras. Gå till **Arkiv-menyn** för mer information.  <br/> |
|Blockerar åtkomst och skickar ett meddelande  <br/> |Den här filen står i konflikt med en princip i din organisation. Om du inte löser konflikten kan åtkomsten till den här filen blockeras. Gå till **Arkiv-menyn** för mer information.  <br/> |

### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a>Anpassad text för principtips i Excel, PowerPoint och Word

Du kan anpassa texten för principtips separat från e-postaviseringen. Till skillnad från anpassad text för e-postaviseringar (se avsnittet ovan) accepterar inte anpassad text för principtips HTML eller token. I stället är anpassad text för principtips oformaterad text endast med en begränsning på 256 tecken.

## <a name="more-information"></a>Mer information

- [Mer information om skydd mot dataförlust](dlp-learn-about-dlp.md)
- [Skapa en DLP-princip från en mall](create-a-dlp-policy-from-a-template.md)
- [Villkor, undantag och åtgärder för DLP-princip (förhandsversion)](./dlp-microsoft-teams.md)
- [Skapa en DLP-princip för att skydda dokument med FCI eller andra egenskaper](protect-documents-that-have-fci-or-other-properties.md)
- [Det här innehåller DLP-principmallarna](what-the-dlp-policy-templates-include.md)
- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)