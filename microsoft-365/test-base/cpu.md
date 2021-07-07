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
# <a name="intelligent-cpu-regression-analysis"></a><span data-ttu-id="b3169-103">Intelligent PROCESSOR-regressionsanalys</span><span class="sxs-lookup"><span data-stu-id="b3169-103">Intelligent CPU regression analysis</span></span>

<span data-ttu-id="b3169-104">CPU-användning kan ange om ett program påverkas av en uppdatering av operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="b3169-104">CPU utilization can indicate whether an application is affected by an operating system update.</span></span> 

<span data-ttu-id="b3169-105">Testbas för Microsoft 365 ger programvaruutvecklare en inblick i regressioner av CPU-prestanda som uppstår när deras program körs på olika versioner av en kommande Windows-uppdatering (OS).</span><span class="sxs-lookup"><span data-stu-id="b3169-105">Test Base for Microsoft 365 provides software developers with an insight into CPU performance regressions which occur when their application is running on different versions of an upcoming Windows Operating System (OS) update.</span></span> 

<span data-ttu-id="b3169-106">Med hjälp av dessa CPU-regressioner kan utvecklare identifiera och lösa programproblem (och potentiella fel) innan OS-uppdateringen distribueras i stor utsträckning, vilket förhindrar en felaktig upplevelse för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="b3169-106">These CPU regressions enable developers to detect and resolve application issues (and potential failures) before the OS update is deployed broadly, thus preventing a bad experience for the end user.</span></span>


### <a name="how-cpu-regression-analysis-works"></a><span data-ttu-id="b3169-107">Så här fungerar regressionsanalys av processorkraften</span><span class="sxs-lookup"><span data-stu-id="b3169-107">How CPU regression analysis works</span></span> ###

<span data-ttu-id="b3169-108">Som Test Base-användare kan du ladda upp programmets binärfiler (i en enda .zip-fil) tillsammans med associerade testskript och välja den Windows OS-version som du vill testa programmet mot på Test Base-portalen i Azure.</span><span class="sxs-lookup"><span data-stu-id="b3169-108">As a Test Base user, you can upload your application's binaries (in a single .zip file), along with associated test scripts and select the Windows OS version against which you would like to test your application on the Test Base portal on Azure.</span></span> 

<span data-ttu-id="b3169-109">Testbastjänsten kör sedan testskripten och utför **CPU-regressionsanalysen.**</span><span class="sxs-lookup"><span data-stu-id="b3169-109">The Test Base service then runs the test scripts and performs the **CPU Regression Analysis**.</span></span> 

<span data-ttu-id="b3169-110">Tjänsten kontrollerar om CPU-användningen för programmet på förhandsversionen av uppdateringen för måloperativsystemet är i linje med cpu-utnyttjandet för den släppta versionen av operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="b3169-110">The service checks if the CPU utilization for the application on the pre-release version of the update for the target OS is in line with the CPU utilization for the released version of the OS.</span></span> 

<span data-ttu-id="b3169-111">CPU-användningen är inte en 100 % like-for-like-jämförelse eftersom processerna som körs på de två versionerna av operativsystemet kanske eller inte är en exakt matchning på grund av olika OS-versioner. Men den analys som utförs av Test Base kan visa om CPU-användningen för programmet påverkas av en kommande OS-uppdatering och särskilt vilka processer som har ansats från tidigare test körs.</span><span class="sxs-lookup"><span data-stu-id="b3169-111">CPU utilization is not a 100% like-for-like comparison because the processes running on the two versions of the OS may or may not be an exact match due to differing OS versions; however, the analysis performed by Test Base can show you whether CPU utilization for your application is impacted by an upcoming OS update and specifically which processes have regressed from previous test runs.</span></span>

<span data-ttu-id="b3169-112">I ögonblicksbilden nedan finns det två OS-versioner som CPU-utnyttjandet jämförs mot för samma program.</span><span class="sxs-lookup"><span data-stu-id="b3169-112">In the snapshot below, there are two OS releases against which the CPU utilizations are compared for the same application.</span></span> 
-   <span data-ttu-id="b3169-113">På fliken för cpu-användning visas den övre och nedre gränsen för användningen av respektive version vid 90 respektive 10:e percentilen.</span><span class="sxs-lookup"><span data-stu-id="b3169-113">The CPU utilization tab shows the upper and lower bounds of utilization for both releases at 90th and 10th percentiles respectively.</span></span> 
-   <span data-ttu-id="b3169-114">Diagrammen visar tidsserier för cpu-utnyttjandet tillsammans med genomsnittligt utnyttjandet.</span><span class="sxs-lookup"><span data-stu-id="b3169-114">The graphs show the time series of CPU utilization along with the average utilization.</span></span> 

<span data-ttu-id="b3169-115">Kunder kan nu använda funktionerna för att avgöra om användningen av deras program cpu påverkas av OS-uppdateringar och särskilt vilka processer som har regresserats från den tidigare körningen.</span><span class="sxs-lookup"><span data-stu-id="b3169-115">Customers can now use the functionality to determine if their application's CPU utilization is impacted by OS updates and specifically which processes have regressed from their previous execution.</span></span>


![CPU-regressionsanalys](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a><span data-ttu-id="b3169-117">Relevant processidentifiering</span><span class="sxs-lookup"><span data-stu-id="b3169-117">Relevant Process Identification</span></span> ###

<span data-ttu-id="b3169-118">Här diskuteras hur du identifierar regresserade processer i programmet.</span><span class="sxs-lookup"><span data-stu-id="b3169-118">Here, we discuss how to identify regressed processes in the application.</span></span> 

<span data-ttu-id="b3169-119">För att analysera prestanda regression krävs spårning av olika typer av prestandaräknare för varje process som körs på en virtuell dator under testkörningen.</span><span class="sxs-lookup"><span data-stu-id="b3169-119">Analyzing performance regression requires tracking different kinds of performance counters for every process running on a virtual machine during the test run.</span></span> 

<span data-ttu-id="b3169-120">En sådan analys fångar många variabler för många processer för ett givet program.</span><span class="sxs-lookup"><span data-stu-id="b3169-120">Such analysis captures a lot of variables for a lot of processes for a given application.</span></span> <span data-ttu-id="b3169-121">Alla processer är inte kopplade till en körning eller ett program.</span><span class="sxs-lookup"><span data-stu-id="b3169-121">Not all processes are associated with a run or application.</span></span> <span data-ttu-id="b3169-122">För att komma runt den här utmaningen används en gemensam algoritm för informationsrankning med hjälp av sannolikhet och informationsteori för att ta reda på vilka processer som är mest relevanta för ett givet program.</span><span class="sxs-lookup"><span data-stu-id="b3169-122">To work around this challenge, a mutual information ranking algorithm using probability and information theory is applied to figure out which processes are most relevant for a given application.</span></span> 

<span data-ttu-id="b3169-123">Ett program kan ses som en typ av fristående slumpvariabel medan en process anses vara en annan typ av slumpmässig variabel.</span><span class="sxs-lookup"><span data-stu-id="b3169-123">An application can be considered one type of discrete random variable while a process is considered another kind of discrete random variable.</span></span> <span data-ttu-id="b3169-124">Kopplingen av de två slumpmässiga variablerna mäts med villkorsstyrda sannolikheter för relevans.</span><span class="sxs-lookup"><span data-stu-id="b3169-124">The association of the two random variables is measured using conditional probabilities for relevance.</span></span> 

<span data-ttu-id="b3169-125">Processer visas sedan i den ordning de är relevanta för varje program.</span><span class="sxs-lookup"><span data-stu-id="b3169-125">Processes are then displayed in the order of their relevance for each application.</span></span> <span data-ttu-id="b3169-126">En delmängd av processer som övervakas kan övervakas som standard och relevanta processer för regressionsanalys av processorkraften är också favorit.</span><span class="sxs-lookup"><span data-stu-id="b3169-126">You can also favorite a subset of processes that can be monitored, by default, along with relevant processes for CPU regression analysis.</span></span> <span data-ttu-id="b3169-127">När en regression har upptäckts kan du ladda ned verktyget Windows Analysera prestanda och analysera orsaker till regressioner i CPU-prestanda.</span><span class="sxs-lookup"><span data-stu-id="b3169-127">Once a regression is detected, you can download the Windows Performance Analyzer toolkit and analyze reasons for CPU performance regressions.</span></span> 

<span data-ttu-id="b3169-128">I Windows Performance Analyzer används händelsespårningslogg (ETL) som indata och dessa .etl-filer är tillgängliga i loggfilerna som kan laddas ned för test körs på portalen.</span><span class="sxs-lookup"><span data-stu-id="b3169-128">The Windows Performance Analyzer takes event trace log (ETL) as inputs and these .etl files are available in the log files downloadable for test runs on the portal.</span></span> <span data-ttu-id="b3169-129">Om du vill veta mer om felsökning av CPU-prestanda kan du läsa Windows i Analysera prestanda.</span><span class="sxs-lookup"><span data-stu-id="b3169-129">If you would like to know more about debugging CPU performance, see the Windows Performance Analyzer documentation.</span></span>

