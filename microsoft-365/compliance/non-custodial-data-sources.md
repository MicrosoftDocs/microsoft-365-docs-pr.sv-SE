---
title: Lägga till icke-förfallna datakällor i ett Advanced eDiscovery fall
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
description: Du kan lägga till icke-tilläggsdatakällor till ett Advanced eDiscovery fall och placera ett hold i datakällan. Icke-försvöjda datakällor indexeras om, så allt innehåll som markerats som delvis indexerats om för att göra det helt och snabbt sökbart.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/31/2020
ms.locfileid: "52161709"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Lägga till icke-förfallna datakällor i ett Advanced eDiscovery fall

I Advanced eDiscovery fall uppfyller den inte alltid dina behov att associera en Microsoft 365 datakälla med en vårdnadshavare i ärendet. Men du kanske fortfarande behöver koppla dessa data till ett ärende så att du kan söka i dem, lägga till dem i en granskningsuppsättning och analysera och granska dem. Funktionen i Advanced eDiscovery kallas *icke-förseningsdatakällor* och gör att du kan lägga till data i ett ärende utan att behöva koppla dem till en vårdnadshavare. Det gäller även samma Advanced eDiscovery för icke-sammanhängande data som är tillgängliga för data som är associerade med vårdnadshavare. Två av de mest användbara sakerna som du kan använda för icke-uppslagna data är att placera dem i förvaring och bearbeta dem med hjälp av [Avancerad indexering.](indexing-custodian-data.md)

## <a name="add-a-non-custodial-data-source"></a>Lägga till en datakälla som inte är i följd

Följ dessa steg för att lägga till och hantera icke-förfallna datakällor i Advanced eDiscovery fall.

1. På **Advanced eDiscovery** klickar du på det ärende du vill lägga till data i.

2. Klicka på **fliken Datakällor** och sedan på **Lägg till**  >  **datakälla Lägg till dataplatser.**

3. På den **utfällliga sidan Nya icke-tilläggsdataplatser** väljer du de datakällor som du vill lägga till för ärendet. Du kan lägga till flera postlådor och webbplatser genom att expandera **avsnitten SharePoint** eller **Exchange** och sedan klicka på **Redigera**.

   ![Lägga SharePoint webbplatser och Exchange postlådor som icke-uppslagna datakällor](../media/NonCustodialDataSources1.png)

   - **SharePoint – klicka** på Redigera **för att** lägga till webbplatser. Välj en webbplats i listan eller så kan du söka efter en webbplats genom att skriva webbplatsadressen i sökfältet. Välj de webbplatser som du vill lägga till som icke-objektande datakällor och klicka på Lägg **till.**

   - **Exchange – klicka** på Redigera **för att** lägga till postlådor. Skriv ett namn eller alias (minst tre tecken) i sökrutan för postlådor eller distributionsgrupper. Markera de postlådor som du vill lägga till som icke-lika datakällor och klicka på Lägg **till.**

   > [!NOTE]
   > Du kan använda **avsnitten SharePoint** och **Exchange** för att lägga till webbplatser och postlådor som är kopplade till en Grupp- eller Yammer-grupp som icke-sammanhängande datakällor. Du måste separat lägga till postlådan och webbplatsen som är kopplade till en grupp eller Yammer grupp.

4. När du lägger till icke-tilläggsdatakällor kan du välja att placera dessa platser som förvaring eller inte. Markera eller avmarkera **kryssrutan Håll** ned bredvid datakällan om du vill markera den som väntande.

5. Klicka **på** Lägg till längst ned på den utfällliga sidan Nya **icke-förfallna dataplatser** för att lägga till datakällor för ärendet.

   Varje icke-ljudande datakälla som du har lagt till visas på **sidan Datakällor.** Icke-ljudande datakällor identifieras med **värdet för Dataplats** i **kolumnen Källtyp.**

   ![Icke-uppsövade datakällor på fliken Datakällor](../media/NonCustodialDataSources2.png)

När du lägger till icke-namngivna datakällor i ärendet skapas ett jobb med namnet  Indexera om *icke-förfallna data* och visas på fliken Jobb för ärendet. När jobbet har skapats indexeras indexeringsprocessen Avancerat i och datakällorna indexeras om.

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>Hantera förvaring för datakällor som inte kan innehålla data som inte kan administreras

När du placerar ett ärende i en datakälla som inte är försend med ett dokument skapas automatiskt en princip för förvaring som innehåller de icke-dokumentade datakällorna för ärendet. När du placerar andra icke-uppsagd datakällor i förvaring läggs de till i den här principen för förvaring.

1. Öppna Advanced eDiscovery och välj **fliken** Håll ned.

2. Klicka **på NCDSHold- \<GUID\>**, där GUID-värdet är unikt för ärendet.

   På den utfällande sidan visas information och statistik om icke-direktförseliga datakällor som är i förvaring.

   ![På den utfällande sidan för icke-förfallna datakällor visas statistik](../media/NonCustodialDataSourcesHoldFlyout.png)

3. Klicka **på Redigera** förvaring för att visa de icke-dokumentade datakällor som har satts på is och utföra följande hanteringsuppgifter:

   - På sidan **Platser kan** du släppa en icke-ljudande datakälla genom att ta bort den från förvaringen. När en datakälla släpps tas inte den icke-förfallna datakällan bort från det aktuella ärendet. Det här tar bara bort det kvart som lades till i datakällan.

   - På sidan **Fråga** kan du redigera förvaringen om du vill skapa ett frågebaserat förvarings nekat ärende som tillämpas på alla icke-förfallna datakällor.
