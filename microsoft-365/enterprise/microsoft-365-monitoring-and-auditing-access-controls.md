---
title: Microsoft 365 övervakning och granskning av Access-kontroller
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 'Sammanfattning: en sammanfattning av de olika kontroll-och gransknings kontroller som finns tillgängliga i Microsoft 365.'
ms.openlocfilehash: f1302c4056bfd605e35aae08d8f5355f8d204db2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694645"
---
# <a name="monitoring-and-auditing-access-controls-in-microsoft-365"></a><span data-ttu-id="681e8-103">Övervaka och granska Access-kontroller i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="681e8-103">Monitoring and Auditing Access Controls in Microsoft 365</span></span>

<span data-ttu-id="681e8-104">Microsoft utför omfattande övervakning och granskning av alla delegeringar, behörigheter och åtgärder som sker i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="681e8-104">Microsoft performs extensive monitoring and auditing of all delegation, privileges, and operations that occur within Microsoft 365.</span></span> <span data-ttu-id="681e8-105">Microsoft 365 Access Control är en automatiserad process som är inbyggd i principen om minst privilegium och som innehåller kontroller för data åtkomst och granskningar:</span><span class="sxs-lookup"><span data-stu-id="681e8-105">Microsoft 365 access control is an automated process built on the principle of least privilege and incorporating data access controls and audits:</span></span>

- <span data-ttu-id="681e8-106">Alla tillåtna åtkomster går att spåra till en unik användare.</span><span class="sxs-lookup"><span data-stu-id="681e8-106">All permitted access is traceable to a unique user.</span></span> <span data-ttu-id="681e8-107">Det är möjligt för administratörer att hantera kund innehåll.</span><span class="sxs-lookup"><span data-stu-id="681e8-107">Administrators are accountable for their handling of customer content.</span></span>
- <span data-ttu-id="681e8-108">Förfrågningar om åtkomst kontroll, godkännande och administrativa åtgärder sparas för att analysera säkerhets-och illvilliga händelser.</span><span class="sxs-lookup"><span data-stu-id="681e8-108">Access control requests, approvals, and administrative operations logs are captured for analysis of security and malicious events.</span></span>
- <span data-ttu-id="681e8-109">Åtkomst nivåer granskas i nära real tid baserat på medlemskap i säkerhets grupper för att säkerställa att endast användare som har godkänt företags berättigande och uppfyller villkoren för berättigande åtkomst till systemen.</span><span class="sxs-lookup"><span data-stu-id="681e8-109">Access levels are reviewed in near real-time based on security group membership to ensure that only users who have authorized business justifications and meet the eligibility requirements have access to the systems.</span></span>
- <span data-ttu-id="681e8-110">Microsoft 365, dess Access-kontroller och stöd tjänster, inklusive Azure Active Directory och fysiska data Center, granskas regelbundet av oberoende tredje parter för att uppfylla [ISO/iec 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP)och andra [standarder](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span><span class="sxs-lookup"><span data-stu-id="681e8-110">Microsoft 365, its access controls, and supporting services, including Azure Active Directory and physical datacenters, are regularly audited by independent third-parties for compliance with [ISO/IEC 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP), and other [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span>
- <span data-ttu-id="681e8-111">Microsoft 365-tekniker måste vidta årlig säkerhetsutbildning, granska utökade åtkomst rekommendationer och bekräfta Microsofts säkerhets-och integritets policyer för att underhålla tjänsten.</span><span class="sxs-lookup"><span data-stu-id="681e8-111">Microsoft 365 engineers must take yearly security training, review elevated access best procedures, and acknowledge Microsoft's security and privacy policies to maintain entitlements to the service.</span></span>

<span data-ttu-id="681e8-112">Automatiska larm utlöses när misstänkt aktivitet identifieras, till exempel flera misslyckade inloggningar inom en kort tids period.</span><span class="sxs-lookup"><span data-stu-id="681e8-112">Automated alerts trigger when suspicious activity is detected, such as multiple failed logins within a short period.</span></span> <span data-ttu-id="681e8-113">Microsoft 365 Security Response-teamet använder dator inlärning och omfattande data analys för att granska och analysera aktivitet, leta efter oregelbunden åtkomst mönster och proaktiva reagera på avvikande och olagliga aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="681e8-113">The Microsoft 365 Security Response team uses machine learning and big data analysis to review and analyze activity, look for irregular access patterns, and proactively respond to anomalous and illicit activities.</span></span> <span data-ttu-id="681e8-114">Microsoft samarbetar också med en särskild grupp av utträngda testare och deltar i det återkommande röda teamet och blå grupp-övningar för att hitta säkerhets-och åtkomst kontroll problem i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="681e8-114">Microsoft also employs a dedicated team of penetration testers and engages in periodic Red Team and Blue Team exercises to find security and access control issues in the service.</span></span> <span data-ttu-id="681e8-115">Kunder kan kontrol lera effektiviteten hos åtkomst kontroll systemen genom att använda gransknings rapporter och API: et för hanterings aktivitet som tillhandahålls av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="681e8-115">Customers can verify the effectiveness of access control systems by using audit reports and the management activity API provided by Microsoft 365.</span></span>

<span data-ttu-id="681e8-116">Mer information finns i [referens för hanterings aktivitet](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) och [granskning och rapportering 365 av aktiviteter i](microsoft-365-auditing-and-reporting-overview.md)Office 365.</span><span class="sxs-lookup"><span data-stu-id="681e8-116">For more information, see [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) and [Auditing and reporting in Microsoft 365](microsoft-365-auditing-and-reporting-overview.md).</span></span>
