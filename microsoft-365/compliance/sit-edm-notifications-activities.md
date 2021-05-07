---
title: Skapa meddelande för exakta datamatchningsaktiviteter (förhandsversion)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lär dig att skapa aviseringar för exakta datamatchningsaktiviteter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e2f67ef0f276211483519bd5e246e4e041b2b15
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162037"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a><span data-ttu-id="77646-103">Skapa meddelande för exakta datamatchningsaktiviteter (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="77646-103">Create notifications for exact data match activities (preview)</span></span>

<span data-ttu-id="77646-104">När du [skapar anpassade typer av känslig information med exakt datamatchning (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) finns det ett antal aktiviteter som har skapats i [granskningsloggen](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="77646-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="77646-105">Du kan använda cmdleten [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell för att skapa meddelande som visar när dessa aktiviteter inträffar:</span><span class="sxs-lookup"><span data-stu-id="77646-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="77646-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="77646-106">CreateSchema</span></span>
- <span data-ttu-id="77646-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="77646-107">EditSchema</span></span>
- <span data-ttu-id="77646-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="77646-108">RemoveSchema</span></span>
- <span data-ttu-id="77646-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="77646-109">UploadDataFailed</span></span>
- <span data-ttu-id="77646-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="77646-110">UploadDataCompleted</span></span>

> [!NOTE]
> <span data-ttu-id="77646-111">Möjligheten att skapa meddelande för EDM-aktiviteter är endast tillgänglig för World Wide- och GCC-moln.</span><span class="sxs-lookup"><span data-stu-id="77646-111">The ability to create notifications for EDM activities is only available for the World Wide and GCC clouds only.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="77646-112">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="77646-112">Pre-requisites</span></span>

<span data-ttu-id="77646-113">Det konto du använder måste vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="77646-113">The account you use must be one of the following:</span></span>

- <span data-ttu-id="77646-114">en global administratör</span><span class="sxs-lookup"><span data-stu-id="77646-114">a global admin</span></span>
- <span data-ttu-id="77646-115">efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="77646-115">compliance administrator</span></span>
- <span data-ttu-id="77646-116">Exchange Online-administratör</span><span class="sxs-lookup"><span data-stu-id="77646-116">Exchange Online administrator</span></span>

<span data-ttu-id="77646-117">Läs mer om DLP-behörigheter i [Behörigheter](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="77646-117">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="77646-118">EDM-baserad klassificering ingår i dessa prenumerationer</span><span class="sxs-lookup"><span data-stu-id="77646-118">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="77646-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="77646-119">Office 365 E5</span></span>
- <span data-ttu-id="77646-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="77646-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="77646-121">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="77646-121">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="77646-122">Microsoft E5/A5 Information Protection och styrning</span><span class="sxs-lookup"><span data-stu-id="77646-122">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="77646-123">Läs mer om DLP-licensiering i [licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span><span class="sxs-lookup"><span data-stu-id="77646-123">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="77646-124">Konfigurera meddelande för EDM-aktiviteter</span><span class="sxs-lookup"><span data-stu-id="77646-124">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="77646-125">Ansluta till [Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="77646-125">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="77646-126">Kör cmdleten `New-ProtectionAlert` med den aktivitet som du vill skapa meddelande för.</span><span class="sxs-lookup"><span data-stu-id="77646-126">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="77646-127">Om du, till exempel, vill få ett meddelande när åtgärden inträffade i **UploadDataCompleted**, kör</span><span class="sxs-lookup"><span data-stu-id="77646-127">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="77646-128">för de **UploadDataFailed** kan du köra</span><span class="sxs-lookup"><span data-stu-id="77646-128">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="77646-129">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="77646-129">Related articles</span></span>

- [<span data-ttu-id="77646-130">Skapa anpassade typer av känslig information med exakt datamatchning U(EDM)</span><span class="sxs-lookup"><span data-stu-id="77646-130">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="77646-131">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="77646-131">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert?view=exchange-ps)