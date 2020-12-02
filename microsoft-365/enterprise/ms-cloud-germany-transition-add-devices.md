---
title: Ytterligare enhets information för migreringen från Microsoft Cloud Deutschland
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
description: 'Sammanfattning: ytterligare enhets information på tjänster när du flyttar från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska data centret.'
ms.openlocfilehash: da05a3c2eb6a8d579c53d403a1ef575c389eda12
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551959"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="21908-103">Ytterligare enhets information för migreringen från Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="21908-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="21908-104">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="21908-104">Frequently asked questions</span></span>

<span data-ttu-id="21908-105">**Hur vet jag om min organisation påverkas?**</span><span class="sxs-lookup"><span data-stu-id="21908-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="21908-106">Administratörer bör kontrol lera `https://portal.microsoftazure.de` om de har registrerade enheter.</span><span class="sxs-lookup"><span data-stu-id="21908-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="21908-107">Om din organisation har registrerade enheter påverkas det.</span><span class="sxs-lookup"><span data-stu-id="21908-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="21908-108">**Vad händer med mina användare?**</span><span class="sxs-lookup"><span data-stu-id="21908-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="21908-109">Användare från en registrerad enhet kommer inte längre att kunna logga in efter migreringen och [Slutför Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration-fasen.</span><span class="sxs-lookup"><span data-stu-id="21908-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="21908-110">Kontrol lera att alla dina enheter är registrerade med den globala slut punkten innan organisationen kopplas bort från Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="21908-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="21908-111">**När registrerar mina användare en ny omregistrera deras enheter?**</span><span class="sxs-lookup"><span data-stu-id="21908-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="21908-112">Det är viktigt för din framgång att du bara avregistrerar och registrerar om dina enheter under den separata migrations fasen [för Microsoft Cloud-Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="21908-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="21908-113">**Hur återställer jag enhetens tillstånd efter migrering?**</span><span class="sxs-lookup"><span data-stu-id="21908-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="21908-114">För Hybrid Azure AD-anslutna och företagsägda Windows-enheter som är registrerade med Azure AD kan administratörer hantera migreringen av dessa enheter via fjärrutlös ande arbets flöden som avregistrerar de gamla enhets tillstånden.</span><span class="sxs-lookup"><span data-stu-id="21908-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="21908-115">För alla andra enheter, inklusive personliga Windows-enheter som är registrerade i Azure AD, måste slutanvändaren utföra dessa steg manuellt.</span><span class="sxs-lookup"><span data-stu-id="21908-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="21908-116">För Azure AD-anslutna enheter måste användare ha ett lokalt administratörs konto för att avregistrera och sedan registrera om sina enheter.</span><span class="sxs-lookup"><span data-stu-id="21908-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="21908-117">Microsoft publicerar instruktioner för hur du återställer enhetens status.</span><span class="sxs-lookup"><span data-stu-id="21908-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="21908-118">**Hur vet jag att alla mina enheter är registrerade i det offentliga molnet?**</span><span class="sxs-lookup"><span data-stu-id="21908-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="21908-119">Om du vill kontrol lera att dina enheter är registrerade i det offentliga molnet bör du exportera och ladda ned listan över enheter från Azure AD-portalen till ett Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="21908-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="21908-120">Filtrera sedan de enheter som är registrerade (med hjälp av kolumnen _registeredTime_ ) efter den [avgränsade flytt fasen från Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="21908-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="21908-121">Enhets registrering är inaktiverat efter migrering av klient organisationen och kan inte aktive ras eller inaktive ras.</span><span class="sxs-lookup"><span data-stu-id="21908-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="21908-122">Om Intune inte används loggar du in på ditt abonnemang och kör det här kommandot för att återaktivera alternativet:</span><span class="sxs-lookup"><span data-stu-id="21908-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="21908-123">Windows hybrid Azure AD-anslutning</span><span class="sxs-lookup"><span data-stu-id="21908-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="21908-124">Windows i nivå</span><span class="sxs-lookup"><span data-stu-id="21908-124">Windows down-level</span></span>

<span data-ttu-id="21908-125">_Windows-_ enheter som använder tidigare versioner av Windows (till exempel Windows 8,1 eller Windows 7), eller som kör Windows Server-versioner tidigare än 2019 och 2016, är Windows-produkter.</span><span class="sxs-lookup"><span data-stu-id="21908-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="21908-126">Om sådana enheter registrerades förut måste du avregistrera och registrera om dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="21908-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="21908-127">Använd följande kommando på enheten för att avgöra om en Windows-enhet med en låg nivå tidigare varit ansluten till Azure AD:</span><span class="sxs-lookup"><span data-stu-id="21908-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="21908-128">Om enheten tidigare varit ansluten till Azure AD och om enheten har nätverks anslutning till globala Azure AD-slutpunkter ser du följande utdata:</span><span class="sxs-lookup"><span data-stu-id="21908-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="21908-129">Berörda enheter har "enhets status" och värdet "okänt".</span><span class="sxs-lookup"><span data-stu-id="21908-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="21908-130">Om resultatet är "enheten är inte ansluten" eller om "enhetens status"-värde är "OK", ignorerar du följande vägledning.</span><span class="sxs-lookup"><span data-stu-id="21908-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="21908-131">Endast för enheter som visar att enheten är kopplad (via deviceId, tumavtryck och så vidare) och vars "enhets status"-värde är "okänt", ska administratörer köra följande kommando i kontexten för en domän användare som loggar in på en sådan enhet.</span><span class="sxs-lookup"><span data-stu-id="21908-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="21908-132">Det föregående kommandot behöver bara köras en gång per domän användare som loggar in på den Windows-baserade enheten.</span><span class="sxs-lookup"><span data-stu-id="21908-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="21908-133">Det här kommandot bör köras i kontexten för domän användar inloggningen.</span><span class="sxs-lookup"><span data-stu-id="21908-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="21908-134">Tillräckligt med försiktighet måste vidtas för att inte köra det här kommandot när användaren loggar in.</span><span class="sxs-lookup"><span data-stu-id="21908-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="21908-135">När föregående kommando körs raderas det kopplade läget för den lokala hybrid Azure AD-anslutna datorn för den användare som loggat in.</span><span class="sxs-lookup"><span data-stu-id="21908-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="21908-136">Och om datorn fortfarande är konfigurerad för att bli hybrid Azure AD-ansluten till klient organisationen försöker den ansluta när användaren loggar in igen.</span><span class="sxs-lookup"><span data-stu-id="21908-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="21908-137">Windows-aktuell</span><span class="sxs-lookup"><span data-stu-id="21908-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="21908-138">Koppla från</span><span class="sxs-lookup"><span data-stu-id="21908-138">Unjoin</span></span>

<span data-ttu-id="21908-139">Om du vill ta reda på om Windows 10-enheten tidigare varit ansluten till Azure AD kör du följande kommando på enheten:</span><span class="sxs-lookup"><span data-stu-id="21908-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="21908-140">Om enheten är hybrid Azure AD-ansluten ser administratören följande utdata:</span><span class="sxs-lookup"><span data-stu-id="21908-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="21908-141">Om utdata är "AzureAdJoined: No", ignorerar du följande vägledning.</span><span class="sxs-lookup"><span data-stu-id="21908-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="21908-142">För enheter som visar att enheten är ansluten till Azure AD kör du följande kommando som administratör för att ta bort enhetens anslutna status.</span><span class="sxs-lookup"><span data-stu-id="21908-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="21908-143">Föregående kommando måste bara köras en gång i en administrativ kontext på Windows-enheten.</span><span class="sxs-lookup"><span data-stu-id="21908-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="21908-144">Hybrid annons Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="21908-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="21908-145">Enheten ansluts automatiskt till Azure AD utan användar-eller administratörs åtgärd så länge enheten har nätverks anslutning till globala Azure AD-slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="21908-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="21908-146">Windows Azure AD-anslutning</span><span class="sxs-lookup"><span data-stu-id="21908-146">Windows Azure AD Join</span></span>

### <a name="unjoin"></a><span data-ttu-id="21908-147">Koppla från</span><span class="sxs-lookup"><span data-stu-id="21908-147">Unjoin</span></span>

<span data-ttu-id="21908-148">För att avgöra om en Windows 10-enhet tidigare varit ansluten till Azure AD kan användaren eller administratören köra följande kommando på enheten:</span><span class="sxs-lookup"><span data-stu-id="21908-148">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="21908-149">Om enheten är ansluten till Azure AD ser användaren eller administratören följande resultat:</span><span class="sxs-lookup"><span data-stu-id="21908-149">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="21908-150">Om utdata är "AzureAdJoined: NO", ignorerar du följande vägledning.</span><span class="sxs-lookup"><span data-stu-id="21908-150">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="21908-151">Användare: om enheten är en Azure AD ansluten kan en användare koppla från enheten från inställningarna.</span><span class="sxs-lookup"><span data-stu-id="21908-151">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="21908-152">Kontrol lera att det finns ett lokalt administratörs konto på enheten innan du kopplar från enheten från Azure AD.</span><span class="sxs-lookup"><span data-stu-id="21908-152">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="21908-153">Det lokala administratörs kontot krävs för att logga in på enheten igen.</span><span class="sxs-lookup"><span data-stu-id="21908-153">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="21908-154">Administratör: om organisationens administratör vill koppla från användarnas enheter som är Azure AD-anslutna kan de göra det genom att köra följande kommando på varje enhet med hjälp av en mekanism som grup princip.</span><span class="sxs-lookup"><span data-stu-id="21908-154">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="21908-155">Administratören måste kontrol lera att det finns ett lokalt administratörs konto på enheten innan du kopplar från enheten från Azure AD.</span><span class="sxs-lookup"><span data-stu-id="21908-155">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="21908-156">Det lokala administratörs kontot behövs för att logga in på enheten igen.</span><span class="sxs-lookup"><span data-stu-id="21908-156">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="21908-157">Föregående kommando måste bara köras en gång i en administrativ kontext på Windows-enheten.</span><span class="sxs-lookup"><span data-stu-id="21908-157">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="21908-158">Azure AD Join/re-registrering</span><span class="sxs-lookup"><span data-stu-id="21908-158">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="21908-159">Användaren kan ansluta till enheten till Azure AD från Windows-inställningar: **inställningar > konton > åtkomst till arbets-eller skol > Anslut**.</span><span class="sxs-lookup"><span data-stu-id="21908-159">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="21908-160">Windows Azure AD registrerad (företag)</span><span class="sxs-lookup"><span data-stu-id="21908-160">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="21908-161">Om du vill ta reda på om Windows 10-enheten är Azure AD-registrerad kör du följande kommando på enheten:</span><span class="sxs-lookup"><span data-stu-id="21908-161">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="21908-162">Om enheten är Azure AD registrerad visas följande:</span><span class="sxs-lookup"><span data-stu-id="21908-162">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="21908-163">Så här tar du bort det befintliga Azure AD-registrerade kontot på enheten:</span><span class="sxs-lookup"><span data-stu-id="21908-163">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="21908-164">Om du vill ta bort Azure AD-det registrerade kontot på enheten använder du CleanupWPJ, ett verktyg som du kan ladda ned härifrån: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="21908-164">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="21908-165">Extrahera ZIP-filen och kör **WPJCleanup. cmd**.</span><span class="sxs-lookup"><span data-stu-id="21908-165">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="21908-166">Det här verktyget startar den rätta körbara filen baserat på Windows-versionen på enheten.</span><span class="sxs-lookup"><span data-stu-id="21908-166">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="21908-167">Genom att använda en funktion som grup princip kan administratören köra kommandot på enheten i kontexten för en användare som är inloggad på enheten.</span><span class="sxs-lookup"><span data-stu-id="21908-167">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="21908-168">Om du vill inaktivera Web Account Manager-prompten för att registrera enheten i Azure AD, lägger du till det här registervärdet:</span><span class="sxs-lookup"><span data-stu-id="21908-168">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="21908-169">Plats: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="21908-169">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="21908-170">Typ: DWORD (32 bitar)</span><span class="sxs-lookup"><span data-stu-id="21908-170">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="21908-171">Namn: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="21908-171">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="21908-172">Värde data: 1</span><span class="sxs-lookup"><span data-stu-id="21908-172">Value data: 1</span></span>

<span data-ttu-id="21908-173">Närvaron av det här registervärdet bör blockera arbets plats anslutning och förhindra användare från att se uppmaningar att gå med i enheten.</span><span class="sxs-lookup"><span data-stu-id="21908-173">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="21908-174">Android</span><span class="sxs-lookup"><span data-stu-id="21908-174">Android</span></span>

<span data-ttu-id="21908-175">För Android måste användarna avregistrera och registrera om sina enheter.</span><span class="sxs-lookup"><span data-stu-id="21908-175">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="21908-176">Det här kan du göra via programmet Microsoft Authenticator eller företagsportalsappen.</span><span class="sxs-lookup"><span data-stu-id="21908-176">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="21908-177">Från Microsoft Authenticator-appen kan användarna gå till **inställningar > enhets registrering**.</span><span class="sxs-lookup"><span data-stu-id="21908-177">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="21908-178">Därifrån kan användarna avregistrera och registrera om sina enheter.</span><span class="sxs-lookup"><span data-stu-id="21908-178">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="21908-179">Från företags portalen kan användare gå till fliken **enheter** och ta bort enheten.</span><span class="sxs-lookup"><span data-stu-id="21908-179">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="21908-180">Därefter omregistrerar du enheten på nytt med hjälp av företags portalen.</span><span class="sxs-lookup"><span data-stu-id="21908-180">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="21908-181">Användare kan också avregistrera och registrera om genom att ta bort kontot från sidan konto inställningar och sedan lägga till arbets kontot igen.</span><span class="sxs-lookup"><span data-stu-id="21908-181">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="21908-182">För att avregistrera och registrera enheten på Android med hjälp av Microsoft Authenticator-appen:</span><span class="sxs-lookup"><span data-stu-id="21908-182">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="21908-183">Öppna Microsoft Authenticator-appen och gå till **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="21908-183">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="21908-184">Välj **enhets registrering**.</span><span class="sxs-lookup"><span data-stu-id="21908-184">Select **Device registration**.</span></span>
3.  <span data-ttu-id="21908-185">Avregistrera enheten genom att välja **avregistrering**.</span><span class="sxs-lookup"><span data-stu-id="21908-185">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="21908-186">Registrera **enheten igen** genom att skriva in din e-postadress och välj sedan **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="21908-186">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="21908-187">Så här avregistrerar och registrerar du en Android-enhet på nytt på Android-sidan:</span><span class="sxs-lookup"><span data-stu-id="21908-187">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="21908-188">Öppna **enhets inställningar** och gå till **konton**.</span><span class="sxs-lookup"><span data-stu-id="21908-188">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="21908-189">Välj det arbets konto som du vill registrera om och välj **ta bort konto**.</span><span class="sxs-lookup"><span data-stu-id="21908-189">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="21908-190">När kontot har tagits bort väljer du **Lägg till konto > arbets konto** på sidan **konton** .</span><span class="sxs-lookup"><span data-stu-id="21908-190">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="21908-191">För **arbets plats anslutning** skriver du din e-postadress och väljer **Anslut** för att slutföra registreringen av enheten.</span><span class="sxs-lookup"><span data-stu-id="21908-191">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="21908-192">För att avregistrera och registrera enheten på Android från företags portalen:</span><span class="sxs-lookup"><span data-stu-id="21908-192">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="21908-193">Starta företags Portal och gå till fliken **enheter** .</span><span class="sxs-lookup"><span data-stu-id="21908-193">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="21908-194">Välj enhet för att Visa enhets informationen.</span><span class="sxs-lookup"><span data-stu-id="21908-194">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="21908-195">På menyn punkter (tre punkter) väljer du **ta bort enhet** och slutför borttagningen genom att bekräfta i dialog rutan.</span><span class="sxs-lookup"><span data-stu-id="21908-195">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="21908-196">Du ska nu vara utloggad från företagsportalsappen.</span><span class="sxs-lookup"><span data-stu-id="21908-196">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="21908-197">Välj **Logga in** för att registrera enheten på nytt.</span><span class="sxs-lookup"><span data-stu-id="21908-197">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="21908-198">Om du vill ha mer information om åtgärder som krävs under migrations fasen för denna arbets belastning, eller om det påverkar administrationen eller användningen, läser du informationen om Azure Active Directory i [Ytterligare allmän information för migreringen från Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span><span class="sxs-lookup"><span data-stu-id="21908-198">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory in [Additional general information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span></span>

## <a name="ios"></a><span data-ttu-id="21908-199">iOS</span><span class="sxs-lookup"><span data-stu-id="21908-199">iOS</span></span>

<span data-ttu-id="21908-200">På iOS-enheter måste en användare manuellt ta bort alla cachelagrade konton från Microsoft Authenticator, avregistrera enheten och logga ut från alla egna appar på enheten.</span><span class="sxs-lookup"><span data-stu-id="21908-200">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="21908-201">Steg 1: ta bort kontot från programmet Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="21908-201">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="21908-202">Tryck på kontot i Microsoft Authenticator-appen.</span><span class="sxs-lookup"><span data-stu-id="21908-202">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="21908-203">Tryck på ikonen **Inställningar** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="21908-203">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="21908-204">Om du inte ser ikonen **Inställningar** kanske du inte använder den senaste versionen av Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="21908-204">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="21908-205">Tryck på knappen **ta bort konto** .</span><span class="sxs-lookup"><span data-stu-id="21908-205">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="21908-206">Tryck **på alla appar på den här enheten**.</span><span class="sxs-lookup"><span data-stu-id="21908-206">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="21908-207">Steg 2: avregistrera enheten från Microsoft Authenticator-appen</span><span class="sxs-lookup"><span data-stu-id="21908-207">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="21908-208">Tryck på Meny ikonen i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="21908-208">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="21908-209">Tryck på **Inställningar** och sedan på **enhets registrering**.</span><span class="sxs-lookup"><span data-stu-id="21908-209">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="21908-210">Om ditt konto visas trycker du på **avregistrera enheten** och **fortsätter** i dialog rutan.</span><span class="sxs-lookup"><span data-stu-id="21908-210">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="21908-211">Inget konto visas.</span><span class="sxs-lookup"><span data-stu-id="21908-211">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="21908-212">Steg 3: Logga ut från enskilda appar om det behövs</span><span class="sxs-lookup"><span data-stu-id="21908-212">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="21908-213">Användare kan gå till enskilda appar som Outlook, team och OneDrive och ta bort konton från dessa program.</span><span class="sxs-lookup"><span data-stu-id="21908-213">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="21908-214">Mer information</span><span class="sxs-lookup"><span data-stu-id="21908-214">More information</span></span>

<span data-ttu-id="21908-215">Komma igång:</span><span class="sxs-lookup"><span data-stu-id="21908-215">Getting started:</span></span>

- [<span data-ttu-id="21908-216">Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna</span><span class="sxs-lookup"><span data-stu-id="21908-216">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="21908-217">Hjälp för Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="21908-217">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="21908-218">Så här väljer du för migrering</span><span class="sxs-lookup"><span data-stu-id="21908-218">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="21908-219">Kund upplevelse under migreringen</span><span class="sxs-lookup"><span data-stu-id="21908-219">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="21908-220">Flytta genom över gången:</span><span class="sxs-lookup"><span data-stu-id="21908-220">Moving through the transition:</span></span>

- [<span data-ttu-id="21908-221">Åtgärder och konsekvenser för migreringen</span><span class="sxs-lookup"><span data-stu-id="21908-221">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="21908-222">Övrig för hands arbete</span><span class="sxs-lookup"><span data-stu-id="21908-222">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="21908-223">Ytterligare information om [tjänster](ms-cloud-germany-transition-add-general.md), [enheter](ms-cloud-germany-transition-add-devices.md), [erfarenheter](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="21908-223">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="21908-224">Molnappar:</span><span class="sxs-lookup"><span data-stu-id="21908-224">Cloud apps:</span></span>

- [<span data-ttu-id="21908-225">Information om programmet för Dynamics 365 migration</span><span class="sxs-lookup"><span data-stu-id="21908-225">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="21908-226">Information om datamigreringshanteraren för Power BI</span><span class="sxs-lookup"><span data-stu-id="21908-226">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="21908-227">Komma igång med din uppgradering av Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="21908-227">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
