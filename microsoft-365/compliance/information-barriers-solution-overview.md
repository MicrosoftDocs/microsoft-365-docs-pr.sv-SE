---
title: Informationsbarriärer i Microsoft 365
description: Lär dig hur du konfigurerar informationsbarriärer i Microsoft 365.
keywords: Microsoft 365, insider-risk, efterlevnad
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: a4c7b711c0a977e0980cd0c72f9369833e9e5c65
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "52161806"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="eef03-104">Informationsbarriärer i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eef03-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="eef03-105">Microsoft 365 möjliggör kommunikation och samarbete mellan grupper och organisationer samt stöd för sätt att begränsa kommunikation och samarbete mellan specifika grupper av användare vid behov.</span><span class="sxs-lookup"><span data-stu-id="eef03-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="eef03-106">Det kan inkludera situationer eller scenarier där du vill begränsa kommunikation och samarbete mellan två grupper för att undvika att en intressekonflikt uppstår i organisationen.</span><span class="sxs-lookup"><span data-stu-id="eef03-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="eef03-107">Det kan också vara situationer där du behöver begränsa kommunikation och samarbete mellan vissa personer i organisationen för att skydda intern information.</span><span class="sxs-lookup"><span data-stu-id="eef03-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="eef03-108">Informationsbarriärer stöds i Microsoft Teams, SharePoint Online och OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="eef03-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="eef03-109">En efterlevnadsadministratör eller informationsbarriäradministratör kan definiera principer för att tillåta eller förhindra kommunikation mellan grupper av användare i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eef03-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="eef03-110">Informationsbarriärprinciper kan användas i situationer som dessa:</span><span class="sxs-lookup"><span data-stu-id="eef03-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="eef03-111">Användare i daggruppen ska inte kommunicera eller dela filer med marknadsföringsteamet</span><span class="sxs-lookup"><span data-stu-id="eef03-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="eef03-112">Ekonomipersonal som arbetar med konfidentiell företagsinformation ska inte kommunicera eller dela filer med vissa grupper inom organisationen</span><span class="sxs-lookup"><span data-stu-id="eef03-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="eef03-113">Ett internt team med affärshemlighetsmaterial ska inte ringa eller chatta online med personer i vissa grupper inom organisationen</span><span class="sxs-lookup"><span data-stu-id="eef03-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="eef03-114">En forskningsgrupp ska endast ringa eller chatta online med ett utvecklingsteam</span><span class="sxs-lookup"><span data-stu-id="eef03-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="eef03-115">Konfigurera informationsbarriärer för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eef03-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="eef03-116">Använd följande steg för att konfigurera informationsbarriärer för din organisation:</span><span class="sxs-lookup"><span data-stu-id="eef03-116">Use the following steps to configure information barriers for your organization:</span></span>

![Steg för att hitta information om Insider-risklösning](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="eef03-118">Läs mer [om informationsbarriärer](information-barriers.md) i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eef03-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="eef03-119">Konfigurera [krav och behörigheter](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="eef03-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="eef03-120">Segmentanvändare [i organisationen](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="eef03-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="eef03-121">Skapa och konfigurera [principer för informationsbarriärer](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="eef03-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="eef03-122">Tillämpa [principer för informationsbarriärer](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="eef03-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="eef03-123">Mer information om informationsbarriärer</span><span class="sxs-lookup"><span data-stu-id="eef03-123">More information about information barriers</span></span>

- [<span data-ttu-id="eef03-124">Attribut för informationsbarriärsprinciper</span><span class="sxs-lookup"><span data-stu-id="eef03-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="eef03-125">Redigera eller ta bort informationsbarriärer</span><span class="sxs-lookup"><span data-stu-id="eef03-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)