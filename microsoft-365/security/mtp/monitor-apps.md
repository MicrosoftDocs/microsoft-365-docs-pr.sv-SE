---
title: Programövervakning & rapportering – Säkerhetscenter
description: Lär dig hur du får mer insyn i hur du använder molnappen i din organisation. Omfattar olika typer av appar, deras risknivå och aviseringar.
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, appar
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
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930528"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="38353-105">Appövervakning och -rapportering i Microsoft 365 säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="38353-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="38353-106">De här rapporterna ger mer insyn i hur molnappar används i organisationen.</span><span class="sxs-lookup"><span data-stu-id="38353-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="38353-107">Omfattar olika typer av appar, deras risknivå och aviseringar.</span><span class="sxs-lookup"><span data-stu-id="38353-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="38353-108">Övervaka e-postkonton som är riskerade</span><span class="sxs-lookup"><span data-stu-id="38353-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="38353-109">**E-postskydd** visar att e-postkonton är riskerade.</span><span class="sxs-lookup"><span data-stu-id="38353-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="38353-110">Du kan välja ett konto om du vill undersöka ytterligare i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="38353-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![Kort för e-postskydd](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="38353-112">Övervaka programbehörigheter som beviljas av användare</span><span class="sxs-lookup"><span data-stu-id="38353-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="38353-113">**Cloud App Security – OAuth-appar** visar appar som upptäcks av Cloud App Security och som har beviljats behörighet av användare.</span><span class="sxs-lookup"><span data-stu-id="38353-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="38353-114">Cloud App Securitys riskkatalog innehåller över 16 000 appar som bedöms använda mer än 70 riskfaktorer.</span><span class="sxs-lookup"><span data-stu-id="38353-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="38353-115">Riskfaktorerna börjar med allmän information, som programutgivaren.</span><span class="sxs-lookup"><span data-stu-id="38353-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="38353-116">Sedan flyttas programmet till säkerhetsåtgärder och kontroller, till exempel om appen stöder kryptering i vila eller ger en granskningslogg över användaraktivitet.</span><span class="sxs-lookup"><span data-stu-id="38353-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![OAuth-appskort för Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="38353-118">Övervaka användarkonton i molnappen</span><span class="sxs-lookup"><span data-stu-id="38353-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="38353-119">**Molnappkonton för granskning listar** konton som kan behöva uppmärksammas.</span><span class="sxs-lookup"><span data-stu-id="38353-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cloud App-konton för granskningskort](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="38353-121">Förstå vilka molnappar som används</span><span class="sxs-lookup"><span data-stu-id="38353-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="38353-122">**Identifierade molnappar (kategorier)** visar vilka typer av appar som används i organisationen.</span><span class="sxs-lookup"><span data-stu-id="38353-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="38353-123">Den länkar till instrumentpanelen för molnidentifiering i Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="38353-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="38353-124">Mer information finns i [Snabbstart: Arbeta med identifierade appar.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="38353-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Identifierat kategorikort för molnappar](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="38353-126">Övervaka var användare får åtkomst till molnappar</span><span class="sxs-lookup"><span data-stu-id="38353-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="38353-127">**Platser för aktivitet i molnappar** visar var användare använder molnappar.</span><span class="sxs-lookup"><span data-stu-id="38353-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Kort för aktivitet i Molnapp](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="38353-129">Övervaka hälsotillståndet för arbetsbelastningen för infrastrukturen</span><span class="sxs-lookup"><span data-stu-id="38353-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="38353-130">**Infrastrukturstatus visar** hälsostatusvarningar om infrastrukturarbetsbelastningar i Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="38353-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="38353-131">Azure Defender ger enhetlig säkerhetshantering och Defender för Office 365 i både lokala och molnbaserade arbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="38353-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="38353-132">Du kan samla in, söka efter och analysera säkerhetsdata från olika källor, inklusive brandväggar och andra partnerlösningar.</span><span class="sxs-lookup"><span data-stu-id="38353-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="38353-133">Mer information finns i [Azure Defender-dokumentationen.](https://docs.microsoft.com/azure/security-center/)</span><span class="sxs-lookup"><span data-stu-id="38353-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Hälsokort för infrastruktur](../../media/infrastructure-health.png)
