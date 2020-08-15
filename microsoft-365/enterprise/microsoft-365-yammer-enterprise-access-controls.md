---
title: Microsoft 365 Yammer Enterprise Access-kontroller
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
description: Den här artikeln innehåller en kort sammanfattning av företags åtkomst kontroller för Yammer i produktions miljön.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8bdf357ddd7f5c0b549d291fd4732924608085b9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696741"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="89795-103">Kontroller för Yammer Enterprise Access</span><span class="sxs-lookup"><span data-stu-id="89795-103">Yammer enterprise access controls</span></span> 

<span data-ttu-id="89795-104">Fysisk och logisk åtkomst till Yammer-produktions miljön begränsas till en mindre uppsättning människor (infrastruktur och tjänster).</span><span class="sxs-lookup"><span data-stu-id="89795-104">Physical and logical access to the Yammer production environment is restricted to a small set of people (infrastructure and operations).</span></span> <span data-ttu-id="89795-105">Precis som med andra Microsoft 365-tekniker har Yammer-tekniker ingen ständig åtkomst till kunddata.</span><span class="sxs-lookup"><span data-stu-id="89795-105">As with other Microsoft 365 engineers, Yammer engineers have zero standing access to customer data.</span></span> <span data-ttu-id="89795-106">Åtkomst måste begäras med hjälp av ett godkännande baserat inloggnings system som liknar låsning med ett begränsat antal god kännare.</span><span class="sxs-lookup"><span data-stu-id="89795-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox with a limited number of approvers.</span></span> <span data-ttu-id="89795-107">God kännare verifiera begäran (till exempel kontrollerar de om begäran är legitim baserat på behov, affärs fråga, tid etc.) och Godkänn eller avvisa begäran.</span><span class="sxs-lookup"><span data-stu-id="89795-107">Approvers verify the request (for example, they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="89795-108">Om begäran godkänns ges JIT-åtkomst under en definierad och begränsad tid.</span><span class="sxs-lookup"><span data-stu-id="89795-108">If the request is approved, JIT access is granted for a defined and limited time.</span></span> <span data-ttu-id="89795-109">När åtkomst tiden har överskridits förfaller Access automatiskt.</span><span class="sxs-lookup"><span data-stu-id="89795-109">After access time is exceeded, the access automatically expires.</span></span>

<span data-ttu-id="89795-110">Precis som med andra Microsoft 365-tjänster använder multi-factority all åtkomst till produktions miljön för Yammer.</span><span class="sxs-lookup"><span data-stu-id="89795-110">As with other Microsoft 365 services, all access to the Yammer production environment uses multi-factor authentication.</span></span> <span data-ttu-id="89795-111">Alla Access-och kommando historik skrivs till en användare, och loggas och granskas regelbundet av Yammer-säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="89795-111">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="89795-112">Mer information om Yammer-administration och-hantering finns i [Hjälp för Yammer-administratörer](https://docs.microsoft.com/yammer/yammer-landing-page).</span><span class="sxs-lookup"><span data-stu-id="89795-112">For more information about Yammer administration and management, see [Yammer admin help](https://docs.microsoft.com/yammer/yammer-landing-page).</span></span>