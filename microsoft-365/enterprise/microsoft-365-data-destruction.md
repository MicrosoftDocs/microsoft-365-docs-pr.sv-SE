---
title: Microsoft 365 data förstörelse
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: En översikt över Microsofts principer för åter användning, kasse ring och destruktion av Microsoft 365 Data Center-diskar och-servrar.
ms.openlocfilehash: bd5afd427f55952066bac06d2bd4e61f45a4562f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694526"
---
# <a name="microsoft-365-data-destruction"></a>Microsoft 365 data förstörelse

## <a name="physical-data-destruction"></a>Fysisk data förstörelse

Microsoft har policyer för data hantering som används för att återvinna och kassera disk enheter och servrar som inte fungerar eller tas ur bruk. Microsoft utför en fysisk sanerad process innan de använder alla Microsoft 365-diskenheter som är förenliga med nationella Central Institutet för standarder och teknik för speciella publikationer 800-88 ([NIST SP 800-88 för att Språkspråk](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)). Eftersom alla disk enheter i Microsoft 365 är krypterade med BitLocker Volume Encryption-kryptering är NIST SP 800-88-kompatibla radering inte tekniskt nödvändigt. Microsoft utför ändå den här processen.

Havererade diskar som används i Microsoft 365-Datadata är fysiskt förstörda och granskade genom ISO-processen. Till gångs typ bestämmer lämpliga kasse rings sätt. För hård diskar som inte kan rensas använder Microsoft en förstörelse-process för att förstöra mediet och göra att det inte går att återställa information. Till exempel är diskar fysiskt förstörda, pulverized eller förbrännings. Microsoft behåller alla poster i förstöringen och utför en liknande språk oberoende process på servrar som återanvänds i Microsoft 365. Dessa rikt linjer omfattar både elektronisk och fysisk språkspråkion.

Varje data Center använder en fysisk förstörelse-process för att avyttra sina diskar. Säkra lager platser för lagrings medier som är avsedda för disk kasse ring på varje område i data centret. Varje säker lager plats har övervakning av video övervakning. När en kasse rings plats når cirka 50%-kapacitet, kontaktar webbplats tjänst gruppen det fysiska säkerhets teamet för att koordinera borttagningen. Webbplats tjänstens personal och ett säkerhets kontor tar bort lagret för säker lagring och placerar det i ett angivet säkert förvarings område. Principer och förfaranden för hantering av data som bär ande enheter under bortskaffandet testas rutinmässigt, inklusive förfaranden för att säkerställa tillståndet hos maskiner som godkänts för destruktion.

I data förstörelse processen raderas diskar på ett sätt som är kompatibelt med NIST 800-88 (om möjligt) och sedan placeras i ett industriellt förstörelsei och fysiskt Demolished. Microsoft underhåller ansvar för till gångar som lämnar data centret med NIST SP 800-88 enhetlig rengöring/rensning, till exempel destruktion, kryptering, korrekt inventering, spårning och skydd av en kedja av vårdnad under transport. Den här processen övervakas via sluten TV och ett skrotnings intyg utfärdas vid slut.

Microsoft använder data rader från en [Extreme Protocol-lösning](https://www.enterprisedataerasure.com/) (EPS). EPS-program har stöd för NIST för SP 800-88 för rengöring och rensning/säker radering. Innan du rengör eller förstör skapas en inventering av Microsoft Asset Manager. Om en leverantör används för destruktion, ger leverantören ett skrotnings intyg för varje till gång som förstörts av Asset Manager.

## <a name="virtual-data-destruction"></a>Virtuell data förstörelse

Microsoft har policyer för data hantering och procedurer som kan användas för att skydda den virtuella förstöringen av data för att förhindra att data delas upp på lämpligt sätt mellan tjänst klienter eller blir tillgängliga när du är hård borttagning i tjänsten. Data som tas bort från tjänsten i en klient organisation är inte tillgängliga för en annan tjänst innehavare, även om någon av underliggande fysiska lagrings enheter tilldelas. Det här är ett resultat av de sammansatta effekterna av flera virtualiserings-och fragmenterings tekniker som används för att skala virtuella miljöer, de aktiva borttagnings funktionerna i program inom varje tjänst klient organisation (till exempel att [nollställa sidan](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)) och nödvändiga krypterings processer för medie-och program innehåll.