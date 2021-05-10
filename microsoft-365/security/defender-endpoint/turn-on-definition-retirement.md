---
title: Aktivera att definitionen inaktiveras för Microsoft Defender Antivirus
description: Aktivera att definitionen inaktiveras för Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, definition som finns i retirement
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
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296496"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="9ea55-104">Aktivera att definitionen inaktiveras</span><span class="sxs-lookup"><span data-stu-id="9ea55-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9ea55-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9ea55-105">**Applies to:**</span></span>

- [<span data-ttu-id="9ea55-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9ea55-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9ea55-107">Du kan konfigurera att en definition ska sluta användas med grupprinciper.</span><span class="sxs-lookup"><span data-stu-id="9ea55-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="9ea55-108">Definition som inte längre behövs kontrollerar om en dator har de säkerhetsuppdateringar som krävs för att skydda den mot ett visst säkerhetshål.</span><span class="sxs-lookup"><span data-stu-id="9ea55-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="9ea55-109">Om systemet inte är sårbart för sårbarheten som identifieras av en definition kommer den definitionen att "dras tillbaka".</span><span class="sxs-lookup"><span data-stu-id="9ea55-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="9ea55-110">Om all säkerhetsinformation för ett visst protokoll dras tillbaka analyseras inte det protokollet längre.</span><span class="sxs-lookup"><span data-stu-id="9ea55-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="9ea55-111">Om du aktiverar den här funktionen kan du förbättra prestandan.</span><span class="sxs-lookup"><span data-stu-id="9ea55-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="9ea55-112">Nätverksskydd påverkar inte nätverksprestandan på datorer som är uppdaterade med de senaste säkerhetsuppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="9ea55-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="9ea55-113">Använda grupprincip för att ta ut en definition</span><span class="sxs-lookup"><span data-stu-id="9ea55-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="9ea55-114">Öppna konsolen Grupprinciphantering på slutpunkten [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="9ea55-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="9ea55-115">Gå till **Administrativa mallar för**  >  **datorkonfiguration** Windows  >  **komponenter**  >  **Microsoft Defender Antivirus** System  >  **för nätverksinspektion.**</span><span class="sxs-lookup"><span data-stu-id="9ea55-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="9ea55-116">Välj **Aktivera att definitionen inaktiveras**.</span><span class="sxs-lookup"><span data-stu-id="9ea55-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="9ea55-117">Den här principen är aktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="9ea55-117">By default, this policy is enabled.</span></span> <span data-ttu-id="9ea55-118">Om denna **anges som Ej konfigurerad** kommer den att vara aktiverad.</span><span class="sxs-lookup"><span data-stu-id="9ea55-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="9ea55-119">Om du vill redigera principen väljer du **länken Redigera principinställning.**</span><span class="sxs-lookup"><span data-stu-id="9ea55-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="9ea55-120">Välj **Aktiverad** och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="9ea55-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="9ea55-121">Distribuera det uppdaterade grupprincipobjektet.</span><span class="sxs-lookup"><span data-stu-id="9ea55-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="9ea55-122">Se [Konsolen för hantering av grupprincip](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="9ea55-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="9ea55-123">Använder du grupprincipobjekt lokalt?</span><span class="sxs-lookup"><span data-stu-id="9ea55-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="9ea55-124">Se hur de översätter i molnet.</span><span class="sxs-lookup"><span data-stu-id="9ea55-124">See how they translate in the cloud.</span></span> <span data-ttu-id="9ea55-125">[Analysera lokala grupprincipobjekt med grupprincipanalyser i olika Microsoft Endpoint Manager – förhandsversion.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="9ea55-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="9ea55-126">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="9ea55-126">Related articles</span></span>

- [<span data-ttu-id="9ea55-127">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ea55-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="9ea55-128">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="9ea55-128">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="9ea55-129">Så här skapar och distribuerar du skydd mot skadlig programvara: Molnskyddstjänst</span><span class="sxs-lookup"><span data-stu-id="9ea55-129">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)