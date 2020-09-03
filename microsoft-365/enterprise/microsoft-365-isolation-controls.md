---
title: Kontroller för Microsoft 365-isolering
ms.author: robmazz
author: robmazz
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
description: Lär dig hur isolerings kontroller fungerar i Microsoft 365, vilket gör det möjligt för tjänsterna att fungera och att vara autonomt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb0989f19002267ab92bf184a12a4076f753580e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332382"
---
# <a name="microsoft-365-isolation-controls"></a><span data-ttu-id="c1d9b-103">Kontroller för Microsoft 365-isolering</span><span class="sxs-lookup"><span data-stu-id="c1d9b-103">Microsoft 365 isolation controls</span></span> 

<span data-ttu-id="c1d9b-104">Microsoft arbetar kontinuerligt med att kontrol lera att arkitekturen för flera innehavare av Microsoft 365 stöder säkerhet på företags nivå, sekretess, integritet, lokal, internationell [och tillgänglighet.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)</span><span class="sxs-lookup"><span data-stu-id="c1d9b-104">Microsoft continuously works to ensure that the multi-tenant architecture of Microsoft 365 supports enterprise-level security, confidentiality, privacy, integrity, local, international, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span> <span data-ttu-id="c1d9b-105">Skalan och omfattningen av tjänster som tillhandahålls av Microsoft gör det svårt och icke-ekonomiskt att hantera Microsoft 365 med betydande mänsklig interaktion.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-105">The scale and the scope of services provided by Microsoft make it difficult and non-economical to manage Microsoft 365 with significant human interaction.</span></span> <span data-ttu-id="c1d9b-106">Microsoft 365-tjänsterna tillhandahålls via flera globalt distribuerade Data Center, och är mycket automatiserade med få saker som kräver mänsklig touch eller åtkomst till kund innehåll.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-106">Microsoft 365 services are provided through multiple globally distributed data centers, each highly automated with few operations requiring a human touch or any access to customer content.</span></span> <span data-ttu-id="c1d9b-107">Vår personal har stöd för dessa tjänster och data Center med automatiserade verktyg och lättillgänglig fjärråtkomst.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-107">Our staff supports these services and data centers using automated tools and highly secure remote access.</span></span> 

<span data-ttu-id="c1d9b-108">Microsoft 365 består av flera tjänster som tillhandahåller viktiga företags funktioner och bidrar till hela Microsoft 365-upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-108">Microsoft 365 is composed of multiple services that provide important business functionality and contribute to the entire Microsoft 365 experience.</span></span> <span data-ttu-id="c1d9b-109">Alla de här tjänsterna är fristående och har utformats för att integreras med varandra.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-109">Each of these services is self-contained and designed to integrate with one another.</span></span>

<span data-ttu-id="c1d9b-110">Microsoft 365 är utformat med följande principer:</span><span class="sxs-lookup"><span data-stu-id="c1d9b-110">Microsoft 365 is designed with the following principles:</span></span>

 - <span data-ttu-id="c1d9b-111">\*\* [Tjänsteorienterad arkitektur](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):\*\* utforma och utveckla program vara i form av driftskompatibla tjänster som ger väl definierade företags funktioner.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-111">**[Service-Oriented Architecture](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span></span>
 - <span data-ttu-id="c1d9b-112">**[Drift säkerhet](https://www.microsoft.com/download/details.aspx?id=40872):** en struktur som innehåller de kunskaper som erhålls genom olika funktioner som är unika för Microsoft, inklusive [livs cykeln för Microsofts säkerhets utveckling](https://www.microsoft.com/sdl/default.aspx), [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)och djupgående medvetenhet om det Cybersecurity hotet liggande.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-112">**[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** a framework that incorporates the knowledge gained through various capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="c1d9b-113">Microsoft 365-tjänster tillsammans med varandra, men är utformade och implementerade så att de kan distribueras och användas som autonoma tjänster, oberoende av varandra.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-113">Microsoft 365 services inter-operate with each other, but are designed and implemented so they can be deployed and operated as autonomous services, independent of each other.</span></span> <span data-ttu-id="c1d9b-114">Microsoft är åtskilda tullar och ansvars områden för Microsoft 365 för att minska möjligheterna till otillbörlig eller oavsiktlig modifiering av organisationens till gångar.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-114">Microsoft segregates duties and areas of responsibility for Microsoft 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets.</span></span> <span data-ttu-id="c1d9b-115">Microsoft 365-team har definierat roller som en del av en omfattande rollbaserad åtkomst kontroll.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-115">Microsoft 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="c1d9b-116">Innehålls isolering för kunder</span><span class="sxs-lookup"><span data-stu-id="c1d9b-116">Customer content isolation</span></span>

<span data-ttu-id="c1d9b-117">Allt kund innehåll i en klient organisation är isolerat från andra klient organisationer och från operationer och system data som används i hanteringen av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-117">All customer content in a tenant is isolated from other tenants and from operations and systems data used in the management of Microsoft 365.</span></span> <span data-ttu-id="c1d9b-118">Flera former av skydd implementeras i Microsoft 365 för att minimera risken för problem med Microsoft 365-tjänsten eller ett program.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-118">Multiple forms of protection are implemented throughout Microsoft 365 to minimize the risk of compromise of any Microsoft 365 service or application.</span></span> <span data-ttu-id="c1d9b-119">Flera former av skydd hindrar också obehörig åtkomst till klient organisationen eller Microsoft 365-systemet.</span><span class="sxs-lookup"><span data-stu-id="c1d9b-119">Multiple forms of protection also prevent unauthorized access to the information of tenants or the Microsoft 365 system itself.</span></span>

<span data-ttu-id="c1d9b-120">Information om hur Microsoft implementerar logisk isolering av klient organisations data i Microsoft 365 finns i avsnittet [klient isolering i Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c1d9b-120">For information about how Microsoft implements logical isolation of tenant data within Microsoft 365, see [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span></span>
