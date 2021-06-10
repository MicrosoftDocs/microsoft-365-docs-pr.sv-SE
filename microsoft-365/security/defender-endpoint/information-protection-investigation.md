---
title: Använda känslighetsetiketter för att prioritera incidentsvar
description: Lär dig hur du kan använda känslighetsetiketter för att prioritera och undersöka incidenter
keywords: information, skydd, data, förlust, skydd, etiketter, dlp, incident, undersökning, undersökning
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bff490edcc79bc8f96e65c8b27586ca8b54e5bce
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186131"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="2f552-104">Använda känslighetsetiketter för att prioritera incidentsvar</span><span class="sxs-lookup"><span data-stu-id="2f552-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f552-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2f552-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f552-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2f552-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f552-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f552-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2f552-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2f552-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2f552-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2f552-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="2f552-110">En typisk avancerad livscykel för beständiga hot involverar datainfiltrering.</span><span class="sxs-lookup"><span data-stu-id="2f552-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="2f552-111">Vid säkerhetstillbud är det viktigt att ha möjlighet att prioritera undersökningar där känsliga filer kan vara känsliga så att företagsdata och företagsinformation skyddas.</span><span class="sxs-lookup"><span data-stu-id="2f552-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="2f552-112">Defender för Endpoint gör prioriteringen av säkerhetstillbud enklare med hjälp av känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="2f552-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="2f552-113">Känslighetsetiketter identifierar snabbt incidenter som involverar enheter med känslig information, till exempel konfidentiell information.</span><span class="sxs-lookup"><span data-stu-id="2f552-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="2f552-114">Undersöka incidenter med känslig information</span><span class="sxs-lookup"><span data-stu-id="2f552-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="2f552-115">Lär dig hur du använder datakänslighetsetiketter för att prioritera undersökning av incidenter.</span><span class="sxs-lookup"><span data-stu-id="2f552-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="2f552-116">Etiketter identifieras för Windows 10, version 1809 eller senare.</span><span class="sxs-lookup"><span data-stu-id="2f552-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="2f552-117">I Microsoft Defender Säkerhetscenter du **Incidenter**.</span><span class="sxs-lookup"><span data-stu-id="2f552-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="2f552-118">Rulla till höger för att se **kolumnen Datakänslighet.**</span><span class="sxs-lookup"><span data-stu-id="2f552-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="2f552-119">I den här kolumnen visas känslighetsetiketter som har observerats på enheter som är relaterade till incidenterna och som anger om känsliga filer kan påverkas av händelsen.</span><span class="sxs-lookup"><span data-stu-id="2f552-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![Bild av kolumnen datakänslighet](images/data-sensitivity-column.png)

    <span data-ttu-id="2f552-121">Du kan också filtrera baserat på **datakänslighet**</span><span class="sxs-lookup"><span data-stu-id="2f552-121">You can also filter based on **Data sensitivity**</span></span> 

    ![Bild av filtret för datakänslighet](images/data-sensitivity-filter.png)

3. <span data-ttu-id="2f552-123">Öppna incidentsidan för ytterligare undersökning.</span><span class="sxs-lookup"><span data-stu-id="2f552-123">Open the incident page to further investigate.</span></span>

    ![Bild på information om incidentsidan](images/incident-page.png)

4. <span data-ttu-id="2f552-125">Välj fliken **Enheter** för att identifiera enheter som lagrar filer med känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="2f552-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![Bild på enhetsfliken](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="2f552-127">Välj de enheter som lagrar känsliga data och sök igenom tidslinjen för att identifiera vilka filer som kan påverkas och vidta lämpliga åtgärder för att säkerställa att data skyddas.</span><span class="sxs-lookup"><span data-stu-id="2f552-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="2f552-128">Du kan begränsa händelser som visas på enhetens tidslinje genom att söka efter datakänslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="2f552-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="2f552-129">Då visas endast händelser som är associerade med filer som har sa etikettnamn.</span><span class="sxs-lookup"><span data-stu-id="2f552-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![Bild på tidslinjen på enheten med begränsade sökresultat baserat på etikett](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="2f552-131">Dessa datapunkter visas även genom DeviceFileEvents vid avancerad sökning, så att avancerade frågor och schemaidentifiering kan ta hänsyn till känslighetsetiketter och filskyddsstatus.</span><span class="sxs-lookup"><span data-stu-id="2f552-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
