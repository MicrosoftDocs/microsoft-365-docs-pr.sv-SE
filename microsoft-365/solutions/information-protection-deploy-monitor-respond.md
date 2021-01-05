---
title: Övervaka och svara på data integritets incidenter i din organisation
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
description: Använd gransknings-och larm principer och data subjekt förfrågningar för att övervaka och svara på frågor om person uppgifter.
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749593"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="246cc-103">Övervaka och svara på data integritets incidenter i din organisation</span><span class="sxs-lookup"><span data-stu-id="246cc-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="246cc-104">Microsoft 365-funktioner är tillgängliga för att hjälpa dig att övervaka, undersöka och svara på data integritets incidenter i din organisation när du operationalize relaterade funktioner.</span><span class="sxs-lookup"><span data-stu-id="246cc-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="246cc-105">Att ha processer, procedurer och annan dokumentation för var och en av dessa kan också vara viktiga för att påvisa efterlevnad av myndighets organ.</span><span class="sxs-lookup"><span data-stu-id="246cc-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="246cc-106">De omfattar:</span><span class="sxs-lookup"><span data-stu-id="246cc-106">These include:</span></span> 

- <span data-ttu-id="246cc-107">Principer för granskning och avisering</span><span class="sxs-lookup"><span data-stu-id="246cc-107">Auditing and alert policies</span></span>
- <span data-ttu-id="246cc-108">Data subjekt begär Anden (inklusive innehålls sökning och eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="246cc-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="246cc-109">Ytterligare verktyg och rapporter</span><span class="sxs-lookup"><span data-stu-id="246cc-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="246cc-110">Data integritets regler som påverkar användning av övervaknings-och svars verktyg</span><span class="sxs-lookup"><span data-stu-id="246cc-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="246cc-111">Här är ett exempel på en lista över data integritets regler som kan gälla för informations styrnings kontroller:</span><span class="sxs-lookup"><span data-stu-id="246cc-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="246cc-112">LGPD artikel 46</span><span class="sxs-lookup"><span data-stu-id="246cc-112">LGPD Article 46</span></span>
- <span data-ttu-id="246cc-113">LGPD artikel 48</span><span class="sxs-lookup"><span data-stu-id="246cc-113">LGPD Article 48</span></span>
- <span data-ttu-id="246cc-114">GDPR-artikel (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="246cc-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="246cc-115">GDPR-artikel (15) (1) (e)</span><span class="sxs-lookup"><span data-stu-id="246cc-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="246cc-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="246cc-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="246cc-117">164.308 (a) (1) (II) (D))</span><span class="sxs-lookup"><span data-stu-id="246cc-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="246cc-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="246cc-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="246cc-119">164.308 (a) (6) (II)</span><span class="sxs-lookup"><span data-stu-id="246cc-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="246cc-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="246cc-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="246cc-121">164.312 (b))</span><span class="sxs-lookup"><span data-stu-id="246cc-121">164.312(b))</span></span>
- <span data-ttu-id="246cc-122">CCPA (1798.105 (c))</span><span class="sxs-lookup"><span data-stu-id="246cc-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="246cc-123">Mer information finns i [utvärdera data integritets risker och identifiera känslig information](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="246cc-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="246cc-124">Reglerna för data integritet tar vanligt vis upp följande för övervakning och svar:</span><span class="sxs-lookup"><span data-stu-id="246cc-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="246cc-125">Granskning, avisering och rapportering för aktiviteter relaterade till lagring, delning och bearbetning av person uppgifter</span><span class="sxs-lookup"><span data-stu-id="246cc-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="246cc-126">Möjligheten att svara på en fråga om data som kan besvaras (DSR) och i vissa fall genomföra utredning och andra administrativa åtgärder för att uppfylla sådana önskemål.</span><span class="sxs-lookup"><span data-stu-id="246cc-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="246cc-127">Organisationen kan också välja att utföra övervakning och svars aktiviteter i andra syften, till exempel andra behov eller av affärs skäl.</span><span class="sxs-lookup"><span data-stu-id="246cc-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="246cc-128">Att fastställa övervaknings-och svars schema för data integritet ska utföras som en del av övergripande övervakning och svars planering, implementering och hantering.</span><span class="sxs-lookup"><span data-stu-id="246cc-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="246cc-129">För att hjälpa dig att komma igång med ett övervaknings-och svars schema i Microsoft 365 för data integritets regler, visar den här artikeln användbara funktioner i Microsoft 365 för att besvara frågor som:</span><span class="sxs-lookup"><span data-stu-id="246cc-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="246cc-130">Vilken sorts daglig övervakning, undersöknings-och rapporterings teknik finns tillgängliga för de olika data typerna och källorna?</span><span class="sxs-lookup"><span data-stu-id="246cc-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="246cc-131">Vilka mekanismer behövs för att hantera data ämnes förfrågningar (DSRs) och eventuella hjälp åtgärder, till exempel anonymisering, bortredigering och borttagning.</span><span class="sxs-lookup"><span data-stu-id="246cc-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="246cc-132">Principer för granskning och larm i säkerhets-och kompatibilitetstillstånd</span><span class="sxs-lookup"><span data-stu-id="246cc-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="246cc-133">Se de här artiklarna för att konfigurera granskning, avancerad granskning och aviserings principer:</span><span class="sxs-lookup"><span data-stu-id="246cc-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="246cc-134">Enhetlig granskning</span><span class="sxs-lookup"><span data-stu-id="246cc-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="246cc-135">Postlådegranskning</span><span class="sxs-lookup"><span data-stu-id="246cc-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="246cc-136">Avancerad granskning</span><span class="sxs-lookup"><span data-stu-id="246cc-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="246cc-137">Aviseringsprinciper</span><span class="sxs-lookup"><span data-stu-id="246cc-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="246cc-138">Data subjekt begär Anden för GDPR och CCPA</span><span class="sxs-lookup"><span data-stu-id="246cc-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="246cc-139">Information om hur du svarar på en DSR-data i Microsoft 365 finns i artikeln om [GDPR och CCPA](../compliance/gdpr-dsr-office365.md) .</span><span class="sxs-lookup"><span data-stu-id="246cc-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="246cc-140">Hantera borttagna användare i Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="246cc-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="246cc-141">För Microsoft Stream, när en användare tas bort från Azure Active Directory (Azure AD), om deras namn var kopplad till en bokförd direkt uppspelnings video innan den punkten förblir e-postadressen kopplad till videon.</span><span class="sxs-lookup"><span data-stu-id="246cc-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="246cc-142">Se [Hantera borttagna användare från Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) för att ta bort den.</span><span class="sxs-lookup"><span data-stu-id="246cc-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="246cc-143">Insider riskhantering som ett undersöknings verktyg</span><span class="sxs-lookup"><span data-stu-id="246cc-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="246cc-144">[Insider riskhantering i microsoft 365](../compliance/insider-risk-management.md) är en funktion i Microsoft Support Administration Center som hjälper dig att minimera intern risken genom att låta dig upptäcka, undersöka och vidta åtgärder för riskfyllda aktiviteter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="246cc-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
