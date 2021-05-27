---
title: Stack med stegvisa skydd mot hot i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: Följ sökvägen till ett inkommande meddelande via filtreringsstacken för hot i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e892ebe04887527cf57e4ea44f67c4aaa775b228
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683301"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a>Steg-för-steg skydd mot hot i Microsoft Defender för Office 365

Microsoft Defender för Office 365 skydd eller filtreringsstack kan delas upp i fyra faser, som i den här artikeln. Vanligtvis passerar inkommande e-post genom alla dessa faser före leverans, men den faktiska sökvägen som e-post tar omfattas av organisationens Defender för Office 365 konfiguration.

> [!TIP]
> Håll utkik efter en enhetlig bild  av alla fyra defenderfaserna i slutet av den här artikeln för att få Office 365 skydd!

## <a name="phase-1---edge-protection"></a>Fas 1 – Edge Protection

Tyvärr är Edge-block som en gång *var kritiska* nu relativt enkla för dåliga aktör att hantera. Med tiden blockeras mindre trafik här, men den är fortfarande en viktig del av högen.  

Edge-block är utformade för att vara automatiska. Om det är falskt positivt meddelas avs avsändarna och får veta hur de ska lösa problemet. Kopplingar från betrodda partner med begränsat rykte kan säkerställa att levererbarheten kan tillhandahållas, eller att tillfälliga åsidosättningar kan göras, vid registrering av nya slutpunkter.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="Fas 1 av filtrering i Defender för Office 365 är Edge Protection.":::

1. **Nätverksbegränsning skyddar** Office 365 infrastruktur och kunder från DOS-attacker (Denial of Service) genom att begränsa antalet meddelanden som kan skickas av en viss uppsättning infrastruktur.

2. **IP-rykte och -begränsning blockerar** meddelanden som skickas från kända dåliga ip-adresser. Om en specifik IP skickar många meddelanden under en kort tidsperiod kommer de att begränsas.

3. **Ryktet** blockerar alla meddelanden som skickas från en känd felaktig domän.

4. **Katalogbaserade gränsfiltreringsblock** försöker samla in organisationens kataloginformation via SMTP.

5. **Identifiering av bakåtcatter förhindrar** att en organisation ansar ogiltiga rapporter om utebliven leverans (NDR-rapporter).

6. **Förbättrad filtrering för kopplingar bevarar** autentiseringsinformation även när trafiken passerar genom en annan enhet innan den når Office 365. Detta förbättrar filtrering av staplar, inklusive heuristisk gruppering, skydd mot förfalskning och utbildningmodeller mot nätfiske, även i komplexa dirigeringsscenarier eller hybriddirigeringsscenarier.

## <a name="phase-2---sender-intelligence"></a>Fas 2 – Sender Intelligence

Funktioner i avsändarinformation är avgörande för att upptäcka skräppost, massutskick, personifiering och obehöriga förfalskningsmeddelanden och även för att göra identifiering av meddelanden. De flesta av dessa funktioner kan konfigureras individuellt.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="Fas 2 av filtrering i MDO är Sender Intelligence.":::

1. **Identifiering av konto** komprometteringar utlöses och aviseringar höjs när ett konto har avvikande beteende, konsekvent med intrång. I vissa fall blockeras användarkontot och hindras från att skicka ytterligare e-postmeddelanden tills problemet har lösts av en organisations säkerhetsgrupp.

2. **E-postautentisering** involverar både konfigurerade kundmetoder och metoder i molnet, i syfte att säkerställa att avsändare är behöriga och autentiserade e-postare. Dessa metoder mot förfalskning.
    - **SPF kan** avvisa e-post baserat på DNS TXT-poster som listar IP-adresser och servrar som tillåts skicka e-post för organisationens räkning.
    - **DKIM** tillhandahåller en krypterad signatur som autentiserar avsändaren.
    - **Med DMARC** kan administratörer markera SPF och DKIM som krävs i deras domän och tillämpa justering mellan resultaten för dessa två tekniker.
    - **ARC** är inte kundkonfigurerat, men bygger på DMARC för att fungera med vidarebefordran i distributionslistor, samtidigt som du spelar in en autentiseringskedja.

3. **Förfalskningsinformation** klarar av att filtrera de som är tillåtna för förfalskning (d.v.s. de som skickar e-post åt ett annat konto eller vidarebefordrar för en distributionslista) från skadliga avsändare som imiterar organisationsdomäner eller kända externa domäner. Den separerar legitima "åt" e-post från avsändare som förfalskning ger skräppost och nätfiskemeddelanden.

    **Förfalskningsinformation inom årsorganisationen** identifierar och blockerar förfalskningsförsök från en domän inom organisationen.

4. **Förfalskningsinformation över hela** domänen identifierar och blockerar förfalskningsförsök från en domän utanför organisationen.

5. **Med** massfiltrering kan administratörer konfigurera en BCL -nivå (Bulk Confidence Level) som anger om meddelandet skickades från en massavsändare. Administratörer kan använda skjutreglaget Massutskick i principen mot skräppost för att bestämma vilken nivå av massutskick som ska behandlas som skräppost.

6. **Postlådeintelligens** lär sig av vanliga användar-e-postbeteenden. Den använder en användares kommunikationsdiagram för att identifiera när en avsändare bara verkar vara någon som användaren normalt kommunicerar med, men faktiskt är skadlig. Den här metoden identifierar personifiering.

7. **Postlådeintelligens** aktiverar eller inaktiverar förbättrade personifieringsresultat baserat på varje användares enskilda avsändarmappning. När den här funktionen är aktiverad kan du identifiera personifiering.

8. **Med användarpersonifiering** kan en administratör skapa en lista med högvärdesmålen som sannolikt kommer att utge sig för att vara. Om ett e-postmeddelande kommer in där avsändaren bara verkar ha samma namn och adress som det skyddade högvärdeskontot markeras eller taggas e-postmeddelandet. (Till exempel *trα cye@contoso.com* för *tracye@contoso.com*).

9. **Domänpersonifiering identifierar** domäner som liknar mottagarens domän och som försöker se ut som en intern domän. Den här personifieringen kan till *tracye@liw α re.com* för *tracye@litware.com*.

## <a name="phase-3---content-filtering"></a>Fas 3 – Innehållsfiltrering

I den här fasen börjar filtreringsstacken att hantera det specifika innehållet i e-postmeddelandet, inklusive hyperlänkar och bifogade filer.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="Fas 3 av filtrering i MDO är innehållsfiltrering.":::

1. **Transportregler** (kallas även e-postflödesregler eller Exchange-transportregler) gör att en administratör kan vidta en mängd olika åtgärder när ett meddelande har en lika stor mängd villkor uppfylls. Alla meddelanden som flödar genom organisationen utvärderas mot aktiverade e-postflödesregler/transportregler.

2. **Microsoft Defender Antivirus** och två *antivirusmotorer från tredje part används för* att identifiera all känd skadlig programvara i bifogade filer.

3. Antivirusmotorerna (AV) används också för att skriva in  alla bifogade filer, så att blockering av Type kan blockera alla typer av bifogade filer som administratören anger.

4. När Microsoft Defender för Office 365 identifierar en skadlig bifogad fil läggs filens hashtagg och en hash-hash av aktivt innehåll till i Exchange Online Protection (EOP) rykte. **Blockering av ryktet** för bifogade filer blockerar filen i Office 365, och på slutpunkter, genom MSAV-molnsamtal.

5. **Med heuristisk gruppering** kan det fastställas att en fil är misstänkt baserat på leverans heuristisk. När en misstänkt bifogad fil hittas pausas hela kampanjen och filen begränsats. Om filen skulle vara skadlig blockeras hela kampanjen.

6. **Maskininlärningsmodeller** agerar på meddelandehuvud, brödtext och URL:er för att identifiera nätfiskeförsök.

7. Microsoft använder ett rykte från URL-begränsat läge (URL) samt URL-rykte från tredjepartsfeeds i url-ryktesblockering , för att blockera ett meddelande med en känd skadlig URL.

8. **Innehålls heuristics** kan identifiera misstänkta meddelanden utifrån struktur och ordfrekvens i meddelandets brödtext, med hjälp av maskininlärningsmodeller.

9. **Valv i** begränsat läge för bifogade filer för varje bifogad fil för Defender Office 365 kunder. Med dynamisk analys kan du identifiera hot som aldrig tidigare har upptäckts.

10. **Detonation för länkat** innehåll behandlar alla URL-länkar till en fil i ett e-postmeddelande som en bifogad fil, asynkront begränsat filen vid leverans.

11. **URL-detonation** inträffar när den överordnade nätfisketekniken upptäcker att ett meddelande eller en URL är misstänkt. URL-detonation i begränsat läge URL:er i meddelandet vid leverans.

## <a name="phase-4---post-delivery-protection"></a>Fas 4 – Skydd efter leverans

Det sista steget äger rum efter e-post- eller filleverans, och då gäller e-post som finns i olika postlådor och filer och länkar som visas i klienter som Microsoft Teams.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="Fas 4 av filtreringen i Defender Office 365 skydd efter leverans.":::

1. **Valv Links** är Defender Office 365 det tidsklickande skyddet. Alla URL:er i varje meddelande radbruts för att peka på Microsoft Valv Links-servrar. När man klickar på en URL kontrolleras den mot det senaste ryktet, innan användaren omdirigeras till målwebbplatsen. URL-adressen är asynkront begränsat för att uppdatera dess rykte.

2. **ZAP (Zero-Hour Auto-purge)** för nätfiske retroaktivt identifierar och neutralerar skadliga nätfiskemeddelanden som redan har Exchange Online postlådor.

3. **ZAP för skadlig programvara** identifierar och neutralerar retroaktivt skadliga meddelanden som redan har levererats till Exchange Online postlådor.

4. **ZAP för nätfiske** retroaktivt identifierar och neutraliserar skadliga skräppostmeddelanden som redan har levererats till Exchange Online postlådor.

5. **Kampanjvyer** gör det möjligt för administratörer att se en helhetsbild av en attack, snabbare och mer fullständigt, än vad ett team skulle kunna utan automation. Microsoft utnyttjar de stora mängder information om skydd mot nätfiske, skydd mot skräppost och skadlig programvara i hela tjänsten för att identifiera kampanjer och gör sedan det möjligt för administratörer att undersöka dem från början till slut, inklusive mål, effekter och flöden, som också finns tillgängliga i en nedladdningsbar kampanj.

6. **Med tilläggen Rapportmeddelande** kan användare enkelt rapportera falska positiva resultat (bra e-postmeddelande, felaktigt markerat som dåligt *)* eller falskt negativa (felaktigt e-postmeddelande markerat som *bra)* till Microsoft för vidare analys.

7. **Valv för Office-klienter** har samma Valv-skydd med klickning som inbyggt i Office-klienter som Word, PowerPoint och Excel.

8. **Skydd för OneDrive, SharePoint** och Teams har samma skydd för bifogade filer i Valv mot skadliga filer, inbyggt i OneDrive, SharePoint och Microsoft Teams.

9. När en URL-adress som pekar på en fil markeras efter leverans visar **detonationen** för länkat innehåll en varningssida tills begränsat läge för filen är klar och URL:en identifieras som säker.

## <a name="the-filtering-stack-diagram"></a>Filtreringsstackdiagrammet

Det slutliga diagrammet (som med alla delar av diagrammet som skriver det) kan komma att ändras allt eftersom *produkten växer och utvecklar.* Bokmärk den här sidan och använd **alternativet** för feedback som du hittar längst ned om du behöver fråga efter uppdateringar. För dina poster är det här högen med alla faser i ordning:

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="Alla faser av filtrering i MDO i ordningsföljd, 1 till 4.":::

## <a name="more-information"></a>Mer information

Behöver du konfigurera Microsoft Defender för Office 365 ***just nu** _? Använd den här _now*, [med detta steg för att](protect-against-threats.md) börja skydda din organisation.

*Särskilt tack från MSFTTracyP och docs-skrivteamet till Giulian Garruba för innehållet*.
