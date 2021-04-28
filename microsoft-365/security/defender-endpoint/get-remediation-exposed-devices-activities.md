---
title: Lista över exponerade enheter med en åtgärdsaktivitet
description: Returnerar information om exponerade enheter för den angivna åtgärdsaktiviteten.
keywords: apis, remediation, remediation api, get, remediation tasks,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 097d8d784ca7c02fce1fc0e9fc51bdc272951f4a
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061194"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="182f1-104">Lista över exponerade enheter med en åtgärdsaktivitet</span><span class="sxs-lookup"><span data-stu-id="182f1-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="182f1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="182f1-105">**Applies to:**</span></span>

- [<span data-ttu-id="182f1-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="182f1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="182f1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="182f1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="182f1-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="182f1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="182f1-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="182f1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="182f1-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="182f1-110">API Description</span></span>

<span data-ttu-id="182f1-111">Returnerar information om exponerade enheter för den angivna åtgärdsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="182f1-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="182f1-112">[Läs mer om åtgärder](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="182f1-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="182f1-113">Lista över exponerade enheter som är associerade med en åtgärdsaktivitet (ID)</span><span class="sxs-lookup"><span data-stu-id="182f1-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="182f1-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="182f1-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

<span data-ttu-id="182f1-115">**Egenskapsinformation**</span><span class="sxs-lookup"><span data-stu-id="182f1-115">**Properties** details</span></span>

<span data-ttu-id="182f1-116">Egenskap (id)</span><span class="sxs-lookup"><span data-stu-id="182f1-116">Property (id)</span></span> | <span data-ttu-id="182f1-117">Datatyp</span><span class="sxs-lookup"><span data-stu-id="182f1-117">Data type</span></span> | <span data-ttu-id="182f1-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="182f1-118">Description</span></span> | <span data-ttu-id="182f1-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="182f1-119">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="182f1-120">id</span><span class="sxs-lookup"><span data-stu-id="182f1-120">id</span></span> | <span data-ttu-id="182f1-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="182f1-121">String</span></span> | <span data-ttu-id="182f1-122">Enhets-ID</span><span class="sxs-lookup"><span data-stu-id="182f1-122">Device ID</span></span> | <span data-ttu-id="182f1-123">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="182f1-123">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="182f1-124">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="182f1-124">computerDnsName</span></span> | <span data-ttu-id="182f1-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="182f1-125">String</span></span> | <span data-ttu-id="182f1-126">Enhetsnamn</span><span class="sxs-lookup"><span data-stu-id="182f1-126">Device name</span></span> | <span data-ttu-id="182f1-127">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="182f1-127">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="182f1-128">osPlatform</span><span class="sxs-lookup"><span data-stu-id="182f1-128">osPlatform</span></span> | <span data-ttu-id="182f1-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="182f1-129">String</span></span> | <span data-ttu-id="182f1-130">Operativsystem för enheter</span><span class="sxs-lookup"><span data-stu-id="182f1-130">Device operating system</span></span> | <span data-ttu-id="182f1-131">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="182f1-131">WindowsServer2012R2</span></span>
<span data-ttu-id="182f1-132">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="182f1-132">rbacGroupName</span></span> | <span data-ttu-id="182f1-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="182f1-133">String</span></span> | <span data-ttu-id="182f1-134">Namnet på enhetsgruppen som enheten är associerad med</span><span class="sxs-lookup"><span data-stu-id="182f1-134">Name of the device group this device is associated with</span></span> | <span data-ttu-id="182f1-135">Servrar</span><span class="sxs-lookup"><span data-stu-id="182f1-135">Servers</span></span>

## <a name="example"></a><span data-ttu-id="182f1-136">Exempel</span><span class="sxs-lookup"><span data-stu-id="182f1-136">Example</span></span>

<span data-ttu-id="182f1-137">**Exempel på** förfrågan</span><span class="sxs-lookup"><span data-stu-id="182f1-137">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

<span data-ttu-id="182f1-138">**Svarsexempel**</span><span class="sxs-lookup"><span data-stu-id="182f1-138">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="182f1-139">Se även</span><span class="sxs-lookup"><span data-stu-id="182f1-139">See also</span></span>

- [<span data-ttu-id="182f1-140">Åtgärdsmetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="182f1-140">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="182f1-141">Få en åtgärdsaktivitet efter ID</span><span class="sxs-lookup"><span data-stu-id="182f1-141">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="182f1-142">Lista alla åtgärder</span><span class="sxs-lookup"><span data-stu-id="182f1-142">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="182f1-143">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="182f1-143">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="182f1-144">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="182f1-144">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
