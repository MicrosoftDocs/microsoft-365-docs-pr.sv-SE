---
title: Skapa aviseringar för exakta datamatchningsaktiviteter
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
ms.openlocfilehash: da00c43ae9ba5b129129027df16f49ef80b8757d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288173"
---
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="e0b96-103">Skapa aviseringar för exakta datamatchningsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="e0b96-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="e0b96-104">När du [skapar anpassade typer av känslig information med exakt datamatchning (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) finns det ett antal aktiviteter som har skapats i [granskningsloggen](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="e0b96-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="e0b96-105">Du kan använda cmdleten [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell för att skapa meddelande som visar när dessa aktiviteter inträffar:</span><span class="sxs-lookup"><span data-stu-id="e0b96-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="e0b96-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="e0b96-106">CreateSchema</span></span>
- <span data-ttu-id="e0b96-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="e0b96-107">EditSchema</span></span>
- <span data-ttu-id="e0b96-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="e0b96-108">RemoveSchema</span></span>
- <span data-ttu-id="e0b96-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="e0b96-109">UploadDataFailed</span></span>
- <span data-ttu-id="e0b96-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="e0b96-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="e0b96-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e0b96-111">Pre-requisites</span></span>

<span data-ttu-id="e0b96-112">Det konto du använder måste vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="e0b96-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="e0b96-113">en global administratör</span><span class="sxs-lookup"><span data-stu-id="e0b96-113">a global admin</span></span>
- <span data-ttu-id="e0b96-114">efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="e0b96-114">compliance administrator</span></span>
- <span data-ttu-id="e0b96-115">Exchange Online-administratör</span><span class="sxs-lookup"><span data-stu-id="e0b96-115">Exchange Online administrator</span></span>

<span data-ttu-id="e0b96-116">Läs mer om DLP-behörigheter i [Behörigheter](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="e0b96-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="e0b96-117">EDM-baserad klassificering ingår i dessa prenumerationer</span><span class="sxs-lookup"><span data-stu-id="e0b96-117">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="e0b96-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e0b96-118">Office 365 E5</span></span>
- <span data-ttu-id="e0b96-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e0b96-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="e0b96-120">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="e0b96-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="e0b96-121">Microsoft E5/A5 Information Protection och styrning</span><span class="sxs-lookup"><span data-stu-id="e0b96-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="e0b96-122">Läs mer om DLP-licensiering i [licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span><span class="sxs-lookup"><span data-stu-id="e0b96-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="e0b96-123">Konfigurera meddelande för EDM-aktiviteter</span><span class="sxs-lookup"><span data-stu-id="e0b96-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="e0b96-124">Ansluta till [Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="e0b96-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell)</span></span> 

2. <span data-ttu-id="e0b96-125">Kör cmdleten `New-ProtectionAlert` med den aktivitet som du vill skapa meddelande för.</span><span class="sxs-lookup"><span data-stu-id="e0b96-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="e0b96-126">Om du, till exempel, vill få ett meddelande när åtgärden inträffade i **UploadDataCompleted**, kör</span><span class="sxs-lookup"><span data-stu-id="e0b96-126">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="e0b96-127">för de **UploadDataFailed** kan du köra</span><span class="sxs-lookup"><span data-stu-id="e0b96-127">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="e0b96-128">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="e0b96-128">Related articles</span></span>

- [<span data-ttu-id="e0b96-129">Skapa anpassade typer av känslig information med exakt datamatchning U(EDM)</span><span class="sxs-lookup"><span data-stu-id="e0b96-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="e0b96-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="e0b96-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert)