---
title: Övervaka och svara på sekretessincidenter för data i din organisation
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Använd gransknings- och aviseringsprinciper och dataförfrågningar för att övervaka och svara på incidenter med personuppgifter.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928430"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="c0f9c-103">Övervaka och svara på sekretessincidenter för data i din organisation</span><span class="sxs-lookup"><span data-stu-id="c0f9c-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="c0f9c-104">Microsoft 365-funktioner är tillgängliga så att du kan övervaka, undersöka och svara på datasekretessincidenter i din organisation när du driftiserar relaterade funktioner.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="c0f9c-105">Att ha processer, procedurer och annan dokumentation för var och en av dessa kan också vara viktigt för att visa efterlevnad för reglerande myndigheter.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="c0f9c-106">De omfattar:</span><span class="sxs-lookup"><span data-stu-id="c0f9c-106">These include:</span></span> 

- <span data-ttu-id="c0f9c-107">Gransknings- och aviseringsprinciper</span><span class="sxs-lookup"><span data-stu-id="c0f9c-107">Auditing and alert policies</span></span>
- <span data-ttu-id="c0f9c-108">Dataförfrågningar från registrerade personer (inklusive innehållssökning och eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="c0f9c-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="c0f9c-109">Ytterligare verktyg för marknadsföring och rapportering</span><span class="sxs-lookup"><span data-stu-id="c0f9c-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="c0f9c-110">Sekretessregler för data som påverkar användningen av övervaknings- och svarsverktyg</span><span class="sxs-lookup"><span data-stu-id="c0f9c-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="c0f9c-111">Här är ett exempel på en lista med regler för datasekretess som kan relatera till kontroller för informationsstyrning:</span><span class="sxs-lookup"><span data-stu-id="c0f9c-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="c0f9c-112">LGPD, artikel 46</span><span class="sxs-lookup"><span data-stu-id="c0f9c-112">LGPD Article 46</span></span>
- <span data-ttu-id="c0f9c-113">LGPD, artikel 48</span><span class="sxs-lookup"><span data-stu-id="c0f9c-113">LGPD Article 48</span></span>
- <span data-ttu-id="c0f9c-114">GDPR-artikel (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="c0f9c-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="c0f9c-115">GDPR-artikel (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="c0f9c-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="c0f9c-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="c0f9c-117">164,308(a)(1)(ii)(D))</span><span class="sxs-lookup"><span data-stu-id="c0f9c-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="c0f9c-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="c0f9c-119">164,308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="c0f9c-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="c0f9c-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="c0f9c-121">164,312(b))</span><span class="sxs-lookup"><span data-stu-id="c0f9c-121">164.312(b))</span></span>
- <span data-ttu-id="c0f9c-122">CCPA (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="c0f9c-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="c0f9c-123">Mer information finns i Utvärdera [datasekretessrisker och identifiera känslig information.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="c0f9c-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="c0f9c-124">Datasekretessbestämmelser uppmanar vanligtvis till följande för övervakning och svar:</span><span class="sxs-lookup"><span data-stu-id="c0f9c-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="c0f9c-125">Granska, meddela och rapportera aktiviteter som rör lagring, delning och bearbetning av personuppgifter</span><span class="sxs-lookup"><span data-stu-id="c0f9c-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="c0f9c-126">Möjligheten att svara på en data subject request (DSR) och i vissa fall utföra administrativa åtgärder för att uppfylla sådana begäranden.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="c0f9c-127">Din organisation kan också vilja utföra övervaknings- och svarsaktiviteter för andra ändamål, till exempel för andra efterlevnadsbehov eller av företagsskäl.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="c0f9c-128">Att upprätta ett system för övervakning och svar för datasekretess bör göras som en del av den övergripande uppföljnings- och svarsplaneringen, -implementeringen och -hanteringen.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="c0f9c-129">I den här artikeln finns användbara funktioner i Microsoft 365 för att få hjälp med att komma igång med övervakning och svarsschema i Microsoft 365 för att få svar på frågor som:</span><span class="sxs-lookup"><span data-stu-id="c0f9c-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="c0f9c-130">Vilken typ av teknik för övervakning, undersökning och rapportering finns tillgänglig för olika datatyper och källor?</span><span class="sxs-lookup"><span data-stu-id="c0f9c-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="c0f9c-131">Vilka mekanismer kommer att behövas för att hantera DSR-begäranden (Data Subject Requests) och alla åtgärder, till exempel anonymisering, redaion och borttagning.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="c0f9c-132">Gransknings- och aviseringsprinciper i Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="c0f9c-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="c0f9c-133">Läs följande artiklar för att konfigurera granskning, avancerad granskning och aviseringsprinciper:</span><span class="sxs-lookup"><span data-stu-id="c0f9c-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="c0f9c-134">Enhetlig granskning</span><span class="sxs-lookup"><span data-stu-id="c0f9c-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="c0f9c-135">Postlådegranskning</span><span class="sxs-lookup"><span data-stu-id="c0f9c-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="c0f9c-136">Avancerad granskning</span><span class="sxs-lookup"><span data-stu-id="c0f9c-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="c0f9c-137">Aviseringsprinciper</span><span class="sxs-lookup"><span data-stu-id="c0f9c-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="c0f9c-138">Data subject requests for the GDPR and CCPA</span><span class="sxs-lookup"><span data-stu-id="c0f9c-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="c0f9c-139">Se [Data Subject Requests för GDPR och CCPA](/compliance/regulatory/gdpr-dsr-Office365) för information om hur du svarar på en DSR i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-139">See [Data Subject Requests for the GDPR and CCPA](/compliance/regulatory/gdpr-dsr-Office365) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="c0f9c-140">Hantera borttagna användare i Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="c0f9c-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="c0f9c-141">När en användare för Microsoft Stream tas bort från Azure Active Directory (Azure AD), och om användarens namn var kopplat till en publicerad Stream-video innan den tidpunkten, förblir deras e-postadress kopplad till videon.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="c0f9c-142">Se [Hantera borttagna användare från Microsoft Stream om du vill](/stream/managing-deleted-users) ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-142">See [Manage deleted users from Microsoft Stream](/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="c0f9c-143">Insider-riskhantering som ett effektivt verktyg</span><span class="sxs-lookup"><span data-stu-id="c0f9c-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="c0f9c-144">[Insider-riskhantering i Microsoft 365](../compliance/insider-risk-management.md) är en funktion i administrationscentret för Microsofts efterlevnad som hjälper dig minimera den interna risken genom att du kan upptäcka, undersöka och vidta åtgärder för riskaktiviteter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c0f9c-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>