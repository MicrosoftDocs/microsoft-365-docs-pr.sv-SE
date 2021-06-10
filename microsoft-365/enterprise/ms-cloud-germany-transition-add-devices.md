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
description: 'Sammanfattning: Ytterligare enhetsinformation om tjänster när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365 tjänster i den nya tyska datacenterområdet.'
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861312"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="2c10f-103">Ytterligare enhetsinformation för migreringen från Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="2c10f-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="2c10f-104">Azure AD-anslutna och registrerade enheter som är anslutna till Microsoft Cloud Deutschland måste migreras efter fas 9 och före fas 10.</span><span class="sxs-lookup"><span data-stu-id="2c10f-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="2c10f-105">Migreringen av en enhet beror på typen av enheter, operativsystemet och AAD-relationen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="2c10f-106">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="2c10f-106">Frequently asked questions</span></span>

<span data-ttu-id="2c10f-107">**Hur vet jag om min organisation påverkas?**</span><span class="sxs-lookup"><span data-stu-id="2c10f-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="2c10f-108">Administratörer bör kontrollera `https://portal.microsoftazure.de` om de har några registrerade eller Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="2c10f-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="2c10f-109">Om din organisation har registrerade enheter påverkas du.</span><span class="sxs-lookup"><span data-stu-id="2c10f-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="2c10f-110">**Hur påverkar det mina användare?**</span><span class="sxs-lookup"><span data-stu-id="2c10f-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="2c10f-111">Användare från en registrerad enhet kan inte längre logga in när migreringsfasen [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) har slutförts och slutpunkterna för Microsoft Cloud Deutschland har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="2c10f-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="2c10f-112">Se till att alla dina enheter är registrerade med den globala slutpunkten innan din organisation kopplas bort från Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="2c10f-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="2c10f-113">**När registrerar mina användare sina enheter igen?**</span><span class="sxs-lookup"><span data-stu-id="2c10f-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="2c10f-114">Det är viktigt att du bara avregistrerar och registrerar dina enheter igen när [fas 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) är klar.</span><span class="sxs-lookup"><span data-stu-id="2c10f-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="2c10f-115">Du måste slutföra omregistreringen innan fas 10 startar, annars kan åtkomsten till din enhet gå förlorade.</span><span class="sxs-lookup"><span data-stu-id="2c10f-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="2c10f-116">**Hur återställer jag enhetens status efter migreringen?**</span><span class="sxs-lookup"><span data-stu-id="2c10f-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="2c10f-117">För företagsägda Windows enheter som är registrerade med Azure AD kan administratörer hantera migreringen av dessa enheter via fjärrutlösta arbetsflöden som avregistrerar de gamla enhets tillstånden.</span><span class="sxs-lookup"><span data-stu-id="2c10f-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="2c10f-118">För alla andra enheter, inklusive personliga Windows enheter som är registrerade i Azure AD, måste slutanvändaren utföra dessa steg manuellt.</span><span class="sxs-lookup"><span data-stu-id="2c10f-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="2c10f-119">För Azure AD-anslutna enheter måste användarna ha ett lokalt administratörskonto för att avregistrera och sedan registrera sina enheter på nytt.</span><span class="sxs-lookup"><span data-stu-id="2c10f-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="2c10f-120">Se detaljerade anvisningar om hur du återställer enhetens tillstånd nedan.</span><span class="sxs-lookup"><span data-stu-id="2c10f-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="2c10f-121">**Hur vet jag att alla mina enheter är registrerade i det offentliga molnet?**</span><span class="sxs-lookup"><span data-stu-id="2c10f-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="2c10f-122">Om du vill kontrollera om dina enheter är registrerade i det offentliga molnet bör du exportera och ladda ned listan med enheter från Azure AD-portalen till ett Excel kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="2c10f-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="2c10f-123">Filtrera sedan de enheter som är registrerade (med hjälp av kolumnen _registeredTime)_ efter migreringsfasen Separat från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="2c10f-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="2c10f-124">Ytterligare överväganden</span><span class="sxs-lookup"><span data-stu-id="2c10f-124">Additional considerations</span></span>
<span data-ttu-id="2c10f-125">Enhetsregistrering inaktiveras efter migrering av klientorganisationen och kan inte aktiveras eller inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="2c10f-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="2c10f-126">Om Intune inte används loggar du in på din prenumeration och kör det här kommandot för att aktivera alternativet igen:</span><span class="sxs-lookup"><span data-stu-id="2c10f-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="2c10f-127">**VIKTIGT!** Intune-tjänstens huvudnamn aktiveras efter e-handelsmigrering, vilket innebär aktivering av enhetsregistrering för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2c10f-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="2c10f-128">Om du blockerade enhetsregistrering för Azure AD före migreringen måste du inaktivera Intune-tjänstens huvudnamn med PowerShell om du vill inaktivera enhetsregistrering för Azure AD med Azure AD-portalen igen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="2c10f-129">Du kan inaktivera Intune-tjänstens huvudnamn med det här kommandot Azure Active Directory PowerShell för Graph modul.</span><span class="sxs-lookup"><span data-stu-id="2c10f-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="2c10f-130">Azure AD-anslutning</span><span class="sxs-lookup"><span data-stu-id="2c10f-130">Azure AD Join</span></span>
<span data-ttu-id="2c10f-131">Det här gäller Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="2c10f-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="2c10f-132">Om en enhet är Azure AD ansluten måste den kopplas bort från Azure AD och anslutas igen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="2c10f-133">[![Azure AD-Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2c10f-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="2c10f-134">Om användaren är administratör på en annan Windows 10 kan användaren avregistrera enheten från Azure AD och åter ansluta till den igen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="2c10f-135">Om han eller hon inte har administratörsbehörighet behöver användaren autentiseringsuppgifter för ett lokalt administratörskonto på den här datorn.</span><span class="sxs-lookup"><span data-stu-id="2c10f-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="2c10f-136">En administratör kan skapa ett lokalt administratörskonto på enheten genom att följa den här konfigurationssökvägen:</span><span class="sxs-lookup"><span data-stu-id="2c10f-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="2c10f-137">*Inställningar > konton > andra konton > okänd > Lägg till användare utan Microsoft-konto*</span><span class="sxs-lookup"><span data-stu-id="2c10f-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="2c10f-138">Steg 1: Avgör om enheten är Azure-ID ansluten</span><span class="sxs-lookup"><span data-stu-id="2c10f-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="2c10f-139">Logga in med användarnaS e-post och lösenord.</span><span class="sxs-lookup"><span data-stu-id="2c10f-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="2c10f-140">Gå till Inställningar > Konton > Åtkomst till arbete eller skola.</span><span class="sxs-lookup"><span data-stu-id="2c10f-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="2c10f-141">Leta efter en användare i listan som är **ansluten till ... s Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="2c10f-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="2c10f-142">Om en ansluten användare finns fortsätter du med steg 2.</span><span class="sxs-lookup"><span data-stu-id="2c10f-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="2c10f-143">Om inte krävs inga ytterligare åtgärder.</span><span class="sxs-lookup"><span data-stu-id="2c10f-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="2c10f-144">Steg 2: Koppla bort enheten från Azure AD</span><span class="sxs-lookup"><span data-stu-id="2c10f-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="2c10f-145">Tryck **på Koppla** från på det anslutna arbets- eller skolkontot.</span><span class="sxs-lookup"><span data-stu-id="2c10f-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="2c10f-146">Bekräfta frånkopplingen två gånger.</span><span class="sxs-lookup"><span data-stu-id="2c10f-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="2c10f-147">Ange lokalt administratörsnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="2c10f-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="2c10f-148">Enheten kopplas från.</span><span class="sxs-lookup"><span data-stu-id="2c10f-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="2c10f-149">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="2c10f-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="2c10f-150">Steg 3: Anslut enheten till Azure AD</span><span class="sxs-lookup"><span data-stu-id="2c10f-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="2c10f-151">användaren loggar in med den lokala administratörens autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="2c10f-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="2c10f-152">Gå till **Inställningar** sedan **Konton och** komma åt arbete eller **skola**</span><span class="sxs-lookup"><span data-stu-id="2c10f-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="2c10f-153">Tryck **på Anslut**</span><span class="sxs-lookup"><span data-stu-id="2c10f-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="2c10f-154">**VIKTIGT:** Tryck **på Anslut till Azure AD**</span><span class="sxs-lookup"><span data-stu-id="2c10f-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="2c10f-155">Ange användarens e-postadress och lösenord.</span><span class="sxs-lookup"><span data-stu-id="2c10f-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="2c10f-156">Enheten är ansluten</span><span class="sxs-lookup"><span data-stu-id="2c10f-156">The device is connected</span></span>
6.  <span data-ttu-id="2c10f-157">Starta om enheten</span><span class="sxs-lookup"><span data-stu-id="2c10f-157">Restart the device</span></span> 
7.  <span data-ttu-id="2c10f-158">med din e-postadress och ditt lösenord</span><span class="sxs-lookup"><span data-stu-id="2c10f-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="2c10f-159">Azure AD Registered (företagsägd)</span><span class="sxs-lookup"><span data-stu-id="2c10f-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="2c10f-160">För att avgöra om Windows 10 är Azure AD-registrerad kör du följande kommando på enheten:</span><span class="sxs-lookup"><span data-stu-id="2c10f-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="2c10f-161">Om enheten är Azure AD Registrerad ser du följande utdata:</span><span class="sxs-lookup"><span data-stu-id="2c10f-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="2c10f-162">Så här tar du bort det befintliga Azure AD-registrerade kontot på enheten:</span><span class="sxs-lookup"><span data-stu-id="2c10f-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="2c10f-163">Om du vill ta bort det Azure AD-registrerade kontot på enheten använder du CleanupWPJ, ett verktyg som du kan ladda ned härifrån: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="2c10f-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="2c10f-164">Extrahera ZIP-filen och kör **WPJCleanup.cmd**.</span><span class="sxs-lookup"><span data-stu-id="2c10f-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="2c10f-165">Det här verktyget startar rätt körbar baserat på versionen av Windows på enheten.</span><span class="sxs-lookup"><span data-stu-id="2c10f-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="2c10f-166">Genom att använda en mekanism som grupprincip kan administratören köra kommandot på enheten i samband med alla användare som är inloggade på enheten.</span><span class="sxs-lookup"><span data-stu-id="2c10f-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="2c10f-167">Om du vill inaktivera Web Account Manager-uppmaningar om att registrera enheten i Azure AD lägger du till det här registervärdet:</span><span class="sxs-lookup"><span data-stu-id="2c10f-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="2c10f-168">Plats: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="2c10f-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="2c10f-169">Typ: DWORD (32 bitar)</span><span class="sxs-lookup"><span data-stu-id="2c10f-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="2c10f-170">Namn: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="2c10f-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="2c10f-171">Värdedata: 1</span><span class="sxs-lookup"><span data-stu-id="2c10f-171">Value data: 1</span></span>

<span data-ttu-id="2c10f-172">Förekomsten av det här registervärdet bör blockera anslutning till arbetsplatsen och förhindra att användarna ser uppmaningar om att ansluta till enheten.</span><span class="sxs-lookup"><span data-stu-id="2c10f-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="2c10f-173">Android</span><span class="sxs-lookup"><span data-stu-id="2c10f-173">Android</span></span>

<span data-ttu-id="2c10f-174">För Android måste användarna avregistrera sig och registrera sina enheter igen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="2c10f-175">Det kan du göra via Microsoft Authenticator eller det Företagsportal appen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="2c10f-176">Från Microsoft Authenticator kan användarna gå till **enhetsregistreringen Inställningar >.**</span><span class="sxs-lookup"><span data-stu-id="2c10f-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="2c10f-177">Därifrån kan användare avregistrera sig och registrera sin enhet igen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="2c10f-178">I Företagsportal enheter kan användarna gå till **fliken Enheter** och ta bort enheten.</span><span class="sxs-lookup"><span data-stu-id="2c10f-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="2c10f-179">Därefter kan du registrera enheten igen med hjälp av Företagsportal.</span><span class="sxs-lookup"><span data-stu-id="2c10f-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="2c10f-180">Användare kan också avregistrera och registrera igen genom att ta bort kontot från sidan kontoinställningar och sedan lägga till arbetskontot igen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="2c10f-181">Så här avregistrerar du och registrerar om enheten på Android med hjälp av Microsoft Authenticator appen:</span><span class="sxs-lookup"><span data-stu-id="2c10f-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="2c10f-182">Öppna Microsoft Authenticator och gå till **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2c10f-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="2c10f-183">Välj **Enhetsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="2c10f-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="2c10f-184">Avregistrera enheten genom att välja **Avregistrera**.</span><span class="sxs-lookup"><span data-stu-id="2c10f-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="2c10f-185">För **enhetsregistrering** registrerar du enheten igen genom att skriva din e-postadress och väljer **registrera**.</span><span class="sxs-lookup"><span data-stu-id="2c10f-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="2c10f-186">Så här avregistrerar du och registrerar en Android-enhet på Inställningar Android-enhet:</span><span class="sxs-lookup"><span data-stu-id="2c10f-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="2c10f-187">Öppna **Enhetshanteraren Inställningar** gå till **Konton**.</span><span class="sxs-lookup"><span data-stu-id="2c10f-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="2c10f-188">Välj det arbetskonto du vill registrera igen och välj Ta **bort konto**.</span><span class="sxs-lookup"><span data-stu-id="2c10f-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="2c10f-189">När kontot har tagits bort går du till **sidan Konton** och väljer Lägg till konto **> Arbetskonto**.</span><span class="sxs-lookup"><span data-stu-id="2c10f-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="2c10f-190">I **Workplace Join** skriver du din e-postadress och väljer **Anslut** för att slutföra registreringen av enheten.</span><span class="sxs-lookup"><span data-stu-id="2c10f-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="2c10f-191">Så här avregistrerar du och registrerar om enheten på Android från Företagsportal:</span><span class="sxs-lookup"><span data-stu-id="2c10f-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="2c10f-192">Starta Företagsportal gå till **fliken** Enheter.</span><span class="sxs-lookup"><span data-stu-id="2c10f-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="2c10f-193">Välj enheten om du vill se enhetsinformationen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="2c10f-194">På ellipsmenyn (tre punkter) väljer du Ta **bort** enhet och slutför borttagningen genom att bekräfta i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2c10f-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="2c10f-195">Du bör nu vara utloggad från Företagsportal appen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="2c10f-196">Välj **Logga in** för att registrera enheten igen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="2c10f-197">Mer information om åtgärder som krävs under migreringsfasen av den här arbetsbelastningen, eller som påverkar administration eller användning, finns i informationen om Azure Active Directory (Azure AD) i Ytterligare Azure AD-information för migreringen från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition-azure-ad.md)</span><span class="sxs-lookup"><span data-stu-id="2c10f-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="2c10f-198">iOS</span><span class="sxs-lookup"><span data-stu-id="2c10f-198">iOS</span></span>

<span data-ttu-id="2c10f-199">På iOS-enheter måste en användare manuellt ta bort cachelagrade konton från Microsoft Authenticator, avregistrera enheten och logga ut från alla inbyggda appar på enheten.</span><span class="sxs-lookup"><span data-stu-id="2c10f-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="2c10f-200">Steg 1: Om det finns tar du bort kontot från Microsoft Authenticator programmet</span><span class="sxs-lookup"><span data-stu-id="2c10f-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="2c10f-201">Tryck på kontot i Microsoft Authenticator appen.</span><span class="sxs-lookup"><span data-stu-id="2c10f-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="2c10f-202">Tryck **Inställningar** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="2c10f-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="2c10f-203">Om du inte ser ikonen **Inställningar** kanske du inte använder den senaste versionen av Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="2c10f-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="2c10f-204">Tryck på **knappen Ta bort** konto.</span><span class="sxs-lookup"><span data-stu-id="2c10f-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="2c10f-205">Tryck **på Alla appar på den här enheten**.</span><span class="sxs-lookup"><span data-stu-id="2c10f-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="2c10f-206">Steg 2: Avregistrera enheten från Microsoft Authenticator appen</span><span class="sxs-lookup"><span data-stu-id="2c10f-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="2c10f-207">Tryck på menyikonen i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="2c10f-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="2c10f-208">Tryck **Inställningar** och sedan **på Enhetsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="2c10f-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="2c10f-209">Om ditt konto visas trycker du på **Avregistrera enhet** **och Fortsätt** i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2c10f-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="2c10f-210">Därefter bör du inte se något konto.</span><span class="sxs-lookup"><span data-stu-id="2c10f-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="2c10f-211">Steg 3: Logga ut från enskilda appar om det behövs</span><span class="sxs-lookup"><span data-stu-id="2c10f-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="2c10f-212">Användare kan gå till enskilda appar som Outlook, Teams och OneDrive och ta bort konton från dessa program.</span><span class="sxs-lookup"><span data-stu-id="2c10f-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="2c10f-213">Mer information</span><span class="sxs-lookup"><span data-stu-id="2c10f-213">More information</span></span>

<span data-ttu-id="2c10f-214">Komma igång:</span><span class="sxs-lookup"><span data-stu-id="2c10f-214">Getting started:</span></span>

- [<span data-ttu-id="2c10f-215">Migrering från Microsoft Cloud Deutschland till Office 365 i de nya tyska datacenterområdena</span><span class="sxs-lookup"><span data-stu-id="2c10f-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="2c10f-216">Migreringshjälp för Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="2c10f-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="2c10f-217">Så här väljer du in för migrering</span><span class="sxs-lookup"><span data-stu-id="2c10f-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="2c10f-218">Kundupplevelse under migreringen</span><span class="sxs-lookup"><span data-stu-id="2c10f-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="2c10f-219">Flytta genom övergången:</span><span class="sxs-lookup"><span data-stu-id="2c10f-219">Moving through the transition:</span></span>

- [<span data-ttu-id="2c10f-220">Åtgärder och påverkan i migreringsfaser</span><span class="sxs-lookup"><span data-stu-id="2c10f-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="2c10f-221">Ytterligare arbete</span><span class="sxs-lookup"><span data-stu-id="2c10f-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="2c10f-222">Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="2c10f-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="2c10f-223">Molnappar:</span><span class="sxs-lookup"><span data-stu-id="2c10f-223">Cloud apps:</span></span>

- [<span data-ttu-id="2c10f-224">Information om Dynamics 365-migreringsprogram</span><span class="sxs-lookup"><span data-stu-id="2c10f-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="2c10f-225">Power BI i migreringsprogrammet</span><span class="sxs-lookup"><span data-stu-id="2c10f-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="2c10f-226">Komma igång med din Microsoft Teams uppgradering</span><span class="sxs-lookup"><span data-stu-id="2c10f-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)