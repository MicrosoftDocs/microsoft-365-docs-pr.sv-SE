---
title: Steg 1. Triangel och analysera den första incidenten
description: Så här triangelr du och påbörjar analysen av din första incident i Microsoft 365 Defender.
keywords: incidenter, varningar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365, incidentsvar, cyberattack
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1890b4f9b4c71efebe833ebaee62debedbf0fb72
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52115026"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>Steg 1. Triangel och analysera den första incidenten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

När du ägnar lite tid åt att etablera, implementera och underhålla säkerhetsåtgärder enligt organisationens standarder, kan du konfigurera säkerhetslösningar som hjälper dig att snabbt identifiera säkerhetsrisker och hot. Microsoft 365 Med Defender kan du identifiera, kontrollera och undersöka incidenter med hjälp av ett fönster av glas där du kan hitta den information du behöver för att fatta snabba beslut. 

När ett säkerhetstillbud har upptäckts visar Microsoft 365 Defender information som du behöver prioritera eller prioritera en händelse framför andra. Efter att ha avbestämt prioritering kan analytiker sedan fokusera på att undersöka ärenden som tilldelats dem.

## <a name="detection-by-microsoft-365-defender"></a>Identifiering av Microsoft 365 Defender

Microsoft 365 Defender tar emot aviseringar och händelser från flera Microsoft-säkerhetsplattformar som identifieringskällor för att skapa en bild och kontext för skadlig aktivitet. Det här är de möjliga identifieringskällorna:

- [Microsoft Defender för Slutpunkt](../defender-endpoint/microsoft-defender-endpoint.md) är en identifiering och åtgärd på slutpunkt-lösning (Identifiering och åtgärd på slutpunkt) som använder Microsoft Defender antivirus samt molnaktiverad avancerad lösning med Microsofts Graph. Defender för Endpoint är en enhetlig plattform för förebyggande skydd, identifiering efter intrång, automatiserad undersökning och svar. It protects endpoints from cyberthreats, detects advanced attacks and data breaches, automates security incidents, and improves security upp. 
- [Microsoft Defender för](https://docs.microsoft.com/defender-for-identity/what-is) identitet är en molnbaserad säkerhetslösning som använder dina lokala AD DS-signaler (Active Directory Domain Services) för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga Insider-åtgärder riktade till organisationen. 
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) fungerar som en gatekeeper till företag med tillgång i realtid mellan dina företagsanvändare och de molnresurser de använder, var användarna än befinner sig och oavsett vilken enhet de använder. 
- [Microsoft Defender för Office 365](../office-365-security/overview.md) skyddar organisationen mot skadliga hot i e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. 
- [Azure Säkerhetscenter](https://docs.microsoft.com/azure/security-center/security-center-introduction) är ett enhetligt säkerhetshanteringssystem för infrastruktur som förstärker säkerheten på dina datacenter och som ger avancerat skydd i både hybridarbetsbelastningen och i molnet. 

I Microsoft 365 Defender [identifieras incidenter](incidents-overview.md) genom att korrelera aviseringar från de olika identifieringskällorna. I stället för att använda resurssträngar ihop eller urskilja flera aviseringar i sina respektive incidenter kan du börja med incidentkön i Microsoft 365 Defender direkt. På så sätt kan du hantera incidenter på ett effektivt sätt i alla slutpunkter, identiteter, e-post och program, och minska skadan från en attack.

## <a name="triage-your-incidents"></a>Se till att dina incidenter

Incidentsvar i Microsoft 365 Defender startar när du prioriterar listan över incidenter med hjälp av din organisations rekommenderade prioriteringsmetod. Att bestämma prioritet eller ange ärendets prioritetsnivå, som sedan avgör i vilken ordning de ska undersökas. 

Ett användbart exempel på guide för att avgöra vilken incident som ska prioriteras i Microsoft 365 Defender kan sammanfattas av formeln: *Allvarlighet + Påverkan = Prioritet*. 

- **Allvarlighetsgrad** är den nivå som Microsoft 365 Defender och dess integrerade säkerhetskomponenter. 
- **Påverkan** avgörs av organisationen och omfattar i allmänhet, men inte begränsat till, ett tröskelvärde för påverkade användare, enheter, tjänster som påverkas (eller en kombination av dessa) och även aviseringstyp. 

Analytiker initierar sedan undersökningar baserat **på de** prioritetskriterier som angetts av organisationen.

Prioriteringen av incidenter kan variera beroende på organisation. NIST rekommenderar även vad gäller incidentens funktions- och informationseffekter och återställningsmöjligheter.  

Det här är bara en metod för triage: 

1. Gå till sidan [med incidenter](incidents-overview.md) för att påbörja triangeln. Här kan du se en lista över incidenter som påverkar din organisation. Som standard ordnas de från det senaste till det äldsta incidenten. Härifrån kan du även se olika kolumner för varje incident med bland annat allvarlighetsgrad, kategori, antal aktiva aviseringar och berörda enheter. Du kan anpassa uppsättningen kolumner och sortera incidentkön efter några av kolumnerna genom att välja kolumnnamnet. Du kan också filtrera incidentkön efter dina behov. En fullständig lista över tillgängliga filter finns i [Prioritera incidenter.](incident-queue.md#available-filters)
  
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Exempel på incidentkön"::: 

    Ett exempel på hur du kan utföra tre åtgärder för den här uppsättningen ärenden är att prioritera incidenter som påverkade fler användare och enheter. I det här exemplet kan du prioritera incident-ID 6769 eftersom det påverkade det största antalet enheter: 7 enheter, 6 användare och 2 postlådor. Dessutom ser händelsen ut att innehålla aviseringar från Microsoft Defender för identitet som anger en identitetsbaserad avisering och möjliga autentiseringsstölder.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="Exempel på en incident med hög påverkan":::
 
2. Markera cirkeln bredvid namnet på incidenten om du vill granska informationen. Ett sidofönster visas till höger, som innehåller ytterligare information som kan hjälpa dig ytterligare. 
 
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="Exempel på sidofönster för incidenter"::: 

   Om du till exempel tittar på vilka [MITRE ATT&CK-taktiker](https://attack.mitre.org/) attackerarna använde baserat på incidentens kategorier, kan du prioritera incidenten eftersom attackeraren använde stulna autentiseringsuppgifter, etablerat kommando och kontroll, utfört rörelse och utsorterat vissa data. Det här föreslår att attacken redan har gått djupare in i nätverket och eventuellt stulen konfidentiell information.

   Om organisationen har implementerat ramverket Nollförtroende kan du överväga att prioritera åtkomst till autentiseringsuppgifter som ett viktigt säkerhetsfel.
 
   När du rullar nedåt i sidofönstret visas specifika berörda enheter, till exempel användare, enheter och postlådor. Du kan kontrollera exponeringsnivån för varje enhet och ägare till berörda postlådor.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="Exempel på information i sidofönstret för ett incidentfönster"::: 
 
3. Du hittar de associerade aviseringarna längre ned i sidofönstret. Microsoft 365 Defender har redan utfört korrelationen för sa varningar till en enda incident, vilket sparar tid och resurser bättre för att åtgärda attacken. Aviseringar är misstänkta och därmed eventuellt skadliga systemhändelser som föreslår en närvaro av en attacker i ett nätverk. 

   I det här exemplet har 87 enskilda aviseringar fastställt vara en del av ett säkerhetstillbud. Du kan visa alla aviseringar för att få en snabb bild av hur attacken utspelade sig.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Exempel på aviseringar i sidofönstret för incidenter"::: 
 
## <a name="analyze-your-first-incident"></a>Analysera den första incidenten

Det är lika viktigt att förstå sammanhangs omgivande aviseringar. Ofta är ett meddelande inte en enskild oberoende händelse. Det finns en kedja av processer som skapats, kommandon och åtgärder som kanske inte har inträffat samtidigt. Därför måste en analytiker leta efter den första och sista aktiviteterna i den misstänkta enhetens tidslinjer för att förstå sammanhanget för aviseringarna.

Det finns flera sätt att läsa och analysera data med hjälp av Microsoft 365 Defender, men målet för analytiker är att svara på incidenter så snabbt som möjligt. Även om Microsoft 365 Defender avsevärt kan minska medelvärdet för att åtgärda [(MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) genom den branschledande funktionen Autoreparation finns det alltid fall som kräver manuell analys. 

Här är ett exempel:

1. När prioriterad prioritet har fastställts påbörjar en analytiker en detaljerad analys genom att välja incidentnamnet. Den här sidan visar **Incidentsammanfattning** där data visas på flikar för att hjälpa dig med analysen. Under fliken **Aviseringar** visas typen av aviseringar. Analytiker kan klicka på varje avisering för att öka detaljgranskningen mot respektive identifieringskälla. 

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="Exempel på fliken Sammanfattning för ett incident"::: 
 
    En snabb guide om vilka domäner som varje identifieringskälla omfattar finns i [avsnittet Identifiera](#detection-by-microsoft-365-defender) i den här artikeln.

2.  Från fliken **Aviseringar** kan en analytiker pivotera till identifieringskällan för en mer detaljerad undersökning och analys. Om du till exempel väljer Identifiering av skadlig kod Microsoft Cloud App Security identifieringskällan kommer analytikern till motsvarande aviseringssida.
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="Exempel på val av avisering om en händelse"::: 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Exempel på en motsvarande sida i Microsoft Cloud App Security"::: 
  
3.  Om du vill undersöka exemplet ytterligare bläddrar du längst ned på sidan för att visa de användare **som påverkas.** Om du vill se aktiviteten och kontexten runt identifieringen av skadlig programvara väljer du An hills användarsida . 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="Exempel på en användarsida":::
  
4.  På användarsidan finns en kronologisk lista över händelser som börjar med en riskabel inloggning från en *IP-adressavisering för tor-nätverket.* Även om en aktivitet är misstänkt beror på hur en organisation bedriver sin verksamhet, kan i de flesta fall användningen av The Router (TOR), ett nätverk där användarna kan surfa på webben anonymt, ses som mycket osannolikt och onödigt i företagsmiljöer för vanliga onlineåtgärder.
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="Exempel på den kronologiska listan med händelser för en användare":::
  
5.  Varje avisering kan väljas för att få mer information om aktiviteten. Om du till exempel **väljer Aktivitet från en IP-adressavisering** för Tor kommer du till den aviseringens egen sida. An autentisera är administratör för Office 365, vilket innebär att hon har förhöjda behörigheter och att källhändelsen kan ha lett till åtkomst till konfidentiell information. 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Exempel på information om Microsoft Cloud App Security"::: 
 
6.  Genom att välja andra aviseringar kan en analytiker få en fullständig bild av attacken.

## <a name="next-step"></a>Nästa steg

[![Steg 2: Lär dig hur du åtgärdar incidenter](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)

Lär dig [hur du åtgärdar incidenter](first-incident-remediate.md).

## <a name="see-also"></a>Se även

- [Översikt över incidenter](incidents-overview.md)
- [Analysera incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
