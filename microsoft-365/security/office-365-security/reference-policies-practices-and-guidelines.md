---
title: Referensprinciper, metoder och riktlinjer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft har utvecklat olika policyer, metoder och använder flera branschrekommendationer för att skydda våra användare från olämplig, oönskad eller skadlig e-post.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f53b1c36417b15e366b527dd1c12e4f23c06f632
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406602"
---
# <a name="reference-policies-practices-and-guidelines"></a><span data-ttu-id="b7821-103">Referens: principer, övningar och riktlinjer</span><span class="sxs-lookup"><span data-stu-id="b7821-103">Reference: Policies, practices, and guidelines</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b7821-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="b7821-104">**Applies to**</span></span>
- [<span data-ttu-id="b7821-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b7821-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b7821-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="b7821-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b7821-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7821-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b7821-108">Microsoft arbetar för att tillhandahålla den mest betrodda användarupplevelsen på webben.</span><span class="sxs-lookup"><span data-stu-id="b7821-108">Microsoft is dedicated to helping provide the most trusted user experience on the web.</span></span> <span data-ttu-id="b7821-109">Därför har Microsoft utvecklat olika policyer, metoder och använder flera branschrekommendationer för att skydda våra användare från olämplig, oönskad eller skadlig e-post.</span><span class="sxs-lookup"><span data-stu-id="b7821-109">Therefore, Microsoft has developed various policies, procedures, and adopted several industry best practices to help protect our users from abusive, unwanted, or malicious email.</span></span> <span data-ttu-id="b7821-110">Avsändare som försöker skicka e-post till användare bör se till att de är helt förstådda och följer hjälpen i den här artikeln för att hjälpa till med detta och för att undvika potentiella leveransproblem.</span><span class="sxs-lookup"><span data-stu-id="b7821-110">Senders attempting to send email to users should ensure they fully understand and are following the guidance in this article to help in this effort and to help avoid potential delivery issues.</span></span>

<span data-ttu-id="b7821-111">Om du inte följer dessa policyer och riktlinjer kanske det inte är möjligt för vårt supportteam att hjälpa dig.</span><span class="sxs-lookup"><span data-stu-id="b7821-111">If you are not in compliance with these policies and guidelines, it may not be possible for our support team to assist you.</span></span> <span data-ttu-id="b7821-112">Om du följer riktlinjerna, metoderna och principerna som beskrivs i den här artikeln och fortfarande har leveransproblem baserat på din avsändande IP-adress följer du anvisningarna för att skicka en begäran om avlistning.</span><span class="sxs-lookup"><span data-stu-id="b7821-112">If you are adhering to the guidelines, practices, and policies presented in this article and are still experiencing delivery issues based on your sending IP address, please follow the steps to submit a delisting request.</span></span> <span data-ttu-id="b7821-113">Instruktioner finns i Använda [avlisteportalen för att ta bort dig själv från listan spärrade avsändare.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)</span><span class="sxs-lookup"><span data-stu-id="b7821-113">For instructions, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="general-microsoft-policies"></a><span data-ttu-id="b7821-114">Allmänna Principer för Microsoft</span><span class="sxs-lookup"><span data-stu-id="b7821-114">General Microsoft policies</span></span>

<span data-ttu-id="b7821-115">E-post som skickas till Microsoft 365-användare måste följa Microsofts policyer för e-postöverföring och användning av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7821-115">Email sent to Microsoft 365 users must comply with all Microsoft policies governing email transmission and use of Microsoft 365.</span></span>

- <span data-ttu-id="b7821-116">Villkor för tjänster som gäller Microsoft 365; i synnerhet att förbjuda användning av tjänsten för skräppost eller distribuera skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="b7821-116">Terms of Services applicable to Microsoft 365; in particular, the prohibition against using the service to spam or distribute malware.</span></span>

- [<span data-ttu-id="b7821-117">Avtal för Microsoft-tjänster</span><span class="sxs-lookup"><span data-stu-id="b7821-117">Microsoft Services Agreement</span></span>](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a><span data-ttu-id="b7821-118">Myndighetsföreskrifter</span><span class="sxs-lookup"><span data-stu-id="b7821-118">Governmental regulations</span></span>

<span data-ttu-id="b7821-119">E-post som skickas till Microsoft 365-användare måste följa alla tillämpliga lagar och bestämmelser som gäller för e-postkommunikation i tillämplig jurisdiktion.</span><span class="sxs-lookup"><span data-stu-id="b7821-119">Email sent to Microsoft 365 users must adhere to all applicable laws and regulations governing email communications in the applicable jurisdiction.</span></span>

- [<span data-ttu-id="b7821-120">CAN-SPAM Act: En regelefterlevnadsguide för företag</span><span class="sxs-lookup"><span data-stu-id="b7821-120">CAN-SPAM Act: A Compliance Guide for Business</span></span>](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [<span data-ttu-id="b7821-121">"Remove Me" Responses and Responsibilities: Email Marketers must Honor "Unsubscribe" Claims</span><span class="sxs-lookup"><span data-stu-id="b7821-121">"Remove Me" Responses and Responsibilities: Email Marketers Must Honor "Unsubscribe" Claims</span></span>](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a><span data-ttu-id="b7821-122">Tekniska riktlinjer</span><span class="sxs-lookup"><span data-stu-id="b7821-122">Technical guidelines</span></span>

<span data-ttu-id="b7821-123">E-post som skickas till Microsoft 365 måste följa de tillämpliga rekommendationer som listas i dokumenten nedan (vissa länkar är endast tillgängliga på engelska).</span><span class="sxs-lookup"><span data-stu-id="b7821-123">Email sent to Microsoft 365 should comply with the applicable recommendations listed in the documents below (some links are only available in English).</span></span>

- [<span data-ttu-id="b7821-124">RFC 2505: Anti-Spam Recommendations for SMTP MTAs</span><span class="sxs-lookup"><span data-stu-id="b7821-124">RFC 2505: Anti-Spam Recommendations for SMTP MTAs</span></span>](https://www.ietf.org/rfc/rfc2505.txt)

- [<span data-ttu-id="b7821-125">RFC 2920: SMTP-tjänsttillägg för kommandoledning</span><span class="sxs-lookup"><span data-stu-id="b7821-125">RFC 2920: SMTP Service Extension for Command Pipelining</span></span>](https://www.ietf.org/rfc/rfc2920.txt)

<span data-ttu-id="b7821-126">Dessutom måste e-postservrar som ansluter till Microsoft 365 följa följande krav:</span><span class="sxs-lookup"><span data-stu-id="b7821-126">In addition, email servers connecting to Microsoft 365 must adhere to the following requirements:</span></span>

- <span data-ttu-id="b7821-127">Avsändaren förväntas följa alla tekniska standarder för överföring av internet-e-post, som publicerats av IETF (Internet Engineering Task Force, Internet Engineering Force), inklusive RFC 5321, RFC 5322 och andra.</span><span class="sxs-lookup"><span data-stu-id="b7821-127">Sender is expected to comply with all technical standards for the transmission of Internet email, as published by The Internet Society's Internet Engineering Task Force (IETF), including RFC 5321, RFC 5322, and others.</span></span>

- <span data-ttu-id="b7821-128">Efter ett givet numeriskt SMTP-felsvar mellan 500 och 599 (kallas även permanent svar vid utebliven leverans eller NDR) får avsändaren inte försöka att skicka meddelandet igen till mottagaren.</span><span class="sxs-lookup"><span data-stu-id="b7821-128">After given a numeric SMTP error response code between 500 and 599 (also known as a permanent non-delivery response or NDR), the sender must not attempt to retransmit that message to that recipient.</span></span>

- <span data-ttu-id="b7821-129">Efter flera icke-leveranssvar måste avsändaren upphöra med fler försök att skicka e-post till den mottagaren.</span><span class="sxs-lookup"><span data-stu-id="b7821-129">After multiple non-delivery responses, the sender must cease further attempts to send email to that recipient.</span></span>

- <span data-ttu-id="b7821-130">Meddelanden får inte skickas via oskyddat e-postrelä eller proxyservrar.</span><span class="sxs-lookup"><span data-stu-id="b7821-130">Messages must not be transmitted through insecure email relay or proxy servers.</span></span>

- <span data-ttu-id="b7821-131">Mekanismen för att avsluta prenumerationen, antingen från enskilda listor eller alla listor hos avsändaren, måste vara tydligt dokumenterad och lätt att hitta och använda för mottagarna.</span><span class="sxs-lookup"><span data-stu-id="b7821-131">The mechanism for unsubscribing, either from individual lists or all lists hosted by the sender, must be clearly documented and easy for recipients to find and use.</span></span>

- <span data-ttu-id="b7821-132">Anslutningar från dynamiskt IP-blanksteg kanske inte accepteras.</span><span class="sxs-lookup"><span data-stu-id="b7821-132">Connections from dynamic IP space may not be accepted.</span></span>

- <span data-ttu-id="b7821-133">E-postservrar måste ha giltiga omvända DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="b7821-133">Email servers must have valid reverse DNS records.</span></span>

## <a name="reputation-management"></a><span data-ttu-id="b7821-134">Rykteshantering</span><span class="sxs-lookup"><span data-stu-id="b7821-134">Reputation management</span></span>

<span data-ttu-id="b7821-135">Avsändare, Internetleverantörer och andra tjänsteleverantörer bör aktivt hantera ryktet för dina utgående IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="b7821-135">Senders, ISP's, and other service providers should actively manage the reputation of your outbound IP addresses.</span></span>

## <a name="microsoft-365-limits"></a><span data-ttu-id="b7821-136">Begränsningar för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7821-136">Microsoft 365 limits</span></span>

<span data-ttu-id="b7821-137">Avsändare måste följa de Microsoft 365-begränsningar som anges i [Exchange Online Protection Limits.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)</span><span class="sxs-lookup"><span data-stu-id="b7821-137">Senders must adhere to Microsoft 365 limits listed in [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).</span></span>

## <a name="email-delivery-resources-and-organizations"></a><span data-ttu-id="b7821-138">Resurser för e-postleverans och organisationer</span><span class="sxs-lookup"><span data-stu-id="b7821-138">Email delivery resources and organizations</span></span>

<span data-ttu-id="b7821-139">Microsoft arbetar aktivt med branschorgan och tjänsteleverantörer för att förbättra internet- och e-postesystemen.</span><span class="sxs-lookup"><span data-stu-id="b7821-139">Microsoft actively works with industry bodies and service providers in order to improve the internet and email ecosystem.</span></span> <span data-ttu-id="b7821-140">Dessa organisationer har publicerat dokument med bästa praxis som vi ger support och rekommenderar avsändare följer.</span><span class="sxs-lookup"><span data-stu-id="b7821-140">These organizations have published best practice documents that we support and recommend senders adhere to.</span></span> <span data-ttu-id="b7821-141">Det förbättrar möjligheten att leverera e-post bland flera olika e-postleverantörer över hela världen.</span><span class="sxs-lookup"><span data-stu-id="b7821-141">This improves your ability to deliver email among several email service providers around the world.</span></span>

- [<span data-ttu-id="b7821-142">Messaging Malware Mobile – anti abuse working group</span><span class="sxs-lookup"><span data-stu-id="b7821-142">Messaging Malware Mobile Anti-Abuse Working Group</span></span>](https://www.m3aawg.org/)

- [<span data-ttu-id="b7821-143">Online Trust Alliance</span><span class="sxs-lookup"><span data-stu-id="b7821-143">Online Trust Alliance</span></span>](https://www.internetsociety.org/ota/)

- [<span data-ttu-id="b7821-144">E-postavsändare & leverantörsavsändare</span><span class="sxs-lookup"><span data-stu-id="b7821-144">Email Sender & Provider Coalition</span></span>](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a><span data-ttu-id="b7821-145">Rapportering av missbruk och skräppost</span><span class="sxs-lookup"><span data-stu-id="b7821-145">Abuse and spam reporting</span></span>

<span data-ttu-id="b7821-146">Om du vill rapportera olagliga, olämpliga, oönskade eller skadliga e-postmeddelanden, se [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="b7821-146">To report unlawful, abusive, unwanted or malicious email, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="b7821-147">Att skicka dessa typer av kommunikation är ett brott mot Microsoft-principen och lämpliga åtgärder vidtas på bekräftade rapporter.</span><span class="sxs-lookup"><span data-stu-id="b7821-147">Sending these types of communications is a violation of Microsoft policy, and appropriate action will be taken on confirmed reports.</span></span>

## <a name="law-enforcement"></a><span data-ttu-id="b7821-148">Upprätthållande av lagstiftning</span><span class="sxs-lookup"><span data-stu-id="b7821-148">Law enforcement</span></span>

<span data-ttu-id="b7821-149">Om du är medlem i lagens verkställande och vill hjälpa Microsoft Corporation med juridisk dokumentation om Office 365, eller om du har frågor om juridisk dokumentation du har skickat till Microsoft, kan du ringa (1) (425) 722-1299.</span><span class="sxs-lookup"><span data-stu-id="b7821-149">If you are a member of law enforcement and wish to serve Microsoft Corporation with legal documentation regarding Office 365, or if you have questions regarding legal documentation you have submitted to Microsoft, please call (1) (425) 722-1299.</span></span>
