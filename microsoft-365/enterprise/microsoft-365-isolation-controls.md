---
title: Microsoft 365 isolationskontroller
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
description: Lär dig hur avgränsningskontroller fungerar inom Microsoft 365, så att tjänster kan överse med varandra eller vara fristående vid behov.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918948"
---
# <a name="microsoft-365-isolation-controls"></a><span data-ttu-id="3e137-103">Microsoft 365 isolationskontroller</span><span class="sxs-lookup"><span data-stu-id="3e137-103">Microsoft 365 isolation controls</span></span> 

<span data-ttu-id="3e137-104">Microsoft arbetar kontinuerligt för att säkerställa att arkitekturen för flera innehavare i Microsoft 365 har stöd för säkerhet på företagsnivå, konfidentialitet, sekretess, integritet, lokala, internationella och [tillgänglighetsstandarder.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)</span><span class="sxs-lookup"><span data-stu-id="3e137-104">Microsoft continuously works to ensure that the multi-tenant architecture of Microsoft 365 supports enterprise-level security, confidentiality, privacy, integrity, local, international, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span> <span data-ttu-id="3e137-105">Omfattning och omfattning för tjänster som tillhandahålls av Microsoft gör det svårt och icke-ekonomiskt att hantera Microsoft 365 med betydande mänsklig interaktion.</span><span class="sxs-lookup"><span data-stu-id="3e137-105">The scale and the scope of services provided by Microsoft make it difficult and non-economical to manage Microsoft 365 with significant human interaction.</span></span> <span data-ttu-id="3e137-106">Microsoft 365 tjänster tillhandahålls via flera globalt distribuerade datacenter, var och en automatiserad i hög grad med få åtgärder som kräver ett mänskligt tryck eller åtkomst till kundinnehåll.</span><span class="sxs-lookup"><span data-stu-id="3e137-106">Microsoft 365 services are provided through multiple globally distributed data centers, each highly automated with few operations requiring a human touch or any access to customer content.</span></span> <span data-ttu-id="3e137-107">Vår personal stödjer dessa tjänster och datacenter med automatiska verktyg och mycket säker fjärråtkomst.</span><span class="sxs-lookup"><span data-stu-id="3e137-107">Our staff supports these services and data centers using automated tools and highly secure remote access.</span></span> 

<span data-ttu-id="3e137-108">Microsoft 365 består av flera tjänster som ger viktiga affärsfunktioner och bidrar till hela Microsoft 365 upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="3e137-108">Microsoft 365 is composed of multiple services that provide important business functionality and contribute to the entire Microsoft 365 experience.</span></span> <span data-ttu-id="3e137-109">Var och en av dessa tjänster är fristående och utformade för att integreras med varandra.</span><span class="sxs-lookup"><span data-stu-id="3e137-109">Each of these services is self-contained and designed to integrate with one another.</span></span>

<span data-ttu-id="3e137-110">Microsoft 365 är utformat med följande principer:</span><span class="sxs-lookup"><span data-stu-id="3e137-110">Microsoft 365 is designed with the following principles:</span></span>

 - <span data-ttu-id="3e137-111">**[Tjänstorienterad arkitektur](/previous-versions/aa480021(v=msdn.10)): utforma** och utveckla programvara i form av interoperabla tjänster som ger väldefinierade affärsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="3e137-111">**[Service-Oriented Architecture](/previous-versions/aa480021(v=msdn.10)):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span></span>
 - <span data-ttu-id="3e137-112">**[Operational Security Assurance:](https://www.microsoft.com/download/details.aspx?id=40872)** ett ramverk som införlivar de kunskaper som har fåtts med olika funktioner som är unika för Microsoft, inklusive Microsoft [Security Development Lifecycle,](https://www.microsoft.com/sdl/default.aspx) [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)och djup förståelse för hotbilden för cyberhot.</span><span class="sxs-lookup"><span data-stu-id="3e137-112">**[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** a framework that incorporates the knowledge gained through various capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="3e137-113">Microsoft 365 tjänster samarbetar med varandra, men är utformade och implementerade så att de kan användas och drivs som autonoma tjänster, oberoende av varandra.</span><span class="sxs-lookup"><span data-stu-id="3e137-113">Microsoft 365 services inter-operate with each other, but are designed and implemented so they can be deployed and operated as autonomous services, independent of each other.</span></span> <span data-ttu-id="3e137-114">Microsoft överger uppgifter och ansvarsområden för Microsoft 365 för att minska möjligheter för obehöriga eller oavsiktliga ändringar eller missbruk av organisationens tillgångar.</span><span class="sxs-lookup"><span data-stu-id="3e137-114">Microsoft segregates duties and areas of responsibility for Microsoft 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets.</span></span> <span data-ttu-id="3e137-115">Microsoft 365 grupper har definierat roller som en del av en omfattande rollbaserad mekanism för åtkomstkontroll.</span><span class="sxs-lookup"><span data-stu-id="3e137-115">Microsoft 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="3e137-116">Avgränsning av kundinnehåll</span><span class="sxs-lookup"><span data-stu-id="3e137-116">Customer content isolation</span></span>

<span data-ttu-id="3e137-117">Allt kundinnehåll i en klientorganisation isoleras från andra klientorganisationar och från verksamhets- och systemdata som används för hantering av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e137-117">All customer content in a tenant is isolated from other tenants and from operations and systems data used in the management of Microsoft 365.</span></span> <span data-ttu-id="3e137-118">Flera olika former av skydd implementeras Microsoft 365 hela tiden för att minimera risken för att en Microsoft 365 tjänst eller program går ur.</span><span class="sxs-lookup"><span data-stu-id="3e137-118">Multiple forms of protection are implemented throughout Microsoft 365 to minimize the risk of compromise of any Microsoft 365 service or application.</span></span> <span data-ttu-id="3e137-119">Flera olika former av skydd förhindrar också obehörig åtkomst till information från klientorganisationen eller Microsoft 365 system.</span><span class="sxs-lookup"><span data-stu-id="3e137-119">Multiple forms of protection also prevent unauthorized access to the information of tenants or the Microsoft 365 system itself.</span></span>

<span data-ttu-id="3e137-120">Information om hur Microsoft implementerar logisk avgränsning av klientdata i Microsoft 365 finns i [Innehavarisolering i Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3e137-120">For information about how Microsoft implements logical isolation of tenant data within Microsoft 365, see [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span></span>