---
title: CPU-regressionsanalys
description: Förstå regressionsresultat och mätvärden för CPU-förbrukning
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322996"
---
# <a name="intelligent-cpu-regression-analysis"></a>Intelligent PROCESSOR-regressionsanalys

CPU-användning kan ange om ett program påverkas av en uppdatering av operativsystemet. 

Testbas för Microsoft 365 ger programvaruutvecklare en inblick i regressioner av CPU-prestanda som uppstår när deras program körs på olika versioner av en kommande Windows-uppdatering (OS). 

Med hjälp av dessa CPU-regressioner kan utvecklare identifiera och lösa programproblem (och potentiella fel) innan OS-uppdateringen distribueras i stor utsträckning, vilket förhindrar en felaktig upplevelse för slutanvändaren.


### <a name="how-cpu-regression-analysis-works"></a>Så här fungerar regressionsanalys av processorkraften ###

Som Test Base-användare kan du ladda upp programmets binärfiler (i en enda .zip-fil) tillsammans med associerade testskript och välja den Windows OS-version som du vill testa programmet mot på Test Base-portalen i Azure. 

Testbastjänsten kör sedan testskripten och utför **CPU-regressionsanalysen.** 

Tjänsten kontrollerar om CPU-användningen för programmet på förhandsversionen av uppdateringen för måloperativsystemet är i linje med cpu-utnyttjandet för den släppta versionen av operativsystemet. 

CPU-användningen är inte en 100 % like-for-like-jämförelse eftersom processerna som körs på de två versionerna av operativsystemet kanske eller inte är en exakt matchning på grund av olika OS-versioner. Men den analys som utförs av Test Base kan visa om CPU-användningen för programmet påverkas av en kommande OS-uppdatering och särskilt vilka processer som har ansats från tidigare test körs.

I ögonblicksbilden nedan finns det två OS-versioner som CPU-utnyttjandet jämförs mot för samma program. 
-   På fliken för cpu-användning visas den övre och nedre gränsen för användningen av respektive version vid 90 respektive 10:e percentilen. 
-   Diagrammen visar tidsserier för cpu-utnyttjandet tillsammans med genomsnittligt utnyttjandet. 

Kunder kan nu använda funktionerna för att avgöra om användningen av deras program cpu påverkas av OS-uppdateringar och särskilt vilka processer som har regresserats från den tidigare körningen.


![CPU-regressionsanalys](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a>Relevant processidentifiering ###

Här diskuteras hur du identifierar regresserade processer i programmet. 

För att analysera prestanda regression krävs spårning av olika typer av prestandaräknare för varje process som körs på en virtuell dator under testkörningen. 

En sådan analys fångar många variabler för många processer för ett givet program. Alla processer är inte kopplade till en körning eller ett program. För att komma runt den här utmaningen används en gemensam algoritm för informationsrankning med hjälp av sannolikhet och informationsteori för att ta reda på vilka processer som är mest relevanta för ett givet program. 

Ett program kan ses som en typ av fristående slumpvariabel medan en process anses vara en annan typ av slumpmässig variabel. Kopplingen av de två slumpmässiga variablerna mäts med villkorsstyrda sannolikheter för relevans. 

Processer visas sedan i den ordning de är relevanta för varje program. En delmängd av processer som övervakas kan övervakas som standard och relevanta processer för regressionsanalys av processorkraften är också favorit. När en regression har upptäckts kan du ladda ned verktyget Windows Analysera prestanda och analysera orsaker till regressioner i CPU-prestanda. 

I Windows Performance Analyzer används händelsespårningslogg (ETL) som indata och dessa .etl-filer är tillgängliga i loggfilerna som kan laddas ned för test körs på portalen. Om du vill veta mer om felsökning av CPU-prestanda kan du läsa Windows i Analysera prestanda.

