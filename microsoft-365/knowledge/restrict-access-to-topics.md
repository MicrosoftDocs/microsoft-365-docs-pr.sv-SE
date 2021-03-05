---
title: Begränsa åtkomst till ämnen i Microsoft Viva-ämnen
description: Hur du utesluter ämnen för att förhindra att de upptäcks.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: b8c49c96ace14ac1ba03411b5670d8e77268109a
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453915"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Begränsa åtkomst till ämnen i Microsoft Viva-ämnen

I Microsoft Viva kan intressenter i organisationen vilja se till att specifika ämnen inte upptäcks och exponeras för dina licensierade användare. Du kanske arbetar på ett projekt som du inte vill visa information om ännu. Office 365-behörigheter på webbplatser, filer och andra resurser hindrar användare av ämneserfarenheter från att visa känslig information i ämnen, men det finns ytterligare säkerhetsåtgärder för att förhindra att särskilda ämnen upptäcks.

Medan kunskapsadministratörer styr nätverksinställningarna för kunskap för att förhindra att ämnen upptäcks, behöver kunskapshanterare och andra intressenter få veta hur det görs så att de kan samarbeta.

> [!Important] 
> I den här artikeln beskrivs olika sätt att förhindra att ämnen identifieras genom AI eller visas i din miljö som ett ytterligare säkerhetsskydd. Det är viktigt att observera att användare i Viva Topics inte har behörighet att visa något i ett ämne som de inte har åtkomst till via Office 365-behörigheter. Även om en användare kan visa ett ämne kommer dess filer, webbplatser och sidor som de inte har Office 365-behörighet att visa inte att visas för dem. Att se till att behörigheter för känsliga filer ställs in korrekt bör vara det primära säkerhetsåtgärden.

## <a name="prevent-topics-from-being-identified"></a>Förhindra att ämnen identifieras

Knowledge admin can restrict access to specific topics by preventing them from found in initial indexing. Det finns två sätt att utföra den här uppgiften i administrationsinställningarna för Knowledge Network i administrationscentret för Microsoft 365.
 
- [Välj SharePoint-webbplatser som ska undantas](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)från ämnesidentifiering: Du kan använda den här inställningen för att förhindra att vissa SharePoint-webbplatser crawlas för ämnen.
- [Undanta avsnitt efter namn:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)Administratörer kan använda den här inställningen för att förhindra att vissa ämnen upptäcks med namn. I administratörsinställningarna för Knowledge Network kan en administratör ladda upp en lista med ämnen som ska undantas i en CSV-fil. Du kan utesluta avsnitt som innehåller exakta eller partiella träffar i ett ämnesnamn.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Förhindra att avsnitt visas för specifika användare

Kunskapsadministratörer kan också [välja vilka som kan visa ämnen i organisationen.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules) Med den här inställningen kan du välja vilka licensierade användare som kan visa alla ämnen. I en pilotmiljö kanske du till exempel bara vill tillåta att en liten grupp användare kan visa ämnen.

## <a name="remove-topics-from-being-viewed"></a>Ta bort ämnen från att visas

Kunskapshanterare kan välja att [ta bort ämnen](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) så att användarna inte längre kan se dem. På sidan **Hantera ämnen** i Ämnescenter **kan knowledge** managers välja att avvisa vissa ämnen för att förhindra att de visas. Ämnen kan tas bort oavsett om de är i föreslaget eller bekräftat tillstånd.

Borttagna ämnen kan senare läggas till som visningsbara ämnen vid behov. 


## <a name="see-also"></a>Se även



  






