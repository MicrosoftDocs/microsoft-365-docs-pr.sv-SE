---
title: Innehåll som lagrats Exchange Online postlådor
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
description: Innehåll som skapas av molnbaserade appar i Microsoft 365 lagras eller associeras med en användares Exchange Online postlåda. Det här innehållet kan sökas med Microsofts verktyg för eDiscovery.
ms.openlocfilehash: 872e618486c273e07e8dcf98d61bbbb7d8f95051
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/17/2021
ms.locfileid: "52161844"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>Innehåll som lagrats Exchange Online eDiscovery-postlådor

En postlåda i Exchange Online används främst för att lagra e-postrelaterade objekt som meddelanden, kalenderobjekt, uppgifter och anteckningar. Men det ändras när fler molnbaserade appar också lagrar sina data i en användares postlåda. En fördel med att lagra data i en postlåda är att du kan använda sökverktygen för innehållssökning, Core eDiscovery och Advanced eDiscovery för att hitta, visa och exportera data från dessa molnbaserade appar. Data från vissa av dessa appar lagras i dolda mappar som finns i ett underträd för icke-personliga meddelanden (icke-IPM) i postlådan. Data från andra molnbaserade appar  lagras kanske inte i  postlådan, men de är kopplade till postlådan och returneras i sökningar (om dessa data matchar sökfrågan). Oavsett om molnbaserade data lagras i eller associeras med en användarpostlåda är data vanligtvis inte synliga i en e-postklient när en användare öppnar sin postlåda.

I följande tabell visas de appar som antingen lagrar eller associerar data med en molnbaserad postlåda. Tabellen beskriver också vilken typ av innehåll som varje app skapar.

|Microsoft 365 appen|Beskrivning|
|:---------|:---------|
|Formulär|Formulär och svar i ett formulär lagras i filer som är bifogade i e-postmeddelanden och lagras i en dold mapp i postlådan för den användare som skapade formuläret. Formulär som har skapats före april 2020 lagras som en PDF-fil. Formulär som skapas efter 2020 lagras som en JSON-fil.  Svar på ett formulär lagras i en CSV-fil. När du exporterar innehåll från Formulär i en PST-fil finns dessa data i mappen **ApplicationDataRoot** i en undermapp med följande globalt unika identifierade (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87.** |
|Microsoft 365-grupper|E-postmeddelanden, kalenderobjekt, kontakter (personer), anteckningar och uppgifter lagras i postlådan som är kopplad till en Microsoft 365 grupp.|
|Outlook/Exchange Online|E-postmeddelanden, kalenderobjekt, kontakter (personer), anteckningar och uppgifter lagras i en användares postlåda.|
|Kontakter|Kontakter i appen Kontakter (som är samma kontakter som de som är tillgängliga i Outlook) lagras i en användares postlåda.|
|Klassschema|Planer som skapas i Klassschema lagras i postlådan för Microsoft 365 grupp som etableras när en ny plan skapas. Alias för grupppostlådan är namnet på planen.|
|Skype för företag|Konversationer i Skype för företag lagras i mappen Konversationshistorik i en användares postlåda. Om postlådan för en deltagare i ett Skype-möte placeras i Bevarande av juridiska skäl eller tilldelas till en bevarandeprincip, behålls filer som är bifogade till ett möte i deltagarnas postlåda.|
|Sway|Sway-yta lagras som en HTML-fil som bifogas i ett e-postmeddelande och lagras i en dold mapp i postlådan för den användare som skapade Sway-yta. När du exporterar innehåll från Sway i en PST-fil finns dessa data i mappen **ApplicationDataRoot** i en undermapp med namnet med följande GUID: **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba.**|
|Uppgifter|Uppgifter i appen Uppgifter (som är samma uppgifter som de som är tillgängliga i Outlook) lagras i en användares postlåda.|
|Teams|Konversationer som ingår i en Teams är kopplade till den Teams postlådan. Konversationer som ingår i chattlistan i Teams (kallas *även 1 x* N-chattar) kopplas till postlådan för de användare som deltar i chatten. Dessutom är sammanfattningsinformation för möten och samtal i en Teams kopplad till postlådor för användare som ringt in till mötet eller samtalet. När du söker efter Teams innehåll söker du efter innehåll i Teams-postlådan efter innehåll i kanalkonversationer och söker efter innehåll i användarpostlådor i 1 x N chattar.|
|To-Do|Uppgifter (uppgifter som sparas i att göra-listor) i *To-Do-appen lagras* i en användares postlåda.|
|Yammer|Konversationer och kommentarer i en Yammer-community är kopplade till Microsoft 365-gruppens postlåda, samt användarens postlåda för författaren och eventuella namngivna mottagare (@ omnämnda eller kopia till användare). Privata meddelanden som skickas utanför en Yammer-community lagras i postlådan för de användare som deltar i det privata meddelandet.|  
||||

> [!NOTE]
> Om ett spärrat värde sätts på en postlåda (genom att använda innehåll i Core eDiscovery- och Advanced eDiscovery-fall), bevaras inte innehåll från Forms och Sway av spärrade eDiscovery- och Advanced eDiscovery-ärenden.
