---
title: Administrations aktivitets API för Office 365
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
- M365-analytics
f1.keywords:
- NOCSH
description: 'I den här artikeln hittar du en kort sammanfattning av API: t för hanterings aktiviteten för Office 365 och informationen som tillhandahålls från aktivitets loggar.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d51f27f28b0adb84ef43004664ef310567263b9
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332310"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="50036-103">Administrations aktivitets API för Office 365</span><span class="sxs-lookup"><span data-stu-id="50036-103">Office 365 Management Activity API</span></span>

<span data-ttu-id="50036-104">Microsoft tillhandahåller repor ting Services som du kan använda för att få en samlad transaktions information om din Office 365-klient.</span><span class="sxs-lookup"><span data-stu-id="50036-104">Microsoft provides reporting services you can use to obtain aggregated transactional information about your Office 365 tenant.</span></span> <span data-ttu-id="50036-105">[API-modulen för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) använder en branschstandardiserade RESTful-design och OAuth v2 för autentisering.</span><span class="sxs-lookup"><span data-stu-id="50036-105">The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) uses an industry-standard RESTful design and OAuth v2 for authentication.</span></span> <span data-ttu-id="50036-106">Det gör det enkelt att börja experimentera med data och insugning till visualiserings verktyg och program.</span><span class="sxs-lookup"><span data-stu-id="50036-106">This makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications.</span></span> <span data-ttu-id="50036-107">API-funktionen ger en datafeed med information om användare, administratör, åtgärder och säkerhets aktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="50036-107">The API provides a data feed with information about user, administrator, operations, and security activity in Office 365.</span></span> <span data-ttu-id="50036-108">Uppgifterna kan bevaras i reglerings syfte, eller kombineras med data från en lokal infrastruktur eller andra källor.</span><span class="sxs-lookup"><span data-stu-id="50036-108">The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources.</span></span> <span data-ttu-id="50036-109">Detta hjälper till att skapa en övervaknings lösning för verksamhet, säkerhet och efterlevnad i hela företaget.</span><span class="sxs-lookup"><span data-stu-id="50036-109">This helps build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="50036-110">API för hanterings aktivitet i Office 365 ger information om olika åtgärder för användare, administratörer, system och händelser från Office 365 och Azure Active Directory-aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="50036-110">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="50036-111">API tillhandahåller ett enhetligt gransknings schema med över 10 fält gemensamt för alla tjänster.</span><span class="sxs-lookup"><span data-stu-id="50036-111">The API provides a consistent audit schema with over 10 fields common across all the services.</span></span> <span data-ttu-id="50036-112">API gör det möjligt för organisationer att skapa enkla anslutningar mellan händelser och gör det möjligt för nya sätt att ta hand om data.</span><span class="sxs-lookup"><span data-stu-id="50036-112">The API allows organizations to make easy connections between events, and enables new ways to reason over the data.</span></span>

<span data-ttu-id="50036-113">Dussin tals oberoende program varu tillverkare som samarbetar med Microsoft och har inbyggda lösningar baserade på API: t.</span><span class="sxs-lookup"><span data-stu-id="50036-113">Dozens of Independent Software Vendors (ISVs) partnered with Microsoft and have built solutions based on the API.</span></span> <span data-ttu-id="50036-114">Vissa lösningar är bara fokus på Office 365-data och andra källdata från flera moln leverantörer och lokala system för att skapa en enhetlig vy över operationer, säkerhet och efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="50036-114">Some solutions focus solely on Office 365 data and others source data from multiple cloud providers and on-premises systems to create a unified view of operations, security, and compliance-related activity.</span></span> 

<span data-ttu-id="50036-115">Mer information finns i referens för [hanterings AKTIVITETS API för Office-365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="50036-115">For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
