---
title: Övervaka och svara på datasekretessincidenter i din organisation
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Använd gransknings- och varningspolicyer och förfrågningar från registrerade för att övervaka och svara på personuppgiftsincidenter.
ms.openlocfilehash: 8fdba5799ca9ee97a013c1322e5e79f6bf38764a
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522079"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="98b76-103">Övervaka och svara på datasekretessincidenter i din organisation</span><span class="sxs-lookup"><span data-stu-id="98b76-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="98b76-104">Microsoft 365-funktioner är tillgängliga för att hjälpa dig att övervaka, undersöka och svara på datasekretessincidenter i organisationen när du operationaliserar relaterade funktioner.</span><span class="sxs-lookup"><span data-stu-id="98b76-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="98b76-105">Att ha processer, förfaranden och annan dokumentation för var och en av dessa kan också vara viktigt för att visa att tillsynsorganen följer reglerna.</span><span class="sxs-lookup"><span data-stu-id="98b76-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="98b76-106">De omfattar:</span><span class="sxs-lookup"><span data-stu-id="98b76-106">These include:</span></span> 

- <span data-ttu-id="98b76-107">Gransknings- och varningsprinciper</span><span class="sxs-lookup"><span data-stu-id="98b76-107">Auditing and alert policies</span></span>
- <span data-ttu-id="98b76-108">Förfrågningar från registrerade (inklusive innehållssökning och eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="98b76-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="98b76-109">Ytterligare utredningsverktyg och rapportering</span><span class="sxs-lookup"><span data-stu-id="98b76-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="98b76-110">Bestämmelser om datasekretess som påverkar användningen av övervaknings- och svarsverktyg</span><span class="sxs-lookup"><span data-stu-id="98b76-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="98b76-111">Här är ett exempel på datasekretessregler som kan relatera till informationsstyrningskontroller:</span><span class="sxs-lookup"><span data-stu-id="98b76-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="98b76-112">LGPD Artikel 46</span><span class="sxs-lookup"><span data-stu-id="98b76-112">LGPD Article 46</span></span>
- <span data-ttu-id="98b76-113">LGPD Artikel 48</span><span class="sxs-lookup"><span data-stu-id="98b76-113">LGPD Article 48</span></span>
- <span data-ttu-id="98b76-114">GDPR Artikel 5.1 f</span><span class="sxs-lookup"><span data-stu-id="98b76-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="98b76-115">GDPR Artikel 15.1 e</span><span class="sxs-lookup"><span data-stu-id="98b76-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="98b76-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="98b76-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="98b76-117">164.308 a.1 ii(D))</span><span class="sxs-lookup"><span data-stu-id="98b76-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="98b76-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="98b76-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="98b76-119">164.308 a.6 ii</span><span class="sxs-lookup"><span data-stu-id="98b76-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="98b76-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="98b76-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="98b76-121">164.312 b)</span><span class="sxs-lookup"><span data-stu-id="98b76-121">164.312(b))</span></span>
- <span data-ttu-id="98b76-122">CCPA (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="98b76-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="98b76-123">Mer information finns i [Bedöma datasekretessrisker och identifiera känslig information](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="98b76-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="98b76-124">Reglerna för datasekretess kräver i allmänhet följande för övervakning och svar:</span><span class="sxs-lookup"><span data-stu-id="98b76-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="98b76-125">Granskning, registrering och rapportering för aktiviteter som rör lagring, delning och behandling av personuppgifter</span><span class="sxs-lookup"><span data-stu-id="98b76-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="98b76-126">Möjligheten att svara på en registrerad begäran (DSR) och i vissa fall utföra utredningsåtgärder och andra administrativa åtgärder för att uppfylla sådana förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="98b76-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="98b76-127">Din organisation kan också vilja utföra övervaknings- och svarsaktiviteter för andra ändamål, till exempel andra efterlevnadsbehov eller av affärsmässiga skäl.</span><span class="sxs-lookup"><span data-stu-id="98b76-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="98b76-128">Upprätta ditt övervaknings- och svarssystem för datasekretess bör göras som en del av övergripande övervaknings- och svarsplanering, implementering och hantering.</span><span class="sxs-lookup"><span data-stu-id="98b76-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="98b76-129">För att hjälpa dig att komma igång med ett övervaknings- och svarsschema i Microsoft 365 för datasekretessbestämmelser innehåller den här artikeln en lista över användbara funktioner i Microsoft 365 för att svara på frågor som:</span><span class="sxs-lookup"><span data-stu-id="98b76-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="98b76-130">Vilken typ av daglig övervaknings-, utrednings- och rapporteringsteknik finns tillgänglig för de olika datatyperna och källorna?</span><span class="sxs-lookup"><span data-stu-id="98b76-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="98b76-131">Vilka mekanismer kommer att behövas för att hantera registrerade förfrågningar (DSRs) och eventuella avhjälpande åtgärder, till exempel anonymisering, bortredigeringsverktyg och radering.</span><span class="sxs-lookup"><span data-stu-id="98b76-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="98b76-132">Gransknings- och varningsprinciper i säkerhets- och efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="98b76-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="98b76-133">Se de här artiklarna för att konfigurera gransknings-, avancerade gransknings- och varningsprinciper:</span><span class="sxs-lookup"><span data-stu-id="98b76-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="98b76-134">Enhetlig granskning</span><span class="sxs-lookup"><span data-stu-id="98b76-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="98b76-135">Postlådegranskning</span><span class="sxs-lookup"><span data-stu-id="98b76-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="98b76-136">Avancerad granskning</span><span class="sxs-lookup"><span data-stu-id="98b76-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="98b76-137">Aviseringsprinciper</span><span class="sxs-lookup"><span data-stu-id="98b76-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="98b76-138">Registrerades begäran om GDPR och CCPA</span><span class="sxs-lookup"><span data-stu-id="98b76-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="98b76-139">Se [Registrerade förfrågningar om GDPR och CCPA](../compliance/gdpr-dsr-office365.md) för information om hur du svarar på en DSR i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98b76-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="98b76-140">Hantera borttagna användare i Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="98b76-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="98b76-141">När en användare tas bort från Azure Active Directory (Azure AD) för Microsoft Stream, om deras namn var associerat med en postad Stream-video före den punkten, förblir deras e-postadress associerad med videon.</span><span class="sxs-lookup"><span data-stu-id="98b76-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="98b76-142">Se [Hantera borttagna användare från Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) om du vill ta bort den.</span><span class="sxs-lookup"><span data-stu-id="98b76-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="additional-investigative-tools"></a><span data-ttu-id="98b76-143">Ytterligare utredningsverktyg</span><span class="sxs-lookup"><span data-stu-id="98b76-143">Additional investigative tools</span></span>

<span data-ttu-id="98b76-144">Här är ytterligare två verktyg som kan vara användbara för att övervaka, undersöka och åtgärda datasekretessrelaterade incidenter i organisationen:</span><span class="sxs-lookup"><span data-stu-id="98b76-144">Here are two additional tools that might be useful for monitoring, investigating, and remediating data privacy-related incidents in your organization:</span></span>

- <span data-ttu-id="98b76-145">[Insider-riskhantering i Microsoft 365](../compliance/insider-risk-management.md), en funktion i Microsoft Compliances administrationscenter för att minimera interna risker genom att du kan identifiera, undersöka och vidta åtgärder för riskfyllda aktiviteter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="98b76-145">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md), a feature of the Microsoft Compliance admin center to help minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
- <span data-ttu-id="98b76-146">[Dataundersökningar i Microsoft 365](../compliance/overview-data-investigations.md), en funktion i Microsoft Compliance admin center för att söka efter känsliga, skadliga eller felplacerade data över Microsoft 365, och sedan undersöka vad som hände med att vidta lämpliga åtgärder för att åtgärda händelsen.</span><span class="sxs-lookup"><span data-stu-id="98b76-146">[Data investigations in Microsoft 365](../compliance/overview-data-investigations.md), a feature of the Microsoft Compliance admin center to search for sensitive, malicious, or misplaced data across Microsoft 365, and then investigate what happened to take the appropriate actions to remediate the incident.</span></span>
