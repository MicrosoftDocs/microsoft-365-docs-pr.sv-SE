---
title: Konfigurera Office 365 ATP-policyer för nätfiske
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 08/29/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
description: Skydd mot nätfiske, med omfattande skydd som en del av Office 365 Advanced Threat Protection och grundläggande skydd i Office 365 Exchange Online Protection, kan skydda din organisation från skadliga personifieringsbaserade nätfiskeattacker och andra nätfiskeattacker.
ms.openlocfilehash: cc9c8ec0aa819696f3c53cff690be40ae82009fb
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42806039"
---
# <a name="set-up-office-365-atp-anti-phishing-and-anti-phishing-policies"></a>Konfigurera Office 365 ATP-policyer för nätfiske och nätfiske

[ATP-skydd mot nätfiske](atp-anti-phishing.md), en del av [Office 365 Advanced Threat Protection](office-365-atp.md), kan skydda din organisation från skadliga personifieringsbaserade nätfiskeattacker och andra nätfiskeattacker. Om du är global office 365 Enterprise-global eller säkerhetsadministratör kan du konfigurera ATP-policyer för antinätsfiske.

Nätfiskeattacker finns i en mängd olika former från råvarubaserade attacker till riktade spjut phishing eller valfångst. Med den växande komplexiteten är det svårt för ens ett tränat öga att identifiera några av dessa sofistikerade attacker. Lyckligtvis kan Office 365 Advanced Threat Protection hjälpa. Du kan ställa in en ATP-policy för att se till att din organisation skyddas mot sådana attacker.

> [!NOTE]
> ATP-antinätfiske är endast tillgängligt i Advanced Threat Protection (ATP). ATP ingår i prenumerationer, till exempel [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. Om din organisation har en Office 365-prenumeration som inte inkluderar Office 365 ATP kan du eventuellt köpa ATP som ett tillägg. Mer information finns i [Office 365 Advanced Threat Protection-abonnemang och priser](https://products.office.com/exchange/advance-threat-protection) och beskrivningen av office [365 Advanced Threat Protection Service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Kontrollera att din organisation använder den senaste versionen av Office 365 ProPlus på Windows för att dra full nytta av ATP-skydd mot nätfiske.

En anti-phishing-princip är också tillgänglig för Office 365 Exchange Online Protection, med en begränsad uppsättning anti-förfalskningsskydd som är avsett att skydda mot autentiseringsbaserade och bedrägeribaserade attacker.

Vad du ska göra:

1. Granska förutsättningarna.

2. Läs mer om dina anti-phishing- och ATP-alternativ för anti-phishing.Learn about your anti-phishing and ATP anti-phishing policy options.

3. Konfigurera en policy mot nätfiske eller en ATP-policy för nätfiske.

> [!IMPORTANT]
> Mer information om hur flera tekniker tillämpas läser du [Vilken princip som gäller när flera skyddsmetoder och identifieringssökningar körs på din e-post](how-policies-and-protections-are-combined.md).

## <a name="review-the-prerequisites"></a>Granska förutsättningarna

- Om du vill definiera (eller redigera) ATP-principer måste du tilldelas en lämplig roll. Några exempel beskrivs i följande tabell:

  |Roll|Var/hur tilldelad|
  |---------|---------|
  |Global administratör för Office 365|Personen som registrerar sig för att köpa Office 365 är som standard en global administratör. (Se [Om Office 365-administratörsroller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) att lära sig mer.)|
  |Säkerhetsadministratör|Administrationscenter för[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory ( )|
  |Exchange Online Organisation Management|Administrationscenter[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)för Exchange ( ) <br>eller <br>  PowerShell-cmdlets (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

  Mer information om roller och behörigheter finns [i Behörigheter &amp; i Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Du kommer förmodligen att ställa in flera anti-phishing-principer för din organisation. Office 365 tillämpar dessa principer i den ordning de finns med på **sidan Anti-phishing** och **ATP-antinätfiske** i Säkerhetsefterlevnadscenter. &amp; När du har granskat dina [principalternativ](#learn-about-atp-anti-phishing-policy-options)tar du dig tid att bestämma hur många principer du behöver och prioriteten för varje.

- Planera att spendera ungefär 5-15 minuter för att konfigurera din första anti-phishing-policy.

- Ge upp till 30 minuter innan den nya eller uppdaterade principen sprids till alla Office 365-datacenter.

## <a name="set-up-an-anti-phishing-or-atp-anti-phishing-policy"></a>Konfigurera en anti-phishing- eller ATP-antinätspolicy

Varje organisation i Office 365 har en standardprincip mot nätfiske som gäller för alla användare. Du kan skapa flera anpassade policyer för nätfiske som du kan ändra omfattning för specifika användare, grupper eller domäner i organisationen. De anpassade principer som du skapar har företräde framför standardprincipen. Du lägger till, redigerar och tar bort policyer för &amp; nätfiske i Office 365 Security Compliance Center.

1. Gå [https://protection.office.com](https://protection.office.com) till och logga in med ditt arbets- eller skolkonto.

2. Välj **Princip**i det &amp; vänstra navigeringsfönstret i Office **Threat management**365 Security Compliance Center.

3. På sidan **Policy** väljer du **Anti-phishing** eller **ATP anti-phishing**.

4. Gör något av följande på sidan **Anti-phishing** eller **ATP mot nätfiske:**

   - Så här lägger du till en ny princip **välj + Skapa**.

   - Om du vill redigera en befintlig princip väljer du principnamnet i listan som visas på sidan **Anti-phishing.** (Alternativt kan du välja **Standardprincip** ovanför listan.) Välj **Redigera princip**på sidan som visas .

5. Ange namn, beskrivning och inställningar för principen. Mer information finns i Läs mer om alternativ för [atp-policyför bekämpning av nätfiske.](#learn-about-atp-anti-phishing-policy-options)

6. När du har granskat dina inställningar väljer du **Skapa den här principen** (eller **Spara**).

## <a name="learn-about-atp-anti-phishing-policy-options"></a>Läs mer om aku-policyalternativ för anti-phishing

När du konfigurerar eller redigerar dina ATP-policyer mot nätfiske kan du välja mellan flera alternativ som ger det mest sofistikerade och omfattande skyddet, enligt beskrivningen i följande tabell:

|**Den här inställningen**|**Gör detta**|**Använd när du vill:**|
|:-----|:-----|:-----|
|**Lägga till användare att skydda**|Definierar vilka e-postadresser som ska skyddas av principen. Du kan lägga till upp till 60 interna och externa adresser som du vill skydda mot personifiering.|När du vill vara säker på att e-post utanför organisationen inte är en personifiering av en av användarna i listan över användare som du skyddar. Exempel på användare som du kanske vill skydda är chefer på hög nivå, företagare, externa styrelseledamöter och så vidare.  <br/> Den här listan över skyddade användare skiljer sig från listan över personer som principen gäller för, eller snarare, för vilken principen tillämpas. Du definierar de gäller för listan i avsnittet **Tillämpad** på i principalternativen.  <br/> Om du till `Mary Smith <marys@contoso.com>` exempel lägger till som användare för att skydda använder du principen på gruppen "Alla användare". Detta skulle säkerställa att ett e-postmeddelande som verkade imitera "Mary Smith" skickas till en användare i "Alla användare" gruppen skulle ageras på av policyn.|
|**Lägga till domäner för att skydda**|Gör att du kan välja vilka domäner du vill skydda mot personifiering. Du kan ange att principen innehåller alla dina anpassade domäner, en kommaavgränsad lista över domäner eller en kombination av de två. Om du väljer **Inkludera domäner som jag äger automatiskt**och senare lägger till en domän i din Office 365-organisation, kommer den här anti-phishing-principen att finnas på plats för den nya domänen.|När du vill vara säker på att e-post utanför organisationen inte är en personifiering av en av de domäner som definierats i listan över verifierade domäner eller en partnerdomän.|
|**Välj åtgärder**|Välj den åtgärd som ska vidtas när Office 365 identifierar ett personifieringsförsök mot de användare och domäner som du har lagt till i principen. Du kan välja olika åtgärder för användare och domäner i samma anti-phishing-princip. Dessa åtgärder gäller för alla inkommande e-postmeddelanden som har identifierats av Office 365 som personifierar ett användarkonto eller en domän som är under skydd av denna anti-phishing-policy.  <br/> **Meddelande om karantän** E-post skickas till Office 365 karantän. När du väljer det här alternativet skickas inte e-postmeddelandet till den ursprungliga mottagaren.  <br/> **Omdirigera meddelande till en annan e-postadress** E-post skickas till den e-postadress du anger. Du kan ange flera e-postadresser. När du väljer det här alternativet skickas inte e-postmeddelandet till den ursprungliga mottagaren.  <br/> **Flytta meddelande till mottagarnas skräppostmapp** E-post skickas till mottagarnas skräppostmapp. När du väljer det här alternativet skickas e-postmeddelandet fortfarande till den ursprungliga mottagaren men placeras inte i mottagarens inkorg.  <br/> **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia** E-post levereras till den ursprungliga mottagaren. Dessutom läggs de användare som du identifierar till i raden hemlig kopia av meddelandet innan det levereras. När du väljer det här alternativet skickas e-postmeddelandet fortfarande till den ursprungliga mottagarens inkorg.  <br/> **Tillämpa inga åtgärder** E-post levereras till den ursprungliga mottagarens inkorg. Inga andra åtgärder kommer att vidtas i e-postmeddelandet.  <br/> **Aktivera tips om nätfiskeskydd** Aktiverar säkerhetstips mot nätfiske i e-post.|När du vill vidta en åtgärd för meddelanden som Office 365 har fastställt som en personifiering av en användare eller domän enligt definitionen i principen.|
|**Aktivera information om postlådan**|Aktiverar eller inaktiverar postlådeinformation för den här principen. Du kan bara aktivera postlådeinformation för molnbaserade konton, det vill säga konton vars postlåda finns helt i Office 365.| Den här funktionen använder maskininlärning för att fastställa en användares e-postmönster med sina kontakter. Med den här informationen kan AI bättre skilja mellan äkta och nätfiske.|
|**Aktivera postlådeinformationsbaserat personifieringsskydd**|Aktiverar eller inaktiverar postlådeinformation för personifieringsskydd för den här principen. Den viktiga aspekten här är kontrollen av personifieringen för en viss postlåda.|När du vill förbättra personifieringsresultat för användare baserat på varje användares individuella avsändarkarta. Med den här informationen kan Office 365 anpassa identifiering av personifiering och bättre hantera falska positiva. När användaren personifierar upptäcks, baserat på postlådeinformation, kan du definiera vilken åtgärd som ska vidtas på meddelandet.|
|**Lägga till betrodda avsändare och domäner**|Definierar e-postadresser och domäner som inte betraktas som personifiering av den här principen. Meddelanden från avsändarens e-postadresser och domäner som du lägger till som betrodda avsändare och domäner kommer aldrig att klassificeras som en personifieringsbaserad attack. Därför tillämpas inte åtgärderna och inställningarna i den här principen på meddelanden från dessa avsändare och domäner.  <br/><br/>Den maximala gränsen för dessa listor är cirka 1000 poster.|När användare interagerar med domäner eller användare som utlöser personifiering men anses vara säkra. Om en partner till exempel har samma/liknande visningsnamn eller domännamn som en användare som definierats i listan.|
|**Tillämpad på**|Definierar mottagare vars inkommande e-postmeddelanden omfattas av principens regler. Du kan skapa villkor och undantag för de mottagare som är associerade med principen.  <br/> Du kan till exempel skapa en global princip för din organisation genom att tillämpa regeln på alla mottagare i domänen.  <br/> Du kan också skapa undantagsregler, till exempel en regel som inte skannar e-postmeddelanden för en viss grupp mottagare.|Varje princip måste associeras med en uppsättning användare, till exempel användare i en viss grupp eller domän.|
|**Avancerade nätfisketströsklar**|Definierar inställningarnas nivå för hur nätfiskemeddelanden hanteras.  <br/> **Standard**: E-post som misstänks vara phish hanteras på vanligt sätt.  <br/> **Aggressiv**: Systemet hanterar e-post som misstänks vara phish med en hög grad av förtroende, på samma sätt som de som misstänks med en mycket hög grad av förtroende.  <br/> **Mer aggressiv**: Systemet hanterar e-post som misstänks vara phish med en medelhög eller hög grad av förtroende, på samma sätt som de som misstänks med en mycket hög grad av förtroende.  <br/> **Mest aggressiva**: Systemet hanterar e-postmeddelanden som misstänks vara phish med en låg, medelhög eller hög grad av förtroende, på samma sätt som de som misstänks med en mycket hög grad av förtroende.|När du vill vara mer aggressiv vid behandling av potentiellt phishing-meddelanden i Office 365. Till exempel kommer meddelanden med en mycket hög sannolikhet att vara phish har de mest aggressiva åtgärder som vidtas på dem medan meddelanden med låg sannolikhet har mindre aggressiva åtgärder som vidtagits på dem. Den här inställningen påverkar även andra delar av filtreringssystemet som kombinerar signaler. Detta betyder inte nödvändigtvis att olika åtgärder genomförs.  I huvudsak du ställa in sannolikheten för post är phish, för att bestämma (samma) utsedda åtgärder. Risken för att flytta bra meddelanden ökar när nivån på inställningarna ökar.|

## <a name="learn-about-anti-phishing-policy-options"></a>Läs mer om policyalternativ för anti-nätfiske

När du konfigurerar eller redigerar din anti-phishing kan du välja mellan flera alternativ, enligt beskrivningen i följande tabell:

|**Den här inställningen**|**Gör detta**|**Använd när du vill:**|
|:-----|:-----|:-----|
|**Tillämpad på**|Definierar mottagare vars inkommande e-postmeddelanden omfattas av principens regler. Du kan skapa villkor och undantag för de mottagare som är associerade med principen.  <br/> Du kan till exempel skapa en global princip för din organisation genom att tillämpa regeln på alla mottagare i domänen.  <br/> Du kan också skapa undantagsregler, till exempel en regel som inte skannar e-postmeddelanden för en viss grupp mottagare.|Varje princip måste associeras med en uppsättning användare, till exempel användare i en viss grupp eller domän.|
|**Välj åtgärder**|Välj den åtgärd som ska vidtas när Office 365 identifierar ett intra-org- eller externt-organisationsförfalskningsförsök mot användarna. Dessa åtgärder gäller för alla inkommande e-postmeddelanden som har identifierats av Office 365 som ett förfalskningsförsök för användare som är under skydd av denna anti-phishing-policy.  <br/> **Meddelande om karantän** E-post skickas till Office 365 karantän. När du väljer det här alternativet skickas inte e-postmeddelandet till den ursprungliga mottagaren.  <br/> **Flytta meddelande till mottagarnas skräppostmapp** E-post skickas till mottagarnas skräppostmapp. När du väljer det här alternativet skickas e-postmeddelandet fortfarande till den ursprungliga mottagaren men placeras inte i mottagarens inkorg.  <br/> **Tillämpa inga åtgärder** E-post levereras till den ursprungliga mottagarens inkorg. Inga andra åtgärder kommer att vidtas i e-postmeddelandet.|När du vill vidta en åtgärd för meddelanden som Office 365 har fastställt som ett förfalskningsförsök för interna eller externa domäner enligt definitionen i principen.|

När din organisation har konfigurerat policyer mot nätfiske eller ATP-policyer mot nätfiske kan du se hur tjänsten fungerar genom [att visa rapporter för avancerat hotskydd](view-reports-for-atp.md).

## <a name="example-anti-phishing-policy-to-protect-a-user-and-a-domain"></a>Exempel: Anti-phishing-policy för att skydda en användare och en domän

I det här exemplet anges en princip som heter "Domän och VD" som ger både användar- och `contoso.com`domänskydd mot personifiering och sedan tillämpar principen på alla e-postmeddelanden som tas emot av användare inom domänen . Säkerhetsadministratören har fastställt att principen måste uppfylla dessa affärskrav:

- Policyn måste ge skydd för vd:s e-postkonto och hela domänen.

- Meddelanden som bedöms vara personifieringsförsök mot vd:s användarkonto måste omdirigeras till säkerhetsadministratörens e-postadress.

- Meddelanden som är fast beslutna att vara personifieringsförsök mot domänen är mindre brådskande och bör sättas i karantän för senare granskning.

Säkerhetsadministratören på Contoso kan använda värden som följande för att skapa en anti-phishing-princip som uppfyller dessa behov.

|||
|:-----|:-----|
|**Inställning eller alternativ**|**Exempel**|
|Namn|Domän och VD|
|Beskrivning|Se till att VD och vår domän inte utger sig för att vara uttjänta.|
|Lägga till användare att skydda|Vd:s e-postadress på ett minimum.|
|Lägga till domäner för att skydda|Organisationsdomänen som inkluderar VD:s kontor.|
|Välj åtgärder|Om e-post skickas av en personifierat användare: Välj **Omdirigera meddelande till en annan e-postadress** och skriv sedan säkerhetsadministratörens e-postadress, till exempel `securityadmin@contoso.com`.  <br/> Om e-post skickas av en personifierat domän: Välj **Karantänmeddelande**.|
|Information om brevlådan|Som standard väljs postlådeinformation när du skapar en ny anti-phishing-princip. Lämna den här inställningen **På** för bästa resultat.|
|Lägga till betrodda avsändare och domäner|Definiera i det här exemplet inga åsidosättningar.|
|Tillämpad på|Välj **Mottagardomänen är**. Under **något av dessa**väljer du **Välj**. Välj **+ Lägg till**. Markera kryssrutan bredvid namnet på domänen, `contoso.com`till exempel i listan och välj sedan Lägg **till**. Välj **Klar**.|

## <a name="delete-an-anti-phishing-or-atp-anti-phishing-policy"></a>Ta bort en anti-phishing- eller ATP-anti-phishing-policy

Du kan ta bort anpassade principer &amp; som du har skapat med hjälp av Security Compliance Center. Du kan inte ta bort standardprincipen för din organisation. Vi rekommenderar att &amp; du använder Security Compliance Center för att granska eller redigera någon av dina ATP-principer.

1. Gå [https://protection.office.com](https://protection.office.com) till och logga in med ditt arbets- eller skolkonto.

2. Välj **Princip**i den vänstra navigeringen under **Hothantering**.

3. På sidan **Policy** väljer du **Anti-phishing** eller **ATP anti-phishing**.

4. Välj principnamnet i listan på sidan **Anti-phishing** eller **ATP-bekämpning av nätfiske.**

5. På sidan som visas väljer du **Ta bort princip**. Ge upp till 30 minuter innan ändringarna sprids till alla Office 365-datacenter.

## <a name="next-steps"></a>Nästa steg

När dina anti-phishing-policyer är på plats kan du se hur dina hotskyddsfunktioner fungerar för din organisation genom att visa rapporter. Mer information finns i följande resurser:

- [Visa rapporter för säkerhetsrapporter för Office 365 ATP](view-reports-for-atp.md) eller [Visa e-postsäkerhetsrapporter](view-email-security-reports.md)

- [Använda Threat Explorer (eller identifiering i realtid)](threat-explorer.md)

Håll koll på nya funktioner som kommer till ATP. besök [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) och lär dig mer om [nya funktioner som läggs till i ATP](office-365-atp.md#new-features-in-office-365-atp).
