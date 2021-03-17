---
title: AD FS-migreringssteg för migreringen från Microsoft Cloud Deutschland
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
description: 'Sammanfattning: Ad FS-migreringssteg (Active Directory Federation Services) för migreringen från Microsoft Cloud Deutschland.'
ms.openlocfilehash: 852fc8f93158d7b6080f1add5a05e7367539f889
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838419"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="7e982-103">AD FS-migreringssteg för migreringen från Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="7e982-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="7e982-104">Den här konfigurationsändringen måste tillämpas när som helst innan fas 2 startar.</span><span class="sxs-lookup"><span data-stu-id="7e982-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="7e982-105">När fas 2 är slutförd kommer konfigurationsändringen att fungera och du kan logga in via globala slutpunkter för Office 365, till exempel `https://portal.office.com` .</span><span class="sxs-lookup"><span data-stu-id="7e982-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="7e982-106">Om du implementerar konfigurationsändringen före fas 2 fungerar ännu  inte de globala Office 365-slutpunkterna, men det nya förtroende som förlitar sig på parten fortfarande är en del av AD FS-konfigurationen (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="7e982-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="7e982-107">Kunder som använder federerad autentisering med AD FS (Active Directory Federation Services) bör inte göra ändringar i utfärdare AV URI:er som används för alla autentiseringar med AD DS (Lokal Active Directory Domain Services) under migreringen.</span><span class="sxs-lookup"><span data-stu-id="7e982-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="7e982-108">Att ändra utfärdare-URI:er leder till autentiseringsfel för användare i domänen.</span><span class="sxs-lookup"><span data-stu-id="7e982-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="7e982-109">Uri:er för utfärdare kan ändras direkt i  AD FS eller när en domän konverteras från hanterad _till federerad_ och tvärtom.</span><span class="sxs-lookup"><span data-stu-id="7e982-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="7e982-110">Vi rekommenderar att du inte lägger till, tar bort eller konverterar en federerad domän i Azure AD-klientorganisationen som har migrerats.</span><span class="sxs-lookup"><span data-stu-id="7e982-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="7e982-111">Uri:er för utfärdare kan ändras när migreringen är fullständig.</span><span class="sxs-lookup"><span data-stu-id="7e982-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="7e982-112">Så här förbereder du AD FS-servergruppen för migreringen från Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="7e982-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="7e982-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span><span class="sxs-lookup"><span data-stu-id="7e982-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="7e982-114">Namnge säkerhetskopian **MicrosoftCloudDeutschlandOnly** för att ange att den bara har information om Microsoft Cloud Deutschland-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="7e982-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7e982-115">Säkerhetskopian innehåller inte bara det befintliga Office 365 Relying Party Trust för Microsoft Cloud Deutschland, utan även alla andra Relying Party-förtroenden som finns i respektive AD FS-servergrupp.</span><span class="sxs-lookup"><span data-stu-id="7e982-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="7e982-116">Testa återställningen med hjälp av säkerhetskopian MicrosoftCloudDeutschlandOnly. AD FS-servergruppen bör fortsätta fungera som Endast Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="7e982-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="7e982-117">När du har slutfört och testat AD FS-säkerhetskopieringen utför du följande steg för att lägga till ett nytt förtroende för den beroende parten i din ADFS-konfiguration:</span><span class="sxs-lookup"><span data-stu-id="7e982-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="7e982-118">Öppna AD FS-hanteringskonsolen.</span><span class="sxs-lookup"><span data-stu-id="7e982-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="7e982-119">I den vänstra rutan på ADFS-hanteringskonsolen navigerar du till menyn Förtroenden för **förlitande** part.</span><span class="sxs-lookup"><span data-stu-id="7e982-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="7e982-120">I den högra rutan väljer du **Lägg till förtroende för förlitande part...**</span><span class="sxs-lookup"><span data-stu-id="7e982-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="7e982-121">Välj **Börja** på **välkomstsidan** i guiden Lägg till förtroende för förlitande part.</span><span class="sxs-lookup"><span data-stu-id="7e982-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="7e982-122">Välj Importera **data om den** beroende part som är publicerad online eller i ett lokalt nätverk på sidan Välj **datakälla.**</span><span class="sxs-lookup"><span data-stu-id="7e982-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="7e982-123">Värdet **för federationsmetadataadress (värdnamn** eller URL) måste anges till `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="7e982-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="7e982-124">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7e982-124">Click **Next**.</span></span>

6. <span data-ttu-id="7e982-125">På sidan **Ange visningsnamn** skriver du visningsnamnet, till exempel **Microsoft Office 365 Identity Platform WorldWide.**</span><span class="sxs-lookup"><span data-stu-id="7e982-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="7e982-126">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7e982-126">Click **Next**.</span></span>

7. <span data-ttu-id="7e982-127">Om du använder ADFS i Windows Server 2012 går du till guidesidan Konfigurera multifaktorautentisering **nu?** och väljer rätt val enligt dina autentiseringskrav.</span><span class="sxs-lookup"><span data-stu-id="7e982-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="7e982-128">Om du väljer Jag vill inte konfigurera flerfaktorautentisering för detta förtroende för förlitar sig på part för **stunden.**</span><span class="sxs-lookup"><span data-stu-id="7e982-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="7e982-129">Du kan ändra den här inställningen senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="7e982-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="7e982-130">För AD FS 2012: Behåll Tillåt  alla användare att använda den här beroende parten markerad under Välj auktoriseringsregler i välj utfärdningsauktoriseringsregler och klicka på **Nästa.** </span><span class="sxs-lookup"><span data-stu-id="7e982-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

8. <span data-ttu-id="7e982-131">För AD FS 2016 och AD FS 2019: På sidan Välj åtkomstkontrollprincip väljer du lämplig åtkomstkontrollprincip och klickar på **Nästa.** </span><span class="sxs-lookup"><span data-stu-id="7e982-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="7e982-132">Om inget är valt fungerar inte lita på den beroende **partens** förtroende.</span><span class="sxs-lookup"><span data-stu-id="7e982-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

9. <span data-ttu-id="7e982-133">Klicka **på** Nästa på **sidan Är redo att lägga till** förtroende för att slutföra guiden.</span><span class="sxs-lookup"><span data-stu-id="7e982-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

10. <span data-ttu-id="7e982-134">Klicka **på** Stäng på **sidan** Slutför.</span><span class="sxs-lookup"><span data-stu-id="7e982-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="7e982-135">Genom att stänga guiden upprättas lita på den beroende parten med den globala Office 365-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7e982-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="7e982-136">Det finns dock ännu inga regler för utfärdningstransformning.</span><span class="sxs-lookup"><span data-stu-id="7e982-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="7e982-137">Du kan använda [AD FS-hjälpen för](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) att generera rätt regler för utfärdningstransformning.</span><span class="sxs-lookup"><span data-stu-id="7e982-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="7e982-138">De anspråksregler som skapats med AD FS-hjälpen kan antingen läggas till manuellt via AD FS-hanteringskonsolen eller med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7e982-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="7e982-139">AD FS-hjälpen genererar de PowerShell-skript som krävs.</span><span class="sxs-lookup"><span data-stu-id="7e982-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="7e982-140">[AD FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) genererar standardutformningsregler som levereras med produkten.</span><span class="sxs-lookup"><span data-stu-id="7e982-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="7e982-141">Men om anpassade regler för utfärdningstransformering finns i Microsoft Cloud Deutschland Relying Party Trust (till exempel anpassade utfärdare av URI:er, oföränderliga ICKE-standard-ID eller andra anpassningar), måste reglerna som genereras av AD FS-hjälpen ändras på ett sätt som passar den anpassade logik som för närvarande gäller för Microsoft Cloud Deutschland som förlitar sig på part.</span><span class="sxs-lookup"><span data-stu-id="7e982-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="7e982-142">Om de här anpassningarna inte är integrerade i reglerna som genereras via [AD FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)  fungerar troligtvis inte autentisering för **Microsoft Office 365 Identity Platform WorldWide** för dina federerade identiteter.</span><span class="sxs-lookup"><span data-stu-id="7e982-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="7e982-143">Kör **Generera anspråk i** AD [FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) och  kopiera PowerShell-skriptet med alternativet Kopiera i det övre högra hörnet i skriptet.</span><span class="sxs-lookup"><span data-stu-id="7e982-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="7e982-144">Följ anvisningarna i AD [FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) om hur du kör PowerShell-skriptet i AD FS-servergruppen för att generera det globala litande partförtroendet.</span><span class="sxs-lookup"><span data-stu-id="7e982-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span>

3. <span data-ttu-id="7e982-145">Kontrollera att två Relying PartyTtrusts finns. en för Microsoft Cloud Deutschland och en för den globala Office 365-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7e982-145">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="7e982-146">Följande kommando kan användas för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="7e982-146">The following command can be leveraged for the check.</span></span> <span data-ttu-id="7e982-147">Den bör returnera två rader och respektive namn och identifierare.</span><span class="sxs-lookup"><span data-stu-id="7e982-147">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="7e982-148">Säkerhetskopiera din fullständiga migreringskonfiguration, inklusive båda förtroenden från förlitande part, med [hjälp av de här stegen.](#backup)</span><span class="sxs-lookup"><span data-stu-id="7e982-148">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="7e982-149">Spara den med namnet **MicrosoftCloudDeutschlandAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="7e982-149">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="7e982-150">Under migreringen kontrollerar du regelbundet att AD FS-autentisering fungerar med Microsoft Cloud Deutschland och Microsoft Global-molnet i de olika migreringssteg som stöds.</span><span class="sxs-lookup"><span data-stu-id="7e982-150">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>


## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="7e982-151">AD FS-katastrofåterställning (WID-databas)</span><span class="sxs-lookup"><span data-stu-id="7e982-151">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="7e982-152">Om du vill återställa AD FS-servergruppen i en katastrof måste snabb återställningsverktyget för [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) utnyttjas.</span><span class="sxs-lookup"><span data-stu-id="7e982-152">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="7e982-153">Därför måste verktyget laddas ned och innan migreringen startar måste en säkerhetskopia skapas och lagras på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="7e982-153">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="7e982-154">I det här exemplet har följande kommandon körts för att backa upp en servergrupp som körs på en WID-databas:</span><span class="sxs-lookup"><span data-stu-id="7e982-154">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="7e982-155">Backa upp en AD FS-servergrupp</span><span class="sxs-lookup"><span data-stu-id="7e982-155">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="7e982-156">Installera AD FS Rapid Restore Tool på den primära AD FS-servern.</span><span class="sxs-lookup"><span data-stu-id="7e982-156">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="7e982-157">Importera modulen i en PowerShell-session med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="7e982-157">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="7e982-158">Kör kommandot för säkerhetskopiering:</span><span class="sxs-lookup"><span data-stu-id="7e982-158">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="7e982-159">Spara säkerhetskopian på ett säkert sätt på önskad destination.</span><span class="sxs-lookup"><span data-stu-id="7e982-159">Store the backup safely on a desired destination.</span></span>


### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="7e982-160">Återställa en AD FS-servergrupp</span><span class="sxs-lookup"><span data-stu-id="7e982-160">Restore an AD FS Farm</span></span>

<span data-ttu-id="7e982-161">Om servergruppen misslyckades helt och det inte går att återgå till den gamla servergruppen gör du följande.</span><span class="sxs-lookup"><span data-stu-id="7e982-161">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="7e982-162">Flytta den tidigare skapade och lagrade säkerhetskopian till den nya primära AD FS-servern.</span><span class="sxs-lookup"><span data-stu-id="7e982-162">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="7e982-163">Kör följande `Restore-ADFS` PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="7e982-163">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="7e982-164">Om det behövs importerar du AD FS SSL-certifikatet i förväg.</span><span class="sxs-lookup"><span data-stu-id="7e982-164">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="7e982-165">Peka dina nya DNS-poster eller belastningsutjämnaren på de nya AD FS-servrarna.</span><span class="sxs-lookup"><span data-stu-id="7e982-165">Point your new DNS records or load balancer to the new AD FS servers.</span></span>


## <a name="more-information"></a><span data-ttu-id="7e982-166">Mer information</span><span class="sxs-lookup"><span data-stu-id="7e982-166">More information</span></span>

<span data-ttu-id="7e982-167">Komma igång:</span><span class="sxs-lookup"><span data-stu-id="7e982-167">Getting started:</span></span>

- [<span data-ttu-id="7e982-168">Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i nya tyska datacenterområden</span><span class="sxs-lookup"><span data-stu-id="7e982-168">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="7e982-169">Migreringshjälp för Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="7e982-169">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="7e982-170">Så här väljer du in för migrering</span><span class="sxs-lookup"><span data-stu-id="7e982-170">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="7e982-171">Kundupplevelse under migreringen</span><span class="sxs-lookup"><span data-stu-id="7e982-171">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="7e982-172">Flytta genom övergången:</span><span class="sxs-lookup"><span data-stu-id="7e982-172">Moving through the transition:</span></span>

- [<span data-ttu-id="7e982-173">Åtgärder och påverkan i migreringsfaser</span><span class="sxs-lookup"><span data-stu-id="7e982-173">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="7e982-174">Ytterligare arbete</span><span class="sxs-lookup"><span data-stu-id="7e982-174">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="7e982-175">Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="7e982-175">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="7e982-176">Molnappar:</span><span class="sxs-lookup"><span data-stu-id="7e982-176">Cloud apps:</span></span>

- [<span data-ttu-id="7e982-177">Information om Dynamics 365-migreringsprogram</span><span class="sxs-lookup"><span data-stu-id="7e982-177">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="7e982-178">Information om Migreringsprogram för Power BI</span><span class="sxs-lookup"><span data-stu-id="7e982-178">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="7e982-179">Komma igång med uppgraderingen till Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e982-179">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
