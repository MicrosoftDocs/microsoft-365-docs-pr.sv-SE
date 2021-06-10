---
title: Aktivera den begränsade regelbunden Microsoft Defender Antivirus genomsökningsfunktionen
description: Med begränsad regelbunden genomsökning kan du Microsoft Defender Antivirus förutom dina andra installerade AV-leverantörer
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2ae56c0f67501eb8603d5d28c4ed0c4af01a8c9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274607"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="d531d-104">Använd begränsad periodisk genomsökning i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="d531d-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d531d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d531d-105">**Applies to:**</span></span>

- [<span data-ttu-id="d531d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d531d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d531d-107">Begränsad regelbunden genomsökning är en särskild typ av identifiering och åtgärd av hot som kan aktiveras när du har installerat en annan antivirusprodukt på en annan Windows 10 enhet.</span><span class="sxs-lookup"><span data-stu-id="d531d-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="d531d-108">Det kan bara aktiveras i vissa situationer.</span><span class="sxs-lookup"><span data-stu-id="d531d-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="d531d-109">Mer information om begränsad regelbunden genomsökning och hur Microsoft Defender Antivirus fungerar med andra antivirusprogram finns [i Microsoft Defender Antivirus kompatibilitet.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="d531d-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="d531d-110">**Microsoft rekommenderar inte att du använder den här funktionen i företagsmiljöer. Det här är en funktion som främst är avsedd för konsumenter.**</span><span class="sxs-lookup"><span data-stu-id="d531d-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="d531d-111">Den här funktionen använder endast en begränsad delmängd av Microsoft Defender Antivirus-funktionerna för att identifiera skadlig programvara och kommer inte att kunna identifiera den största delen av skadlig programvara och potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="d531d-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="d531d-112">Dessutom är hanterings- och rapporteringsfunktionerna begränsade.</span><span class="sxs-lookup"><span data-stu-id="d531d-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="d531d-113">Microsoft rekommenderar företag att välja sin primära antiviruslösning och använda den exklusivt.</span><span class="sxs-lookup"><span data-stu-id="d531d-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="d531d-114">Aktivera begränsad regelbunden genomsökning</span><span class="sxs-lookup"><span data-stu-id="d531d-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="d531d-115">Som standard aktiveras Microsoft Defender Antivirus på en Windows 10-enhet om det inte finns någon annan antivirusprodukt installerad, eller om den andra produkten är inaktiv, har gått ut eller inte fungerar som den ska.</span><span class="sxs-lookup"><span data-stu-id="d531d-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="d531d-116">Om Microsoft Defender Antivirus har aktiverats visas de vanliga alternativen för att konfigurera den på den enheten:</span><span class="sxs-lookup"><span data-stu-id="d531d-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![Windows-säkerhet-app som visar Microsoft Defender AV-alternativ, inklusive alternativ för genomsökning, inställningar och uppdateringsalternativ](images/vtp-wdav.png)

<span data-ttu-id="d531d-118">Om ett annat antivirusprogram är installerat och fungerar som det ska Microsoft Defender Antivirus av sig själv.</span><span class="sxs-lookup"><span data-stu-id="d531d-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="d531d-119">Appen Windows-säkerhet ändrar avsnittet **Skydd mot &** virus för att visa status om av-produkten, och ge en länk till produktens konfigurationsalternativ.</span><span class="sxs-lookup"><span data-stu-id="d531d-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="d531d-120">Under eventuella avI-produkter från tredje part visas en ny länk **Microsoft Defender Antivirus alternativ**.</span><span class="sxs-lookup"><span data-stu-id="d531d-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="d531d-121">Om du klickar på länken expanderas växlingsknappen som aktiverar begränsad regelbunden genomsökning.</span><span class="sxs-lookup"><span data-stu-id="d531d-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="d531d-122">Observera att det begränsade periodiska alternativet är en växlingsknapp för att aktivera eller inaktivera regelbunden genomsökning.</span><span class="sxs-lookup"><span data-stu-id="d531d-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="d531d-123">Om du för skjut **reglaget** till På visas standardalternativen för Microsoft Defender AV under tredje parts AV-produkt.</span><span class="sxs-lookup"><span data-stu-id="d531d-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="d531d-124">Det begränsade alternativet för regelbunden genomsökning visas längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="d531d-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d531d-125">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="d531d-125">Related articles</span></span>

- [<span data-ttu-id="d531d-126">Konfigurera skydd för beteende, heuristisk och realtid</span><span class="sxs-lookup"><span data-stu-id="d531d-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d531d-127">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="d531d-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)