---
title: Aktivera domän anslutna Windows 10-enheter för att hanteras av Microsoft 365 för företag
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Läs om hur du aktiverar Microsoft 365 för att skydda lokala Active Directory-anslutna Windows 10-enheter med några få steg.
ms.openlocfilehash: 0b597110447272be128bfe1866234ac25a8e67e6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407087"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="451d4-103">Aktivera domän anslutna Windows 10-enheter för att hanteras av Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="451d4-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="451d4-104">Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.</span><span class="sxs-lookup"><span data-stu-id="451d4-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="451d4-105">Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter.**</span><span class="sxs-lookup"><span data-stu-id="451d4-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="451d4-106">Dessa enheter är anslutna till både din lokala Active Directory och Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="451d4-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="451d4-107">I det här videoklippet beskrivs hur du ställer in det här för det vanligaste scenariot, vilket också beskrivs i anvisningarna nedan.</span><span class="sxs-lookup"><span data-stu-id="451d4-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="451d4-108">Innan du börjar kontrollerar du att du har slutfört de här stegen:</span><span class="sxs-lookup"><span data-stu-id="451d4-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="451d4-109">Synkronisera användare till Azure AD med Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="451d4-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="451d4-110">Slutför synkroniseringen av Organisationsenhet (OU) i Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="451d4-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="451d4-111">Kontrollera att alla domänanvändare som du synkroniserar har licenser till Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="451d4-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="451d4-112">Anvisningar [finns i Synkronisera domänanvändare till Microsoft.](manage-domain-users.md)</span><span class="sxs-lookup"><span data-stu-id="451d4-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="451d4-113">1. Verifiera MDM Authority i Intune</span><span class="sxs-lookup"><span data-stu-id="451d4-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="451d4-114">Gå till [Slutpunktshanteraren,](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) välj Enhetsregistrering på sidan Microsoft  Intune och kontrollera sedan på sidan Översikt att **MDM-behörighet** är **Intune.**</span><span class="sxs-lookup"><span data-stu-id="451d4-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="451d4-115">Om **MDM-behörighet** **är Ingen** klickar du på **MDM-instansen** för att ställa in den på **Intune.**</span><span class="sxs-lookup"><span data-stu-id="451d4-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="451d4-116">Om **MDM** authority is **Microsoft Office 365**, go to **Devices**  >  **Enroll devices** and use the **Add MDM authority dialog** on the right to add **Intune MDM** authority **(the Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="451d4-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="451d4-117">2. Kontrollera att Azure AD är aktiverat för anslutning till datorer</span><span class="sxs-lookup"><span data-stu-id="451d4-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="451d4-118">Gå till administrationscentret och välj Azure Active Directory (välj Visa alla om Azure Active Directory inte visas) i listan <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  **administrationscenter.**</span><span class="sxs-lookup"><span data-stu-id="451d4-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="451d4-119">Gå till Azure Active Directory i **administrationscentret** för **Azure Active Directory,** välj **Enheter** och sedan **Enhetsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="451d4-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="451d4-120">Kontrollera **att användare kan ansluta enheter till Azure AD är** aktiverat</span><span class="sxs-lookup"><span data-stu-id="451d4-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="451d4-121">Ange till Alla om du vill aktivera **alla användare.**</span><span class="sxs-lookup"><span data-stu-id="451d4-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="451d4-122">Om du vill aktivera vissa användare anger du **Markerad** för att aktivera en viss grupp av användare.</span><span class="sxs-lookup"><span data-stu-id="451d4-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="451d4-123">Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="451d4-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="451d4-124">Välj **Välj grupper för** att aktivera MDM-användaromfattningen för säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="451d4-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="451d4-125">3. Kontrollera att Azure AD är aktiverat för MDM</span><span class="sxs-lookup"><span data-stu-id="451d4-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="451d4-126">Gå till administrationscentret och <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> välj Slutpunktshanterare (välj Visa alla **om** **Slutpunktshanteraren** inte visas) </span><span class="sxs-lookup"><span data-stu-id="451d4-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="451d4-127">Gå till **Automatisk registrering för Windows-registrering** för enheter   >  **i administrationscentret** för Microsoft  >    >  **Endpoint Manager.**</span><span class="sxs-lookup"><span data-stu-id="451d4-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="451d4-128">Kontrollera att MDM-användaromfattningen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="451d4-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="451d4-129">Om du vill registrera  alla datorer anger du alla att automatiskt registrera alla användardatorer som är medlemmar i Azure AD och nya datorer när användarna lägger till ett arbetskonto i Windows.</span><span class="sxs-lookup"><span data-stu-id="451d4-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="451d4-130">Ange några **som** registrerar datorerna i en viss grupp av användare.</span><span class="sxs-lookup"><span data-stu-id="451d4-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="451d4-131">Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="451d4-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="451d4-132">Välj **Välj grupper för** att aktivera MDM-användaromfattningen för säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="451d4-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="451d4-133">4. Skapa de resurser som krävs</span><span class="sxs-lookup"><span data-stu-id="451d4-133">4. Create the required resources</span></span> 

<span data-ttu-id="451d4-134">Det har blivit enklare att utföra de uppgifter som krävs för att konfigurera [hybrid-AD-koppling](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) med hjälp av cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) som hittades i PowerShell-modulen [SecMgmt.](https://www.powershellgallery.com/packages/SecMgmt)</span><span class="sxs-lookup"><span data-stu-id="451d4-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="451d4-135">När du anropar den här cmdleten skapas och konfigureras den nödvändiga tjänstanslutningspunkten och grupprincipen.</span><span class="sxs-lookup"><span data-stu-id="451d4-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="451d4-136">Du kan installera den här modulen genom att använda följande i en instans av PowerShell:</span><span class="sxs-lookup"><span data-stu-id="451d4-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="451d4-137">Vi rekommenderar att du installerar den här modulen på Den Windows Server som kör Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="451d4-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="451d4-138">Om du vill skapa den tjänstanslutningspunkt och grupprincip som krävs anropar du cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="451d4-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="451d4-139">Du behöver dina autentiseringsuppgifter som global administratör för Microsoft 365 Business Premium när du utför den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="451d4-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="451d4-140">När du är redo att skapa resurserna anropar du följande:</span><span class="sxs-lookup"><span data-stu-id="451d4-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="451d4-141">Det första kommandot upprättar en anslutning till Microsoft-molnet och när du uppmanas att göra det anger du dina autentiseringsuppgifter som global Administratör för Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="451d4-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="451d4-142">5. Länka grupprincip</span><span class="sxs-lookup"><span data-stu-id="451d4-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="451d4-143">I grupprincip Management Console (GPMC) högerklickar du på den plats där du vill länka principen och väljer Länka en befintlig *GPO ...* på snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="451d4-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="451d4-144">Välj principen som skapades i steget ovan och klicka sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="451d4-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="451d4-145">Hämta de senaste administrativa mallarna</span><span class="sxs-lookup"><span data-stu-id="451d4-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="451d4-146">Om du inte ser principen Aktivera automatisk **MDM-registrering** med standardautentiseringsuppgifter för Azure AD kan det beror på att du inte har ADMX installerat för Windows 10, version 1803 eller senare.</span><span class="sxs-lookup"><span data-stu-id="451d4-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="451d4-147">Lös problemet genom att följa de här stegen (Obs! den senaste MDM.admx är bakåtkompatibel):</span><span class="sxs-lookup"><span data-stu-id="451d4-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="451d4-148">Ladda ned: [Administrativa mallar (.admx) för Windows 10 oktober 2020-uppdatering (20H2).](https://www.microsoft.com/download/102157)</span><span class="sxs-lookup"><span data-stu-id="451d4-148">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="451d4-149">Installera paketet på en domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="451d4-149">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="451d4-150">Navigera, beroende på vilken version av administrativa mallar som finns i mappen: **C:\Program (x86)\Microsoft grupprincip\Windows 10 oktober 2020 Uppdatering (20H2).**</span><span class="sxs-lookup"><span data-stu-id="451d4-150">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="451d4-151">Byt **namn på mappen** Principdefinitioner i sökvägen ovan till **Principdefinitioner.**</span><span class="sxs-lookup"><span data-stu-id="451d4-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="451d4-152">Kopiera mappen **Principdefinitioner** till SYSVOL-resursen som standard i **C:\Windows\SYSVOL\domän\Principer.**</span><span class="sxs-lookup"><span data-stu-id="451d4-152">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="451d4-153">Om du planerar att använda ett centralt principarkiv för hela domänen lägger du till innehållet i Principdefinitioner där.</span><span class="sxs-lookup"><span data-stu-id="451d4-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="451d4-154">Om du har flera domänkontrollanter väntar du tills SYSVOL replikerar för att principerna ska vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="451d4-154">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="451d4-155">Den här proceduren fungerar även för alla framtida versioner av administrativa mallar.</span><span class="sxs-lookup"><span data-stu-id="451d4-155">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="451d4-156">Nu bör du kunna se principen Aktivera automatisk **MDM-registrering med standardautentiseringsuppgifter för Azure AD** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="451d4-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
