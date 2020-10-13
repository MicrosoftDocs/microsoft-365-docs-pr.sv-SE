---
title: Program övervakning & rapportering-säkerhets Center
description: Lär dig mer om hur du får mer insikt i moln programmet i din organisation. Inkluderar olika typer av appar, deras risk nivå och aviseringar.
keywords: säkerhet, skadlig program vara, Microsoft 365, M365, säkerhets Center, övervaka, rapport, appar
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
ms.openlocfilehash: 8787bf212db342c84f13f8522e8853310e00c0ce
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429413"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="3b682-105">Program övervakning och rapportering i säkerhets Center för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b682-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3b682-106">Rapporterna visar mer information om hur molnappar används i din organisation.</span><span class="sxs-lookup"><span data-stu-id="3b682-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="3b682-107">Inkluderar olika typer av appar, deras risk nivå och aviseringar.</span><span class="sxs-lookup"><span data-stu-id="3b682-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="3b682-108">Övervaka e-postkonton</span><span class="sxs-lookup"><span data-stu-id="3b682-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="3b682-109">**E-postskydd** visar e-postkonton med risk.</span><span class="sxs-lookup"><span data-stu-id="3b682-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="3b682-110">Du kan välja ett konto att undersöka i Microsoft Defender säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="3b682-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![E-postskydd](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="3b682-112">Övervaka program behörigheter som beviljats av användare</span><span class="sxs-lookup"><span data-stu-id="3b682-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="3b682-113">**Cloud App-säkerhet – appar för OAuth-appar** som identifieras av Cloud App Security som har beviljats behörigheter av användare.</span><span class="sxs-lookup"><span data-stu-id="3b682-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="3b682-114">Cloud App Security-risk katalogen inkluderar över 16 000-program som utvärderas med över 70-riskfaktorer.</span><span class="sxs-lookup"><span data-stu-id="3b682-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="3b682-115">Riskfaktorerna börjar med allmän information, till exempel program utgivaren.</span><span class="sxs-lookup"><span data-stu-id="3b682-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="3b682-116">Därefter flyttas den till säkerhets åtgärder och kontroller, till exempel om appen stöder kryptering på andra eller om det finns en Gransknings logg för användar aktivitet.</span><span class="sxs-lookup"><span data-stu-id="3b682-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App-säkerhet för OAuth-appar](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="3b682-118">Övervaka användar konton för moln program</span><span class="sxs-lookup"><span data-stu-id="3b682-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="3b682-119">**Cloud App-konton för gransknings** listor konton som kan behöva åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="3b682-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cloud App-konton för gransknings kort](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="3b682-121">Förstå vilka molnappar som används</span><span class="sxs-lookup"><span data-stu-id="3b682-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="3b682-122">**Upptäckta moln program (kategorier)** visar vilka typer av program som används i din organisation.</span><span class="sxs-lookup"><span data-stu-id="3b682-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="3b682-123">Den länkar till moln identifierings instrument panelen i Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="3b682-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="3b682-124">Mer information finns i [snabb start: arbeta med upptäckta appar](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="3b682-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Kategori kort för identifierade molnappar](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="3b682-126">Övervaka var användare kommer åt molnappar</span><span class="sxs-lookup"><span data-stu-id="3b682-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="3b682-127">**Cloud App Activity locations** visar var användarna kan komma åt molnappar.</span><span class="sxs-lookup"><span data-stu-id="3b682-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Moln programs aktivitets plats kort](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="3b682-129">Övervaka hälsa för infrastruktur arbets belastningar</span><span class="sxs-lookup"><span data-stu-id="3b682-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="3b682-130">**Infrastruktur hälsa** visar hälso status varningar för infrastruktur arbets belastning i Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="3b682-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="3b682-131">Med Azure Security Center får du enhetlig säkerhets hantering och Avancerat skydd för lokala och moln arbets belastningar.</span><span class="sxs-lookup"><span data-stu-id="3b682-131">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="3b682-132">Du kan samla in, söka efter och analysera säkerhets data från olika källor, bland annat brand väggar och andra partner lösningar.</span><span class="sxs-lookup"><span data-stu-id="3b682-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="3b682-133">Mer information finns i [dokumentationen för Azure säkerhets Center](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="3b682-133">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Infrastruktur hälso kort](../../media/infrastructure-health.png)
