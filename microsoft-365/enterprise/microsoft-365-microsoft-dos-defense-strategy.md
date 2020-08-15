---
title: Microsoft 365-strategi för denial of service
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln hittar du en översikt över Microsofts försvars strategi för DoS-attacker (Denial-of-Service).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f28f7bcb9c6241404c8101bffe7268c5a1917ffa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694794"
---
# <a name="microsoft-365-denial-of-service-defense-strategy"></a>Microsoft 365-strategi för denial of service

Microsofts strategi för att försvara mot nätverksbaserade DOS-angrepp (Denial-of-Service) är unikt på grund av vår skala och globala storlek. Denna skala gör att Microsoft kan utnyttja strategier och teknik som får organisationer, leverantörer och kund organisationer att passa. Det viktigaste i DoS-strategin är vår globala närvaro. Microsoft handlar med Internet leverantörer, peering-leverantörer (offentliga och privata) och privata företag över hela världen. Detta ger Microsoft en viktig Internet närvaro och gör att Microsoft kan absorbera attacker via en större yta.

Med den här unika karaktären använder Microsoft identifierings-och begränsnings processer som skiljer sig från dem som används av stora företag. Strategin bygger på en separation av identifiering och global fördelad minskning genom många nätverks kanter. Många företag använder lösningar från tredje part för att upptäcka och minska angreppen i Edge. Eftersom Edge-kapaciteten för Microsoft har blivit klar är det att ta bort betydelsen av eventuella angrepp mot enskilda eller vissa kanter. På grund av denna unika konfiguration avgränsade Microsoft avvisande och mildrande komponenter. Microsoft distribuerar system med flera nivåer för att upptäcka attacker som är närmare deras mättnads punkter samtidigt som du behåller den globala minskningen i kanten. Den här strategin gör att vi kan hantera flera angrepp samtidigt.

Ett av de mest effektiva och billiga försvar som används av Microsoft mot DoS-attacker minskar tjänstens attacker. Oönskad trafik tas bort från nätverks kanten i stället för att analysera, bearbeta och skrubba data.

I gränssnittet med det offentliga nätverket använder Microsoft speciella säkerhetsenheter för brand vägg, NAT och IP-filtrering. Microsoft använder också global-routning med ECMP i hela världen. Global ECMP routing är ett ramverk för nätverk för att säkerställa att det finns flera globala sökvägar för att nå en tjänst. Med dessa flera sökvägar begränsas attacker mot tjänster till den region från vilken angreppet kommer. Andra regioner bör påverkas inte av det här angreppet, eftersom slutanvändarna skulle kunna använda andra sökvägar för att nå tjänsten i dessa regioner. Microsoft har också utvecklat interna DoS-jämförelse-och identifierings system som använder flödes data, prestanda värden och annan information. Det här är en storskalig moln tjänst i Microsoft Azure som analyserar data som samlats in från olika punkter i Microsoft-nätverk och-tjänster. En arbets belastnings svars grupp för incidenter identifierar roller och ansvars områden i grupper, villkor för eskaleringar och protokoll för att engagera olika team och för att hantera händelser. De här lösningarna skyddar mot DoS-attacker.

Dessutom är molnbaserade arbets belastning konfigurerade med optimerade tröskelvärden baserat på deras protokoll och bandbredds användning för att skydda belastningen.
