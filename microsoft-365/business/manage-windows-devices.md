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
description: Lär dig hur du aktiverar Microsoft 365 för att skydda lokala Active-Directory-anslutna Windows 10-enheter i några få steg.
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564962"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="e2e90-103">Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="e2e90-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="e2e90-104">Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.</span><span class="sxs-lookup"><span data-stu-id="e2e90-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="e2e90-105">Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="e2e90-106">Dessa enheter är anslutna till både din lokala Active Directory och din Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e2e90-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="e2e90-107">I det här videoklippet beskrivs stegen för hur du konfigurerar det här för det vanligaste scenariot, vilket också beskrivs i de steg som följer.</span><span class="sxs-lookup"><span data-stu-id="e2e90-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="e2e90-108">Innan du börjar måste du slutföra följande steg:</span><span class="sxs-lookup"><span data-stu-id="e2e90-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="e2e90-109">Synkronisera användare till Azure AD med Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="e2e90-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="e2e90-110">Fullständig synkronisering av Azure AD Connect-organisationsenhet (OU).</span><span class="sxs-lookup"><span data-stu-id="e2e90-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="e2e90-111">Kontrollera att alla domänanvändare som du synkroniserar har licenser till Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e2e90-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="e2e90-112">Se [Synkronisera domänanvändare till Microsoft](manage-domain-users.md) för stegen.</span><span class="sxs-lookup"><span data-stu-id="e2e90-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="e2e90-113">1. Verifiera MDM-myndigheten i Intune</span><span class="sxs-lookup"><span data-stu-id="e2e90-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="e2e90-114">Gå till portal.azure.com och högst upp på sidan sök efter Intune.</span><span class="sxs-lookup"><span data-stu-id="e2e90-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="e2e90-115">På sidan Microsoft Intune väljer du **Enhetsregistrering** och kontrollera att **MDM-behörigheten** är Intune på **sidan** **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="e2e90-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="e2e90-116">Om **MDM-behörigheten** är **Ingen**klickar du på **MDM-behörigheten** för att ange den till **Intune**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="e2e90-117">Om **MDM-behörigheten** är **Microsoft Office 365**går du till **Devices**  >  **Enheters registrera enheter** och använder dialogrutan Lägg till **MDM-behörighet** till höger för att lägga till **Intune MDM-behörighet** (dialogrutan **Lägg till MDM-auktoritet** är endast tillgänglig om **MDM-behörigheten** är inställd på Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="e2e90-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="e2e90-118">2. Verifiera att Azure AD är aktiverat för att ansluta till datorer</span><span class="sxs-lookup"><span data-stu-id="e2e90-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="e2e90-119">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> och välj Azure Active **Directory** (välj Visa alla om Azure Active Directory inte visas) i listan **Administrationscenter.**</span><span class="sxs-lookup"><span data-stu-id="e2e90-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="e2e90-120">I **administrationscentret**för Azure Active Directory går du till **Azure Active Directory,** väljer **Enheter** och sedan **Enhetsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="e2e90-121">Verifiera**att användare kan ansluta till enheter till Azure AD** är aktiverat</span><span class="sxs-lookup"><span data-stu-id="e2e90-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="e2e90-122">Om du vill aktivera alla användare anger du **alla**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="e2e90-123">Om du vill aktivera specifika användare anger du **till Markerad** för att aktivera en viss grupp användare.</span><span class="sxs-lookup"><span data-stu-id="e2e90-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="e2e90-124">Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e2e90-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="e2e90-125">Välj **välj grupper** om du vill aktivera MDM-användaromfattning för den säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="e2e90-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="e2e90-126">3. Verifiera att Azure AD är aktiverat för MDM</span><span class="sxs-lookup"><span data-stu-id="e2e90-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="e2e90-127">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> och välj **Slutpunktshanterare**t (välj **Visa alla** om **Slutpunktshanteraren** inte visas)</span><span class="sxs-lookup"><span data-stu-id="e2e90-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="e2e90-128">Gå till **Automatisk**registrering av Enheter med Windows Windows-registrering i **administrationscentret för Microsoft Slutpunktshanteraren**  >  **Windows**  >  **Windows Enrollment**  >  **Automatic Enrollment**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="e2e90-129">Kontrollera att MDM-användaromfattningen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="e2e90-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="e2e90-130">Om du vill registrera alla datorer ställer du in på **Alla** för att automatiskt registrera alla användardatorer som är anslutna till Azure AD och nya datorer när användarna lägger till ett arbetskonto i Windows.</span><span class="sxs-lookup"><span data-stu-id="e2e90-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="e2e90-131">Ange till **Vissa** för att registrera datorerna för en viss grupp användare.</span><span class="sxs-lookup"><span data-stu-id="e2e90-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="e2e90-132">Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e2e90-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="e2e90-133">Välj **välj grupper** om du vill aktivera MDM-användaromfattning för den säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="e2e90-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="e2e90-134">4. Ställ in tjänstanslutningspunkt (SCP)</span><span class="sxs-lookup"><span data-stu-id="e2e90-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="e2e90-135">Dessa steg förenklas från [konfigurera hybrid azure AD-anslutning](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span><span class="sxs-lookup"><span data-stu-id="e2e90-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="e2e90-136">För att slutföra de steg du behöver för att använda Azure AD Connect och dina globala administratörs- och Active Directory-administratörslösenord från Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e2e90-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="e2e90-137">Starta Azure AD Connect och välj sedan **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="e2e90-138">På sidan **Ytterligare uppgifter** väljer du **Konfigurera enhetsalternativ**och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="e2e90-139">På sidan **Översikt** väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="e2e90-140">På sidan **Anslut till Azure AD** anger du autentiseringsuppgifterna för en global administratör för Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e2e90-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="e2e90-141">På sidan **Enhetsalternativ** väljer du **Konfigurera Hybrid Azure AD-koppling**och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="e2e90-142">På **SCP-sidan,** för varje skog där du vill att Azure AD Connect ska konfigurera SCP, slutför du följande steg och välj sedan **Nästa:**</span><span class="sxs-lookup"><span data-stu-id="e2e90-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="e2e90-143">Markera rutan bredvid skogsnamnet.</span><span class="sxs-lookup"><span data-stu-id="e2e90-143">Check the box beside the forest name.</span></span> <span data-ttu-id="e2e90-144">Skogen ska vara ditt AD-domännamn.</span><span class="sxs-lookup"><span data-stu-id="e2e90-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="e2e90-145">Öppna listrutan under kolumnen **Autentiseringstjänst** och välj matchande domännamn (det bör bara finnas ett enda alternativ).</span><span class="sxs-lookup"><span data-stu-id="e2e90-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="e2e90-146">Välj **Lägg till** om du vill ange autentiseringsuppgifterna för domänadministratören.</span><span class="sxs-lookup"><span data-stu-id="e2e90-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="e2e90-147">Välj Endast Windows 10 eller senare domänanslutna enheter på sidan **Enhetsoperativsystem.**</span><span class="sxs-lookup"><span data-stu-id="e2e90-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="e2e90-148">På sidan **Klar att konfigurera** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="e2e90-149">På sidan **Konfigurationens klara** väljer du **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="e2e90-150">5. Skapa ett GPO för Intune-registrering – ADMX-metoden</span><span class="sxs-lookup"><span data-stu-id="e2e90-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="e2e90-151">Använda. ADMX-mallfil.</span><span class="sxs-lookup"><span data-stu-id="e2e90-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="e2e90-152">Logga in på AD-server, sök och öppna **Server Manager**  >  **Tools**  >  **Grupprinciphantering**för Serverhanterarens verktyg .</span><span class="sxs-lookup"><span data-stu-id="e2e90-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="e2e90-153">Välj ditt domännamn under **Domäner** och högerklicka på **Grupprincipobjekt** för att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="e2e90-154">Ge det nya nationella användarobjektet ett namn, till exempel "*Cloud_Enrollment*" och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="e2e90-155">Högerklicka på den nya grupprincipobjektet under **Grupprincipobjekt** och välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="e2e90-156">Gå till Administrativa mallar för **datorkonfigurationsprinciper**i Redigeraren för **grupprinciphantering.**  >  **Policies**  >  **Administrative Templates**  >  **Windows Components**  >  **MDM**</span><span class="sxs-lookup"><span data-stu-id="e2e90-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="e2e90-157">Högerklicka på **Aktivera automatisk MDM-registrering med standardautentiseringsuppgifter för Azure AD** och välj sedan **Aktiverad**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="e2e90-158">Stäng redigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e2e90-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2e90-159">Om du inte ser principen **Aktivera automatisk MDM-registrering med standardautentiseringsuppgifter för Azure AD**läser du Hämta de [senaste administrativa mallarna](#get-the-latest-administrative-templates).</span><span class="sxs-lookup"><span data-stu-id="e2e90-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="e2e90-160">6. Distribuera grupprincipen</span><span class="sxs-lookup"><span data-stu-id="e2e90-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="e2e90-161">Markera grupprincipobjektet från steg 3 ovan under **Domäner** > grupprincipobjekt i Serverhanteraren, till exempel "Cloud_Enrollment".</span><span class="sxs-lookup"><span data-stu-id="e2e90-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="e2e90-162">Välj fliken **Omfattning** för dittrincipobjekt.</span><span class="sxs-lookup"><span data-stu-id="e2e90-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="e2e90-163">Högerklicka på länken till domänen under **Länkar**på fliken Scope.</span><span class="sxs-lookup"><span data-stu-id="e2e90-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="e2e90-164">Välj **Tvingad** om du vill distribuera den nationella säkerhetsobjektet och sedan **PÅ OK** på bekräftelseskärmen.</span><span class="sxs-lookup"><span data-stu-id="e2e90-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="e2e90-165">Hämta de senaste administrativa mallarna</span><span class="sxs-lookup"><span data-stu-id="e2e90-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="e2e90-166">Om du inte ser principen **Aktivera automatisk MDM-registrering med standardautentiseringsuppgifter för Azure AD**kan det bero på att du inte har ADMX installerat för Windows 10, version 1803, version 1809 eller version 1903.</span><span class="sxs-lookup"><span data-stu-id="e2e90-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="e2e90-167">För att åtgärda problemet följer du dessa steg (Obs: den senaste MDM.admx är bakåtkompatibel):</span><span class="sxs-lookup"><span data-stu-id="e2e90-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="e2e90-168">Ladda ned: [Administrativa mallar (.admx) för Windows 10 Maj 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="e2e90-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="e2e90-169">Installera paketet på PDC (Primary Domain Controller).</span><span class="sxs-lookup"><span data-stu-id="e2e90-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="e2e90-170">Navigera beroende på version till mappen: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 Maj 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="e2e90-171">Byt namn på mappen **Principdefinitioner** i sökvägen ovan till **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="e2e90-172">Kopiera **mappen Principdefinitioner** till **mappen C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="e2e90-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="e2e90-173">Om du planerar att använda ett centralt principarkiv för hela domänen lägger du till innehållet i PolicyDefinitions där.</span><span class="sxs-lookup"><span data-stu-id="e2e90-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="e2e90-174">Starta om den primära domänkontrollanten för att principen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e2e90-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="e2e90-175">Denna procedur kommer att fungera för alla framtida versioner också.</span><span class="sxs-lookup"><span data-stu-id="e2e90-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="e2e90-176">Nu bör du kunna se principen **Aktivera automatisk MDM-registrering med standard Azure AD-autentiseringsuppgifter** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="e2e90-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

