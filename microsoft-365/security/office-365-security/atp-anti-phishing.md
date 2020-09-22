---
title: ATP-funktioner för skydd mot nätfiske i Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig mer om nätfiske-funktioner som är en del av Office 365 Avancerat skydd för att skydda råvaru & Spear nätfiske-attacker.
ms.openlocfilehash: db1587d0cd60dc94e79b1498e000e63aa2a5ceac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199069"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>ATP-funktioner för skydd mot nätfiske i Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


ATP-nätfiske är en del av [Office 365 Avancerat skydd](office-365-atp.md). ATP-nätfiske tillämpar en uppsättning dator utbildnings modeller tillsammans med algoritmerna för identifiering av personifieringsnivå för inkommande meddelanden för att skydda råvaru-och Spear nät fiske attacker. Alla meddelanden är föremål för en omfattande uppsättning maskin utbildnings modeller utbildade för att upptäcka nät fiske meddelanden, tillsammans med en uppsättning avancerade algoritmer som används för att skydda mot olika användar-och domän användnings attacker. ATP-nätfiske skyddar din organisation utifrån de principer som anges av globala eller säkerhets administratörer för Office 365.
  
Mer information finns i [Konfigurera AntiPhishing-principer i Office 365](set-up-anti-phishing-policies.md).
  
> [!NOTE]
> ATP-nätfiske är bara tillgängligt i avancerat skydd, som ingår i prenumerationer, till exempel [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise, E5, Office 365 Education A5, etc. Om din organisation har en Office 365-prenumeration som inte innehåller Office 365 ATP kan du eventuellt köpa ATP som ett tillägg. Mer information finns i Office 365-prenumerationer [och priser för avancerade hot skydd](https://products.office.com/exchange/advance-threat-protection) samt [Office 365-beskrivningen för avancerat skydd för hotet](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="how-atp-anti-phishing-works"></a>Så här fungerar ATP-anti-nät fiske

ATP-nätfiske kontrollerar inkommande meddelanden för indikatorer som meddelandet kan vara nätfiske. När en användare täcks av en policy för ATP (säkra bilagor, säkra länkar eller anti-nätfiske) utvärderas det inkommande meddelandet av flera olika dator utbildnings modeller som analyserar meddelandet för att avgöra om policyn gäller för meddelandet och lämplig åtgärd vidtas baserat på den konfigurerade principen.
  
ATP-nätfiske gör att Office 365 global-administratörer och säkerhets administratörer kan definiera principer som skyddar mot nätfiske-attacker som inkluderar personifiering av användare och domäner. (eller båda). Office 365 globala administratörer eller säkerhets administratörer definierar inom den princip som användare och domäner ska skyddas från obehöriga attacker med antingen en fast lista över användare eller domäner eller med hjälp av post lådans intelligens. Post lådans intelligens är en avancerad förståelse för en användares e-postvanor och personliga kontakter. ATP lär dig hur enskilda användare kommunicerar med andra användare inom och utanför organisationen och skapar en karta över dessa relationer. Med den här kartan kan du ta reda på mer om hur du ser till att rätt meddelanden identifieras som personifiering.
  
ATP-nätfiske kan användas för en viss uppsättning personer eller grupper i din organisation, eller till en hel domän eller alla dina egna domäner. Mer information finns i [Konfigurera AntiPhishing-principer i Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>Skaffa ATP-nätfiske

ATP-nät fiske funktioner är en del av det [avancerade hotet](office-365-atp.md), ett ATP-skydd gäller emellertid när anti-nätfiske-principer är definierade. (Ett exempel är en personifieringsnivå-baserad princip.) Se [Konfigurera skydd mot nätfiske i Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Så här vet du om ATP-nätfiske är på plats

ATP-policy för anti-phishing måste definieras för att skydd ska fungera. Markera detta för att kontrol lera att skyddet fungerar.

Dessutom kan rapporter användas för att visa hur tjänsten fungerar för din organisation. Mer information finns i [Visa rapporter om Office 365 Avancerat skydd](view-reports-for-atp.md).

För att kunna använda utbildnings modeller för ATP-dator för att vara aktiva för en viss användare måste den användaren vara en del av en mängd [säkra bilagor](atp-safe-attachments.md), [ATP-säkra länkar](atp-safe-links.md)eller ATP-säkerhetspolicyn. 

I följande tabell beskrivs några exempel scenarier. I de här exemplen använder organisationen Office 365 Enterprise E5, som inkluderar Avancerat skydd för hotet.

****

|Exempel på scenario|Gäller ATP-nätfiske i detta fall?|
|---|---|
|Pat organisation har Office 365 Enterprise E5, men ingen har definierat några principer för Safet ATP-bilagor, ATP-säkra länkar eller ATP-avancerade nät fiske.|Nej. Även om funktionen är tillgänglig måste minst en ATP-princip definieras för att utbildnings modellerna för ATP ska fungera. För användning av en användning av ett ATP-Antivirus policy måste också vara på plats.|
|Aaron Lee är en anställd på försäljnings avdelningen på contoso. Aaron Lee organisation har en policy för ATP-skydd på plats som endast gäller för ekonomiska medarbetare.|Nej. I det här fallet gäller ATP-nätfiske (maskin modeller och personifieringstoken) för att finansiera anställda, men andra anställda, inklusive försäljnings avdelningen.|
|Igår kan en Office 365-administratör på jeans organisation skapa en ATP-Antivirus policy som gäller för alla anställda. Tidigare i dag fick Jean fått ett e-postmeddelande som innehåller en personifiering som omfattas av policyn.|Ja. I det här exemplet har Jean en licens för avancerat skydd och en Antivirus policy för ATP med Jean har definierats. Det tar vanligt vis ungefär 30 minuter innan en ny princip börjar gälla i data centers. eftersom en dag har gått i det här fallet ska policyn vara aktiv.|
|

## <a name="related-topics"></a>Relaterade ämnen

[Office 365 Avancerat skydd](office-365-atp.md)
  
[Skydd mot nätfiske i Office 365](anti-phishing-protection.md)
  
[Konfigurera skydd mot nätfiske i Office 365](set-up-anti-phishing-policies.md)
  
[Säkerhets Länkar för ATP i Office 365](atp-safe-links.md)
  
[Konfigurera principer för säkra säkerhets Länkar för ATP i Office 365](set-up-atp-safe-links-policies.md)
  
[Säkra bifogade ATP-filer i Office 365](atp-safe-attachments.md)
  
[Konfigurera principer för säkra bifogade brev via säkerhets meddelanden i Office 365](set-up-atp-safe-attachments-policies.md)
  
[Visa rapporterna för avancerat skydd](view-reports-for-atp.md)
