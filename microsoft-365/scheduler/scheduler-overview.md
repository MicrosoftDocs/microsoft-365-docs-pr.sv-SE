---
title: Schemaläggare för Microsoft 365 Översikt
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Översikt över Schemaläggaren för Microsoft 365.
ms.openlocfilehash: 5429fa5ddb11892d3b7b9bdcf6949fa57dd1c7bb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286259"
---
# <a name="welcome-to-scheduler-for-microsoft-365"></a>Välkommen till Scheduler för Microsoft 365

Schemaläggaren för Microsoft 365 tjänst som låter dig delegera schemaläggningen av möten och avtalade tider till Cortana, din digitala personliga assistent. 

Schemaläggaren använder naturlig språkbearbetning för att tolka e-postmeddelanden som skickas till Cortana (cortana@yourdomain.com) för att hitta en tid att träffas och skicka kalenderinbjudningar till mötesorganisatören.   

Schemaläggare: 

- Kommunicerar med mötesorganisatören och deltagarna via e-post på naturligt språk.
- Hittar en tid att träffas när alla är tillgängliga.
- Koordinaterna mellan externa deltagare utifrån organisatörens tillgänglighet.
- Håller mötesorganisatören informerad om schemaläggningsförloppet och frågar organisatören om vägledning vid behov.
- Förhandlar fram tider för att mötas i upp till två olika tidszoner.
- Skickar inbjudan till mötet från organisatören.
- Lägger till Teams länk till varje möte.
- Ombokar eller avbokar möten bokas in av Cortana.
- Fungerar från alla enheter med åtkomst till e-post.

## <a name="who-can-benefit-from-scheduler-for-microsoft-365"></a>Vem kan du dra nytta av Schemaläggaren för Microsoft 365?

Schemaläggaren tar hand om de tidskrävande besväret med att schemalägga möten så att användarna kan fokusera på viktigare saker. 

Om du regelbundet schemalägger små möten med färre än fem deltagare sparar du tid med Schemaläggaren.  Avdelningar som rekrytering, försäljning, inköp och juridik kan dra nytta av delegering av mötesamordning till Schemaläggaren.

## <a name="how-does-scheduler-for-microsoft-365-work"></a>Hur fungerar Scheduler för Microsoft 365?

Scheduler använder en kombination av artificiell intelligens och human intelligens för att slutföra schemaläggningsförfrågningar som tas emot genom att skicka ett e-postmeddelande till Cortana (Cortana@yourdomain.com).  

Om du vill använda Scheduler lägger du till Cortanas e-postadress i ett e-postmeddelande med de personer du vill ha ett möte med och ber Cortana boka ett möte på naturligt språk. 

I din förfrågan kan du berätta för Cortana hur länge och när du vill träffas. Till exempel **"Cortana, find 45 minutes for us to meet next week".**

När en användare skickar en mötesförfrågan till Cortana gör schedulertjänsten följande: 

- Hittar en tid att mötas utifrån organisatörens och deltagarnas tillgänglighet i samma klientorganisation.
- Om organisatören inte har tillgång till deltagarnas tillgänglighet förhandlar Cortana fram en tid för att träffa med deltagarna via e-post. 
- När en gemensam tid har hittats lägger Cortana till ett Teams möte och skickar ut kalender inbjudningar. 
