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
description: Lär dig mer om funktioner mot nätfiske som ingår i Det avancerade threat protection i Office 365 för att skydda & nätfiskeattacker.
ms.openlocfilehash: dda94145dfbef7466ebd8e1fb9f01d592515f598
ms.sourcegitcommit: 5e8901e7e571f20ede04f460bd3e7077dda004ca
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2020
ms.locfileid: "44875427"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>ATP-funktioner för skydd mot nätfiske i Office 365

ATP anti-phishing är en del av [Office 365 Advanced Threat Protection](office-365-atp.md). ATP-anti-phishing tillämpar en uppsättning maskininlärningsmodeller tillsammans med algoritmer för identifiering av personifiering på inkommande meddelanden för att skydda för råvaru- och spjutfiskeattacker. Alla meddelanden är föremål för en omfattande uppsättning maskininlärningsmodeller som tränas för att identifiera nätfiskemeddelanden, tillsammans med en uppsättning avancerade algoritmer som används för att skydda mot olika personifieringsattacker för användare och domäner. ATP-anti-phishing skyddar din organisation enligt den policy som anges av dina globala Office 365-administratörer eller säkerhetsadministratörer.
  
Mer information finns [i Konfigurera principer mot nätfiske i Office 365](set-up-anti-phishing-policies.md).
  
> [!NOTE]
> ATP-phishing är endast tillgängligt i Avancerat skydd mot hot, som ingår i prenumerationer, till exempel [Microsoft 365 Enterprise,](https://www.microsoft.com/microsoft-365/enterprise/home) [Microsoft 365 Business,](https://www.microsoft.com/microsoft-365/business)Office 365 Enterprise E5, Office 365 Education A5 osv. Om din organisation har en Office 365-prenumeration som inte innehåller Office 365 ATP kan du eventuellt köpa ATP som ett tillägg. Mer information finns i [Office 365 Advanced Threat Protection-abonnemang och priser](https://products.office.com/exchange/advance-threat-protection) och beskrivningen av Office [365 Advanced Threat Protection Service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="how-atp-anti-phishing-works"></a>Så här fungerar ATP anti-phishing

ATP:s anti-phishing-kontroller kontrollerar inkommande meddelanden efter indikatorer på att meddelandet kan vara nätfiske. När en användare omfattas av en ATP-princip (säkra bilagor, säkra länkar eller anti-phishing) utvärderas det inkommande meddelandet av flera maskininlärningsmodeller som analyserar meddelandet för att avgöra om principen gäller för meddelandet och lämpliga åtgärder vidtas, baserat på den konfigurerade principen.
  
ATP-phishing-phishing gör det möjligt för globala Office 365-administratörer eller säkerhetsadministratörer att definiera principer som skyddar mot nätfiskeattacker som inkluderar personifiering av användare eller domäner. (eller båda). Office 365 globala administratörer eller säkerhetsadministratörer definierar i principen vilka användare och domäner som ska skyddas från personifieringsattacker med hjälp av antingen en fast lista över användare eller domäner eller med hjälp av postlådeinformation. Brevlåda intelligens är en avancerad förståelse för en användares e-vanor och personliga kontakter. ATP lär sig hur varje enskild användare kommunicerar med andra användare inom och utanför organisationen och bygger upp en karta över dessa relationer. Med den här kartan kan ATP förstå mer information om hur du säkerställer att rätt meddelanden identifieras som personifiering.
  
ATP-anti-phishing-poliser kan tillämpas på en viss uppsättning personer eller grupper i din organisation, eller på en hel domän eller alla dina anpassade domäner. Mer information finns [i Konfigurera principer mot nätfiske i Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>Så här får du ATP anti-phishing

ATP Anti-Phishing-funktioner är en del av [Avancerat skydd mot hot;](office-365-atp.md) Atp-skydd mot nätfiske gäller dock när anti-phishing-policyer har definierats. (Ett exempel är en personifieringsbaserad princip.) Se [Konfigurera principer för nätfiske i Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Hur man vet om ATP anti-phishing är på plats

ATP:s principer för nätfiske måste definieras för att skyddet ska vara i kraft. Kontrollera detta först för att kontrollera att skyddet är på plats.

Dessutom finns rapporter tillgängliga för att visa hur tjänsten fungerar för din organisation. Mer information finns i [Visa rapporter för avancerat skydd mot office 365](view-reports-for-atp.md).

För att ATP-modeller för inlärning av nätfiske kan vara aktiva för en viss användare måste användaren vara en del av en definierad [ATP Safe-bilagor,](atp-safe-attachments.md) [ATP Safe Links](atp-safe-links.md)eller ATP Anti-Phishing-principen. 

I följande tabell beskrivs några exempelscenarier. I vart och ett av dessa exempel använder organisationen Office 365 Enterprise E5, som innehåller avancerat skydd mot hot.
  
|**Exempel scenario**|**Gäller ATP-anti-phishing i det här fallet?**|
|:-----|:-----|
|Pats organisation har Office 365 Enterprise E5, men ingen har definierat några principer för ATP-säkra bilagor, ATP-säkra länkar eller ATP-avancerad nätfiske ännu.|Nej. Även om funktionen är tillgänglig måste minst en ATP-princip definieras för att ATP-maskininlärningsmodellerna ska fungera. För personifiering måste en ATP-policy mot nätfiske också finnas på plats.|
|Lee är anställd på försäljningsavdelningen på Contoso. Lees organisation har en ATP anti-phishing-policy på plats som endast gäller ekonomianställda.|Nej. I det här fallet skulle ATP anti-phishing (maskinmodeller och personifieringsskydd) gälla för ekonomianställda, men andra anställda, inklusive försäljningsavdelningen, skulle inte göra det.|
|Igår, en Office 365 administratör på Jean organisation inrätta en ATP anti-phishing-policy som gäller för alla anställda. Tidigare idag fick Jean ett e-postmeddelande som innehåller en personifiering som omfattas av policyn.|Ja. I det här exemplet har Jean en licens för avancerat skydd mot hot och en ATP-anti-phishing-policy som inkluderar Jean har definierats. Det tar vanligtvis cirka 30 minuter innan en ny princip börjar gälla över datacenter. eftersom en dag har gått i detta fall bör politiken vara i kraft.|

## <a name="related-topics"></a>Relaterade ämnen

[Office 365 Avancerat skydd](office-365-atp.md)
  
[Skydd mot nätfiske i Office 365](anti-phishing-protection.md)
  
[Konfigurera principer mot nätfiske i Office 365](set-up-anti-phishing-policies.md)
  
[ATP-säkra länkar i Office 365](atp-safe-links.md)
  
[Konfigurera principer för BETRODDa länkar i Office 365](set-up-atp-safe-links-policies.md)
  
[ATP-säkra bilagor i Office 365](atp-safe-attachments.md)
  
[Konfigurera principer för BETRODDA bifogade filer i Office 365](set-up-atp-safe-attachments-policies.md)
  
[Visa rapporterna för avancerat hotskydd](view-reports-for-atp.md)
