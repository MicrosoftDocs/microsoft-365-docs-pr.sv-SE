---
title: Kapacitetsplanering och belastningstestning av SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: I den här artikeln beskrivs hur du kan distribuera till SharePoint Online utan att genomföra traditionella inläsnings test eftersom det inte är tillåtet.
ms.openlocfilehash: a20ed3b5f9b3108d90ec912ec78efa348d4281b1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694764"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Kapacitetsplanering och belastningstestning av SharePoint Online
I den här artikeln beskrivs hur du kan distribuera till SharePoint Online utan traditionella inläsnings test, eftersom det inte är tillåtet att läsa in testning för SharePoint Online. SharePoint Online är en moln tjänst och lastens kapacitet, hälsa och total saldo för tjänsten hanteras av Microsoft.
  
Den bästa metoden för att säkerställa att webbplatsen startas är att följa grundläggande principer, praxis och rekommendationer som är markerade i det abonnemang som [din portal](planportallaunchroll-out.md)börjar på.

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Översikt över hur SharePoint Online utför kapacitets planering 
En av de viktigaste fördelarna med att använda SharePoint Online via en lokal distribution är att molnet är elastiskt samt optimeringar för användare i distribuerade regioner. Vår storskalig miljö är inställd på att betjäna miljon tals användare dagligen, så det är viktigt att vi hanterar kapaciteten effektivt genom att balansera och expandera Server grupper.
  
Även om tillväxten är ofta oförutsägbart för en enda klient organisation i en Server grupp, är det förutsägbart att en mängd begär Anden är tidsödande över tiden. Genom att identifiera tillväxt trenderna i SharePoint Online kan vi planera för framtida utbyggnad.
  
För att effektivt utnyttja kapaciteten och hantera oväntad tillväxt i alla Server grupper har vi automatiserat att spåra och övervaka olika delar av tjänsten. Flera mått används, med ett av de viktigaste som är CPU-belastning, som används som en signal för att bygga upp front servrar. Dessutom rekommenderar vi att du använder en [Stegad/Wave-inställning](planportallaunchroll-out.md), eftersom SQL-miljöerna skal för änd ras i takt med att det går att distribuera och utvecklas. 

Kapaciteten är mer än att bara lägga till mer maskin vara på en gång, men det finns också att hantera och kontrol lera den kapaciteten för att säkerställa att den hanterar giltiga inläsnings begär Anden. Vi rekommenderar att kunderna följer den rekommenderade vägledningen för att säkerställa att de har den bästa upplevelsen. Det innebär också att vi har begränsat mönster och kontroller för att säkerställa att vi inte tillåter "grova" beteende i tjänsten. Men inte alla "dåligt" beteende är avsiktligt måste vi se till att vi begränsar effekten av detta beteende. Mer information om hur du begränsar och hur du undviker det finns i artikeln om att [undvika begränsning av vägledning](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) .

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Varför du inte kan läsa in testa SharePoint Online
Med lokala miljöer används inläsnings testning för att bekräfta skalnings antagande och slutligen för att hitta den avbrotts punkten i en grupp. genom att saturating den med load. 

Med SharePoint Online måste vi göra saker på ett annat sätt eftersom skalan är relativt Fluid och justerar, begränsning och kontroll belastning, baserat på vissa heuristik. Eftersom det är en sådan storskalig miljö för flera innehavare måste vi skydda alla klient organisationer i samma server grupp, så vi kommer automatiskt att reglera eventuella laddnings test. Om du ändå försöker att läsa in test, utöver begränsning, får du inte blev och potentiellt missvisande resultat eftersom Server gruppen du testade i dag sannolikt hade haft ändringar under test fönstret eller inom några timmar efter testningen, allteftersom skalnings-och Server grupp balansering utförts.

I stället för att försöka läsa in testa SharePoint som en tjänst kan du i stället fokusera på att följa rekommendationerna och följa anvisningarna för att [skapa, starta och hantera en felfri Portal](https://go.microsoft.com/fwlink/?linkid=2105838) vägledning.
