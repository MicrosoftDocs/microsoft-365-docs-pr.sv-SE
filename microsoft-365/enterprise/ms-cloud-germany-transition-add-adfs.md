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
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727473"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="cdb99-103">AD FS-migreringssteg för migreringen från Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="cdb99-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="cdb99-104">Den här konfigurationsändringen kan tillämpas när som helst innan fas 4 startar.</span><span class="sxs-lookup"><span data-stu-id="cdb99-104">This configuration change can be applied at any time before phase 4 is starting.</span></span>
<span data-ttu-id="cdb99-105">När fas 2 är slutförd kommer konfigurationsändringen att fungera och du kan logga in på globala slutpunkter för Office 365, till exempel `https://portal.office.com` .</span><span class="sxs-lookup"><span data-stu-id="cdb99-105">Once phase 2 is completed the configuration change will work and you are able to sign in to Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="cdb99-106">Om du implementerar konfigurationsändringen före fas 2 fungerar ännu  inte de globala Office 365-slutpunkterna, men det nya förtroende som förlitar sig på parten fortfarande är en del av AD FS-konfigurationen (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="cdb99-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="cdb99-107">Så här migrerar du AD FS-servergruppen från Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="cdb99-107">To migrate your AD FS farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="cdb99-108">Backa upp dina AD FS-inställningar, inklusive information om FF-förtroende med [hjälp av de här stegen.](#backup)</span><span class="sxs-lookup"><span data-stu-id="cdb99-108">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="cdb99-109">Namnge säkerhetskopian **Microsoft Cloud Deutschland_Only** den bara har information om Microsoft Cloud Deutschland-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="cdb99-109">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="cdb99-110">Testa återställningen med hjälp av säkerhetskopian Microsoft Cloud Deutschland_Only. AD FS-servergruppen bör fortsätta fungera som Endast Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="cdb99-110">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="cdb99-111">När du har slutfört och testat AD FS-säkerhetskopieringen utför du följande steg för att lägga till ett nytt förtroende för den beroende parten i din ADFS-konfiguration:</span><span class="sxs-lookup"><span data-stu-id="cdb99-111">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="cdb99-112">Öppna AD FS-hanteringskonsolen</span><span class="sxs-lookup"><span data-stu-id="cdb99-112">Open the AD FS management console</span></span>
2. <span data-ttu-id="cdb99-113">I den vänstra rutan i ADFS-hanteringskonsolen expanderar du **ADFS** och sedan Förtroenderelationer **och** använder **gruppförtroenden**</span><span class="sxs-lookup"><span data-stu-id="cdb99-113">In the left pane of the ADFS management console, expand **ADFS**, then **Trust Relationships**, then **Relying Party Trusts**</span></span>
3. <span data-ttu-id="cdb99-114">I den högra rutan väljer du **Lägg till förtroende för förlitande part...**</span><span class="sxs-lookup"><span data-stu-id="cdb99-114">In the right pane, select **Add Relying Party Trust...**</span></span>
4. <span data-ttu-id="cdb99-115">Välj **Nästa** på **välkomstsidan** i guiden Lägg till förtroende för förlitande part.</span><span class="sxs-lookup"><span data-stu-id="cdb99-115">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
5. <span data-ttu-id="cdb99-116">Välj Importera **data om den** beroende part som är publicerad online eller i ett lokalt nätverk på sidan Välj **datakälla.**</span><span class="sxs-lookup"><span data-stu-id="cdb99-116">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="cdb99-117">Värdet **för federationsmetadataadress (värdnamn** eller URL) måste anges till `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="cdb99-117">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="cdb99-118">Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="cdb99-118">Then, click **Next**.</span></span>
6. <span data-ttu-id="cdb99-119">På sidan **Välj datakälla** skriver du visningsnamnet, till exempel **Microsoft Office 365 Identity Platform WorldWide.**</span><span class="sxs-lookup"><span data-stu-id="cdb99-119">On the **Select Data Source** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="cdb99-120">Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="cdb99-120">Then, click **Next**.</span></span>
7. <span data-ttu-id="cdb99-121">På sidan Konfigurera **multifaktorautentisering nu?** väljer du ett lämpligt val enligt dina autentiseringskrav.</span><span class="sxs-lookup"><span data-stu-id="cdb99-121">On the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="cdb99-122">Om du väljer Jag vill inte konfigurera flerfaktorautentisering för detta förtroende för förlitar sig på part för **stunden.**</span><span class="sxs-lookup"><span data-stu-id="cdb99-122">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="cdb99-123">Du kan ändra den här inställningen senare om du vill.</span><span class="sxs-lookup"><span data-stu-id="cdb99-123">You can change this setting later if you want to.</span></span>
8. <span data-ttu-id="cdb99-124">Behåll Tillåt alla användare  att komma åt **den** här beroende parten som är vald på Klicka på **Nästa** i välj utfärdningsauktoriseringsregler</span><span class="sxs-lookup"><span data-stu-id="cdb99-124">On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected click **Next**</span></span>
9. <span data-ttu-id="cdb99-125">Klicka **på** Nästa på **sidan Är redo att lägga till** förtroende för att slutföra guiden.</span><span class="sxs-lookup"><span data-stu-id="cdb99-125">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>
10. <span data-ttu-id="cdb99-126">Klicka **på** Stäng på **sidan** Slutför.</span><span class="sxs-lookup"><span data-stu-id="cdb99-126">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="cdb99-127">Genom att stänga guiden upprättas förtroende för den beroende parten med globala Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="cdb99-127">By closing the wizard, the Relying Party Trust with the Office 365 Global services is established.</span></span> <span data-ttu-id="cdb99-128">Det finns dock ännu inga regler för utfärdningstransformning.</span><span class="sxs-lookup"><span data-stu-id="cdb99-128">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="cdb99-129">Du kan använda [AD FS-hjälpen för](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) att generera rätt regler för utfärdningstransformning.</span><span class="sxs-lookup"><span data-stu-id="cdb99-129">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="cdb99-130">De anspråksregler som skapats med AD FS-hjälpen kan antingen läggas till manuellt via AD FS-hanteringskonsolen eller med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdb99-130">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="cdb99-131">AD FS-hjälpen genererar de PowerShell-skript som krävs.</span><span class="sxs-lookup"><span data-stu-id="cdb99-131">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. <span data-ttu-id="cdb99-132">Kör Generera anspråk på AD FS-hjälp och kopiera PowerShell anspråk på transformeringsskript med alternativet Kopiera i det övre högra hörnet i skriptet.  </span><span class="sxs-lookup"><span data-stu-id="cdb99-132">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="cdb99-133">Öppna den textredigerare du föredrar och klistra in PowerShell-skriptet i ett nytt textfönster.</span><span class="sxs-lookup"><span data-stu-id="cdb99-133">Open your preferred text editor and paste the PowerShell script into a new text window.</span></span>
3. <span data-ttu-id="cdb99-134">Lägg till följande PowerShell-rader i slutet av det klistrade skriptet från steg 2</span><span class="sxs-lookup"><span data-stu-id="cdb99-134">Add the following PowerShell lines to the end of the pasted script from step 2</span></span>
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. <span data-ttu-id="cdb99-135">Säkra och kör PowerShell-skriptet.</span><span class="sxs-lookup"><span data-stu-id="cdb99-135">Safe and execute the PowerShell script.</span></span>
5. <span data-ttu-id="cdb99-136">Kontrollera att det finns två förtroenden för förlitande part. en för Microsoft Cloud Deutschland och en för den globala Office 365-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="cdb99-136">Verify that two Relying Party trusts are present; one for the Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span>
6. <span data-ttu-id="cdb99-137">Säkerhetskopiera dina förtroenden genom att [följa de här stegen](#backup).</span><span class="sxs-lookup"><span data-stu-id="cdb99-137">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="cdb99-138">Spara den med namnet **FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="cdb99-138">Save it with the name **FFAndWorldwide**.</span></span>
7. <span data-ttu-id="cdb99-139">Slutför backend-migreringen och kontrollera att AD FS fortfarande fungerar under migreringen.</span><span class="sxs-lookup"><span data-stu-id="cdb99-139">Complete your backend migration and verify that AD FS still works during the migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="cdb99-140">AD FS-katastrofåterställning (WID-databas)</span><span class="sxs-lookup"><span data-stu-id="cdb99-140">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="cdb99-141">Om du vill återställa AD FS-servergruppen i en katastrof måste snabb återställningsverktyget för [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) utnyttjas.</span><span class="sxs-lookup"><span data-stu-id="cdb99-141">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="cdb99-142">Därför måste verktyget laddas ned och innan migreringen startar måste en säkerhetskopia skapas och lagras på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="cdb99-142">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="cdb99-143">I det här exemplet (TAT-miljöer) har följande kommandon körts för att backa servergruppen:</span><span class="sxs-lookup"><span data-stu-id="cdb99-143">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="cdb99-144">Backa upp en AD FS-servergrupp</span><span class="sxs-lookup"><span data-stu-id="cdb99-144">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="cdb99-145">Installera AD FS Rapid Restore Tool på den primära AD FS-servern.</span><span class="sxs-lookup"><span data-stu-id="cdb99-145">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="cdb99-146">Importera modulen i en PowerShell-session med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="cdb99-146">Import the module in a PowerShell session with this command.</span></span>
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. <span data-ttu-id="cdb99-147">Kör kommandot för säkerhetskopiering:</span><span class="sxs-lookup"><span data-stu-id="cdb99-147">Run the backup command:</span></span>
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. <span data-ttu-id="cdb99-148">Spara säkerhetskopian på ett säkert sätt på önskad destination.</span><span class="sxs-lookup"><span data-stu-id="cdb99-148">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="cdb99-149">Återställa en AD FS-servergrupp</span><span class="sxs-lookup"><span data-stu-id="cdb99-149">Restore an AD FS Farm</span></span>

<span data-ttu-id="cdb99-150">Om servergruppen misslyckades helt och det inte går att återgå till den gamla servergruppen gör du följande.</span><span class="sxs-lookup"><span data-stu-id="cdb99-150">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="cdb99-151">Flytta den tidigare skapade och lagrade säkerhetskopian till den nya primära AD FS-servern.</span><span class="sxs-lookup"><span data-stu-id="cdb99-151">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="cdb99-152">Kör följande `Restore-ADFS` PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="cdb99-152">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="cdb99-153">Om det behövs importerar du AD FS SSL-certifikatet i förväg.</span><span class="sxs-lookup"><span data-stu-id="cdb99-153">If necessary, import the AD FS SSL certificate beforehand.</span></span>

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. <span data-ttu-id="cdb99-154">Peka dina nya DNS-poster eller belastningsutjämnaren på de nya AD FS-servrarna.</span><span class="sxs-lookup"><span data-stu-id="cdb99-154">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="cdb99-155">Mer information</span><span class="sxs-lookup"><span data-stu-id="cdb99-155">More information</span></span>

<span data-ttu-id="cdb99-156">Komma igång:</span><span class="sxs-lookup"><span data-stu-id="cdb99-156">Getting started:</span></span>

- [<span data-ttu-id="cdb99-157">Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i nya tyska datacenterområden</span><span class="sxs-lookup"><span data-stu-id="cdb99-157">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="cdb99-158">Migreringshjälp för Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="cdb99-158">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="cdb99-159">Så här väljer du in för migrering</span><span class="sxs-lookup"><span data-stu-id="cdb99-159">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="cdb99-160">Kundupplevelse under migreringen</span><span class="sxs-lookup"><span data-stu-id="cdb99-160">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="cdb99-161">Flytta genom övergången:</span><span class="sxs-lookup"><span data-stu-id="cdb99-161">Moving through the transition:</span></span>

- [<span data-ttu-id="cdb99-162">Åtgärder och påverkan i migreringsfaser</span><span class="sxs-lookup"><span data-stu-id="cdb99-162">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="cdb99-163">Ytterligare arbete</span><span class="sxs-lookup"><span data-stu-id="cdb99-163">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="cdb99-164">Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="cdb99-164">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="cdb99-165">Molnappar:</span><span class="sxs-lookup"><span data-stu-id="cdb99-165">Cloud apps:</span></span>

- [<span data-ttu-id="cdb99-166">Information om Dynamics 365-migreringsprogram</span><span class="sxs-lookup"><span data-stu-id="cdb99-166">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="cdb99-167">Information om Migreringsprogram för Power BI</span><span class="sxs-lookup"><span data-stu-id="cdb99-167">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="cdb99-168">Komma igång med uppgraderingen till Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cdb99-168">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
