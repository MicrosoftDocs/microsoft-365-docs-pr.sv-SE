---
title: Inaktivera TLS 1.0 och 1.1 i Microsoft 365 GCC High och DoD
description: Här diskuteras hur Microsoft inaktiverar stöd för TLS 1.1 och 1.0 i GCC High- och DoD-miljöer i Microsoft 365.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162035"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a><span data-ttu-id="867eb-103">Inaktivera TLS 1.0 och 1.1 i Microsoft 365 GCC High och DoD</span><span class="sxs-lookup"><span data-stu-id="867eb-103">Disabling TLS 1.0 and 1.1 in Microsoft 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="867eb-104">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="867eb-104">Summary</span></span>

<span data-ttu-id="867eb-105">I syfte att uppfylla de senaste standarderna för Federal Risk and Authorization Management Program (FedRAMP) inaktiverar vi TLS-versionerna 1.1 och 1.0 i Microsoft 365 för GCC High- och DoD-miljöer.</span><span class="sxs-lookup"><span data-stu-id="867eb-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="867eb-106">Den här ändringen meddelades tidigare via Microsoft Support i Förbereda för obligatorisk användning [av TLS 1.2 i Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="867eb-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="867eb-107">Säkerheten för dina data är viktig och vi strävar efter transparens kring ändringar som kan påverka din användning av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="867eb-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="867eb-108">Även om [implementeringen av Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) inte har några kända säkerhetsproblem förblir vi engagerade i FedRAMP-efterlevnadsstandarder.</span><span class="sxs-lookup"><span data-stu-id="867eb-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="867eb-109">Därför inaktiverade vi TLS 1.1 och 1.0 i Microsoft 365 i GCC High- och DoD-miljöer den 15 januari 2020.</span><span class="sxs-lookup"><span data-stu-id="867eb-109">Therefore, we disabled TLS 1.1 and 1.0 in Microsoft 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="867eb-110">Mer information om hur du tar bort beroenden för TLS 1.1 och 1.0 finns i följande informationsdokument:</span><span class="sxs-lookup"><span data-stu-id="867eb-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="867eb-111">Lösa TLS 1.0-problemet</span><span class="sxs-lookup"><span data-stu-id="867eb-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="867eb-112">Mer information</span><span class="sxs-lookup"><span data-stu-id="867eb-112">More information</span></span>

<span data-ttu-id="867eb-113">Från och med den 15 januari 2020 Microsoft 365 I GCC High- och DoD-miljöer inaktiveras TLS 1.1 och 1.0.</span><span class="sxs-lookup"><span data-stu-id="867eb-113">Starting on January 15, 2020, Microsoft 365 in the GCC High and DoD environments will disable TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="867eb-114">Före den 15 januari 2020 ska alla kombinationer av klientservrar och webbläsarservrar använda TLS version 1.2 (eller en senare version) för att säkerställa att alla anslutningar kan göras utan problem Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="867eb-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Microsoft 365.</span></span> <span data-ttu-id="867eb-115">Detta kan kräva uppdateringar av vissa kombinationer av klientservrar och webbläsarservrar.</span><span class="sxs-lookup"><span data-stu-id="867eb-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="867eb-116">För SharePoint och OneDrive måste du uppdatera och konfigurera .NET med stöd för TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="867eb-116">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="867eb-117">Mer information finns i [Aktivera TLS 1.2 på klienter.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="867eb-117">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

<span data-ttu-id="867eb-118">Du måste uppdatera klientdatorerna för att säkerställa att du har kontinuerlig åtkomst till Office 365 GCC Hög och DoD.</span><span class="sxs-lookup"><span data-stu-id="867eb-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="867eb-119">Du måste uppdatera program som anropar Microsoft 365 API:er via TLS 1.0 eller TLS 1.1 för att använda TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="867eb-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="867eb-120">.NET 4.5 blir TLS 1.1 som standard.</span><span class="sxs-lookup"><span data-stu-id="867eb-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="867eb-121">Om du vill uppdatera .NET-konfigurationen går du till [Aktivera TLS (Transport Layer Security) 1.2 på klienter.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="867eb-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="867eb-122">Mer information finns i Förbereda [för obligatorisk användning av TLS 1.2 i Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="867eb-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="867eb-123">Vi vet att följande klientprogram inte kan använda TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="867eb-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="867eb-124">Android 4.3 och tidigare versioner</span><span class="sxs-lookup"><span data-stu-id="867eb-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="867eb-125">Firefox version 5.0 och tidigare versioner</span><span class="sxs-lookup"><span data-stu-id="867eb-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="867eb-126">Internet Explorer 8–10 på Windows 7 och tidigare versioner</span><span class="sxs-lookup"><span data-stu-id="867eb-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="867eb-127">Internet Explorer 10 på Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="867eb-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="867eb-128">Safari 6.0.4/OS X 10.8.4 och tidigare versioner</span><span class="sxs-lookup"><span data-stu-id="867eb-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="867eb-129">Även om den aktuella analysen av anslutningar till Microsoft Online-tjänster visar att de flesta tjänster och slutpunkter ser mycket lite TLS 1.1- och 1.0-användning, tillhandahåller vi ett meddelande om den här ändringen så att du kan uppdatera berörda klienter eller servrar efter behov innan stödet för TLS 1.1 och 1.0 upphör.</span><span class="sxs-lookup"><span data-stu-id="867eb-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="867eb-130">Om du använder en lokal infrastruktur för hybridscenarier eller AD FS (Active Directory Federation Services) ska du kontrollera att infrastrukturen har stöd för både inkommande och utgående anslutningar som använder TLS 1.2 (eller en senare version).</span><span class="sxs-lookup"><span data-stu-id="867eb-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="867eb-131">Utöver avbrott som kan hända om du använder de angivna klienterna som inte kan använda TLS 1.2 kommer borttagning av TLS 1.1 och 1.0 att hindra dig från att använda följande Microsoft-produkt:</span><span class="sxs-lookup"><span data-stu-id="867eb-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="867eb-132">Lync-telefon</span><span class="sxs-lookup"><span data-stu-id="867eb-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="867eb-133">Referenser</span><span class="sxs-lookup"><span data-stu-id="867eb-133">References</span></span>

<span data-ttu-id="867eb-134">Vägledning och referenser som hjälper till att säkerställa att klienterna använder TLS 1.2 finns i Förbereda för obligatorisk användning av [TLS 1.2 i Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="867eb-134">For guidance and references to help make sure that your clients are using TLS 1.2, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>