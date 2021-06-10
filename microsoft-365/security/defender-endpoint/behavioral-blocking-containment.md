---
title: Beteendeblockering och inneslutning
description: Läs mer om funktioner för beteendeblockering och inneslutning i Microsoft Defender för Endpoint
keywords: Microsoft Defender för Slutpunkt, Identifiering och åtgärd på slutpunkt i blockeringsläge, blockering av passivt läge
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: a6271c1bd3714cfdffc606b7ada9b027e394216d
ms.sourcegitcommit: 2cf7293d610a676726ac891b89366e23810d9142
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52866733"
---
# <a name="behavioral-blocking-and-containment"></a>Beteendeblockering och inneslutning

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Översikt

Dagens hot landskap är över [](/windows/security/threat-protection/intelligence/fileless-threats) av fillös skadlig programvara och som lever utanför landet, mycket polymorfiska hot som muterar snabbare än traditionella lösningar kan hålla dig till och mänskliga drivna attacker som anpassar sig till vad adversaries hittar på komprometterade enheter. Traditionella säkerhetslösningar är inte tillräckliga för att stoppa sådana attacker. du behöver artificiell intelligens (AI) och enheter för utbildning (ML) säkerhetskopierade funktioner, till exempel beteendeblockering och inneslutning, som finns i [Defender för slutpunkt.](/windows/security) 

Funktioner för blockering och inneslutning kan hjälpa till att identifiera och stoppa hot baserat på deras beteende och processträd även när hoten har börjat användas. Nästa generations skydd, Identifiering och åtgärd på slutpunkt Defender för Slutpunktskomponenter och funktioner fungerar tillsammans för funktioner för beteendeblockering och inneslutning. 

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Beteendeblockering och inneslutning":::

Funktioner för blockering och inneslutning fungerar med flera komponenter och funktioner i Defender för Slutpunkt för att stoppa attacker omedelbart och förhindra att attacker fort görs.

- [Nästa generations skydd](microsoft-defender-antivirus-in-windows-10.md) (som inkluderar Microsoft Defender Antivirus) kan identifiera hot genom att analysera beteenden och stoppa hot som har börjat köras.

- [Identifiering och svar av slutpunkter](overview-endpoint-detection-response.md) (Identifiering och åtgärd på slutpunkt) får säkerhetssignaler i nätverket, enheterna och kernel-beteendet. När hot upptäcks skapas aviseringar. Flera aviseringar av samma typ sammanställs till incidenter, vilket gör det enklare för teamet med säkerhetsåtgärder att undersöka och svara.

- [Defender för Endpoint](overview-endpoint-detection-response.md) har ett brett utbud avropsoptisk över identiteter, e-post, data och appar, utöver de nätverks-, slutpunkts- och kernel-funktionssignaler som tas emot via Identifiering och åtgärd på slutpunkt. En komponent i [Microsoft 365 Defender](../defender/microsoft-365-defender.md), Defender för slutpunkt bearbetar och korrelerar dessa signaler, upphöjer identifieringsaviseringar och kopplar relaterade aviseringar i incidenter.

Med dessa funktioner kan fler hot förhindras eller blockeras, även om de börjar köras. När misstänkt beteende upptäcks finns risken kvar, aviseringar skapas och hot stoppas i deras spår. 

Följande bild visar ett exempel på en varning som utlöstes genom funktionella blockerings- och inneslutningsfunktioner:

:::image type="content" source="images/blocked-behav-alert.png" alt-text="Exempel på en avisering genom blockering och inneslutning av beteende":::

## <a name="components-of-behavioral-blocking-and-containment"></a>Komponenter i beteendeblockering och inneslutning

- **Regler för att minska attackytan på [klientsidan](attack-surface-reduction.md)** Fördefinierade vanliga attackbeteenden förhindras från att köras, enligt reglerna för minskning av attackytan. När sådana beteenden försöker köras kan de ses i Microsoft Defender Säkerhetscenter [https://securitycenter.windows.com](https://securitycenter.windows.com) som informationsaviseringar. (Regler för att minska attackytan är inte aktiverade som standard, du konfigurerar principerna i Microsoft Defender Säkerhetscenter.)

- **[Klientbeteendeblockering](client-behavioral-blocking.md)** Hot på slutpunkter upptäcks genom maskininlärning och blockeras och åtgärdas automatiskt. (Klientbeteendeblockering är aktiverat som standard.) 

- **[Blockering av feedbackslingor](feedback-loop-blocking.md)** (kallas även snabbt skydd) Hotidentifiering observeras via beteendeinformation. Hot stoppas och förhindras från att köras på andra slutpunkter. (Blockering av feedbackslingar är aktiverat som standard.) 

- **[Identifiering och svar av slutpunkt (Identifiering och åtgärd på slutpunkt) i blockeringsläge](edr-in-block-mode.md)** Skadliga artefakter eller beteenden som observerats genom skydd efter intrång blockeras och finns. Identifiering och åtgärd på slutpunkt i blockeringsläge fungerar även om Microsoft Defender Antivirus inte är den primära antiviruslösningen. (Identifiering och åtgärd på slutpunkt i blockläge är inte aktiverat som standard, du aktiverar det i Microsoft Defender Säkerhetscenter.) 

Räkna med att fler kommer in när det gäller beteendeblockering och inneslutning, eftersom Microsoft fortsätter att förbättra funktionerna för skydd mot hot. Om du vill se vad som är planerat och lanserat nu kan du besöka [Microsoft 365 översikt.](https://www.microsoft.com/microsoft-365/roadmap)

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>Exempel på beteendeblockering och inneslutning i praktiken

Funktioner för beteendeblockering och inneslutning har blockerat attackertekniker som följande:

- Credential-från LSASS
- Korsprocessinjicering
- Process ihålig
- Förbikoppling av användarkontokontroll
- Manipulera antivirus (till exempel inaktivera det eller lägga till den skadlig programvara som undantag)
- Kontakta kommando och kontroll (C&C) för att ladda ned nyttolaster
- Slantsingling
- Startpoständring
- Pass-the-hash-attacker
- Installation av rotcertifikat
- Användningsförsök för olika säkerhetsproblem

Nedan finns två verkliga exempel på beteendeblockering och inneslutning i praktiken.

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>Exempel 1: Autentiseringsstöldattack mot 100 organisationer

Så som beskrivs i Hot hot mot [elusiva hot: AI-drivna](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)beteendebaserade blockering stoppar attacker i sina spår , en autentiseringsstöldattack mot 100 organisationer runt om i världen har stoppats av funktionsblockering och inneslutningsfunktioner. E-postmeddelanden om försök till nätfiske som innehöll ett lure-dokument har skickats till de riktade organisationerna. Om en mottagare öppnade den bifogade filen kunde ett relaterat fjärrdokument köra kod på användarens enhet och läsa in malware från Malware för Malware, som har stulit autentiseringsuppgifter, lagrat stulna data och väntat på ytterligare instruktioner från en kommando- och kontrollserver. 

Behavior-based device learning models in Defender for Endpoint caught and stopped the attacker's techniques at two points in the attack chain:

- Det första skyddslagret upptäckte sårbarhetsbeteendet. Enhet med utbildning i molnet har identifierat hoten korrekt och omedelbart fått instruktioner om att klientenheten ska blockera attacken.
- Det andra skyddlagret, som hjälpte dig att stoppa fall där attacken kom förbi det första lagret, upptäckte process ihålig process, stoppade processen och tog bort motsvarande filer (till exempelLagraibot). 

När attacken upptäcktes och stoppades utlöstes varningar, till exempel en "initial åtkomstvarning" och visades i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ):

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Avisering om inledande åtkomst i Microsoft Defender Säkerhetscenter":::

Det här exemplet visar hur funktionsbaserade enhetsinlärningsmodeller i molnet lägger till nya skyddslager mot attacker, även efter att de har börjat köra.

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>Exempel 2: NTLM-relä – Variant för skadlig juicy-potatis

Enligt beskrivningen i det senaste blogginlägget upptäcktes blockering och inneslutning av [beteende:](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)Omvandlaoptisk information till skydd i januari 2020 upptäckte Defender för Endpoint en eskaleringsaktivitet för behörigheter på en enhet i en organisation. En avisering som anropades "Möjlig eskalering av behörighet med NTLM-relä" utlöstes.

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="NTLM-varning för skadlig juicy-potatis":::

Hot som visades vara skadlig kod. det var en ny variant som inte syns förut, av ett ökänt hackverktyg som kallas Juicy Potatis, som används av attackerare för att få eskalering av behörighet på en enhet. 

Minuter efter att aviseringen utlöstes analyserades filen och bekräftades vara skadlig. Processen har stoppats och blockerats, enligt följande bild:

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="Artefakt blockerad":::

Några minuter efter att artefakten blockerades blockerades flera instanser av samma fil på samma enhet, vilket hindrade ytterligare attacker eller annan skadlig programvara från att distribuera på enheten. 

Det här exemplet visar att hot identifieras, finns och blockeras automatiskt med funktioner för beteendeblockering och inneslutning. 

## <a name="next-steps"></a>Nästa steg

- [Läs mer om Defender för Slutpunkt](overview-endpoint-detection-response.md)

- [Konfigurera minskningsregler för attackytan](attack-surface-reduction.md)

- [Aktivera Identifiering och åtgärd på slutpunkt i blockeringsläge](edr-in-block-mode.md)

- [Se den senaste globala hotaktiviteten](https://www.microsoft.com/wdsi/threats)

- [Få en översikt över Microsoft 365 Defender](../defender/microsoft-365-defender.md)
