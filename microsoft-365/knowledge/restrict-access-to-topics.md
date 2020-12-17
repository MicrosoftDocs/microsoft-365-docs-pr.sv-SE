---
title: Begränsa åtkomst till ämnen
description: Så här utesluter du ämnen som hindrar dem från att upptäckas.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699068"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a>Begränsa åtkomsten till ämnen i ämnen

I ämnes erfarenheter kanske intressenterna i organisationen vill se till att specifika ämnen inte identifieras och exponeras för dina licensierade användare. Du kan till exempel arbeta med ett projekt som du inte vill visa information om ännu. Office 365-behörigheter på webbplatser, filer och andra resurser gör att användarna inte kan visa känslig information i ämnen, men det finns ytterligare säkerhets åtgärder för att förhindra att vissa ämnen identifieras.

När kunskaps administratörer styr inställningar för kunskaps nätverk för att förhindra att ämnen upptäcks måste kunskaps cheferna och andra intressenter känna till hur det görs, så att de kan samar beta på detta.

> [!Important] 
> I den här artikeln beskrivs olika sätt att förhindra att ämnen identifieras via AI eller visas i din miljö som ytterligare säkerhetsfunktioner. Det är viktigt att tänka på att användare inte har tillstånd att visa något i ett ämne som de inte har behörighet att komma åt via Office 365-behörigheter. Även om en användare kan visa ett ämne kan dess filer, webbplatser och sidor som inte har Office 365-behörigheter att Visa inte visas för dem. Att se till att behörigheterna för känsliga filer är korrekta bör vara din primära säkerhets kontroll.

## <a name="prevent-topics-from-being-identified"></a>Förhindra att ämnen identifieras

Kunskaps administratören kan begränsa åtkomsten till specifika ämnen genom att hindra dem från att hittas vid inledande indexering. Det finns två sätt att göra detta i administratörs inställningarna för kunskaps nätverk i administrations centret för Microsoft 365.
 
- [Välj SharePoint-webbplatser som ska undantas från avsnitts identifiering](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): du kan använda den här inställningen för att förhindra att vissa SharePoint-webbplatser crawlas för avsnitt.
- [Utelämna ämnen efter namn](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): administratörer kan använda den här inställningen för att förhindra att vissa ämnen identifieras med namn. I kunskaps nätverkets administratörs inställningar kan en administratör överföra en lista med ämnen som ska uteslutas i en CSV-fil. Du kan utesluta ämnen med exakt eller delvis matchning av ett avsnitts namn.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Förhindra att ämnen visas av specifika användare

Kunskaps administratörer kan också [välja vem som kan visa ämnen i din organisation](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules). Med den här inställningen kan du välja vilka licensierade användare som ska kunna visa alla ämnen. I en pilot miljö kanske du till exempel vill tillåta att en liten grupp användare inte kan se ämnen.

## <a name="remove-topics-from-being-viewed"></a>Ta bort ämnen som visas

Kunskaps chefer kan välja att [ta bort ämnen](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) så att användare inte längre kan se dem. På sidan **hantera ämnen** i **ämnes Center** kan kunskaps ansvariga välja att avvisa vissa ämnen för att förhindra att de visas. Ämnen kan tas bort oavsett om de är i ett föreslaget eller bekräftat tillstånd.

Borttagna ämnen kan senare läggas tillbaka som visnings bara avsnitt om det behövs. 


## <a name="see-also"></a>Se även



  






