---
title: Svar på säkerhetstillbud
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
localization_priority: Normal
search.appverid:
- MET150
description: Den här lösningen talar om hur de vanligaste cybersäkerhetsattackerna kan se ut i Microsoft 365 och hur du kan svara på dem
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65ff75253f45ae2d0f051dafe73c6e665f89827a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207173"
---
# <a name="security-incident-response"></a><span data-ttu-id="5632f-103">Svar på säkerhetstillbud</span><span class="sxs-lookup"><span data-stu-id="5632f-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5632f-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="5632f-104">**Applies to**</span></span>
- [<span data-ttu-id="5632f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5632f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5632f-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="5632f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5632f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5632f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="5632f-108">**Sammanfattning:** Den här lösningen anger vilka indikatorer som ligger till grund för de vanligaste cybersäkerhetsattackerna i Office 365, hur du bekräftar en viss attack och hur du reagerar på den.</span><span class="sxs-lookup"><span data-stu-id="5632f-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="5632f-109">Lär dig hur du svarar på cyberattacker</span><span class="sxs-lookup"><span data-stu-id="5632f-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="5632f-110">Det går inte att förhindra alla cyberattacker.</span><span class="sxs-lookup"><span data-stu-id="5632f-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="5632f-111">Attacker letar hela tiden efter nya svagheter i din strategi, eller så utnyttjar de gamla.</span><span class="sxs-lookup"><span data-stu-id="5632f-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="5632f-112">Om du vet hur du känner igen en attack kan du reagera snabbare, vilket förkortar varaktigheten för säkerhetshändelsen.</span><span class="sxs-lookup"><span data-stu-id="5632f-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="5632f-113">Den här serien med artiklar hjälper dig att förstå hur en viss typ av attack kan se ut i Microsoft 365 och ger dig instruktioner du kan vidta för att svara.</span><span class="sxs-lookup"><span data-stu-id="5632f-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="5632f-114">De ger ett snabbt sätt att förstå:</span><span class="sxs-lookup"><span data-stu-id="5632f-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="5632f-115">Vad attacken är och hur den fungerar.</span><span class="sxs-lookup"><span data-stu-id="5632f-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="5632f-116">Vad tecken, som kallas indikatorer för kompromettens (IOC), att leta efter och hur du ska leta efter dem.</span><span class="sxs-lookup"><span data-stu-id="5632f-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="5632f-117">Hur du bekräftar attacken positivt.</span><span class="sxs-lookup"><span data-stu-id="5632f-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="5632f-118">Åtgärder för att vidta åtgärder för att minska attacken och skydda organisationen i framtiden.</span><span class="sxs-lookup"><span data-stu-id="5632f-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="5632f-119">Länkar till ingående information om varje attacktyp.</span><span class="sxs-lookup"><span data-stu-id="5632f-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="5632f-120">Kom tillbaka hit varje månad allt eftersom fler artiklar kommer att läggas till med tiden.</span><span class="sxs-lookup"><span data-stu-id="5632f-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="5632f-121">Hitta och åtgärda artiklar</span><span class="sxs-lookup"><span data-stu-id="5632f-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="5632f-122">Identifiera och åtgärda olovliga medgivandebeviljanden i Office 365</span><span class="sxs-lookup"><span data-stu-id="5632f-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="5632f-123">Identifiera och reparera Outlook-regler och inmatningsattacker i anpassade formulär i Office 365</span><span class="sxs-lookup"><span data-stu-id="5632f-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="5632f-124">Incidentsvarsartiklar</span><span class="sxs-lookup"><span data-stu-id="5632f-124">Incident response articles</span></span>

- [<span data-ttu-id="5632f-125">Svara på ett komprometterat e-postkonto i Office 365</span><span class="sxs-lookup"><span data-stu-id="5632f-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="5632f-126">Skydda Microsoft 365 som en expert på cybersäkerhet</span><span class="sxs-lookup"><span data-stu-id="5632f-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="5632f-127">Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare.</span><span class="sxs-lookup"><span data-stu-id="5632f-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="5632f-128">Använd säkerhetsöversikten Microsoft 365 – Prioriteringar för de [första 30, 90](security-roadmap.md) dagarna och senare för att implementera Microsofts rekommenderade metodtips för att skydda din Microsoft 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="5632f-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="5632f-129">Uppgifter som ska utföras under de första 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="5632f-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="5632f-130">De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.</span><span class="sxs-lookup"><span data-stu-id="5632f-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="5632f-131">Uppgifter som ska utföras inom 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="5632f-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="5632f-132">Dessa tar lite mer tid att planera och implementera men förbättrar säkerheten avsevärt</span><span class="sxs-lookup"><span data-stu-id="5632f-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="5632f-133">Efter 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="5632f-133">Beyond 90 days.</span></span> <span data-ttu-id="5632f-134">De här förbättringarna uppnås under de första 90 dagarna.</span><span class="sxs-lookup"><span data-stu-id="5632f-134">These enhancements build in your first 90 days work.</span></span>
