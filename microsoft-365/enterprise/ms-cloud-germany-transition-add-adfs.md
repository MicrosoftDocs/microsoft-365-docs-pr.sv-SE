---
title: Migreringsåtgärder för migrering från Microsoft Cloud Deutschland
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
description: 'Sammanfattning: migrering av AD FS (Active Directory Federation Services) för migrering från Microsoft Cloud Deutschland.'
ms.openlocfilehash: 175734851c2838eb2e224a9afb57a600d4ed9523
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49554816"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="ecb70-103">Migreringsåtgärder för migrering från Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="ecb70-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="ecb70-104">Så här migrerar du din AD FS-servergrupp (Active Directory Federation Services) från Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="ecb70-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="ecb70-105">Säkerhetskopiera dina AD FS-inställningar inklusive AA-förtroende uppgifter med [de här stegen](#backup).</span><span class="sxs-lookup"><span data-stu-id="ecb70-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="ecb70-106">Ge säkerhets kopierings programmet **Microsoft cloud Deutschland_Only** att det endast har Microsoft Cloud Deutschland-klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="ecb70-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="ecb70-107">Testa återställningen med säkerhets kopian för Microsoft Cloud Deutschland_Only kan AD FS-servergruppen fortsätta fungera endast som Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="ecb70-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="ecb70-108">Skapa ett nytt förlitande part-förtroende från **AD FS > Office 365-tjänster**.</span><span class="sxs-lookup"><span data-stu-id="ecb70-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="ecb70-109">I **förlitande part-förtroenden** i AD FS-hanteringskonsolen väljer du **Lägg till förlitande part-förtroende**.</span><span class="sxs-lookup"><span data-stu-id="ecb70-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="ecb70-110">Välj **Nästa** på **välkomst** sidan i guiden Lägg till förlitande part.</span><span class="sxs-lookup"><span data-stu-id="ecb70-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="ecb70-111">Välj **Importera data om den förlitande parten som publicerades online eller på ett lokalt nätverk** på sidan **Välj data källa** .</span><span class="sxs-lookup"><span data-stu-id="ecb70-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="ecb70-112">Värdet för **federationsmetadata (värd namn eller URL)** är inställt på `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="ecb70-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="ecb70-113">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ecb70-113">Click **Next**.</span></span>
7. <span data-ttu-id="ecb70-114">Skriv visnings namnet på sidan **Välj data källa** .</span><span class="sxs-lookup"><span data-stu-id="ecb70-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="ecb70-115">Microsoft rekommenderar **Microsoft Office 365 Identity Platform världen över**.</span><span class="sxs-lookup"><span data-stu-id="ecb70-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="ecb70-116">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ecb70-116">Click **Next**.</span></span>
8. <span data-ttu-id="ecb70-117">Klicka på **Nästa** på fliken **Konfigurera multifaktorautentisering nu?**, **Välj regler för utfärdandeauktorisering** och **klar att lägga till förtroende** sidor.</span><span class="sxs-lookup"><span data-stu-id="ecb70-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="ecb70-118">Klicka på **Stäng** på sidan **Slutför** .</span><span class="sxs-lookup"><span data-stu-id="ecb70-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="ecb70-119">Genom att stänga guiden är förlitande part-förtroendet för Office 365-tjänsterna eSTS.</span><span class="sxs-lookup"><span data-stu-id="ecb70-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="ecb70-120">Inga regler för utfärdandeauktorisering upprättas.</span><span class="sxs-lookup"><span data-stu-id="ecb70-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="ecb70-121">Du kan använda [AD FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) för att generera korrekta regler för utfärdandeauktorisering.</span><span class="sxs-lookup"><span data-stu-id="ecb70-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="ecb70-122">De genererade anspråks reglerna som skapas med AD FS-hjälpen kan antingen läggas till manuellt via AD FS-hanteringskonsolen eller med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ecb70-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="ecb70-123">Med hjälp av AD FS kan du skapa nödvändiga PowerShell-skript som måste köras.</span><span class="sxs-lookup"><span data-stu-id="ecb70-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="ecb70-124">Kör **Skapa anspråk** på AD FS-hjälp och kopiera omvandlingen av PowerShell-anspråk med alternativet **Kopiera** till höger övre högra hörnet i skriptet.</span><span class="sxs-lookup"><span data-stu-id="ecb70-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="ecb70-125">Klistra in den genererade PowerShell-filen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="ecb70-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="ecb70-126">Kör det färdiga skriptet.</span><span class="sxs-lookup"><span data-stu-id="ecb70-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="ecb70-127">Kontrol lera att två förlitande part-förtroenden finns; en för hela världen och en för BF.</span><span class="sxs-lookup"><span data-stu-id="ecb70-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="ecb70-128">Säkerhetskopiera dina förtroenden med [de här stegen](#backup).</span><span class="sxs-lookup"><span data-stu-id="ecb70-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="ecb70-129">Spara den med namnet **FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="ecb70-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="ecb70-130">Slutför din server dels migrering och kontrol lera att AD FS fortfarande fungerar under migreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="ecb70-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="ecb70-131">Återställning av en katastrof för AD FS (WID-databas)</span><span class="sxs-lookup"><span data-stu-id="ecb70-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="ecb70-132">För att återställa AD FS-servergruppen måste [Rapid Restore Tool-verktyget](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) användas av en katastrof.</span><span class="sxs-lookup"><span data-stu-id="ecb70-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="ecb70-133">Verktyget måste laddas ned och innan migreringens början måste en säkerhets kopia skapas och sparas på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="ecb70-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="ecb70-134">I det här exemplet (TAT Environment) har följande kommandon utförts för att säkerhetskopiera Server gruppen:</span><span class="sxs-lookup"><span data-stu-id="ecb70-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="ecb70-135">Säkerhetskopiera en AD FS-servergrupp</span><span class="sxs-lookup"><span data-stu-id="ecb70-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="ecb70-136">Installera AD FS Rapid Restore Tool på den primära AD FS-servern.</span><span class="sxs-lookup"><span data-stu-id="ecb70-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="ecb70-137">Importera modulen i en PowerShell-session med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="ecb70-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="ecb70-138">Kör säkerhets kopierings kommandot:</span><span class="sxs-lookup"><span data-stu-id="ecb70-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="ecb70-139">Spara säkerhets kopian på ett säkert sätt på önskad plats.</span><span class="sxs-lookup"><span data-stu-id="ecb70-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="ecb70-140">Återställa en AD FS-servergrupp</span><span class="sxs-lookup"><span data-stu-id="ecb70-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="ecb70-141">Om din server grupp inte är fullständigt och det inte går att återvända till den gamla gruppen gör du följande:</span><span class="sxs-lookup"><span data-stu-id="ecb70-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="ecb70-142">Flytta den tidigare genererade och lagrade säkerhets kopian till den nya primära AD FS-servern.</span><span class="sxs-lookup"><span data-stu-id="ecb70-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="ecb70-143">Kör följande `Restore-ADFS` PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="ecb70-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="ecb70-144">Importera då AD FS SSL-certifikatet om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ecb70-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="ecb70-145">Peka på de nya DNS-posterna eller belastningsutjämnaren till de nya AD FS-servrarna.</span><span class="sxs-lookup"><span data-stu-id="ecb70-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="ecb70-146">Mer information</span><span class="sxs-lookup"><span data-stu-id="ecb70-146">More information</span></span>

<span data-ttu-id="ecb70-147">Komma igång:</span><span class="sxs-lookup"><span data-stu-id="ecb70-147">Getting started:</span></span>

- [<span data-ttu-id="ecb70-148">Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna</span><span class="sxs-lookup"><span data-stu-id="ecb70-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="ecb70-149">Hjälp för Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="ecb70-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="ecb70-150">Så här väljer du för migrering</span><span class="sxs-lookup"><span data-stu-id="ecb70-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="ecb70-151">Kund upplevelse under migreringen</span><span class="sxs-lookup"><span data-stu-id="ecb70-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="ecb70-152">Flytta genom över gången:</span><span class="sxs-lookup"><span data-stu-id="ecb70-152">Moving through the transition:</span></span>

- [<span data-ttu-id="ecb70-153">Åtgärder och konsekvenser för migreringen</span><span class="sxs-lookup"><span data-stu-id="ecb70-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="ecb70-154">Övrig för hands arbete</span><span class="sxs-lookup"><span data-stu-id="ecb70-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="ecb70-155">Ytterligare information om [tjänster](ms-cloud-germany-transition-add-general.md), [enheter](ms-cloud-germany-transition-add-devices.md), [erfarenheter](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="ecb70-155">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="ecb70-156">Molnappar:</span><span class="sxs-lookup"><span data-stu-id="ecb70-156">Cloud apps:</span></span>

- [<span data-ttu-id="ecb70-157">Information om programmet för Dynamics 365 migration</span><span class="sxs-lookup"><span data-stu-id="ecb70-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="ecb70-158">Information om datamigreringshanteraren för Power BI</span><span class="sxs-lookup"><span data-stu-id="ecb70-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="ecb70-159">Komma igång med din uppgradering av Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ecb70-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
