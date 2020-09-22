---
title: Säkerhets tillbud
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Den här lösningen visar vilka de vanligaste Cybersecurity-attackerna kan se ut i Microsoft 365 och hur de ska reagera på dem
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 221303d43620e89b8200392961d8aa0916c82763
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198709"
---
# <a name="security-incident-response"></a><span data-ttu-id="c20ac-103">Säkerhets tillbud</span><span class="sxs-lookup"><span data-stu-id="c20ac-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="c20ac-104">**Sammanfattning:** Den här lösningen visar vilka indikatorer som gäller för de vanligaste Cybersecurity-attackerna i Office 365, hur man positivt bekräftar eventuella attacker och hur du svarar på det.</span><span class="sxs-lookup"><span data-stu-id="c20ac-104">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="c20ac-105">Lär dig att svara på cyberattacks</span><span class="sxs-lookup"><span data-stu-id="c20ac-105">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="c20ac-106">Alla cyberattacks kan inte vara Thwarted.</span><span class="sxs-lookup"><span data-stu-id="c20ac-106">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="c20ac-107">Attackerare letar ständigt efter nya svagheter i din prenumeration eller de utnyttjar gamla.</span><span class="sxs-lookup"><span data-stu-id="c20ac-107">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="c20ac-108">Att känna till hur man känner igen en attack gör att du kan svara snabbare, vilket minskar giltighets tiden för säkerhets tillbudet.</span><span class="sxs-lookup"><span data-stu-id="c20ac-108">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="c20ac-109">Den här artikeln hjälper dig att förstå vad en viss typ av attack kan se ut i Microsoft 365 och ger dig instruktioner för att svara.</span><span class="sxs-lookup"><span data-stu-id="c20ac-109">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="c20ac-110">Det är snabbt att sätta sig till:</span><span class="sxs-lookup"><span data-stu-id="c20ac-110">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="c20ac-111">Vad attacket är och hur det fungerar.</span><span class="sxs-lookup"><span data-stu-id="c20ac-111">What the attack is and how it works.</span></span>

- <span data-ttu-id="c20ac-112">Vilka tecken kallas för anslags indikationer (IOC) och hur du kan leta efter dem.</span><span class="sxs-lookup"><span data-stu-id="c20ac-112">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="c20ac-113">Bekräfta angreppet positivt.</span><span class="sxs-lookup"><span data-stu-id="c20ac-113">How to positively confirm the attack.</span></span>

- <span data-ttu-id="c20ac-114">Steg för att ta bort angreppet och bättre skydda din organisation i framtiden.</span><span class="sxs-lookup"><span data-stu-id="c20ac-114">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="c20ac-115">Länkar till djupgående information för varje typ av attack.</span><span class="sxs-lookup"><span data-stu-id="c20ac-115">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="c20ac-116">Kom tillbaka här varje månad allteftersom fler artiklar läggs till över tiden.</span><span class="sxs-lookup"><span data-stu-id="c20ac-116">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="c20ac-117">Identifiera och åtgärda artiklar</span><span class="sxs-lookup"><span data-stu-id="c20ac-117">Detect and remediate articles</span></span>

- [<span data-ttu-id="c20ac-118">Identifiera och åtgärda olovliga medgivandebeviljanden i Office 365</span><span class="sxs-lookup"><span data-stu-id="c20ac-118">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="c20ac-119">Identifiera och reparera Outlook-regler och inmatningsattacker i anpassade formulär i Office 365</span><span class="sxs-lookup"><span data-stu-id="c20ac-119">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="c20ac-120">Artiklar om incident svar</span><span class="sxs-lookup"><span data-stu-id="c20ac-120">Incident response articles</span></span>

- [<span data-ttu-id="c20ac-121">Svara på ett komprometterat e-postkonto i Office 365</span><span class="sxs-lookup"><span data-stu-id="c20ac-121">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="c20ac-122">Skydda Microsoft 365 som en expert på cybersäkerhet</span><span class="sxs-lookup"><span data-stu-id="c20ac-122">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="c20ac-123">Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare.</span><span class="sxs-lookup"><span data-stu-id="c20ac-123">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="c20ac-124">Använd [microsofts 365 säkerhets plan – de viktigaste prioriteringarna för de första 30 dagarna, 90 dagar och senare](security-roadmap.md) för att implementera Microsofts rekommenderade metod tips för att skydda Microsoft 365-organisationen.</span><span class="sxs-lookup"><span data-stu-id="c20ac-124">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="c20ac-125">Uppgifter som ska utföras under de första 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="c20ac-125">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="c20ac-126">De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.</span><span class="sxs-lookup"><span data-stu-id="c20ac-126">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="c20ac-127">Uppgifter som ska utföras inom 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="c20ac-127">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="c20ac-128">Det tar lite längre tid att planera och implementera men det är avsevärt bättre Posture</span><span class="sxs-lookup"><span data-stu-id="c20ac-128">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="c20ac-129">Efter 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="c20ac-129">Beyond 90 days.</span></span> <span data-ttu-id="c20ac-130">De här förbättringarna uppnås under de första 90 dagarna.</span><span class="sxs-lookup"><span data-stu-id="c20ac-130">These enhancements build in your first 90 days work.</span></span>
