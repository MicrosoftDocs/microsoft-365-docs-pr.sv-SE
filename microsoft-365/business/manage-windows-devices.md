---
title: Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 för företag
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
description: Lär dig hur du aktiverar Microsoft 365 för att skydda lokala Active-Directory-anslutna Windows 10-enheter med bara några få steg.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560852"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="64755-103">Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="64755-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="64755-104">Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.</span><span class="sxs-lookup"><span data-stu-id="64755-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="64755-105">Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter**.</span><span class="sxs-lookup"><span data-stu-id="64755-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="64755-106">Dessa enheter är anslutna till både din lokala Active Directory och din Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="64755-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="64755-107">I det här videoklippet beskrivs stegen för hur du ställer in det här för det vanligaste scenariot, vilket också beskrivs i de steg som följer.</span><span class="sxs-lookup"><span data-stu-id="64755-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="64755-108">Innan du börjar måste du följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="64755-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="64755-109">Synkronisera användare till Azure AD med Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="64755-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="64755-110">Fullständig Synkronisering av Azure AD Connect-organisationsenhet (OU).</span><span class="sxs-lookup"><span data-stu-id="64755-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="64755-111">Kontrollera att alla domänanvändare som du synkroniserar har licenser till Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="64755-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="64755-112">Se [Synkronisera domänanvändare till Microsoft](manage-domain-users.md) för stegen.</span><span class="sxs-lookup"><span data-stu-id="64755-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="64755-113">1. Verifiera MDM-myndighet i Intune</span><span class="sxs-lookup"><span data-stu-id="64755-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="64755-114">Gå till [Slutpunktshanteraren](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) och välj **Enhetsregistrering**på sidan **Översikt** och kontrollera att **MDM-behörigheten** är **Intune**.</span><span class="sxs-lookup"><span data-stu-id="64755-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="64755-115">Om **MDM-behörigheten** är **Ingen**klickar du på **MDM-behörigheten** för att ställa in den på **Intune**.</span><span class="sxs-lookup"><span data-stu-id="64755-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="64755-116">Om **MDM-behörigheten** är **Microsoft Office 365**går du till **Devices**  >  **Enheters registrera enheter** och använder dialogrutan Lägg till **MDM-behörighet** till höger för att lägga till **Intune MDM-behörighet** (dialogrutan **Lägg till MDM-auktoritet** är endast tillgänglig om **MDM-behörigheten** är inställd på Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="64755-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="64755-117">2. Verifiera att Azure AD är aktiverat för att ansluta till datorer</span><span class="sxs-lookup"><span data-stu-id="64755-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="64755-118">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> och välj Azure Active **Directory** (välj Visa alla om Azure Active Directory inte visas) i listan **Administrationscenter.**</span><span class="sxs-lookup"><span data-stu-id="64755-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="64755-119">I **administrationscentret**för Azure Active Directory går du till **Azure Active Directory,** väljer **Enheter** och sedan **Enhetsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="64755-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="64755-120">Verifiera**att användare kan ansluta till enheter till Azure AD** är aktiverat</span><span class="sxs-lookup"><span data-stu-id="64755-120">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="64755-121">Om du vill aktivera alla användare anger du **alla**.</span><span class="sxs-lookup"><span data-stu-id="64755-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="64755-122">Om du vill aktivera specifika användare anger du **till Markerad** för att aktivera en viss grupp användare.</span><span class="sxs-lookup"><span data-stu-id="64755-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="64755-123">Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="64755-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="64755-124">Välj **välj grupper** om du vill aktivera MDM-användaromfattning för den säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="64755-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="64755-125">3. Verifiera att Azure AD är aktiverat för MDM</span><span class="sxs-lookup"><span data-stu-id="64755-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="64755-126">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> och välj **Slutpunktshanterare**t (välj **Visa alla** om **Slutpunktshanteraren** inte visas)</span><span class="sxs-lookup"><span data-stu-id="64755-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="64755-127">Gå till Automatisk registrering av **Enheter**med Windows Windows-registrering i **administrationscentret för Microsoft Slutpunktshanteraren**  >  **Windows**  >  **Windows Enrollment**  >  **Automatic Enrollment**.</span><span class="sxs-lookup"><span data-stu-id="64755-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="64755-128">Kontrollera att MDM-användaromfattningen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="64755-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="64755-129">Om du vill registrera alla datorer ställer du in på **Alla** för att automatiskt registrera alla användardatorer som är anslutna till Azure AD och nya datorer när användarna lägger till ett arbetskonto i Windows.</span><span class="sxs-lookup"><span data-stu-id="64755-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="64755-130">Ange att **vissa** ska registrera datorerna för en viss grupp användare.</span><span class="sxs-lookup"><span data-stu-id="64755-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="64755-131">Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="64755-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="64755-132">Välj **välj grupper** om du vill aktivera MDM-användaromfattning för den säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="64755-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="64755-133">4. Skapa de resurser som krävs</span><span class="sxs-lookup"><span data-stu-id="64755-133">4. Create the required resources</span></span> 

<span data-ttu-id="64755-134">Att utföra de uppgifter som krävs för att [konfigurera hybrid Azure AD-koppling](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) har förenklats med hjälp av cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) som finns i [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-modulen.</span><span class="sxs-lookup"><span data-stu-id="64755-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="64755-135">När du anropar den här cmdleten skapas och konfigureras den tjänstanslutningspunkt och grupprincip som krävs.</span><span class="sxs-lookup"><span data-stu-id="64755-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="64755-136">Du kan installera den här modulen genom att anropa följande från en instans av PowerShell:</span><span class="sxs-lookup"><span data-stu-id="64755-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="64755-137">Vi rekommenderar att du installerar den här modulen på Windows Server som kör Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="64755-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="64755-138">Om du vill skapa den nödvändiga tjänstanslutningspunkten och grupprincipen anropar du cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="64755-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="64755-139">Du behöver dina globala administratörsuppgifter för Microsoft 365 Business Premium när du utför den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="64755-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="64755-140">När du är redo att skapa resurserna aktiverar du följande:</span><span class="sxs-lookup"><span data-stu-id="64755-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="64755-141">Det första kommandot upprättar en anslutning till Microsoft-molnet och när du uppmanas att ange dina globala administratörsautentiseringsuppgifter för Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="64755-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="64755-142">5. Länka koncernpolicyn</span><span class="sxs-lookup"><span data-stu-id="64755-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="64755-143">Högerklicka på den plats där du vill länka principen i Konsolen Grupprinciphantering (GPMC) och välj *Länka ett befintligt grupprincipobjekt...* på snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="64755-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="64755-144">Markera den princip som skapats i ovanstående steg och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="64755-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="64755-145">Hämta de senaste administrativa mallarna</span><span class="sxs-lookup"><span data-stu-id="64755-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="64755-146">Om du inte ser principen **Aktivera automatisk MDM-registrering med standardautentiseringsuppgifter för Azure AD**kan det bero på att du inte har ADMX installerat för Windows 10, version 1803, version 1809 eller version 1903.</span><span class="sxs-lookup"><span data-stu-id="64755-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="64755-147">För att åtgärda problemet följer du dessa steg (Obs: den senaste MDM.admx är bakåtkompatibel):</span><span class="sxs-lookup"><span data-stu-id="64755-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="64755-148">Ladda ned: [Administrativa mallar (.admx) för Windows 10 Maj 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="64755-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="64755-149">Installera paketet på PDC (Primary Domain Controller).</span><span class="sxs-lookup"><span data-stu-id="64755-149">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="64755-150">Navigera, beroende på version till mappen: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 Maj 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="64755-150">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="64755-151">Byt namn på mappen **Principdefinitioner** i sökvägen ovan till **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="64755-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="64755-152">Kopiera **mappen Principdefinitioner** till **mappen C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="64755-152">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="64755-153">Om du planerar att använda ett centralt principarkiv för hela domänen lägger du till innehållet i PolicyDefinitions där.</span><span class="sxs-lookup"><span data-stu-id="64755-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="64755-154">Starta om den primära domänkontrollanten för att principen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="64755-154">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="64755-155">Denna procedur kommer att fungera för alla framtida versioner också.</span><span class="sxs-lookup"><span data-stu-id="64755-155">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="64755-156">Nu bör du kunna se principen **Aktivera automatisk MDM-registrering med standard Azure AD-autentiseringsuppgifter** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="64755-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
