---
title: Undersöka Microsoft Defender för slutpunktsfiler
description: Använd undersökningsalternativen för att få information om filer som är associerade med aviseringar, beteenden eller händelser.
keywords: undersök, undersökning, fil, skadlig aktivitet, attack motivation, djupanalys, djupanalysrapport
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a801b6153cf3f273290721756440cfe974103e92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072609"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="09d02-104">Undersöka en fil som är kopplad till en Microsoft Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="09d02-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09d02-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="09d02-105">**Applies to:**</span></span>
- [<span data-ttu-id="09d02-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="09d02-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="09d02-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09d02-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="09d02-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="09d02-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="09d02-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="09d02-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="09d02-110">Undersök informationen i en fil som är associerad med en viss avisering, ett visst beteende eller en händelse för att avgöra om filen har skadliga aktiviteter, identifiera attackor motivationen och förstå den potentiella omfattningen av intrånget.</span><span class="sxs-lookup"><span data-stu-id="09d02-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="09d02-111">Det finns många sätt att komma åt den detaljerade profilsidan för en viss fil.</span><span class="sxs-lookup"><span data-stu-id="09d02-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="09d02-112">Du kan till exempel använda sökfunktionen, klicka på en länk från **aviseringsprocessens träd** **,** incidentdiagram, artefakttidslinje eller välja en händelse som visas på **enhetens tidslinje**.</span><span class="sxs-lookup"><span data-stu-id="09d02-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="09d02-113">När du är på den detaljerade profilsidan kan du växla mellan de nya och gamla sidlayouterna genom att byta **ny Filsida**.</span><span class="sxs-lookup"><span data-stu-id="09d02-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="09d02-114">Resten av den här artikeln beskriver den nyare sidlayouten.</span><span class="sxs-lookup"><span data-stu-id="09d02-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="09d02-115">Du kan hämta information från följande avsnitt i filvyn:</span><span class="sxs-lookup"><span data-stu-id="09d02-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="09d02-116">Filinformation, identifiering av skadlig kod, filföresökning</span><span class="sxs-lookup"><span data-stu-id="09d02-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="09d02-117">Djupanalys</span><span class="sxs-lookup"><span data-stu-id="09d02-117">Deep analysis</span></span>
- <span data-ttu-id="09d02-118">Varningar</span><span class="sxs-lookup"><span data-stu-id="09d02-118">Alerts</span></span>
- <span data-ttu-id="09d02-119">Observerad i organisationen</span><span class="sxs-lookup"><span data-stu-id="09d02-119">Observed in organization</span></span>
- <span data-ttu-id="09d02-120">Djupanalys</span><span class="sxs-lookup"><span data-stu-id="09d02-120">Deep analysis</span></span>
- <span data-ttu-id="09d02-121">Filnamn</span><span class="sxs-lookup"><span data-stu-id="09d02-121">File names</span></span>

<span data-ttu-id="09d02-122">Du kan också vidta åtgärder för en fil från den här sidan.</span><span class="sxs-lookup"><span data-stu-id="09d02-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="09d02-123">Filåtgärder</span><span class="sxs-lookup"><span data-stu-id="09d02-123">File actions</span></span>

<span data-ttu-id="09d02-124">Ovanför filinformationskorten längst upp på profilsidan.</span><span class="sxs-lookup"><span data-stu-id="09d02-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="09d02-125">Åtgärder som du kan utföra här är:</span><span class="sxs-lookup"><span data-stu-id="09d02-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="09d02-126">Stoppa och sätta i karantän</span><span class="sxs-lookup"><span data-stu-id="09d02-126">Stop and quarantine</span></span>
- <span data-ttu-id="09d02-127">Indikator för att lägga till/redigera</span><span class="sxs-lookup"><span data-stu-id="09d02-127">Add/edit indicator</span></span>
- <span data-ttu-id="09d02-128">Ladda ned fil</span><span class="sxs-lookup"><span data-stu-id="09d02-128">Download file</span></span>
- <span data-ttu-id="09d02-129">Kontakta en hotexpert</span><span class="sxs-lookup"><span data-stu-id="09d02-129">Consult a threat expert</span></span>
- <span data-ttu-id="09d02-130">Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="09d02-130">Action center</span></span>

<span data-ttu-id="09d02-131">Mer information om de här åtgärderna finns i [Vidta svarsåtgärder för en fil.](respond-file-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="09d02-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="09d02-132">Filinformation, identifiering av skadlig kod och fildeektering</span><span class="sxs-lookup"><span data-stu-id="09d02-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="09d02-133">Filinformation, incident, identifiering av skadlig kod och arkiv som innehåller information om filen visar olika attribut om filen.</span><span class="sxs-lookup"><span data-stu-id="09d02-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="09d02-134">Du ser information som filens MD5, förhållandet för total virusidentifiering och Microsoft Defender AV-identifiering om det finns tillgängligt, samt filens läkare.</span><span class="sxs-lookup"><span data-stu-id="09d02-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="09d02-135">Filens kreditkort visar var filen sågs på enheter i organisationen och i hela världen.</span><span class="sxs-lookup"><span data-stu-id="09d02-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="09d02-136">Olika användare kan se olika värden i enheten i *organisationsavsnittet* av filens kreditkort.</span><span class="sxs-lookup"><span data-stu-id="09d02-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="09d02-137">Det beror på att kortet visar information baserat på RBAC-omfattningen som en användare har.</span><span class="sxs-lookup"><span data-stu-id="09d02-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="09d02-138">Det betyder att om en användare har beviljats insyn på en viss uppsättning enheter kan de bara se filen som organisatorisk mapp på de enheterna.</span><span class="sxs-lookup"><span data-stu-id="09d02-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![Bild av filinformation](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="09d02-140">Varningar</span><span class="sxs-lookup"><span data-stu-id="09d02-140">Alerts</span></span>

<span data-ttu-id="09d02-141">På **fliken** Aviseringar finns en lista med aviseringar som är associerade med filen.</span><span class="sxs-lookup"><span data-stu-id="09d02-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="09d02-142">Listan täcker mycket av samma information som kön Aviseringar, utom för enhetsgruppen, om sådan finns, den aktuella enheten tillhör.</span><span class="sxs-lookup"><span data-stu-id="09d02-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="09d02-143">Du kan välja vilken typ av information som visas genom att **välja Anpassa** kolumner i verktygsfältet ovanför kolumnrubrikerna.</span><span class="sxs-lookup"><span data-stu-id="09d02-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![Bild på aviseringar relaterade till filavsnittet](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="09d02-145">Observerad i organisationen</span><span class="sxs-lookup"><span data-stu-id="09d02-145">Observed in organization</span></span>

<span data-ttu-id="09d02-146">På **fliken Observerad i** organisationen kan du ange ett datumintervall för att se vilka enheter som har observerats med filen.</span><span class="sxs-lookup"><span data-stu-id="09d02-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="09d02-147">Den här fliken visar maximalt antal 100 enheter.</span><span class="sxs-lookup"><span data-stu-id="09d02-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="09d02-148">Om du _vill_ visa alla enheter med filen exporterar du fliken till en CSV-fil genom att välja **Exportera** i åtgärdsmenyn ovanför flikens kolumnrubriker.</span><span class="sxs-lookup"><span data-stu-id="09d02-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![Bild på den senaste observerade enheten med filen](images/atp-observed-machines.png)

<span data-ttu-id="09d02-150">Använd skjutreglaget eller områdesväljaren för att snabbt ange en tidsperiod som du vill kontrollera händelser som innefattar filen.</span><span class="sxs-lookup"><span data-stu-id="09d02-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="09d02-151">Du kan ange ett så litet tidsfönster som en enda dag.</span><span class="sxs-lookup"><span data-stu-id="09d02-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="09d02-152">Det gör att du kan se endast filer som kommunicerade med IP-adressen vid den tidpunkten, vilket avsevärt minskar onödig bläddring och sökning.</span><span class="sxs-lookup"><span data-stu-id="09d02-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="09d02-153">Djupanalys</span><span class="sxs-lookup"><span data-stu-id="09d02-153">Deep analysis</span></span>

<span data-ttu-id="09d02-154">På **fliken Djupanalys** [](respond-file-alerts.md#deep-analysis)kan du skicka filen för djupanalys för att få mer information om filens beteende och den effekt den får i dina organisationer.</span><span class="sxs-lookup"><span data-stu-id="09d02-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="09d02-155">När du har skickat filen visas den djupa analysrapporten på den här fliken när resultaten är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="09d02-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="09d02-156">Om djupanalys inte hittar något är rapporten tom och resultatutrymmet förblir tomt.</span><span class="sxs-lookup"><span data-stu-id="09d02-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![Bild av djupanalysfliken](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="09d02-158">Filnamn</span><span class="sxs-lookup"><span data-stu-id="09d02-158">File names</span></span>

<span data-ttu-id="09d02-159">På **fliken Filnamn** visas alla namn som filen har observerats att använda i dina organisationer.</span><span class="sxs-lookup"><span data-stu-id="09d02-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![Bild på fliken Filnamn](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="09d02-161">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="09d02-161">Related topics</span></span>

- [<span data-ttu-id="09d02-162">Visa och ordna microsoft Defender för slutpunktskön</span><span class="sxs-lookup"><span data-stu-id="09d02-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="09d02-163">Hantera Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="09d02-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="09d02-164">Undersöka Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="09d02-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="09d02-165">Undersöka enheter i listan Microsoft Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="09d02-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="09d02-166">Undersöka en IP-adress som är kopplad till en Microsoft Defender för Slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="09d02-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="09d02-167">Undersöka en domän som är kopplad till en Microsoft Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="09d02-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="09d02-168">Undersöka ett användarkonto i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="09d02-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="09d02-169">Utföra svarsåtgärder för en fil</span><span class="sxs-lookup"><span data-stu-id="09d02-169">Take response actions on a file</span></span>](respond-file-alerts.md)
