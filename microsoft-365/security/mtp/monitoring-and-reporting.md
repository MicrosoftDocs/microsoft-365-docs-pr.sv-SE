---
title: Övervaka och visa rapporter – Säkerhetscenter
description: Här beskrivs hur Säkerhetscenter i Microsoft 365 ger en översikt över skydd och säkerhetsstatus.
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, status
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4667c39a8d416d7e186d41063d7057109758cd33
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930408"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="d21f1-104">Övervaka och visa rapporter i Microsoft 365 säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="d21f1-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="d21f1-105">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="d21f1-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="d21f1-106">Du kan [utvärdera det i en labbmiljö](https://aka.ms/mtp-trial-lab) eller köra [pilotprojektet i produktion.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="d21f1-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="d21f1-107">Microsoft 365 säkerhetscenter ger en sammanfattning av säkerhetsstatus i din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="d21f1-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="d21f1-108">Säkerhetscentret innehåller avsnittet **Rapporter** med en mängd kort som täcker flera olika områden.</span><span class="sxs-lookup"><span data-stu-id="d21f1-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="d21f1-109">Säkerhetsanalytiker och -administratörer kan spåra korten som en del av sin dagliga verksamhet.</span><span class="sxs-lookup"><span data-stu-id="d21f1-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="d21f1-110">När du gör en detaljerad detaljgranskning ger kort detaljerade rapporter och, i vissa fall, hanteringsalternativ.</span><span class="sxs-lookup"><span data-stu-id="d21f1-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="d21f1-111">Anpassa vyer</span><span class="sxs-lookup"><span data-stu-id="d21f1-111">Customize views</span></span>

<span data-ttu-id="d21f1-112">Som standard grupperas korten i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="d21f1-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="d21f1-113">[Identiteter](monitor-and-report-identities.md) – användarkonton och autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="d21f1-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="d21f1-114">[Data](monitor-data.md) – e-post och dokumentinnehåll</span><span class="sxs-lookup"><span data-stu-id="d21f1-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="d21f1-115">[Enheter](monitor-devices.md) – datorer, mobiltelefoner och andra enheter</span><span class="sxs-lookup"><span data-stu-id="d21f1-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="d21f1-116">[Appar](monitor-apps.md) – program och bifogade onlinetjänster</span><span class="sxs-lookup"><span data-stu-id="d21f1-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="d21f1-117">Växla till **Gruppera efter ämne** för att ordna om korten och gruppera dem i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="d21f1-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="d21f1-118">**Risk** – kort som framhäver enheter, till exempel konton och enheter, som kan vara i riskzonen.</span><span class="sxs-lookup"><span data-stu-id="d21f1-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="d21f1-119">De här korten markerar även möjliga riskkällor, till exempel nya hotkampanjer och privilegierade molnappar</span><span class="sxs-lookup"><span data-stu-id="d21f1-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="d21f1-120">**Identifieringstrender** – kort som markerar nya identifieringar av hot, intrång och principbrott</span><span class="sxs-lookup"><span data-stu-id="d21f1-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="d21f1-121">**Konfiguration och hälsa** – kort som täcker konfiguration och distribution av säkerhetskontroller, inklusive enhets onboarding-tillstånd till hanteringstjänster</span><span class="sxs-lookup"><span data-stu-id="d21f1-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="d21f1-122">**Övriga** – alla andra kort kategoriseras inte under andra ämnen</span><span class="sxs-lookup"><span data-stu-id="d21f1-122">**Other** - all other cards not categorized under other topics</span></span>
