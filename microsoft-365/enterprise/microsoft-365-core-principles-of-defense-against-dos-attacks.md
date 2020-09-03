---
title: 'Microsoft 365 grundläggande principer för skydd mot dos: denial-of-service'
ms.author: robmazz
author: robmazz
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
description: Hur Microsoft utnyttjar de grundläggande principerna för absorption, identifiering och skydd mot DoS-attacker (Denial-of-Service).
ms.openlocfilehash: fb3446570dd8e99ccdb3005a6a7c90ca90a81aee
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331914"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>Grundläggande principer för skydd mot överbelastningsattacker

De tre grundläggande principerna när skydd mot nätbaserade DoS-attacker är absorption, identifiering och minskning. Absorption sker före identifiering och identifiering sker innan den begränsas. Absorption är det bästa försvaret mot en DoS-attack. Om det inte går att hitta angreppet kan det inte begränsas. Men om ännu den minsta DoS-attacken inte kan absorberas kommer inte tjänsterna att överleva tillräckligt länge för att angreppet ska kunna identifieras.

Det är inte ekonomiskt genomförbart för de flesta organisationer att köpa överskotts kapacitet till att absorbera DoS-attacker, eftersom detta kräver avsevärda investeringar i teknologi och tekniska färdigheter. Detta markerar en av säkerhets fördelarna med att använda Microsofts moln tjänster. Skir skala för Microsoft Services ger starkt nätverks skydd till moln kunder på ett kostnads effektivt sätt. Men till och med för stor skala måste det finnas en avvägning mellan absorption, identifiering och minskning. För att hitta saldot kan Microsoft utsätta tillväxt priser för att uppskatta hur många Microsoft behöver absorbera.

Identifiering är ett Cat-och-Mouse-spel. Du måste ständigt leta efter nya sätt som andra är attackerade och prova på att gå ur dina system. Identifiera-> minska-> identifiering-> minskas, etc., är ett permanent, beständigt tillstånd som fortsätter i oändlighet.

## <a name="defending-against-dos-attacks"></a>Försvara mot DoS-attacker

För att det ska kunna försvara sig mot en DoS-attack är det viktigt att upptäcka tidigt. Genom att upptäcka en attack innan systemet är på ett trångt sätt kan försvarare genomföra en svars plan.

Följande formel bidrar till att approximera tiden för en DoS-attack:

   **Maximal kapacitet (i byte/SEK)/tillväxt hastighet (i byte/SEK) = tid att påverka (i SEK)**

Om tids-till-identifiering sker efter en tids fördröjning är det troligt vis att DoS-attacken lyckas. Om tids-till-identifiering sker innan det är dags att påverka bör de attackerade tjänsterna vara online och tillgängliga om det finns begränsningar. Därför finns det bara två saker som kan utföras för att skydda mot DoS-attacker:

- Öka kapaciteten för att öka taket för maximal kapacitet (vilket i sin tur ger mer tid för att upptäcka ett angrepp); respektive
- Förkorta tiden för att upptäcka.

Ökad kapacitet har en direkt beskattnings effekt. Microsoft rekommenderar att kunderna utvecklar minst grundläggande absorptions kapacitet för att säkerställa att de kan klara av viss DoS-attack. Den faktiska absorptions kapaciteten varierar från kund till kund, eftersom varje kund har sina egna tröskelvärden för exponering, risk och ekonomisk outlay. Av ekonomiska skäl är det vanligt vis bara det mest kostnads effektiva försvars sättet att minska tiden mot identifieringen.
