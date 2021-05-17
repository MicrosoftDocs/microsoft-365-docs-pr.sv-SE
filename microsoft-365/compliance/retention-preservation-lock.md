---
title: Använda bevarandelås för att begränsa ändringar av kvarhållningsprinciper och principer för kvarhållningsetiketter
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Använd bevarandelås med kvarhållningsprinciper och kvarhållningsetikettprinciper som hjälp att uppfylla regelkrav och skydda mot otillåtna administratörer.
ms.openlocfilehash: 72f667b970b4257a3a540fb74a121c620892b56d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162141"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="52046-103">Använda bevarandelås för att begränsa ändringar av kvarhållningsprinciper och principer för kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="52046-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="52046-104">*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="52046-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="52046-105">Med bevarandelås låses en kvarhållningsprincip eller en kvarhållningsetikett så att ingen – inte ens en global administratör – kan stänga av principen, ta bort principen eller göra den mindre restriktiv.</span><span class="sxs-lookup"><span data-stu-id="52046-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="52046-106">Den här konfigurationen kan krävas i regler och kan skydda mot otillåtna administratörer.</span><span class="sxs-lookup"><span data-stu-id="52046-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="52046-107">När en kvarhållningsprincip är låst:</span><span class="sxs-lookup"><span data-stu-id="52046-107">When a retention policy is locked:</span></span>

- <span data-ttu-id="52046-108">Ingen kan inaktivera principen eller ta bort den</span><span class="sxs-lookup"><span data-stu-id="52046-108">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="52046-109">Platser kan läggas till men inte tas bort</span><span class="sxs-lookup"><span data-stu-id="52046-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="52046-110">Du kan förlänga kvarhållningsperioden men inte minska den</span><span class="sxs-lookup"><span data-stu-id="52046-110">You can extend the retention period but not decrease it</span></span>

<span data-ttu-id="52046-111">När en princip för kvarhållningsetiketter är låst:</span><span class="sxs-lookup"><span data-stu-id="52046-111">When a retention label policy is locked:</span></span>

- <span data-ttu-id="52046-112">Ingen kan inaktivera principen eller ta bort den</span><span class="sxs-lookup"><span data-stu-id="52046-112">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="52046-113">Platser kan läggas till men inte tas bort</span><span class="sxs-lookup"><span data-stu-id="52046-113">Locations can be added but not removed</span></span>
- <span data-ttu-id="52046-114">Etiketter kan läggas till men inte tas bort</span><span class="sxs-lookup"><span data-stu-id="52046-114">Labels can be added but not removed</span></span>

<span data-ttu-id="52046-115">Sammanfattningsvis kan en låst princip utökas eller förlängas, men den kan inte minskas eller inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="52046-115">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52046-116">Innan du låser en kvarhållningsprincip eller en princip för kvarhållningsetiketter är det viktigt att du förstår effekten och undersöker om den krävs för din organisation.</span><span class="sxs-lookup"><span data-stu-id="52046-116">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="52046-117">Den kan till exempel krävas för att uppfylla regelkrav.</span><span class="sxs-lookup"><span data-stu-id="52046-117">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="52046-118">Administratörer kan inte inaktivera eller ta bort dessa principer när bevarandelåset används.</span><span class="sxs-lookup"><span data-stu-id="52046-118">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="52046-119">Konfigurera bevarandelåset när du har skapat en [-kvarhållningsprincip](create-retention-policies.md)eller en princip för kvarhållningsetiketter som du [publicerar](create-apply-retention-labels.md) eller [använder automatiskt](apply-retention-labels-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="52046-119">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="52046-120">Att låsa en etikettprincip förhindrar inte att en administratör kan minska kvarhållningsperioden för en etikett som ingår i den låsta principen.</span><span class="sxs-lookup"><span data-stu-id="52046-120">Locking a label policy doesn't prevent an administrator from reducing the retention period in a label that is included in the locked policy.</span></span> <span data-ttu-id="52046-121">Det kravet kan med andra begränsningar uppfyllas när du konfigurerar en etikett som markerar objekt som en [regelpost](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="52046-121">That requirement, with other restrictions, can be met when you configure a label to mark items as a [regulatory record](records-management.md#records).</span></span>

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="52046-122">Låsa en kvarhållningsprincip eller princip för kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="52046-122">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="52046-123">Du måste använda PowerShell om du ska använda bevarandelås.</span><span class="sxs-lookup"><span data-stu-id="52046-123">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="52046-124">Eftersom administratörer inte kan inaktivera eller ta bort en kvarhållningsprincip när låset används, är funktionen inte tillgänglig i användargränssnittet som skydd mot oavsiktlig konfiguration.</span><span class="sxs-lookup"><span data-stu-id="52046-124">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="52046-125">Alla principer för kvarhållning och med valfri konfiguration har stöd för bevarandelås.</span><span class="sxs-lookup"><span data-stu-id="52046-125">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="52046-126">[Ansluta till Säkerhets- och efterlevnadscenter i PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="52046-126">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="52046-127">Leta reda på namnet på den princip som du vill låsa genom att köra [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy).</span><span class="sxs-lookup"><span data-stu-id="52046-127">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="52046-128">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="52046-128">For example:</span></span>
    
   ![Lista med kvarhållningsprinciper i PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="52046-130">Om du vill ha ett bevarandelås i principen kör du cmdleten [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) med namnet på principen och parametern *RestrictiveRetention* inställd på sant:</span><span class="sxs-lookup"><span data-stu-id="52046-130">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="52046-131">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="52046-131">For example:</span></span>
    
    ![Parametern RestrictiveRetention i PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="52046-133">När du uppmanas till det läser du och godkänner begränsningarna som medföljer konfigurationen genom att ange **J**:</span><span class="sxs-lookup"><span data-stu-id="52046-133">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>
    
   ![Uppmaning att bekräfta att du vill låsa en kvarhållningsprincip i PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="52046-135">Ett bevarandelås placeras nu i principen.</span><span class="sxs-lookup"><span data-stu-id="52046-135">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="52046-136">För att bekräfta kör du `Get-RetentionCompliancePolicy` igen, men anger namnet på principen och visar principparametrarna:</span><span class="sxs-lookup"><span data-stu-id="52046-136">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="52046-137">Du bör se att **RestrictiveRetention** är inställt på **Sant**.</span><span class="sxs-lookup"><span data-stu-id="52046-137">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="52046-138">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="52046-138">For example:</span></span>

![Låst princip där alla parametrar visas i PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="52046-140">Se även</span><span class="sxs-lookup"><span data-stu-id="52046-140">See also</span></span>

<span data-ttu-id="52046-141">[Resurser som hjälper dig att uppfylla regelkrav för informationsstyrning och hantering av arkivhandlingar](retention-regulatory-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52046-141">[Resources to help you meet regulatory requirements for information governance and records management](retention-regulatory-requirements.md)</span></span>