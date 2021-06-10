---
title: Lista exponerade enheter av en åtgärdsaktivitet
description: Returnerar information om exponerade enheter för den angivna åtgärdsaktiviteten.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation exposed devices
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9b10659f76e5b05bea11f5c6c55ca7c2a34a2db5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772167"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="ecab7-104">Lista exponerade enheter av en åtgärdsaktivitet</span><span class="sxs-lookup"><span data-stu-id="ecab7-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ecab7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ecab7-105">**Applies to:**</span></span>

- [<span data-ttu-id="ecab7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ecab7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ecab7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ecab7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ecab7-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ecab7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ecab7-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ecab7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="ecab7-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="ecab7-110">API Description</span></span>

<span data-ttu-id="ecab7-111">Returnerar information om exponerade enheter för den angivna åtgärdsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="ecab7-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="ecab7-112">[Läs mer om åtgärder](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="ecab7-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="ecab7-113">Lista över exponerade enheter som är associerade med en åtgärdsaktivitet (ID)</span><span class="sxs-lookup"><span data-stu-id="ecab7-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="ecab7-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="ecab7-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="ecab7-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="ecab7-115">Permissions</span></span>

<span data-ttu-id="ecab7-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="ecab7-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ecab7-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ecab7-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="ecab7-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="ecab7-118">Permission type</span></span> | <span data-ttu-id="ecab7-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="ecab7-119">Permission</span></span> | <span data-ttu-id="ecab7-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="ecab7-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ecab7-121">Program</span><span class="sxs-lookup"><span data-stu-id="ecab7-121">Application</span></span> | <span data-ttu-id="ecab7-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="ecab7-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="ecab7-123">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="ecab7-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="ecab7-124">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="ecab7-124">Delegated (work or school account)</span></span> | <span data-ttu-id="ecab7-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="ecab7-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="ecab7-126">\'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'</span><span class="sxs-lookup"><span data-stu-id="ecab7-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="ecab7-127">Egenskapsinformation</span><span class="sxs-lookup"><span data-stu-id="ecab7-127">Properties details</span></span>

<span data-ttu-id="ecab7-128">Egenskap (id)</span><span class="sxs-lookup"><span data-stu-id="ecab7-128">Property (id)</span></span> | <span data-ttu-id="ecab7-129">Datatyp</span><span class="sxs-lookup"><span data-stu-id="ecab7-129">Data type</span></span> | <span data-ttu-id="ecab7-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ecab7-130">Description</span></span> | <span data-ttu-id="ecab7-131">Exempel</span><span class="sxs-lookup"><span data-stu-id="ecab7-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="ecab7-132">id</span><span class="sxs-lookup"><span data-stu-id="ecab7-132">id</span></span> | <span data-ttu-id="ecab7-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="ecab7-133">String</span></span> | <span data-ttu-id="ecab7-134">Enhets-ID</span><span class="sxs-lookup"><span data-stu-id="ecab7-134">Device ID</span></span> | <span data-ttu-id="ecab7-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="ecab7-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="ecab7-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="ecab7-136">computerDnsName</span></span> | <span data-ttu-id="ecab7-137">Sträng</span><span class="sxs-lookup"><span data-stu-id="ecab7-137">String</span></span> | <span data-ttu-id="ecab7-138">Enhetsnamn</span><span class="sxs-lookup"><span data-stu-id="ecab7-138">Device name</span></span> | <span data-ttu-id="ecab7-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="ecab7-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="ecab7-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="ecab7-140">osPlatform</span></span> | <span data-ttu-id="ecab7-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="ecab7-141">String</span></span> | <span data-ttu-id="ecab7-142">Operativsystem för enheter</span><span class="sxs-lookup"><span data-stu-id="ecab7-142">Device operating system</span></span> | <span data-ttu-id="ecab7-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="ecab7-143">WindowsServer2012R2</span></span>
<span data-ttu-id="ecab7-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="ecab7-144">rbacGroupName</span></span> | <span data-ttu-id="ecab7-145">Sträng</span><span class="sxs-lookup"><span data-stu-id="ecab7-145">String</span></span> | <span data-ttu-id="ecab7-146">Namnet på enhetsgruppen som enheten är associerad med</span><span class="sxs-lookup"><span data-stu-id="ecab7-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="ecab7-147">Servrar</span><span class="sxs-lookup"><span data-stu-id="ecab7-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="ecab7-148">Exempel</span><span class="sxs-lookup"><span data-stu-id="ecab7-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="ecab7-149">Exempel på förfrågan</span><span class="sxs-lookup"><span data-stu-id="ecab7-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="ecab7-150">Svarsexempel</span><span class="sxs-lookup"><span data-stu-id="ecab7-150">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ecab7-151">Se även</span><span class="sxs-lookup"><span data-stu-id="ecab7-151">See also</span></span>

- [<span data-ttu-id="ecab7-152">Åtgärdsmetoder och egenskaper</span><span class="sxs-lookup"><span data-stu-id="ecab7-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="ecab7-153">Få en åtgärdsaktivitet efter ID</span><span class="sxs-lookup"><span data-stu-id="ecab7-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="ecab7-154">Lista alla åtgärdsaktiviteter</span><span class="sxs-lookup"><span data-stu-id="ecab7-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="ecab7-155">Riskbaserade hot & hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="ecab7-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="ecab7-156">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="ecab7-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
