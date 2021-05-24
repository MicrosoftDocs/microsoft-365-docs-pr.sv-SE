---
title: Aktivera domänaktiverade Windows 10 att hanteras av Microsoft 365 för företag
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Lär dig hur du Microsoft 365 att skydda lokala Active Directory-anslutna Windows 10 med några få steg.
ms.openlocfilehash: ec80159bdceffd8a13d09a297a2acc1b78c9b1b3
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636095"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="86e98-103">Aktivera att domänaktiverade Windows 10 hanteras av Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="86e98-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="86e98-104">Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.</span><span class="sxs-lookup"><span data-stu-id="86e98-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="86e98-105">Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter.**</span><span class="sxs-lookup"><span data-stu-id="86e98-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="86e98-106">De här enheterna är anslutna till både din lokala Active Directory och din Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="86e98-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

## <a name="watch-configure-hybrid-azure-active-directory-join"></a><span data-ttu-id="86e98-107">Titta på: Konfigurera Azure Active Directory hybridkoppling</span><span class="sxs-lookup"><span data-stu-id="86e98-107">Watch: Configure Hybrid Azure Active Directory join</span></span>

<span data-ttu-id="86e98-108">I den här videon beskrivs stegen för hur du ställer in detta för det vanligaste scenariot, som också beskrivs i anvisningarna nedan.</span><span class="sxs-lookup"><span data-stu-id="86e98-108">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a><span data-ttu-id="86e98-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="86e98-109">Before you begin</span></span>

- <span data-ttu-id="86e98-110">Synkronisera användare till Azure AD med Azure AD Anslut.</span><span class="sxs-lookup"><span data-stu-id="86e98-110">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="86e98-111">Slutför synkroniseringen av Azure AD Anslut organisationsenhet (OU).</span><span class="sxs-lookup"><span data-stu-id="86e98-111">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="86e98-112">Kontrollera att alla domänanvändare som du synkroniserar har licenser för att Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="86e98-112">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="86e98-113">Instruktioner [finns i Synkronisera domänanvändare](manage-domain-users.md) till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="86e98-113">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="86e98-114">1. Verifiera MDM Authority i Intune</span><span class="sxs-lookup"><span data-stu-id="86e98-114">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="86e98-115">Gå till [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) sidan och Microsoft Intune enhetsregistrering . På sidan **Översikt** kontrollerar du att **MDM-behörighet** **är Intune.**</span><span class="sxs-lookup"><span data-stu-id="86e98-115">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="86e98-116">Om **MDM-behörighet** **är Ingen** klickar du på **MDM-behörigheten** för att ange den till **Intune.**</span><span class="sxs-lookup"><span data-stu-id="86e98-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="86e98-117">Om **MDM-behörighet** är **Microsoft Office 365** går du till Enheter Registrera enheter och använder dialogrutan Lägg till MDM-behörighet till höger för att lägga till  >   **Intune MDM-utfärdare** (dialogrutan Lägg till **MDM-utfärdare** är endast tillgänglig om **MDM-instansen** är inställd på  Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="86e98-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="86e98-118">2. Kontrollera att Azure AD är aktiverat för anslutning till datorer</span><span class="sxs-lookup"><span data-stu-id="86e98-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="86e98-119">Gå till administrationscentret och välj Välj Azure Active Directory (välj Visa <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> alla om Azure Active Directory inte visas) i listan **Administrationscenter.** </span><span class="sxs-lookup"><span data-stu-id="86e98-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="86e98-120">I Azure Active Directory **går du** till fliken **Azure Active Directory** väljer Enheter **och** sedan **Enhetsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="86e98-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="86e98-121">Kontrollera **att Användare kan ansluta enheter till Azure AD** är aktiverat</span><span class="sxs-lookup"><span data-stu-id="86e98-121">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="86e98-122">Om du vill aktivera alla användare anger du **alla**.</span><span class="sxs-lookup"><span data-stu-id="86e98-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="86e98-123">Om du vill aktivera vissa användare anger du **markerad** för att aktivera en viss grupp av användare.</span><span class="sxs-lookup"><span data-stu-id="86e98-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="86e98-124">Lägg till önskade domänanvändare som synkroniserats i Azure AD till en [säkerhetsgrupp.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="86e98-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="86e98-125">Välj **Välj grupper för** att aktivera MDM-användaromfattningen för säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="86e98-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="86e98-126">3. Kontrollera att Azure AD är aktiverat för MDM</span><span class="sxs-lookup"><span data-stu-id="86e98-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="86e98-127">Gå till administrationscentret och <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> välj Slutpunkt **hanteramenyer**(välj **Visa alla** **om Endpoint Manager** inte visas)</span><span class="sxs-lookup"><span data-stu-id="86e98-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="86e98-128">I **administrationscentret Microsoft Endpoint Manager du** till Enheter **som Windows**  >    >  **Windows Automatisk**  >  **registrering**.</span><span class="sxs-lookup"><span data-stu-id="86e98-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="86e98-129">Kontrollera att MDM-användaromfattningen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="86e98-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="86e98-130">Om du vill registrera  alla datorer anger du Alla för automatisk registrering av alla användardatorer som är medlemmar i Azure AD och nya datorer när användarna lägger till ett arbetskonto i Windows.</span><span class="sxs-lookup"><span data-stu-id="86e98-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="86e98-131">Ange några **för** att registrera datorer i en viss grupp av användare.</span><span class="sxs-lookup"><span data-stu-id="86e98-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="86e98-132">Lägg till önskade domänanvändare som synkroniserats i Azure AD till en [säkerhetsgrupp.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="86e98-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="86e98-133">Välj **Välj grupper för** att aktivera MDM-användaromfattningen för säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="86e98-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="86e98-134">4. Skapa de resurser som krävs</span><span class="sxs-lookup"><span data-stu-id="86e98-134">4. Create the required resources</span></span> 

<span data-ttu-id="86e98-135">Det har blivit enklare att utföra de uppgifter som krävs för att konfigurera [hybrid-AD-koppling](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) med hjälp av cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) som hittades i PowerShell-modulen [SecMgmt.](https://www.powershellgallery.com/packages/SecMgmt)</span><span class="sxs-lookup"><span data-stu-id="86e98-135">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="86e98-136">När du anropar den här cmdleten skapas och konfigureras den nödvändiga tjänstanslutningspunkten och grupprincipen.</span><span class="sxs-lookup"><span data-stu-id="86e98-136">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="86e98-137">Du kan installera den här modulen genom att skapa följande från en instans av PowerShell:</span><span class="sxs-lookup"><span data-stu-id="86e98-137">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="86e98-138">Vi rekommenderar att du installerar den här modulen på den Windows server som kör Azure AD Anslut.</span><span class="sxs-lookup"><span data-stu-id="86e98-138">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="86e98-139">Om du vill skapa den tjänstanslutningspunkt och grupprincip som krävs anropar du cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="86e98-139">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="86e98-140">Du behöver dina autentiseringsuppgifter Microsoft 365 Business Premium global administratör när du utför den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="86e98-140">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="86e98-141">När du är redo att skapa resurserna anropar du följande:</span><span class="sxs-lookup"><span data-stu-id="86e98-141">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="86e98-142">Med det första kommandot upprättas en anslutning till Microsoft-molnet, och när du uppmanas att göra det anger du dina Microsoft 365 Business Premium som global administratör.</span><span class="sxs-lookup"><span data-stu-id="86e98-142">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="86e98-143">5. Länka grupprincipen</span><span class="sxs-lookup"><span data-stu-id="86e98-143">5. Link the Group Policy</span></span>

1. <span data-ttu-id="86e98-144">I GPMC (Group Policy Management Console) högerklickar du på den plats där du vill länka principen och väljer Länka en befintlig *GPO...* på snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="86e98-144">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="86e98-145">Välj principen som skapades i steget ovan och klicka sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="86e98-145">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="86e98-146">Hämta de senaste administrativa mallarna</span><span class="sxs-lookup"><span data-stu-id="86e98-146">Get the latest Administrative Templates</span></span>

<span data-ttu-id="86e98-147">Om du inte ser principen Aktivera automatisk **MDM-registrering** med standardautentiseringsuppgifter för Azure AD kan det beror på att du inte har ADMX installerat för Windows 10, version 1803 eller senare.</span><span class="sxs-lookup"><span data-stu-id="86e98-147">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="86e98-148">Lös problemet genom att följa de här anvisningarna (Obs! den senaste MDM.admx är bakåtkompatibel):</span><span class="sxs-lookup"><span data-stu-id="86e98-148">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="86e98-149">Ladda ned: [Administrativa mallar (.admx) för Windows 10 oktober 2020-uppdatering (20H2).](https://www.microsoft.com/download/102157)</span><span class="sxs-lookup"><span data-stu-id="86e98-149">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="86e98-150">Installera paketet på en domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="86e98-150">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="86e98-151">Navigera, beroende på versionen av Administrativa mallar, till mappen: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 oktober 2020-uppdatering (20H2).**</span><span class="sxs-lookup"><span data-stu-id="86e98-151">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="86e98-152">Byt **namn på** mappen Principdefinitioner i sökvägen ovan till **Principdefinitioner.**</span><span class="sxs-lookup"><span data-stu-id="86e98-152">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="86e98-153">Kopiera mappen **Principdefinitioner** till SYSVOL-resursen, som standard finns i **C:\Windows\SYSVOL\domän\Principer.**</span><span class="sxs-lookup"><span data-stu-id="86e98-153">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="86e98-154">Om du planerar att använda ett centralt principarkiv för hela domänen lägger du till innehållet i Principdefinitioner där.</span><span class="sxs-lookup"><span data-stu-id="86e98-154">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="86e98-155">Om du har flera domänkontrollanter väntar du tills SYSVOL replikerar för att principerna ska vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="86e98-155">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="86e98-156">Den här proceduren fungerar även för alla framtida versioner av administrativa mallar.</span><span class="sxs-lookup"><span data-stu-id="86e98-156">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="86e98-157">Nu bör du kunna se principen Aktivera automatisk MDM-registrering med hjälp av **standardautentiseringsuppgifter för Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="86e98-157">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

## <a name="related-content"></a><span data-ttu-id="86e98-158">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="86e98-158">Related content</span></span>

<span data-ttu-id="86e98-159">[Synkronisera domänanvändare till Microsoft 365](manage-domain-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="86e98-159">[Synchronize domain users to Microsoft 365](manage-domain-users.md) (article)</span></span>\
<span data-ttu-id="86e98-160">[Skapa en grupp i administrationscentret](../admin/create-groups/create-groups.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="86e98-160">[Create a group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="86e98-161">[Självstudiekurs: Konfigurera Azure Active Directory-hybridlösningar för hanterade domäner](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="86e98-161">[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span></span>