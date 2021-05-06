---
title: E-posttrådning i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: När du genomför en Advanced eDiscovery e-posttrådning parsas en e-postkonversation och varje meddelande avgränsas i olika kategorier.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161619"
---
# <a name="email-threading-in-advanced-ediscovery"></a>E-posttrådning i Advanced eDiscovery

Tänk dig en e-postkonversation som har på gång ett tag. I de flesta fall innehåller det sista e-postmeddelandet i tråden innehållet i alla tidigare e-postmeddelanden. Om du granskar det senaste e-postmeddelandet får du en fullständig kontext av den konversation som inträffat i tråden. E-posttråd identifierar sådana e-postmeddelanden så att granskare kan granska en del av insamlade dokument utan att förlora något sammanhang.

## <a name="what-does-email-threading-do"></a>Vad innebär e-posttrådning?

E-posttrådning parsar varje e-postmeddelande och dekonfigurerar det till enskilda meddelanden. varje e-postmeddelande är en kedja av enskilda meddelanden. Därefter analyseras alla e-postmeddelanden i granskningsuppsättningen för att avgöra om ett e-postmeddelande har unikt innehåll eller om kedjan finns i ett annat e-postmeddelande. I slutet är e-postmeddelanden indelade i fyra kategorier:

- **Inkluderande**: det sista meddelandet i e-postmeddelandet har unikt innehåll, och e-postmeddelandet har alla bifogade filer som inkluderades i andra e-postmeddelanden där innehållet ingår i det här e-postmeddelandet.

- **Inklusive minus**: det sista meddelandet i e-postmeddelandet har unikt innehåll, men e-postmeddelandet innehåller inte några av de bifogade filer som inkluderades i andra e-postmeddelanden som innehållet ingår i det här e-postmeddelandet.

- **Inkluderande kopia**: en exakt kopia av en inkluderande/inkluderande e-post

- **Inget:** Innehållet i det här e-postmeddelandet ingår i minst ett e-postmeddelande som markeras som inkluderande/inkluderande minus.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>Hur skiljer sig den från konversationer i Outlook?

Det här låter ungefär som konversationsgruppingarna i Outlook. Det finns dock vissa viktiga skillnader. Tänk dig en e-postkonversation som är indelade i två konversationer. Någon har till exempel svarat på ett e-postmeddelande som inte är det senaste i konversationen, så de två senaste e-postmeddelandena i konversationen har båda unikt innehåll.

Outlook kunde ändå gruppera e-postmeddelandena i en enda konversation. Att bara läsa det senaste e-postmeddelandet skulle innebära att kontexten för det andra till sista e-postmeddelandet, som också innehåller unikt innehåll, saknas. Eftersom e-posttråd parsar ut varje e-postmeddelande i enskilda komponenter och jämför dem, markerar e-posttrådning både i de två sista e-postmeddelandena som inkluderande, så att du inte missar något sammanhang så länge du läser alla e-postmeddelanden som markerats som inkluderande.
