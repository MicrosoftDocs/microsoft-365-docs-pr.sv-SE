---
title: Förstå hantering av affärskontinuitet i molntjänster
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: Förstå hur planering och implementering av affärskontinuitet fungerar när ni använder molntjänster.
ms.openlocfilehash: f57079da4de7cafe071f5bf2a146290f3034fb60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686064"
---
# <a name="enterprise-business-continuity-management-ebcm-with-cloud-services"></a><span data-ttu-id="00e84-103">Hantera affärskontinuitet (EBCM) med molntjänster</span><span class="sxs-lookup"><span data-stu-id="00e84-103">Enterprise business continuity management (EBCM) with cloud services</span></span>

<span data-ttu-id="00e84-104">Som en del av din organisations digitala transformering måste du granska och uppdatera era planer för haveriberedskap och affärskontinuitet så att de klarar affärsprocesser som är beroende av Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="00e84-104">As part of your organizations digital transformation, you need to revisit and update your disaster recovery and business continuity plans to account for the business process that depend on Microsoft 365 Cloud services.</span></span> <span data-ttu-id="00e84-105">Microsoft 365-molntjänster, som Exchange Online, SharePoint Online och OneDrive för företag, är utformade för att vara mycket motståndskraftiga.</span><span class="sxs-lookup"><span data-stu-id="00e84-105">Microsoft 365 Cloud services, like Exchange Online, SharePoint Online and OneDrive for Business are designed and operated to be highly resilient.</span></span>

> [!NOTE]
> <span data-ttu-id="00e84-106">Du kan läsa mer om Microsofts EBCM-plan i vårt whitepaper [Enterprise Business Continuity Management Program](https://go.microsoft.com/fwlink/?linkid=2121521).</span><span class="sxs-lookup"><span data-stu-id="00e84-106">You can learn more about Microsoft's own EBCM plan in the [Enterprise Business Continuity Management Program whitepaper](https://go.microsoft.com/fwlink/?linkid=2121521).</span></span> <span data-ttu-id="00e84-107">Inloggning krävs.</span><span class="sxs-lookup"><span data-stu-id="00e84-107">Login is required.</span></span>

<span data-ttu-id="00e84-108">Trots motståndskraften kan incidenter inträffa.</span><span class="sxs-lookup"><span data-stu-id="00e84-108">Even with this resilience, service incidents do occur.</span></span> <span data-ttu-id="00e84-109">När de gör det ska din organisation vara förberedd och ha en väldefinierad strategi för affärskontinuitet.</span><span class="sxs-lookup"><span data-stu-id="00e84-109">When they do, your organization should be prepared and have a well-defined business continuity strategy.</span></span>

<span data-ttu-id="00e84-110">Om du inte har uppdaterat dina abonnemang ännu kan du få hjälp av dessa artiklar för att planera strategin så att era tjänster faller tillbaka på ett känt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="00e84-110">If you haven't updated your plans yet this series of topics helps you to plan your strategy so your services can fail to a known state.</span></span> <span data-ttu-id="00e84-111">I de här avsnitten beskrivs viktiga saker som du bör tänka på när du förbättrar kontinuiteten.</span><span class="sxs-lookup"><span data-stu-id="00e84-111">These topics highlight key considerations for improving your continuity readiness.</span></span>

## <a name="list-of-topics-with-links"></a><span data-ttu-id="00e84-112">Lista över avsnitt med länkar</span><span class="sxs-lookup"><span data-stu-id="00e84-112">List of topics with links</span></span>

- [<span data-ttu-id="00e84-113">Kundens och molnpartnerns ansvar</span><span class="sxs-lookup"><span data-stu-id="00e84-113">Customer and cloud partner responsibilities</span></span>](ebcm-customer-and-cloud-partner-ebcm-responsibilities.md)
- [<span data-ttu-id="00e84-114">Microsoft 365-tjänstens återhämtning</span><span class="sxs-lookup"><span data-stu-id="00e84-114">Microsoft 365 service resiliency</span></span>](ebcm-m365-service-resiliency.md)
- [<span data-ttu-id="00e84-115">Utveckla en kontinuitetsplan</span><span class="sxs-lookup"><span data-stu-id="00e84-115">Developing your continuity plan</span></span>](ebcm-developing-your-ebcm-plan.md)
- [<span data-ttu-id="00e84-116">Scenarier för att minimera incidenter i Microsoft 365-tjänsten</span><span class="sxs-lookup"><span data-stu-id="00e84-116">Microsoft 365 service incident mitigation scenarios</span></span>](ebcm-microsoft-365-mitigations.md)
- [<span data-ttu-id="00e84-117">Utbildning och genomgång av affärskontinuitetsplan för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="00e84-117">Microsoft 365 for business continuity plan training and rehearsal</span></span>](ebcm-enterprise-business-continuity-management-plan-rehearsal-and-user-training.md)

## <a name="see-also"></a><span data-ttu-id="00e84-118">Se även</span><span class="sxs-lookup"><span data-stu-id="00e84-118">See also</span></span>

- [<span data-ttu-id="00e84-119">Friskrivning om affärskontinuitet</span><span class="sxs-lookup"><span data-stu-id="00e84-119">Enterprise business continuity legal disclaimer</span></span>](ebcm-legal-disclaimer.md)
