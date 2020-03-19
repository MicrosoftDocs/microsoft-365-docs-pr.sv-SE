---
title: Säkerhetsincidentsvar för Office 365
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
description: Den här lösningen visar hur de vanligaste cybersäkerhetsattackerna kan se ut i Office 365 och hur du svarar på dem
ms.openlocfilehash: 317e685dd9e2b2e0afbf25f0568b352c399e7b87
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808621"
---
# <a name="office-365-security-incident-response"></a><span data-ttu-id="5b0b5-103">Säkerhetsincidentsvar för Office 365</span><span class="sxs-lookup"><span data-stu-id="5b0b5-103">Office 365 Security Incident Response</span></span>

 <span data-ttu-id="5b0b5-104">**Sammanfattning:** Den här lösningen talar om för dig vilka indikatorer na är för de vanligaste cybersäkerhetsattackerna i Office 365, hur du bekräftar en viss attack på ett positivt sätt och hur du svarar på den.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-104">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="overview"></a><span data-ttu-id="5b0b5-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="5b0b5-105">Overview</span></span>

<span data-ttu-id="5b0b5-106">Inte alla cyberattacker kan omintetgöras.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-106">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="5b0b5-107">Angripare letar ständigt efter nya svagheter i din defensiva strategi eller de utnyttjar gamla.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-107">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="5b0b5-108">Att veta hur man känner igen en attack kan du svara på det snabbare, vilket förkortar varaktigheten av säkerhetsincidenten.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-108">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="5b0b5-109">Den här artikelserien hjälper dig att förstå hur en viss typ av angrepp kan se ut i Office 365 och ger dig åtgärder du kan vidta för att svara.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-109">This series of article helps you understand what a particular type of attack might look like in Office 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="5b0b5-110">De är snabba ingångar för att förstå:</span><span class="sxs-lookup"><span data-stu-id="5b0b5-110">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="5b0b5-111">Vad attacken är och hur det fungerar.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-111">What the attack is and how it works.</span></span>

- <span data-ttu-id="5b0b5-112">Vilka tecken, som kallas indikatorer på kompromisser (IOK), att leta efter och hur man letar efter dem.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-112">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="5b0b5-113">Hur man positivt bekräfta attacken.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-113">How to positively confirm the attack.</span></span>

- <span data-ttu-id="5b0b5-114">Åtgärder för att avbryta attacken och bättre skydda din organisation i framtiden.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-114">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="5b0b5-115">Länkar till fördjupad information om varje attacktyp.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-115">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="5b0b5-116">Kom tillbaka hit varje månad eftersom fler artiklar kommer att läggas till med tiden.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-116">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="5b0b5-117">Identifiera och åtgärda artiklar</span><span class="sxs-lookup"><span data-stu-id="5b0b5-117">Detect and remediate articles</span></span>

- [<span data-ttu-id="5b0b5-118">Upptäcka och åtgärda olagliga samtyckesbidrag i Office 365</span><span class="sxs-lookup"><span data-stu-id="5b0b5-118">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="5b0b5-119">Identifiera och åtgärda Outlook-regler och anpassade formulärinjektionsattacker i Office 365</span><span class="sxs-lookup"><span data-stu-id="5b0b5-119">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="5b0b5-120">Artiklar om incidentsvar</span><span class="sxs-lookup"><span data-stu-id="5b0b5-120">Incident response articles</span></span>

- [<span data-ttu-id="5b0b5-121">Svara på ett komprometterat e-postkonto i Office 365</span><span class="sxs-lookup"><span data-stu-id="5b0b5-121">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="5b0b5-122">Säkra Office 365 som ett cybersäkerhetsproffs</span><span class="sxs-lookup"><span data-stu-id="5b0b5-122">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="5b0b5-123">Din Office 365-prenumeration levereras med en kraftfull uppsättning säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-123">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="5b0b5-124">Använd [säkerhetsöversikten för Office 365 – de viktigaste prioriteringarna för de första 30 dagarna, 90 dagarna och därefter](security-roadmap.md) för att implementera Microsofts rekommenderade metodtips för att skydda din Office 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-124">Use the [Office 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="5b0b5-125">Uppgifter att utföra under de första 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-125">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="5b0b5-126">Dessa har omedelbar affekt och är små påverkan på användarna.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-126">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="5b0b5-127">Uppgifter att utföra på 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-127">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="5b0b5-128">Dessa tar lite mer tid att planera och genomföra men avsevärt förbättra din säkerhet hållning</span><span class="sxs-lookup"><span data-stu-id="5b0b5-128">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="5b0b5-129">Bortom 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-129">Beyond 90 days.</span></span> <span data-ttu-id="5b0b5-130">Dessa förbättringar bygga under dina första 90 dagar arbete.</span><span class="sxs-lookup"><span data-stu-id="5b0b5-130">These enhancements build in your first 90 days work.</span></span>
