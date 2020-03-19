---
title: ATP-funktioner för anti-phishing i Office 365
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
description: ATP-antinätfiske är en del av Office 365 Advanced Threat Protection. ATP anti-phishing tillämpar en uppsättning maskininlärningsmodeller tillsammans med algoritmer för identifiering av personifiering på inkommande meddelanden för att ge skydd för nätfiskeattacker för råvaror och spjut. Alla meddelanden är föremål för en omfattande uppsättning maskininlärningsmodeller som är utbildade för att identifiera nätfiskemeddelanden, tillsammans med en uppsättning avancerade algoritmer som används för att skydda mot olika användar- och domänpersonifieringsattacker.
ms.openlocfilehash: eca12a1f75057aee94762a8a5eef0cceffe327d3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812595"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>ATP-funktioner för anti-phishing i Office 365

ATP-anti-phishing är en del av [Office 365 Advanced Threat Protection](office-365-atp.md). ATP anti-phishing tillämpar en uppsättning maskininlärningsmodeller tillsammans med algoritmer för identifiering av personifiering på inkommande meddelanden för att ge skydd för nätfiskeattacker för råvaror och spjut. Alla meddelanden är föremål för en omfattande uppsättning maskininlärningsmodeller som är utbildade för att identifiera nätfiskemeddelanden, tillsammans med en uppsättning avancerade algoritmer som används för att skydda mot olika användar- och domänpersonifieringsattacker. ATP-anti-phishing skyddar din organisation enligt polisen som har angetts av dina globala Office 365-administratörer eller säkerhetsadministratörer.
  
Mer information finns i [Konfigurera antinätfiskeprinciper i Office 365](set-up-anti-phishing-policies.md).
  
> [!NOTE]
> ATP-anti-phishing är endast tillgängligt i Avancerat hotskydd, som ingår i prenumerationer, till exempel [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. Om din organisation har en Office 365-prenumeration som inte inkluderar Office 365 ATP kan du eventuellt köpa ATP som ett tillägg. Mer information finns i [Office 365 Advanced Threat Protection-abonnemang och priser](https://products.office.com/exchange/advance-threat-protection) och beskrivningen av office [365 Advanced Threat Protection Service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="how-atp-anti-phishing-works"></a>Så här fungerar ATP-antinätfiske

ATP-anti-phishing kontrollerar inkommande meddelanden efter indikatorer som meddelandet kan vara nätfiske. När en användare omfattas av en ATP-princip (säkra bilagor, säkra länkar eller nätfiske) utvärderas det inkommande meddelandet av flera maskininlärningsmodeller som analyserar meddelandet för att avgöra om principen gäller för meddelandet och lämplig åtgärd är baserat på den konfigurerade principen.
  
ATP-anti-phishing gör det möjligt för Office 365 globala administratörer eller säkerhetsadministratörer att definiera principer som skyddar mot nätfiskeattacker som inkluderar personifiering av användare eller domäner. (eller båda). Office 365 globala administratörer eller säkerhetsadministratörer definierar i principen vilka användare och domäner som ska skyddas från personifieringsattacker med antingen en fast lista över användare eller domäner eller genom att använda postlådeinformation. Mailbox intelligens är en avancerad förståelse för en användares e-vanor och personliga kontakter. ATP lär sig hur varje enskild användare kommunicerar med andra användare inom och utanför organisationen och bygger upp en karta över dessa relationer. Den här kartan gör det möjligt för ATP att förstå mer information om hur du säkerställer att rätt meddelanden identifieras som personifiering.
  
ATP-antinätfiskepoliser kan tillämpas på en viss uppsättning personer eller grupper i organisationen, eller på en hel domän eller alla dina anpassade domäner. Mer information finns i [Konfigurera antinätfiskeprinciper i Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>Så här får du ATP-anti-phishing

ATP-antinätfiskefunktioner är en del av [avancerat hotskydd.](office-365-atp.md) ATP-skydd mot nätfiske gäller dock när policyer för nätfiske definieras. (Ett exempel är en personifieringsbaserad princip.) Se [Konfigurera antinätfiskeprinciper i Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Så här vet du om ATP-antinätfiske är på plats

ATP-policyer mot nätfiske måste definieras för att skyddet ska kunna gälla. Kontrollera att skyddet är på plats först.

Dessutom finns rapporter tillgängliga för att visa hur tjänsten fungerar för din organisation. Mer information finns i [Visa rapporter för Office 365 Advanced Threat Protection](view-reports-for-atp.md).

För att ATP-modeller för anti-phishing-maskininlärning ska vara aktiva för en viss användare måste användaren vara en del av en definierad [ATP-säkra bilagor,](atp-safe-attachments.md) [ATP-säkra länkar](atp-safe-links.md)eller ATP-policy för nätfiske. 

I följande tabell beskrivs några exempelscenarier. I vart och ett av dessa exempel använder organisationen Office 365 Enterprise E5, som innehåller avancerat hotskydd.
  
|**Exempel på scenario**|**Gäller ATP-antinätfiske i det här fallet?**|
|:-----|:-----|
|Pats organisation har Office 365 Enterprise E5, men ingen har definierat några principer för ATP-säkra bilagor, ATP-säkra länkar eller ATP-avancerad nätfiske ännu.|Nej. Även om funktionen är tillgänglig måste minst en ATP-princip definieras för att ATP-maskininlärningsmodellerna ska fungera. För personifiering måste en ATP-anti-phishing-policy också finnas på plats.|
|Lee är anställd på försäljningsavdelningen på Contoso. Lees organisation har en ATP-policy för nätfiske som endast gäller för att finansiera anställda.|Nej. I det här fallet skulle ATP-anti-phishing (maskinmodeller och personifieringsskydd) gälla för ekonomianställda, men andra anställda, inklusive försäljningsavdelningen, skulle inte göra det.|
|Igår inrättade en Office 365-administratör på Jean organisation en ATP-policy för anti-phishing som gäller för alla anställda. Tidigare idag fick Jean ett e-postmeddelande som innehåller en personifiering som omfattas av policyn.|Ja. I det här exemplet har Jean en licens för avancerat hotskydd och en ATP-anti-phishing-princip som innehåller Jean har definierats. Det tar vanligtvis ungefär 30 minuter innan en ny princip börjar gälla mellan datacenter. eftersom det har gått en dag i detta fall bör politiken gälla.|

## <a name="related-topics"></a>Relaterade ämnen

[Office 365 Avancerat hotskydd](office-365-atp.md)
  
[Skydd mot nätfiske i Office 365](anti-phishing-protection.md)
  
[Konfigurera antinätfiskeprinciper i Office 365](set-up-anti-phishing-policies.md)
  
[ATP-säkra länkar i Office 365](atp-safe-links.md)
  
[Konfigurera eKU-principer för säkra länkar i Office 365](set-up-atp-safe-links-policies.md)
  
[ATP-säkra bilagor i Office 365](atp-safe-attachments.md)
  
[Konfigurera principer för BETRODDa BIFOGADE FILER i ATP i Office 365](set-up-atp-safe-attachments-policies.md)
  
[Visa rapporterna för avancerat hotskydd](view-reports-for-atp.md)
