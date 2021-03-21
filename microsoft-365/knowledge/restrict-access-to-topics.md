---
title: Begränsa åtkomst till ämnen i Microsoft Viva-ämnen
description: Hur du undantar ämnen för att förhindra att de upptäcks.
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
ms.openlocfilehash: dc344e0263bab287133ddb01ecab262440eb9e10
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925958"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Begränsa åtkomst till ämnen i Microsoft Viva-ämnen

I Microsoft Viva kanske intressenter i organisationen vill se till att specifika ämnen inte upptäcks och visas för licensierade användare. Du kanske exempelvis arbetar med ett projekt som du inte vill visa någon information om än. Office 365-behörigheter för webbplatser, filer och andra resurser förhindrar att användare av ämneserfarenheter visar känslig information i ämnen, men det finns ytterligare säkerhetsåtgärder för att förhindra att vissa ämnen upptäcks.

Även om kunskapsadministratörer styr nätverksinställningarna för att förhindra att ämnen upptäcks, behöver kunskapshanterare och andra intressenter veta hur det görs så att de kan arbeta tillsammans.

> [!Important] 
> I den här artikeln beskrivs olika sätt att förhindra att ämnen identifieras genom AI eller visas i din miljö som ett ytterligare säkerhetsskydd. Det är viktigt att observera att användare i Viva-ämnen inte har tillåtelse att visa något i ett ämne som de inte har åtkomst till via Office 365-behörigheter. Även om en användare kan visa ett ämne, dess filer, webbplatser och sidor som de inte har Office 365-behörighet att visa kommer de inte att visas för dem. Att se till att behörigheter för känsliga filer anges korrekt bör vara ditt primära säkerhetsskydd.

## <a name="prevent-topics-from-being-identified"></a>Förhindra att ämnen identifieras

Knowledge admin can restrict access to specific topics by preventing them from found in initial indexing. Du kan utföra den här uppgiften på två sätt i administrationsinställningarna för Knowledge Network i administrationscentret för Microsoft 365.
 
- [Välj SharePoint-webbplatser som ska undantas](./topic-experiences-discovery.md#select-sharepoint-topic-sources)från ämnesidentifiering: Du kan använda den här inställningen för att förhindra att vissa SharePoint-webbplatser crawlas för ämnen.
- [Undanta avsnitt efter namn:](./topic-experiences-discovery.md#exclude-topics-by-name)Administratörer kan använda den här inställningen för att förhindra att vissa ämnen upptäcks med namn. I administratörsinställningarna för Knowledge Network kan en administratör ladda upp en lista med ämnen som ska undantas i en CSV-fil. Du kan utesluta avsnitt som har exakta eller partiella matchningar för ett ämnesnamn.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Förhindra att ämnen visas för specifika användare

Kunskapsadministratörer kan också [välja vem som kan visa ämnen i organisationen.](./topic-experiences-knowledge-rules.md) Med den här inställningen kan du välja vilka licensierade användare som kan visa alla ämnen. I en pilotmiljö kanske du till exempel bara vill att en liten grupp användare ska kunna visa ämnen.

## <a name="remove-topics-from-being-viewed"></a>Ta bort ämnen från att visas

Knowledge managers can choose to [remove topics](./manage-topics.md) so that users can no longer see them. På sidan **Hantera ämnen** i **Ämnescenter kan** knowledge managers välja att avvisa vissa ämnen för att de inte ska visas. Ämnen kan tas bort oavsett om de är i föreslaget eller bekräftat tillstånd.

Borttagna ämnen kan senare läggas till som visningsbara ämnen vid behov. 


## <a name="see-also"></a>Se även



