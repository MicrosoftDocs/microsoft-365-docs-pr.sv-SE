---
title: Grunderna i att identifiera hot i Utforskaren och i realtid i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Använd Utforskaren eller identifieringar i realtid för att undersöka och reagera på hot effektivt.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083194"
---
# <a name="explorer-and-real-time-detections-basics"></a><span data-ttu-id="05824-103">Grundläggande om identifiering av realtid i Utforskaren</span><span class="sxs-lookup"><span data-stu-id="05824-103">Explorer and Real-time detections basics</span></span>

<span data-ttu-id="05824-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="05824-104">**Applies to**</span></span>
- [<span data-ttu-id="05824-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="05824-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="05824-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05824-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="05824-107">I den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="05824-107">In this article:</span></span>

- [<span data-ttu-id="05824-108">Skillnader mellan Identifiering av Utforskaren och Realtidsidentifiering</span><span class="sxs-lookup"><span data-stu-id="05824-108">Differences between Explorer and Real-time detections</span></span>](#differences-between-explorer-and-real-time-detections)
- [<span data-ttu-id="05824-109">Obligatoriska licenser och behörigheter</span><span class="sxs-lookup"><span data-stu-id="05824-109">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="05824-110">Det här är en del av en **serie** med tre artiklar om **Utforskaren (kallas även Hotutforskaren),** e-postsäkerhet och Grundläggande identifieringar i Utforskaren och **Realtidsidentifiering** (till exempel skillnader mellan verktygen och behörigheter som krävs för att hantera dem).</span><span class="sxs-lookup"><span data-stu-id="05824-110">This is part of a **3-article series** on **Explorer (also known as Threat Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="05824-111">De andra två artiklarna i den här serien är [Hot efter hot i Utforskaren](threat-hunting-in-threat-explorer.md) och [E-postsäkerhet med Utforskaren.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="05824-111">The other two articles in this series are [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="05824-112">I den här artikeln förklaras skillnaden mellan rapportering av identifiering av realtid och de licenser och behörigheter som krävs.</span><span class="sxs-lookup"><span data-stu-id="05824-112">This article explains the difference between Explorer and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="05824-113">Om din organisation har Microsoft Defender för [Office 365](defender-for-office-365.md) [](#required-licenses-and-permissions)och du har behörighet kan du använda  **Utforskaren** (kallas även **Threat Explorer)** eller identifiering i realtid för att upptäcka och åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="05824-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** (also known as **Threat Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="05824-114">Gå till Microsoft 365 Defender <https://security.microsoft.com> **e-postsamarbete** **i & Microsoft 365 Defender och** välj sedan **Utforskaren** _eller_ Identifiering av realtid.</span><span class="sxs-lookup"><span data-stu-id="05824-114">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<span data-ttu-id="05824-115">Med dessa verktyg kan du:</span><span class="sxs-lookup"><span data-stu-id="05824-115">With these tools, you can:</span></span>

- <span data-ttu-id="05824-116">Se skadlig programvara som upptäckts Microsoft 365 säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="05824-116">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="05824-117">Visa nätfiske-URL och klicka på bedömningsdata.</span><span class="sxs-lookup"><span data-stu-id="05824-117">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="05824-118">Starta en automatiserad undersökning och svarsprocess från en vy i Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="05824-118">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="05824-119">Undersök skadlig e-post med mera.</span><span class="sxs-lookup"><span data-stu-id="05824-119">Investigate malicious email, and more.</span></span>

<span data-ttu-id="05824-120">Mer information finns i [E-postsäkerhet med Utforskaren.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="05824-120">For more information, see [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-explorer-and-real-time-detections"></a><span data-ttu-id="05824-121">Skillnader mellan Identifiering av Utforskaren och Realtidsidentifiering</span><span class="sxs-lookup"><span data-stu-id="05824-121">Differences between Explorer and Real-time detections</span></span>

- <span data-ttu-id="05824-122">*Realtidsidentifiering är* ett rapporteringsverktyg som finns i Defender för Office 365 abonnemang 1.</span><span class="sxs-lookup"><span data-stu-id="05824-122">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="05824-123">*Threat Explorer* är ett sök- och åtgärdsverktyg för hot som finns i Defender för Office 365 abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="05824-123">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="05824-124">Med rapporten Realtidsidentifiering kan du visa identifieringar i realtid.</span><span class="sxs-lookup"><span data-stu-id="05824-124">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="05824-125">Threat Explorer gör detta också, men det ger ytterligare information för en viss attack, till exempel markera attackkampanjer och [](automated-investigation-response-office.md)ger säkerhetsgrupper möjlighet att åtgärda hot (inklusive utlösa en automatiserad undersökning och svarsundersökning).</span><span class="sxs-lookup"><span data-stu-id="05824-125">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="05824-126">Vyn *All e-post* är tillgänglig i Utforskaren med hot, men ingår inte i rapporten om identifieringar i realtid.</span><span class="sxs-lookup"><span data-stu-id="05824-126">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="05824-127">Filtreringsfunktioner och åtgärder för filtrering ingår i Utforskaren för hot.</span><span class="sxs-lookup"><span data-stu-id="05824-127">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="05824-128">Mer information finns i [Microsoft Defender för Office 365 Beskrivning: Funktionstillgänglighet i Defender för Office 365 abonnemang.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)</span><span class="sxs-lookup"><span data-stu-id="05824-128">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="05824-129">Obligatoriska licenser och behörigheter</span><span class="sxs-lookup"><span data-stu-id="05824-129">Required licenses and permissions</span></span>

<span data-ttu-id="05824-130">Du måste ha [Microsoft Defender Office 365](defender-for-office-365.md) kunna använda Utforskaren eller identifieringar i realtid:</span><span class="sxs-lookup"><span data-stu-id="05824-130">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="05824-131">Utforskaren ingår endast i Defender för Office 365 abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="05824-131">Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="05824-132">Rapporten Identifieringar i realtid ingår i Defender för Office 365 abonnemang 1.</span><span class="sxs-lookup"><span data-stu-id="05824-132">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="05824-133">Säkerhetsåtgärder-team måste tilldela licenser för alla användare som ska skyddas av Defender för Office 365 och vara medvetna om att identifieringar i Utforskaren och Realtidsidentifiering visar identifieringsdata för licensierade användare.</span><span class="sxs-lookup"><span data-stu-id="05824-133">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="05824-134">Om du vill visa och *använda Utforskaren* eller Identifiering i realtid måste du ha följande behörigheter:</span><span class="sxs-lookup"><span data-stu-id="05824-134">To view and use Explorer *or* Real-time detections, you need the following permissions:</span></span>

- <span data-ttu-id="05824-135">I Defender för Office 365:</span><span class="sxs-lookup"><span data-stu-id="05824-135">In Defender for Office 365:</span></span>
  - <span data-ttu-id="05824-136">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="05824-136">Organization Management</span></span>
  - <span data-ttu-id="05824-137">Säkerhetsadministratör (det här kan tilldelas Azure Active Directory administrationscentret ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="05824-137">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="05824-138">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="05824-138">Security Reader</span></span>
- <span data-ttu-id="05824-139">I Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="05824-139">In Exchange Online:</span></span>
  - <span data-ttu-id="05824-140">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="05824-140">Organization Management</span></span>
  - <span data-ttu-id="05824-141">View-Only organisationshantering</span><span class="sxs-lookup"><span data-stu-id="05824-141">View-Only Organization Management</span></span>
  - <span data-ttu-id="05824-142">View-Only mottagare</span><span class="sxs-lookup"><span data-stu-id="05824-142">View-Only Recipients</span></span>
  - <span data-ttu-id="05824-143">Efterlevnadshantering</span><span class="sxs-lookup"><span data-stu-id="05824-143">Compliance Management</span></span>

<span data-ttu-id="05824-144">Mer information om roller och behörigheter finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="05824-144">To learn more about roles and permissions, see the following articles:</span></span>

- [<span data-ttu-id="05824-145">Behörigheter på Microsoft 365 Defender-portalen</span><span class="sxs-lookup"><span data-stu-id="05824-145">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="05824-146">Behörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="05824-146">Permissions in Exchange Online</span></span>](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a><span data-ttu-id="05824-147">Mer information</span><span class="sxs-lookup"><span data-stu-id="05824-147">More information</span></span>

- [<span data-ttu-id="05824-148">Hotutforskaren samlar in e-postinformation på sidan för e-post entitet</span><span class="sxs-lookup"><span data-stu-id="05824-148">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="05824-149">Hitta och undersöka skadlig e-post som har levererats</span><span class="sxs-lookup"><span data-stu-id="05824-149">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="05824-150">Visa skadliga filer som upptäckts SharePoint Online, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="05824-150">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="05824-151">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="05824-151">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="05824-152">Automatisk undersökning och svar i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="05824-152">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
