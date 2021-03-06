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
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500884"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Begränsa åtkomst till ämnen i Microsoft Viva-ämnen

I Microsoft Viva kanske intressenter i organisationen vill se till att specifika ämnen inte upptäcks och visas för licensierade användare. Du kanske exempelvis arbetar med ett projekt som du inte vill visa någon information om än. Även Office 365 behörigheter på webbplatser, filer och andra resurser kommer att förhindra att användare av ämneserfarenheter visar känslig information i ämnen, finns det ytterligare säkerhetsåtgärder för att förhindra att vissa ämnen någonsin upptäcks.

Även om kunskapsadministratörer styr inställningarna för att förhindra att ämnen upptäcks, behöver knowledge chefer och andra intressenter veta hur det görs så att de kan arbeta tillsammans.

> [!Important] 
> I den här artikeln beskrivs olika sätt att förhindra att ämnen identifieras genom AI eller visas i din miljö som ett ytterligare säkerhetsskydd. Det är viktigt att observera att användare i Viva-ämnen inte har tillåtelse att visa något i ett ämne som de inte har åtkomst Office 365 via Office 365 behörigheter. Även om en användare kan visa ett ämne, dess filer, webbplatser och sidor som de inte har Office 365 att visa kommer de inte att visas för dem. Att se till att behörigheter för känsliga filer anges korrekt bör vara ditt primära säkerhetsskydd.

## <a name="prevent-topics-from-being-identified"></a>Förhindra att ämnen identifieras

Knowledge admin can restrict access to specific topics by preventing them from found in initial indexing. Du kan utföra den här uppgiften på två sätt i administrationsinställningarna för Viva Topics Microsoft 365 administrationscentret för viva ämnen.
 
- [Välj SharePoint webbplatser som](./topic-experiences-discovery.md#select-sharepoint-topic-sources)ska undantas från identifiering av ämnen: Du kan använda den här inställningen för att förhindra att specifika SharePoint-webbplatser crawlas för ämnen.
- [Undanta avsnitt efter namn:](./topic-experiences-discovery.md#exclude-topics-by-name)Administratörer kan använda den här inställningen för att förhindra att vissa ämnen upptäcks med namn. I administratörsinställningarna för Viva Topics kan en administratör ladda upp en lista med ämnen som ska undantas i en CSV-fil. Du kan utesluta avsnitt som har exakta eller partiella matchningar för ett ämnesnamn.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Förhindra att ämnen visas för specifika användare

Kunskapsadministratörer kan också [välja vem som kan visa ämnen i organisationen.](./topic-experiences-knowledge-rules.md) Med den här inställningen kan du välja vilka licensierade användare som kan visa alla ämnen. I en pilotmiljö kanske du till exempel bara vill att en liten grupp användare ska kunna visa ämnen.

## <a name="remove-topics-from-being-viewed"></a>Ta bort ämnen från att visas

Knowledge managers can choose to [remove topics](./manage-topics.md) so that users can no longer see them. På sidan **Hantera ämnen** i **Ämnescenter kan** knowledge managers välja att avvisa vissa ämnen för att de inte ska visas. Ämnen kan tas bort oavsett om de är i föreslaget eller bekräftat tillstånd.

Borttagna ämnen kan senare läggas till som visningsbara ämnen vid behov. 


## <a name="see-also"></a>Se även



