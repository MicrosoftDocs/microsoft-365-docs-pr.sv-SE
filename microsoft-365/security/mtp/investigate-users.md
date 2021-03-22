---
title: Undersöka användare i Microsoft 365 Säkerhetscenter
description: undersöka användare i Säkerhetscenter för Microsoft 365
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, identiteter, data, enheter, appar
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 32c496a212e038d649fdc9880c8ac829ee4a5337
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927246"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="addf0-104">Undersöka användare i Microsoft 365 Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="addf0-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="addf0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="addf0-105">**Applies to:**</span></span>

- <span data-ttu-id="addf0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="addf0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="addf0-107">Som en del av din undersökning kan du se att en användare har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="addf0-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="addf0-108">Användarsidan för Microsoft 365 säkerhetscenter kombinerar information från Microsoft Defender för Slutpunkt, Microsoft Defender för identitet och Microsoft Cloud App-säkerhet (beroende på vilka licenser du har).</span><span class="sxs-lookup"><span data-stu-id="addf0-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="addf0-109">Den här sidan är en idealisk utgångspunkt för att undersöka användare och potentiella incidenter.</span><span class="sxs-lookup"><span data-stu-id="addf0-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="addf0-110">![Användarsida](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="addf0-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="addf0-111">På den här sidan visas information som är specifik för säkerhetsrisken för en användare.</span><span class="sxs-lookup"><span data-stu-id="addf0-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="addf0-112">Detta omfattar en poäng som hjälper till att utvärdera risker, nya händelser och varningar som bidragit till den totala risken för användaren med mera.</span><span class="sxs-lookup"><span data-stu-id="addf0-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="addf0-113">Du kan komma åt den här sidan från flera områden i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="addf0-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="addf0-114">Du kan komma åt den här sidan från en specifik händelse på **fliken** Användare. Vissa aviseringar kan inkludera användare som en specifik tillgång som påverkas.</span><span class="sxs-lookup"><span data-stu-id="addf0-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="addf0-115">Du kan också söka efter användare.</span><span class="sxs-lookup"><span data-stu-id="addf0-115">You can also search for users.</span></span>  

<span data-ttu-id="addf0-116">Läs mer om hur du undersöker användare och potentiella risker [i den här självstudiekursen om Cloud App-säkerhet.](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them)</span><span class="sxs-lookup"><span data-stu-id="addf0-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="addf0-117">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="addf0-117">Related topics</span></span>

- [<span data-ttu-id="addf0-118">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="addf0-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="addf0-119">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="addf0-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="addf0-120">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="addf0-120">Manage incidents</span></span>](manage-incidents.md)