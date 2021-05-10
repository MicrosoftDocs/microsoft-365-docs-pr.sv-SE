---
title: Aktivera protokolligenkänning för Microsoft Defender Antivirus
description: Aktivera protokolligenkänning för Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, protokolligenkänning
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
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296495"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="39624-104">Aktivera protokolligenkänning</span><span class="sxs-lookup"><span data-stu-id="39624-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="39624-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="39624-105">**Applies to:**</span></span>

- [<span data-ttu-id="39624-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="39624-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="39624-107">Med den här principinställningen kan du konfigurera protokolligenkänning för nätverksskydd mot sårbarheter av kända säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="39624-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="39624-108">Om du aktiverar eller inte konfigurerar den här inställningen aktiveras protokolligenkänning.</span><span class="sxs-lookup"><span data-stu-id="39624-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="39624-109">Om du inaktiverar den här inställningen inaktiveras protokolligenkänningen.</span><span class="sxs-lookup"><span data-stu-id="39624-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="39624-110">Använda grupprinciper för att konfigurera protokolligenkänning</span><span class="sxs-lookup"><span data-stu-id="39624-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="39624-111">Öppna konsolen Grupprinciphantering på slutpunkten [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="39624-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="39624-112">Gå till **Administrativa mallar för**  >  **datorkonfiguration** Windows  >  **komponenter**  >  **Microsoft Defender Antivirus** System  >  **för nätverksinspektion.**</span><span class="sxs-lookup"><span data-stu-id="39624-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="39624-113">Välj **protokolligenkänning**.</span><span class="sxs-lookup"><span data-stu-id="39624-113">Select **protocol recognition**.</span></span> <span data-ttu-id="39624-114">Den här principen är aktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="39624-114">By default, this policy is enabled.</span></span> <span data-ttu-id="39624-115">Om denna **anges som Ej konfigurerad** kommer den att vara aktiverad.</span><span class="sxs-lookup"><span data-stu-id="39624-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="39624-116">Om du vill redigera principen väljer du **länken Redigera principinställning.**</span><span class="sxs-lookup"><span data-stu-id="39624-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="39624-117">Välj **Aktiverad** och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="39624-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="39624-118">Distribuera det uppdaterade grupprincipobjektet.</span><span class="sxs-lookup"><span data-stu-id="39624-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="39624-119">Se [Konsolen för hantering av grupprincip](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="39624-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="39624-120">Använder du grupprincipobjekt lokalt?</span><span class="sxs-lookup"><span data-stu-id="39624-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="39624-121">Se hur de översätter i molnet.</span><span class="sxs-lookup"><span data-stu-id="39624-121">See how they translate in the cloud.</span></span> <span data-ttu-id="39624-122">[Analysera lokala grupprincipobjekt med grupprincipanalyser i olika Microsoft Endpoint Manager – förhandsversion.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="39624-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="39624-123">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="39624-123">Related articles</span></span>

- [<span data-ttu-id="39624-124">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="39624-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="39624-125">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="39624-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="39624-126">Så här skapar och distribuerar du skydd mot skadlig programvara: Molnskyddstjänst</span><span class="sxs-lookup"><span data-stu-id="39624-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)