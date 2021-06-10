---
title: Säkerhets trimning för Microsoft Viva Topics
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Översikt över hur säkerhet används för att visa ämnen.
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939629"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Säkerhets trimning för Microsoft Viva Topics 

Viva Topics-användare kan inte visa information i ämnen som deras befintliga Office 365 hindrar dem från att se. Allt som en användare ser på en ämnessida (till exempel SharePoint, dokument, filer) är information som de redan har tillåtelse att se. Viva Topics ändrar inga befintliga behörigheter.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Varför två användare kan ha olika vyer av samma ämne

När ett ämne skapas med AI eller manuell läroplan kan det innehålla en beskrivning av ämnet, alternativa namn, personer kopplade till ämnet samt webbplatser, sidor och filer relaterade till ämnet. När den här informationen visas på en ämnessida är det möjligt att två användare som visar samma ämne ser min inte samma information.
  
När användare 1 till exempel visar ämnessidan för Neptune kan de se den här vyn av ämnessidan.

![Neptune-ämne för användare 1](../media/knowledge-management/user2-topic-view.png) </br> 

Men när Användare 2 tittar på samma Neptune-ämnessida skiljer sig deras vy från Användare 1.  Användare 2 kan se *filen DG-2000 Produktöversikt* i avsnittet Fästa filer och sidor på ämnessidan, som inte visas för Användare 1.  

![Neptune-ämne för användare 2](../media/knowledge-management/user1-topic-view.png) </br> 

Skillnaden i vad användarna kan se med samma ämne är att användarna kanske inte har den Office 365 kunna visa en relaterad webbplats eller fil.  Viva Topics respekterar behörigheterna som anges för objekt i ett ämne och kan inte ändra åtkomsten till dem. I vårt exempel kan användare 1 inte visa filen *DG-2000 produktöversikt* på ämnessidan för Neptune eftersom användare 1 inte har Office 365 behörighet att visa filen.

Om en användare inte kan se tillräckligt med information i ett ämne för att det ska vara användbart, kommer ämnet inte att vara tillgängligt för användaren. När detta händer kan användaren inte se det markerade avsnittet. En annan användare som har behörighet till mer information i avsnittet för att vara användbar kommer att kunna se avsnittet.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Ämnesbehörigheter för kunskapshanterare och ämnesdeltagare

Användare som har tilldelats behörigheter för att hantera ämnen – knowledge managers – kan bara visa information som de har behörighet att se i ämnen.

På samma sätt kan användare som har behörighet att skapa och redigera ämnesbehörigheter – ämnesdeltagare – bara visa information som de har behörighet att se i ämnen. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI kontra manuellt curated topic information

Ämnen kan innehålla information som genereras av AI och information som lagts till eller redigerats av ämnesdeltagare eller kunskapshanterare.

 - Information i ett ämne som har lagts till av AI visas bara för personer som har åtkomst till källinnehållet.
 - Information om ämnesbeskrivningar och personer som har lagts till manuellt eller redigerats av en ämnesdeltagare eller knowledge manager visas för alla som kan se ämnet.
 - Filer, sidor och webbplatser visas bara för användare som har behörighet till källinnehållet, oavsett om de har lagts till manuellt eller lagts till av AI.

I följande tabell beskrivs vad användare – ämnesanvändare, deltagare och kunskapshanterare – kan se i ett visst ämne baserat på deras behörigheter.

|Ämnesobjekt|Vad användarna kan se|
|:---------|:------------------|
|Ämnesnamn|Användarna kan se ämnesnamnet för ämnen i ämnescentret. Vissa ämnen kanske inte visas om användarna inte har behörighet till källinnehållet eller har en låg relevans för användaren.|
|Ämnesbeskrivning|AI-genererade beskrivningar visas endast för användare som har behörighet till källinnehållet. Manuellt angivna eller redigerade beskrivningar visas för alla användare.|
|Kontakter|Fästa personer visas för alla användare. Föreslagna personer visas bara för användare som har behörighet till källinnehållet.|
|Filer|Filer visas bara för användare som har behörighet till källinnehållet.|
|Sidor|Sidor visas bara för användare som har behörighet till källinnehållet.|
|Webbplatser|Webbplatser visas bara för användare som har behörighet till källinnehållet.|




## <a name="see-also"></a>Se även

