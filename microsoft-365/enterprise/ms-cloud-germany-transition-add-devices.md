---
title: Ytterligare enhetsinformation för migreringen från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Sammanfattning: Ytterligare enhetsinformation om tjänster när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928162"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="9d2b2-103">Ytterligare enhetsinformation för migreringen från Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="9d2b2-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9d2b2-104">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="9d2b2-104">Frequently asked questions</span></span>

<span data-ttu-id="9d2b2-105">**Hur vet jag om min organisation påverkas?**</span><span class="sxs-lookup"><span data-stu-id="9d2b2-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="9d2b2-106">Administratörer bör kontrollera `https://portal.microsoftazure.de` om de har några registrerade enheter.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="9d2b2-107">Om din organisation har registrerade enheter påverkas du.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="9d2b2-108">**Hur påverkar det mina användare?**</span><span class="sxs-lookup"><span data-stu-id="9d2b2-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="9d2b2-109">Användare från en registrerad enhet kommer inte längre att kunna [](ms-cloud-germany-transition.md#how-is-the-migration-organized) logga in när migreringen har fasat in Azure AD-migreringen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="9d2b2-110">Se till att alla dina enheter är registrerade med den globala slutpunkten innan din organisation kopplas bort från Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="9d2b2-111">**När registrerar mina användare sina enheter igen?**</span><span class="sxs-lookup"><span data-stu-id="9d2b2-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="9d2b2-112">Det är viktigt att du endast avregistrerar och registrerar dina enheter igen under migreringsfasen Separat från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="9d2b2-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="9d2b2-113">**Hur återställer jag enhetens status efter migreringen?**</span><span class="sxs-lookup"><span data-stu-id="9d2b2-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="9d2b2-114">För hybrid-Azure AD-anslutna och företagsägda Windows-enheter som är registrerade med Azure AD kan administratörer hantera migreringen av dessa enheter genom fjärrutlösta arbetsflöden som avregistrerar de gamla enhets tillstånden.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="9d2b2-115">För alla andra enheter, inklusive personliga Windows-enheter som är registrerade i Azure AD, måste slutanvändaren utföra de här stegen manuellt.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="9d2b2-116">För Azure AD-anslutna enheter måste användarna ha ett lokalt administratörskonto för att avregistrera och sedan registrera sina enheter på nytt.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="9d2b2-117">Microsoft publicerar instruktioner för hur man återställer enhetens status.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="9d2b2-118">**Hur vet jag att alla mina enheter är registrerade i det offentliga molnet?**</span><span class="sxs-lookup"><span data-stu-id="9d2b2-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="9d2b2-119">Om du vill kontrollera om dina enheter är registrerade i det offentliga molnet bör du exportera och ladda ned listan med enheter från Azure AD-portalen till ett Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="9d2b2-120">Filtrera sedan de enheter som är registrerade (med hjälp av kolumnen _registeredTime)_ efter migreringsfasen Separat från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="9d2b2-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="9d2b2-121">Enhetsregistrering inaktiveras efter migrering av klientorganisationen och kan inte aktiveras eller inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="9d2b2-122">Om Intune inte används loggar du in på din prenumeration och kör det här kommandot för att aktivera alternativet igen:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="9d2b2-123">Hybrid Azure AD-anslutning</span><span class="sxs-lookup"><span data-stu-id="9d2b2-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="9d2b2-124">Windows-nednivå</span><span class="sxs-lookup"><span data-stu-id="9d2b2-124">Windows down-level</span></span>

<span data-ttu-id="9d2b2-125">_Windows-enheter_ på nedåtnivå är Windows-enheter som för närvarande kör tidigare versioner av Windows (till exempel Windows 8.1 eller Windows 7) eller som kör Windows Server-versioner tidigare än 2019 och 2016.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="9d2b2-126">Om sådana enheter har registrerats tidigare måste du avregistrera och registrera om enheterna.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="9d2b2-127">Använd följande kommando på enheten för att avgöra om en Windows-enhet på lägre nivå tidigare var ansluten till Azure AD:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="9d2b2-128">Om enheten tidigare var ansluten till Azure AD, och enheten har nätverksanslutning till globala Azure AD-slutpunkter, ser du följande utdata:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="9d2b2-129">De enheter som påverkas har "Enhetens status" med värdet "Okänt".</span><span class="sxs-lookup"><span data-stu-id="9d2b2-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="9d2b2-130">Om utdata är "Enheten är inte ansluten" eller om "Enhetens status" är "Ok", ignorera följande vägledning.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="9d2b2-131">Endast för enheter som visar att enheten är ansluten (på grund av enhetensId, thumbprint och så vidare) och vars "Enhetstillstånd"-värde är "Okänt", bör administratörer köra följande kommando i samband med att en domänanvändare loggar in på en sådan enhet på nedåtnivå:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="9d2b2-132">Föregående kommando behöver bara köras en gång per domänanvändare som loggar in på Windows-nednivåenheten.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="9d2b2-133">Det här kommandot ska köras inom ramen för domänanvändaren som loggar in.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="9d2b2-134">Tillräcklig försiktighet måste vidtas för att inte köra det här kommandot när användaren sedan loggar in.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="9d2b2-135">När föregående kommando körs rensas den sammanskrivna statusen för den lokala Azure AD-sammanskrivna hybriddatorn för den användare som loggade in.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="9d2b2-136">Och om datorn fortfarande är konfigurerad att vara hybrid-Azure AD-ansluten i klientorganisationen försöker den ansluta när användaren loggar in igen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="9d2b2-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="9d2b2-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="9d2b2-138">Ta bort anslutning</span><span class="sxs-lookup"><span data-stu-id="9d2b2-138">Unjoin</span></span>

<span data-ttu-id="9d2b2-139">För att ta reda på om Windows 10-enheten tidigare var ansluten till Azure AD kör du följande kommando på enheten:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="9d2b2-140">Om enheten är Azure AD-ansluten till hybrid ser administratören följande utdata:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="9d2b2-141">Om utdata är "AzureAdJoined : Nej" ignorerar du följande vägledning.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="9d2b2-142">För enheter som visar att enheten är ansluten till Azure AD kör du följande kommando som administratör för att ta bort enhetens anslutna tillstånd.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="9d2b2-143">Föregående kommando behöver bara köras en gång i ett administrativt sammanhang på Windows-enheten.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="9d2b2-144">Hybrid AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="9d2b2-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="9d2b2-145">Enheten ansluts automatiskt till Azure AD utan åtgärd från användare eller administratör så länge enheten är ansluten till globala Azure AD-slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="9d2b2-146">Azure AD-anslutning</span><span class="sxs-lookup"><span data-stu-id="9d2b2-146">Azure AD Join</span></span>

<span data-ttu-id="9d2b2-147">**VIKTIGT!** Intune-tjänstens huvudnamn aktiveras efter e-handelsmigrering, vilket innebär aktivering av enhetsregistrering för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="9d2b2-148">Om du blockerade enhetsregistrering för Azure AD före migreringen måste du inaktivera Intune-tjänstens huvudnamn med PowerShell om du vill inaktivera enhetsregistrering för Azure AD med Azure AD-portalen igen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="9d2b2-149">Du kan inaktivera Intune-tjänstens huvudnamn med det här kommandot i Azure Active Directory PowerShell för Graph-modulen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="9d2b2-150">Ta bort anslutning</span><span class="sxs-lookup"><span data-stu-id="9d2b2-150">Unjoin</span></span>

<span data-ttu-id="9d2b2-151">För att avgöra om Windows 10-enheten tidigare var ansluten till Azure AD kan användaren eller administratören köra följande kommando på enheten:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="9d2b2-152">Om enheten är ansluten till Azure AD ser användaren eller administratören följande utdata:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="9d2b2-153">Om utdata är "AzureAdJoined : NO" ignorerar du följande vägledning.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="9d2b2-154">Användare: Om enheten är Azure AD ansluten kan en användare ta bort enheten från inställningarna.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="9d2b2-155">Kontrollera att det finns ett lokalt administratörskonto på enheten innan du tar bort enheten från Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="9d2b2-156">Det lokala administratörskontot krävs för att logga in på enheten igen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="9d2b2-157">Administratör: Om organisationens administratör vill ta bort användarnas enheter som är Azure AD-anslutna kan de göra det genom att köra följande kommando på var och en av enheterna med hjälp av en mekanism, till exempel grupprincip.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="9d2b2-158">Administratören måste kontrollera att det finns ett lokalt administratörskonto på enheten innan enheten tas bort från Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="9d2b2-159">Det lokala administratörskontot krävs för att logga in på enheten igen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="9d2b2-160">Föregående kommando behöver bara köras en gång i ett administrativt sammanhang på Windows-enheten.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="9d2b2-161">Azure AD- anslutning/omregistrering</span><span class="sxs-lookup"><span data-stu-id="9d2b2-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="9d2b2-162">Användaren kan ansluta enheten till Azure AD från Windows-inställningar: Inställningar för **>-> Arbets- eller skolkonto > Connect.**</span><span class="sxs-lookup"><span data-stu-id="9d2b2-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="9d2b2-163">Azure AD Registered (företagsägd)</span><span class="sxs-lookup"><span data-stu-id="9d2b2-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="9d2b2-164">Om du vill avgöra om Windows 10-enheten är Azure AD-registrerad kör du följande kommando på enheten:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="9d2b2-165">Om enheten är Azure AD Registrerad ser du följande utdata:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="9d2b2-166">Så här tar du bort det befintliga Azure AD-registrerade kontot på enheten:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="9d2b2-167">Om du vill ta bort det Azure AD-registrerade kontot på enheten använder du CleanupWPJ, ett verktyg som du kan ladda ned härifrån: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="9d2b2-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="9d2b2-168">Extrahera ZIP-filen och kör **WPJCleanup.cmd**.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="9d2b2-169">Det här verktyget startar rätt körbar baserat på versionen av Windows på enheten.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="9d2b2-170">Genom att använda en mekanism som grupprincip kan administratören köra kommandot på enheten i samband med alla användare som är inloggade på enheten.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="9d2b2-171">Om du vill inaktivera Web Account Manager-uppmaningar om att registrera enheten i Azure AD lägger du till det här registervärdet:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="9d2b2-172">Plats: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="9d2b2-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="9d2b2-173">Typ: DWORD (32 bitar)</span><span class="sxs-lookup"><span data-stu-id="9d2b2-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="9d2b2-174">Namn: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="9d2b2-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="9d2b2-175">Värdedata: 1</span><span class="sxs-lookup"><span data-stu-id="9d2b2-175">Value data: 1</span></span>

<span data-ttu-id="9d2b2-176">Förekomsten av det här registervärdet bör blockera anslutning till arbetsplatsen och förhindra att användarna ser uppmaningar om att ansluta till enheten.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="9d2b2-177">Android</span><span class="sxs-lookup"><span data-stu-id="9d2b2-177">Android</span></span>

<span data-ttu-id="9d2b2-178">För Android måste användarna avregistrera sig och registrera sina enheter igen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="9d2b2-179">Det kan du göra via appen Microsoft Authenticator eller företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="9d2b2-180">Från Microsoft Authenticator-appen kan användare gå till **Inställningar > Enhetsregistrering.**</span><span class="sxs-lookup"><span data-stu-id="9d2b2-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="9d2b2-181">Därifrån kan användare avregistrera sig och registrera sin enhet igen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="9d2b2-182">Från företagsportalen kan användarna gå till **fliken Enheter** och ta bort enheten.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="9d2b2-183">Därefter kan du registrera enheten igen via företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="9d2b2-184">Användare kan också avregistrera och registrera igen genom att ta bort kontot från sidan kontoinställningar och sedan lägga till arbetskontot igen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="9d2b2-185">Så här avregistrerar du och registrerar om enheten på Android med hjälp av appen Microsoft Authenticator:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="9d2b2-186">Öppna Appen Microsoft Authenticator och gå till **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="9d2b2-187">Välj **Enhetsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="9d2b2-188">Avregistrera enheten genom att välja **Avregistrera**.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="9d2b2-189">För **enhetsregistrering** registrerar du enheten igen genom att skriva din e-postadress och väljer **registrera**.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="9d2b2-190">Så här avregistrerar du och registrerar om en Android-enhet på sidan För Android-inställningar:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="9d2b2-191">Öppna **Enhetsinställningar** och gå till **Konton**.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="9d2b2-192">Välj det arbetskonto du vill registrera igen och välj Ta **bort konto**.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="9d2b2-193">När kontot har tagits bort går du till **sidan Konton** och väljer Lägg till konto **> Arbetskonto**.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="9d2b2-194">I **Workplace Join** skriver du din e-postadress och väljer **Anslut** för att slutföra registreringen av enheten.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="9d2b2-195">Så här avregistrerar du och registrerar om enheten på Android från företagsportalen:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="9d2b2-196">Starta företagsportalen och gå till **fliken** Enheter.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="9d2b2-197">Välj enheten om du vill se enhetsinformationen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="9d2b2-198">På ellipsmenyn (tre punkter) väljer du Ta **bort** enhet och slutför borttagningen genom att bekräfta i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="9d2b2-199">Du bör nu vara utloggad från företagsportalappen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="9d2b2-200">Välj **Logga in** för att registrera enheten igen.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="9d2b2-201">Mer information om åtgärder som krävs under migreringsfasen av den här arbetsbelastningen, eller påverkan på administration eller användning, finns i informationen om Azure Active Directory (Azure AD) i Ytterligare Azure AD-information för migreringen från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition-azure-ad.md)</span><span class="sxs-lookup"><span data-stu-id="9d2b2-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="9d2b2-202">iOS</span><span class="sxs-lookup"><span data-stu-id="9d2b2-202">iOS</span></span>

<span data-ttu-id="9d2b2-203">På iOS-enheter måste en användare manuellt ta bort cachelagrade konton från Microsoft Authenticator, avregistrera enheten och logga ut från alla inbyggda appar på enheten.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="9d2b2-204">Steg 1: Om det finns tar du bort kontot från Microsoft Authenticator-appen</span><span class="sxs-lookup"><span data-stu-id="9d2b2-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="9d2b2-205">Tryck på kontot i appen Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="9d2b2-206">Tryck på **ikonen** Inställningar i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="9d2b2-207">Om du inte ser ikonen **Förinställningar** använder du kanske inte den senaste versionen av Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="9d2b2-208">Tryck på **knappen Ta bort** konto.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="9d2b2-209">Tryck **på Alla appar på den här enheten**.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="9d2b2-210">Steg 2: Avregistrera enheten från Microsoft Authenticator-appen</span><span class="sxs-lookup"><span data-stu-id="9d2b2-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="9d2b2-211">Tryck på menyikonen i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="9d2b2-212">Tryck **på Inställningar** och sedan på **Enhetsregistrering.**</span><span class="sxs-lookup"><span data-stu-id="9d2b2-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="9d2b2-213">Om ditt konto visas trycker du på **Avregistrera enhet** **och Fortsätt** i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="9d2b2-214">Därefter bör du inte se något konto.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="9d2b2-215">Steg 3: Logga ut från enskilda appar om det behövs</span><span class="sxs-lookup"><span data-stu-id="9d2b2-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="9d2b2-216">Användare kan gå till enskilda appar som Outlook, Teams och OneDrive och ta bort konton från dessa appar.</span><span class="sxs-lookup"><span data-stu-id="9d2b2-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="9d2b2-217">Mer information</span><span class="sxs-lookup"><span data-stu-id="9d2b2-217">More information</span></span>

<span data-ttu-id="9d2b2-218">Komma igång:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-218">Getting started:</span></span>

- [<span data-ttu-id="9d2b2-219">Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i nya tyska datacenterområden</span><span class="sxs-lookup"><span data-stu-id="9d2b2-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="9d2b2-220">Migreringshjälp för Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="9d2b2-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="9d2b2-221">Så här väljer du in för migrering</span><span class="sxs-lookup"><span data-stu-id="9d2b2-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="9d2b2-222">Kundupplevelse under migreringen</span><span class="sxs-lookup"><span data-stu-id="9d2b2-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="9d2b2-223">Flytta genom övergången:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-223">Moving through the transition:</span></span>

- [<span data-ttu-id="9d2b2-224">Åtgärder och påverkan i migreringsfaser</span><span class="sxs-lookup"><span data-stu-id="9d2b2-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="9d2b2-225">Ytterligare arbete</span><span class="sxs-lookup"><span data-stu-id="9d2b2-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="9d2b2-226">Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="9d2b2-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="9d2b2-227">Molnappar:</span><span class="sxs-lookup"><span data-stu-id="9d2b2-227">Cloud apps:</span></span>

- [<span data-ttu-id="9d2b2-228">Information om Dynamics 365-migreringsprogram</span><span class="sxs-lookup"><span data-stu-id="9d2b2-228">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="9d2b2-229">Information om Migreringsprogram för Power BI</span><span class="sxs-lookup"><span data-stu-id="9d2b2-229">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="9d2b2-230">Komma igång med uppgraderingen till Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d2b2-230">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)