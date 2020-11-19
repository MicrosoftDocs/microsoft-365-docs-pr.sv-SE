---
title: Övervaka och Visa rapporter – säkerhets Center
description: Här beskrivs hur Microsoft 365 säkerhets Center ger en översikt över skydds-och säkerhets status.
keywords: säkerhet, skadlig program vara, Microsoft 365, M365, säkerhets Center, övervaka, rapport, status
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d52c401c4b2e995e5ec18895c158f77ce0fce746
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356889"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="3ea19-104">Övervaka och Visa rapporter i Microsoft 365 säkerhets Center</span><span class="sxs-lookup"><span data-stu-id="3ea19-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="3ea19-105">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="3ea19-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="3ea19-106">Du kan [utvärdera det i en labb miljö](https://aka.ms/mtp-trial-lab) eller [köra ett pilot projekt i produktionen](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="3ea19-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="3ea19-107">I säkerhets Center för Microsoft 365 finns en sammanfattning av skydds-och säkerhets status i Microsoft 365-miljön.</span><span class="sxs-lookup"><span data-stu-id="3ea19-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="3ea19-108">Säkerhets Center innehåller avsnittet **rapporter** som är en värd för kort som omfattar en mängd olika områden.</span><span class="sxs-lookup"><span data-stu-id="3ea19-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="3ea19-109">Säkerhets analyser och administratörer kan spåra korten som en del av deras dagliga operationer.</span><span class="sxs-lookup"><span data-stu-id="3ea19-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="3ea19-110">För att detaljgranska kan kort tillhandahålla detaljerade rapporter och, i vissa fall, hanterings alternativ.</span><span class="sxs-lookup"><span data-stu-id="3ea19-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="3ea19-111">Anpassa vyer</span><span class="sxs-lookup"><span data-stu-id="3ea19-111">Customize views</span></span>

<span data-ttu-id="3ea19-112">Som standard grupperas korten i dessa kategorier:</span><span class="sxs-lookup"><span data-stu-id="3ea19-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="3ea19-113">[Identiteter](monitor-and-report-identities.md) – användar konton och autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="3ea19-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="3ea19-114">[Data](monitor-data.md) – e-post och dokument innehåll</span><span class="sxs-lookup"><span data-stu-id="3ea19-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="3ea19-115">[Enheter](monitor-devices.md) – datorer, mobil telefoner och andra enheter</span><span class="sxs-lookup"><span data-stu-id="3ea19-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="3ea19-116">[Appar](monitor-apps.md) – program och anslutna online tjänster</span><span class="sxs-lookup"><span data-stu-id="3ea19-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="3ea19-117">Växla till **Gruppera efter ämne** för att ordna om korten och gruppera dem i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="3ea19-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="3ea19-118">**Risk** -kort som framhäver enheter, till exempel konton och enheter, som kan vara utsatta för risk.</span><span class="sxs-lookup"><span data-stu-id="3ea19-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="3ea19-119">Dessa kort kan också framhäva potentiella risk källor, till exempel nya hot-kampanjer och behöriga molnappar</span><span class="sxs-lookup"><span data-stu-id="3ea19-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="3ea19-120">**Identifierings trender** -kort som markerar nya hot identifieringar, avvikelser och policy överträdelser</span><span class="sxs-lookup"><span data-stu-id="3ea19-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="3ea19-121">**Konfiguration och hälsa** -kort som täcker konfiguration och distribution av säkerhets kontroller, inklusive enhetens registrerings tillstånd för Management Services</span><span class="sxs-lookup"><span data-stu-id="3ea19-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="3ea19-122">**Övrigt** – alla andra kort kategoriseras inte under andra ämnen</span><span class="sxs-lookup"><span data-stu-id="3ea19-122">**Other** - all other cards not categorized under other topics</span></span>
