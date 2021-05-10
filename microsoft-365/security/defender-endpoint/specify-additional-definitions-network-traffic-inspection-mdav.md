---
title: Ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik för Microsoft Defender Antivirus
description: Ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik för Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, kontroll av nätverkstrafik
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300261"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="932dc-104">Ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik</span><span class="sxs-lookup"><span data-stu-id="932dc-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="932dc-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="932dc-105">**Applies to:**</span></span>

- [<span data-ttu-id="932dc-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="932dc-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="932dc-107">Du kan ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik med grupprincip.</span><span class="sxs-lookup"><span data-stu-id="932dc-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="932dc-108">Använda grupprincip till att ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik</span><span class="sxs-lookup"><span data-stu-id="932dc-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="932dc-109">Öppna konsolen Grupprinciphantering på slutpunkten [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="932dc-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="932dc-110">Gå till **Windows Komponenter**  >  **Microsoft Defender Antivirus**  >  **System för nätverksinspektion.**</span><span class="sxs-lookup"><span data-stu-id="932dc-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="932dc-111">Välj **Ange ytterligare definitionsuppsättningar för kontroll av nätverkstrafik**.</span><span class="sxs-lookup"><span data-stu-id="932dc-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="932dc-112">Som standard har den här principen inställningen **Ej konfigurerad.**</span><span class="sxs-lookup"><span data-stu-id="932dc-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="932dc-113">Om du vill redigera principen väljer du **länken Redigera principinställning.**</span><span class="sxs-lookup"><span data-stu-id="932dc-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="932dc-114">Välj **Aktiverad** och välj sedan **Visa...** i **avsnittet Alternativ.**</span><span class="sxs-lookup"><span data-stu-id="932dc-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="932dc-115">Lägg till poster i listan och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="932dc-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="932dc-116">Varje post måste anges som ett namnvärdepar, där namnet är en strängrepresentation av en definitionsuppsättning med GUID.</span><span class="sxs-lookup"><span data-stu-id="932dc-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="932dc-117">Som exempel definieras definitionsuppsättningen GUID för att aktivera testsäkerhetsinformation som: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` .</span><span class="sxs-lookup"><span data-stu-id="932dc-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="932dc-118">Värdet används inte, så vi rekommenderar att du ställer in det på `0` .</span><span class="sxs-lookup"><span data-stu-id="932dc-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="932dc-119">Välj **OK** och distribuera sedan det uppdaterade grupprincipobjektet.</span><span class="sxs-lookup"><span data-stu-id="932dc-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="932dc-120">Se [Konsolen för hantering av grupprincip](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="932dc-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="932dc-121">Använder du grupprincipobjekt lokalt?</span><span class="sxs-lookup"><span data-stu-id="932dc-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="932dc-122">Se hur de översätter i molnet.</span><span class="sxs-lookup"><span data-stu-id="932dc-122">See how they translate in the cloud.</span></span> <span data-ttu-id="932dc-123">[Analysera lokala grupprincipobjekt med grupprincipanalyser i olika Microsoft Endpoint Manager – förhandsversion.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="932dc-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="932dc-124">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="932dc-124">Related articles</span></span>

- [<span data-ttu-id="932dc-125">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="932dc-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="932dc-126">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="932dc-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="932dc-127">Så här skapar och distribuerar du skydd mot skadlig programvara: Molnskyddstjänst</span><span class="sxs-lookup"><span data-stu-id="932dc-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)