---
title: Ämne upplever säkerhets trimning (för hands version)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Översikt över hur säkerhet används för att Visa ämnen.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699062"
---
# <a name="topic-experiences-security-trimming-preview"></a>Ämne upplever säkerhets trimning (för hands version)

> [!Note] 
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Läs mer om Project Cortex](https://aka.ms/projectcortex).

Ämnen som gör att användarna inte kan se information om ämnen som de befintliga Office 365-behörigheterna hindrar dem från att se. Allt som en användare ser på en ämnes sida (till exempel SharePoint-webbplatser, dokument, filer) kommer att vara information som de redan är tillåtna för att visas. Avsnitts upplevelser ändrar inte befintliga behörigheter.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Varför två användare kan ha olika vyer av samma ämne

När ett ämne skapas via AI eller manuell bevarande kan det innehålla en beskrivning av ämnet, alternativa namn, personer som är kopplade till ämnet, samt webbplatser, sidor och filer relaterade till avsnittet. När den här informationen visas på en ämnes sida är det möjligt att två användare som visar samma ämne inte ser samma information.
  
Om till exempel en användare 1 visar sidan Neptune, är detta det här som de kan se.

![Neptune-avsnitt för användare 1](../media/knowledge-management/user2-topic-view.png) </br> 

Men när användare 2 tittar på samma Neptune visas en vy från användare 1.  Användare 2 kan se *produkt översikts filen DG-2000* i avsnittet **fästa filer och sidor** på sidan ämne, som inte visas för användare 1. 

![Neptune-avsnitt för användare 2](../media/knowledge-management/user1-topic-view.png) </br> 

Skillnaden i vad användarna kan se i samma avsnitt är att användarna kanske inte har Office 365-behörighet för att visa en relaterad webbplats eller fil.  Avsnitts erfarenheten respekterar de behörigheter som är inställda för objekt i ett ämne och kan inte ändra åtkomsten till dem. I vårt exempel kan inte användare 1 Visa *produkt översikts filen DG-2000* på sidan för Neptune eftersom användare 1 inte har Office 365-behörighet för att visa filen.

Om en användare inte kan se tillräckligt med information i ett ämne för att den ska vara användbar, är avsnittet inte tillgängligt för användaren. I den här instansen visas inte det markerade avsnittet. Men en annan användare som har behörighet till mer information i ämnet för att det ska vara användbart kan se avsnittet.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Behörigheter för ämne för kunskaps chefer och ämnes deltagare

Användare som har tilldelats behörigheter för att hantera ämnen – kunskaps chefer-kommer bara att kunna visa information som de har behörighet att se i avsnitt.

På liknande sätt kan användare som har behörigheten Skapa och redigera ämne-ämnes deltagare-bara visa information som de har behörighet att se i ämnen. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI och manuellt underavsnitts information

Ämnen kan innehålla information som genererats av AI och information som lagts till eller redigerats av ämnes deltagare eller kunskaps chefer.

 - Information i ett ämne som lagts till av AI visas bara för personer som har till gång till käll innehållet.
 - Information som har lagts till manuellt eller redigerats av en ämnes deltagare eller kunskaps chef visas för alla som kan se avsnittet.

I följande tabell beskrivs vad användare – avsnitts läsare, deltagare och kunskaps chefer – kan se i ett visst ämne baserat på deras behörigheter.

|Ämnes objekt|Vad användarna kan se|
|:---------|:------------------|
|Namn på avsnitt|Användare kan se ämnes namnet i alla ämnen i ämnes centret. Vissa ämnen kanske inte visas om de har en liten sökrelevans till användaren.|
|Beskrivning av ämnet|AI-genererade beskrivningar visas endast för användare som har behörighet till käll innehållet. Manuellt angivna eller redigerade beskrivningar visas för alla användare.|
|Kontakter|Fästa personer visas för alla användare. Föreslagna personer visas bara för användare som har behörighet till käll innehållet.|
|Hjälpfiler|Filer visas endast för användare som har behörighet till käll innehållet.|
|Målsidor|Sidor visas bara för användare som har behörighet till käll innehållet.|
|Sidor|Webbplatser visas bara för användare som har behörighet till käll innehållet.|




## <a name="see-also"></a>Se även

