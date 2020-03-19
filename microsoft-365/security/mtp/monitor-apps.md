---
title: Appövervakning och rapportering i säkerhetscentret Microsoft 365
description: Beskriver hur du kan få mer insikt i användningen av molnappar i din organisation
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säkerhetscenter, övervaka, rapportera, appar
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f7b3f2fcaac71eefa2579a0c3fd66666fe00f605
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807654"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="abf94-104">Appövervakning och rapportering i säkerhetscentret Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="abf94-104">App monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="abf94-105">Dessa rapporter ger mer insikt i hur molnappar används i din organisation, inklusive vilka typer av appar, deras risknivå och aviseringar.</span><span class="sxs-lookup"><span data-stu-id="abf94-105">These reports provide more insight into how cloud apps are being used in your organization, including what kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="abf94-106">Övervaka e-postkonton i riskzonen</span><span class="sxs-lookup"><span data-stu-id="abf94-106">Monitor email accounts at risk</span></span>

<span data-ttu-id="abf94-107">**E-postskydd** visar e-postkonton i riskzonen.</span><span class="sxs-lookup"><span data-stu-id="abf94-107">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="abf94-108">Du kan klicka på ett konto för att undersöka vidare i Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="abf94-108">You can click an account to investigate further in Microsoft Defender Security Center.</span></span>

![E-postskyddskort](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="abf94-110">Övervaka appbehörigheter som beviljas av användare</span><span class="sxs-lookup"><span data-stu-id="abf94-110">Monitor app permissions granted by users</span></span>

<span data-ttu-id="abf94-111">**Cloud App Security - OAuth-appar** listar appar som upptäckts av Cloud App Security och som har beviljats behörighet av användare.</span><span class="sxs-lookup"><span data-stu-id="abf94-111">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="abf94-112">Cloud App Securitys riskkatalog innehåller över 16 000 appar som bedöms med över 70 riskfaktorer.</span><span class="sxs-lookup"><span data-stu-id="abf94-112">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="abf94-113">Riskfaktorerna utgår från allmän information, till exempel apputgivaren, till säkerhetsåtgärder och kontroller, till exempel om appen stöder kryptering i vila eller tillhandahåller en granskningslogg över användaraktivitet.</span><span class="sxs-lookup"><span data-stu-id="abf94-113">The risk factors start from general information, such as the app publisher, to security measures and controls, such as whether the app supports for encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App Security OAuth apps kort](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="abf94-115">Övervaka användarkonton för molnappar</span><span class="sxs-lookup"><span data-stu-id="abf94-115">Monitor cloud app user accounts</span></span>

<span data-ttu-id="abf94-116">**Molnappkonton för granskning** listar konton som kan behöva uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="abf94-116">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cloud App-konton för granskningskort](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="abf94-118">Förstå vilka molnappar som används</span><span class="sxs-lookup"><span data-stu-id="abf94-118">Understand which cloud apps are used</span></span>

<span data-ttu-id="abf94-119">**Identifierade molnappar (kategorier)** visar vilka typer av appar som används i din organisation och länkar till cloud discovery-instrumentpanelen i Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="abf94-119">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization and links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="abf94-120">Mer information finns i [Snabbstart: Arbeta med identifierade appar](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="abf94-120">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Kategorierna för identifierade molnappar](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="abf94-122">Övervaka var användare får åtkomst till molnappar</span><span class="sxs-lookup"><span data-stu-id="abf94-122">Monitor where users access cloud apps</span></span>

<span data-ttu-id="abf94-123">**Aktivitetsplatser för molnappar** visar var användarna har åtkomst till molnappar.</span><span class="sxs-lookup"><span data-stu-id="abf94-123">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Cloud App aktivitet platser kort](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="abf94-125">Övervaka hälsotillstånd för infrastrukturarbetsbelastningar</span><span class="sxs-lookup"><span data-stu-id="abf94-125">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="abf94-126">**Infrastrukturhälsa** visar hälsotillståndsaviseringar för infrastrukturarbetsbelastningar i Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="abf94-126">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="abf94-127">Azure Security Center tillhandahåller enhetlig säkerhetshantering och avancerat skydd mot hot över lokala arbetsbelastningar och molnarbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="abf94-127">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="abf94-128">Du kan samla in, söka efter och analysera säkerhetsdata från en mängd olika källor, inklusive brandväggar och andra partnerlösningar.</span><span class="sxs-lookup"><span data-stu-id="abf94-128">You can collect, search, and analyze security data from a variety of sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="abf94-129">Mer information finns i [Dokumentationen till Azure Security Center](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="abf94-129">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Hälsokort för infrastruktur](../../media/infrastructure-health.png)
