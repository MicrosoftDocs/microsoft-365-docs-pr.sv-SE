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
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300221"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="089ab-103">Grundläggande information för Hotutforskaren och Realtidsidentifieringar</span><span class="sxs-lookup"><span data-stu-id="089ab-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="089ab-104">I den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="089ab-104">In this article:</span></span>

- [<span data-ttu-id="089ab-105">Skillnader mellan identifiering av hotutforskaren och realtidsidentifiering</span><span class="sxs-lookup"><span data-stu-id="089ab-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="089ab-106">Obligatoriska licenser och behörigheter</span><span class="sxs-lookup"><span data-stu-id="089ab-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="089ab-107">Det här är en del av en **3-artikelserie** om grunderna för identifiering av  **hotutforskaren (Explorer),** e-postsäkerhet och Utforskaren och **realtidsidentifiering** (till exempel skillnader mellan verktygen och behörigheter som krävs för att hantera dem).</span><span class="sxs-lookup"><span data-stu-id="089ab-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="089ab-108">De andra två artiklarna i den här serien är [hot efter hotutforskaren](threat-hunting-in-threat-explorer.md) och [e-postsäkerhet med Threat Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="089ab-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="089ab-109">I den här artikeln förklaras skillnaden mellan att utforska hot och rapportering av identifieringar i realtid, och de licenser och behörigheter som krävs.</span><span class="sxs-lookup"><span data-stu-id="089ab-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="089ab-110">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="089ab-110">**Applies to**</span></span>
- [<span data-ttu-id="089ab-111">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="089ab-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="089ab-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="089ab-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="089ab-113">Om din organisation har Microsoft Defender för [Office 365](defender-for-office-365.md) [](#required-licenses-and-permissions)och du har behörighet kan du  använda Hotutforskaren **(som** kallas Utforskaren) eller identifieringar i realtid för att identifiera och åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="089ab-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="089ab-114">I **Säkerhets- & säkerhets- och** efterlevnadscenter går du till Hantering av hot och väljer **sedan Utforskaren**  **eller Identifieringar i realtid.**</span><span class="sxs-lookup"><span data-stu-id="089ab-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="089ab-115">Med Microsoft Defender för Office 365 abonnemang 2 visas:</span><span class="sxs-lookup"><span data-stu-id="089ab-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="089ab-116">Med Microsoft Defender för Office 365 abonnemang 1 visas:</span><span class="sxs-lookup"><span data-stu-id="089ab-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Hotutforskaren](../../media/threatmgmt-explorer.png)|![Identifiering i realtid](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="089ab-119">Med dessa verktyg kan du:</span><span class="sxs-lookup"><span data-stu-id="089ab-119">With these tools, you can:</span></span>

- <span data-ttu-id="089ab-120">Se skadlig programvara som upptäckts Microsoft 365 säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="089ab-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="089ab-121">Visa nätfiske-URL och klicka på bedömningsdata.</span><span class="sxs-lookup"><span data-stu-id="089ab-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="089ab-122">Starta en automatiserad undersökning och svarsprocess från en vy i Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="089ab-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="089ab-123">Undersök skadlig e-post med mera.</span><span class="sxs-lookup"><span data-stu-id="089ab-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="089ab-124">Mer information finns i [E-postsäkerhet med Hotutforskaren.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="089ab-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="089ab-125">Skillnader mellan identifiering av hotutforskaren och realtidsidentifiering</span><span class="sxs-lookup"><span data-stu-id="089ab-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="089ab-126">*Realtidsidentifiering är* ett rapporteringsverktyg som finns i Defender för Office 365 abonnemang 1.</span><span class="sxs-lookup"><span data-stu-id="089ab-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="089ab-127">*Threat Explorer* är ett sök- och åtgärdsverktyg för hot som finns i Defender för Office 365 abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="089ab-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="089ab-128">Med rapporten Realtidsidentifiering kan du visa identifieringar i realtid.</span><span class="sxs-lookup"><span data-stu-id="089ab-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="089ab-129">Threat Explorer gör detta också, men det ger ytterligare information för en viss attack, till exempel markera attackkampanjer och [](automated-investigation-response-office.md)ger säkerhetsgrupper möjlighet att åtgärda hot (inklusive utlösa en automatiserad undersökning och svarsundersökning).</span><span class="sxs-lookup"><span data-stu-id="089ab-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="089ab-130">Vyn *All e-post* är tillgänglig i Utforskaren med hot, men ingår inte i rapporten om identifieringar i realtid.</span><span class="sxs-lookup"><span data-stu-id="089ab-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="089ab-131">Filtreringsfunktioner och åtgärder för filtrering ingår i Utforskaren för hot.</span><span class="sxs-lookup"><span data-stu-id="089ab-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="089ab-132">Mer information finns i [Microsoft Defender för Office 365 Beskrivning: Funktionstillgänglighet i Defender för Office 365 abonnemang.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)</span><span class="sxs-lookup"><span data-stu-id="089ab-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="089ab-133">Obligatoriska licenser och behörigheter</span><span class="sxs-lookup"><span data-stu-id="089ab-133">Required licenses and permissions</span></span>

<span data-ttu-id="089ab-134">Du måste ha [Microsoft Defender Office 365](defender-for-office-365.md) kunna använda Utforskaren eller identifieringar i realtid:</span><span class="sxs-lookup"><span data-stu-id="089ab-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="089ab-135">Men Utforskaren ingår endast i Defender för Office 365 abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="089ab-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="089ab-136">Rapporten Identifieringar i realtid ingår i Defender för Office 365 abonnemang 1.</span><span class="sxs-lookup"><span data-stu-id="089ab-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="089ab-137">Säkerhetsåtgärder-team måste tilldela licenser för alla användare som ska skyddas av Defender för Office 365 och vara medvetna om att identifieringar i Utforskaren och Realtidsidentifiering visar identifieringsdata för licensierade användare.</span><span class="sxs-lookup"><span data-stu-id="089ab-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="089ab-138">Om du vill visa och *använda Utforskaren* eller Identifieringar i realtid måste du ha följande:</span><span class="sxs-lookup"><span data-stu-id="089ab-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="089ab-139">För Säkerhets- & Efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="089ab-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="089ab-140">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="089ab-140">Organization Management</span></span>
  - <span data-ttu-id="089ab-141">Säkerhetsadministratör (det här kan tilldelas Azure Active Directory administrationscentret ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="089ab-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="089ab-142">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="089ab-142">Security Reader</span></span>

- <span data-ttu-id="089ab-143">För Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="089ab-143">For Exchange Online:</span></span>

  - <span data-ttu-id="089ab-144">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="089ab-144">Organization Management</span></span>
  - <span data-ttu-id="089ab-145">View-Only organisationshantering</span><span class="sxs-lookup"><span data-stu-id="089ab-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="089ab-146">View-Only mottagare</span><span class="sxs-lookup"><span data-stu-id="089ab-146">View-Only Recipients</span></span>
  - <span data-ttu-id="089ab-147">Efterlevnadshantering</span><span class="sxs-lookup"><span data-stu-id="089ab-147">Compliance Management</span></span>

<span data-ttu-id="089ab-148">Mer information om roller och behörigheter finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="089ab-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="089ab-149">Behörigheter i Säkerhets- och efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="089ab-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="089ab-150">Funktionsbehörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="089ab-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="089ab-151">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="089ab-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="089ab-152">Mer information</span><span class="sxs-lookup"><span data-stu-id="089ab-152">More information</span></span>
- [<span data-ttu-id="089ab-153">Hotutforskaren samlar in e-postinformation på sidan för e-post entitet</span><span class="sxs-lookup"><span data-stu-id="089ab-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="089ab-154">Hitta och undersöka skadlig e-post som har levererats</span><span class="sxs-lookup"><span data-stu-id="089ab-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="089ab-155">Visa skadliga filer som upptäckts SharePoint Online, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="089ab-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="089ab-156">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="089ab-156">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="089ab-157">Automatisk undersökning och svar i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="089ab-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)