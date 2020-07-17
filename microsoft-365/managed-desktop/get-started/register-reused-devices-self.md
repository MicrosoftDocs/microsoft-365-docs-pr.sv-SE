---
title: Registrera befintliga enheter själv
description: Registrera återanvända enheter som du kanske redan har själv så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: abe9e63eb4fcd31993bd26822dc445ff0e48e369
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101491"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="80608-103">Registrera befintliga enheter själv</span><span class="sxs-lookup"><span data-stu-id="80608-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="80608-104">I det här avsnittet beskrivs stegen för att återanvända enheter som du redan har och registrera dem på Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="80608-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="80608-105">Om du arbetar med helt nya enheter följer du stegen i [Registrera nya enheter på Microsoft Managed Desktop själv](register-devices-self.md) i stället.</span><span class="sxs-lookup"><span data-stu-id="80608-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="80608-106">Processen för partners dokumenteras i [Steg för partner för att registrera enheter](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="80608-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="80608-107">Microsoft Managed Desktop kan fungera med helt nya enheter eller så kan du återanvända enheter som du kanske redan har (vilket kräver att du avbildar dem igen).</span><span class="sxs-lookup"><span data-stu-id="80608-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="80608-108">Du kan registrera enheter med hjälp av Microsoft Managed Desktop Admin Portal.</span><span class="sxs-lookup"><span data-stu-id="80608-108">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="80608-109">Förbereda för att registrera befintliga enheter</span><span class="sxs-lookup"><span data-stu-id="80608-109">Prepare to register existing devices</span></span>


<span data-ttu-id="80608-110">Så här registrerar du befintliga enheter:</span><span class="sxs-lookup"><span data-stu-id="80608-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="80608-111">Hämta maskinvaruhhhen för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="80608-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="80608-112">Slå samman hash-data</span><span class="sxs-lookup"><span data-stu-id="80608-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="80608-113">[Registrera enheterna i Microsoft Managed Desktop](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="80608-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="80608-114">Dubbelkolla att bilden är korrekt.</span><span class="sxs-lookup"><span data-stu-id="80608-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="80608-115">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="80608-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="80608-116">Skaffa maskinvaruhhh</span><span class="sxs-lookup"><span data-stu-id="80608-116">Obtain the hardware hash</span></span>

<span data-ttu-id="80608-117">Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaruhhh.</span><span class="sxs-lookup"><span data-stu-id="80608-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="80608-118">Du har fyra alternativ för att hämta den här informationen från enheter som du redan använder:</span><span class="sxs-lookup"><span data-stu-id="80608-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="80608-119">Fråga oem-leverantören om registreringsfilen för Autopilot, som innehåller maskinvaruhännaren.</span><span class="sxs-lookup"><span data-stu-id="80608-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="80608-120">Skapa en anpassad rapport i [Configuration Manager](#configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="80608-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="80608-121">Kör ett Windows PowerShell-skript – antingen med hjälp av [Active Directory](#active-directory-powershell-script-method) eller [manuellt](#manual-powershell-script-method) på varje enhet – och samla in resultaten i en fil.</span><span class="sxs-lookup"><span data-stu-id="80608-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="80608-122">Starta varje enhet – men slutför inte installationsupplevelsen för Windows – och [samla in hasharen på ett flyttbart flashminne](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="80608-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="80608-123">Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="80608-123">Configuration Manager</span></span>

<span data-ttu-id="80608-124">Du kan använda Microsoft Endpoint Configuration Manager för att samla in maskinvaruhcens från befintliga enheter som du vill registrera dig på Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="80608-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80608-125">Alla enheter som du vill hämta den här informationen för måste köra Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="80608-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="80608-126">Du behöver också en enhet som är en Configuration Manager-klient som är ansluten till Configuration Manager-platsen (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="80608-126">You also need a device that is a Configuration Manager client connected to the Configuration Manager (Current Branch) site.</span></span> <span data-ttu-id="80608-127">Du behöver också rollen Reporting Point Site System som konfigurerats i din miljö med SQL Server Reporting Services aktiverat.</span><span class="sxs-lookup"><span data-stu-id="80608-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="80608-128">Om du har uppfyllt alla dessa förutsättningar är du redo att samla in informationen genom att följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="80608-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="80608-129">Välj **Övervakning**i Configuration Manager-konsolen .</span><span class="sxs-lookup"><span data-stu-id="80608-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="80608-130">Expandera **Rapportering**på arbetsytan Övervakning och välj sedan **Rapporter**.</span><span class="sxs-lookup"><span data-stu-id="80608-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="80608-131">Öppna guiden Skapa rapport i avsnittet **Skapa** **rapport** på fliken **Start.**</span><span class="sxs-lookup"><span data-stu-id="80608-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="80608-132">På sidan **Information** ställer du in följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="80608-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="80608-133">**Namn:** Ange ett namn för rapporten.</span><span class="sxs-lookup"><span data-stu-id="80608-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="80608-134">**Beskrivning:** Ange en beskrivning av rapporten.</span><span class="sxs-lookup"><span data-stu-id="80608-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="80608-135">**Server:** Visar namnet på den rapportserver där du skapar den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="80608-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="80608-136">**Sökväg:** Välj **Bläddra** om du vill ange en mapp där du vill lagra rapporten.</span><span class="sxs-lookup"><span data-stu-id="80608-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="80608-137">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="80608-137">Select **Next**.</span></span> 
6. <span data-ttu-id="80608-138">Granska inställningarna på sidan **Sammanfattning.**</span><span class="sxs-lookup"><span data-stu-id="80608-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="80608-139">Välj **Föregående** om du vill ändra inställningarna eller välj **Nästa** om du vill skapa rapporten i Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="80608-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="80608-140">På sidan **Slutförd** väljer du **Stäng** för att avsluta guiden och öppnar **Report Builder** för att ange rapportinställningarna.</span><span class="sxs-lookup"><span data-stu-id="80608-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="80608-141">Ange ditt användarkonto och lösenord om du uppmanas att göra det och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="80608-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="80608-142">Om Report Builder inte är installerat på enheten uppmanas du att installera den.</span><span class="sxs-lookup"><span data-stu-id="80608-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="80608-143">Välj **Kör om du vill installera Report Builder**, som krävs för att ändra och skapa rapporter.</span><span class="sxs-lookup"><span data-stu-id="80608-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="80608-144">**I Microsoft Report Builder**anger du SQL-uttrycket för rapporten och gör så här:</span><span class="sxs-lookup"><span data-stu-id="80608-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="80608-145">Välj **Datauppsättningar**i den vänstra rutan och högerklicka sedan på Lägg till **datauppsättning**.</span><span class="sxs-lookup"><span data-stu-id="80608-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="80608-146">Gå till fliken **Fråga** och ange sedan namnet som *DataSet0*.</span><span class="sxs-lookup"><span data-stu-id="80608-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="80608-147">Välj **Använd en datauppsättning som är inbäddad i rapporten.** Report Builder öppnas.</span><span class="sxs-lookup"><span data-stu-id="80608-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="80608-148">Välj **Datakälla**i **Report Builder:**.</span><span class="sxs-lookup"><span data-stu-id="80608-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="80608-149">Välj standarddatakällan, som ska börja med "AutoGen".</span><span class="sxs-lookup"><span data-stu-id="80608-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="80608-150">Välj **Frågetyp som text**och ange sedan den här frågan:</span><span class="sxs-lookup"><span data-stu-id="80608-150">Choose **Query type as Text**, and then enter this query:</span></span>




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. <span data-ttu-id="80608-151">Navigera till fliken **Fält,** wehre-värden för **Fältnamn** och **Fältkälla** bör redan fyllas i.</span><span class="sxs-lookup"><span data-stu-id="80608-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="80608-152">Om de inte är det väljer du **Lägg till**och väljer sedan **Frågefält**.</span><span class="sxs-lookup"><span data-stu-id="80608-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="80608-153">Ange **fältnamn** och **fältkälla**.</span><span class="sxs-lookup"><span data-stu-id="80608-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="80608-154">Upprepa för vart och ett av dessa värden:</span><span class="sxs-lookup"><span data-stu-id="80608-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="80608-155">Tillverkare</span><span class="sxs-lookup"><span data-stu-id="80608-155">Manufacturer</span></span> 
    - <span data-ttu-id="80608-156">Modell</span><span class="sxs-lookup"><span data-stu-id="80608-156">Model</span></span> 
    - <span data-ttu-id="80608-157">Tal</span><span class="sxs-lookup"><span data-stu-id="80608-157">Serial_Number</span></span> 
    - <span data-ttu-id="80608-158">HårdvaraHash</span><span class="sxs-lookup"><span data-stu-id="80608-158">HardwareHash</span></span>
7. <span data-ttu-id="80608-159">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="80608-159">Select **OK**.</span></span>

<span data-ttu-id="80608-160">**Definiera sedan rapportens visning och skapa rapporten** genom att följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="80608-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="80608-161">Välj **Tabell eller Matris**; en ny guide öppnas.</span><span class="sxs-lookup"><span data-stu-id="80608-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="80608-162">Välj **en befintlig datauppsättning i den här rapporten eller en delad datauppsättning i**Välj en datauppsättning i Välj en **datauppsättning**.</span><span class="sxs-lookup"><span data-stu-id="80608-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="80608-163">Välj **DataSet0** (standard) och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="80608-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="80608-164">Dra **tillverkare,** **modell**och **serienummer** till rutan **Radgrupper.**</span><span class="sxs-lookup"><span data-stu-id="80608-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="80608-165">Dra **HardwareHash** till rutan **Värden** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="80608-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="80608-166">Avmarkera kryssrutorna för **Visa delsummor och totalsummor** och **Grupper för expandera/komprimera.**</span><span class="sxs-lookup"><span data-stu-id="80608-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="80608-167">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="80608-167">Select **Next**.</span></span>
6. <span data-ttu-id="80608-168">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="80608-168">Select **Finish**.</span></span>
7. <span data-ttu-id="80608-169">Välj **Kör** för att köra rapporten.</span><span class="sxs-lookup"><span data-stu-id="80608-169">Select **Run** to run your report.</span></span> <span data-ttu-id="80608-170">Kontrollera att rapporten innehåller den information du förväntar dig.</span><span class="sxs-lookup"><span data-stu-id="80608-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="80608-171">Om det behövs väljer du **Design** för att återgå till designvyn för att ändra rapporten.</span><span class="sxs-lookup"><span data-stu-id="80608-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="80608-172">Välj **Spara** om du vill spara rapporten på rapportservern.</span><span class="sxs-lookup"><span data-stu-id="80608-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="80608-173">Du kan köra den nya rapporten i noden Rapporter på arbetsytan Övervakning.</span><span class="sxs-lookup"><span data-stu-id="80608-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="80608-174">**Slutligen exportera rapporten och använda den för att registrera enheter** genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="80608-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="80608-175">(Du bör bara behöva följa steg 1 och 2 i det här avsnittet om du har navigerat bort efter föregående steg.):</span><span class="sxs-lookup"><span data-stu-id="80608-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="80608-176">Välj **Övervakning**i Configuration Manager-konsolen .</span><span class="sxs-lookup"><span data-stu-id="80608-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="80608-177">Expandera Rapportering **i** **Övervakning**och välj sedan **Rapporter**.</span><span class="sxs-lookup"><span data-stu-id="80608-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="80608-178">Leta reda på rapporten med det namn du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="80608-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="80608-179">Högerklicka på den här rapporten och välj **Kör**.</span><span class="sxs-lookup"><span data-stu-id="80608-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="80608-180">I dialogrutan som öppnas väljer du **Exportera** och väljer sedan **Spara som CSV**.</span><span class="sxs-lookup"><span data-stu-id="80608-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="80608-181">Den här versionen av rapportextraheringshas från alla Windows 10-enheter som Configuration Manager kommunicerar med.</span><span class="sxs-lookup"><span data-stu-id="80608-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="80608-182">Du måste filtrera resultaten till just de enheter som du planerar att registrera dig hos Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="80608-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="80608-183">Frågan i Configuration Manager tillåter inte blanksteg i exporterade kolumnnamn. Det är därför stegen hade du ange "Serial_Number" och "HardwareHash."</span><span class="sxs-lookup"><span data-stu-id="80608-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="80608-184">Nu när du har den exporterade CSV-filen måste du redigera rapportrubrikerna för att läsa *Serienummer* och *Maskinvaruh hash* som visas här innan du fortsätter med enhetsregistrering.</span><span class="sxs-lookup"><span data-stu-id="80608-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="80608-185">Nu kan du gå vidare till [Registrera enheter med hjälp av Admin Portal](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="80608-185">Now you can proceed to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="80608-186">Active Directory PowerShell-skriptmetod</span><span class="sxs-lookup"><span data-stu-id="80608-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="80608-187">I en Active Directory-miljö kan du använda `Get-MMDRegistrationInfo` PowerShell-cmdlet för att fjärrsamla information från enheter i Active Directory-grupper med hjälp av WinRM.</span><span class="sxs-lookup"><span data-stu-id="80608-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="80608-188">Du kan också använda `Get-AD Computer` cmdlet och få filtrerade resultat för en viss maskinvarumodell namn som ingår i katalogen.</span><span class="sxs-lookup"><span data-stu-id="80608-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="80608-189">För att göra detta, först bekräfta dessa förutsättningar och sedan gå vidare med stegen:</span><span class="sxs-lookup"><span data-stu-id="80608-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="80608-190">WinRM är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="80608-190">WinRM is enabled.</span></span>
- <span data-ttu-id="80608-191">De enheter som du vill registrera är aktiva i nätverket (det vill säga de är inte frånkopplade eller avstängda).</span><span class="sxs-lookup"><span data-stu-id="80608-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="80608-192">Kontrollera att du har en domänautentiseringsparameter som har behörighet att köras på distans på enheterna.</span><span class="sxs-lookup"><span data-stu-id="80608-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="80608-193">Kontrollera att Windows-brandväggen ger åtkomst till WMI.</span><span class="sxs-lookup"><span data-stu-id="80608-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="80608-194">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="80608-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="80608-195">Öppna kontrollpanelen **för Windows Defender-brandväggen** och välj **Tillåt en app eller funktion via Windows Defender-brandväggen**.</span><span class="sxs-lookup"><span data-stu-id="80608-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="80608-196">Leta reda på **WMI (Windows Management Instrumentation)** i listan, aktivera både **privat och offentligt**och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="80608-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="80608-197">Öppna en PowerShell-prompt med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="80608-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="80608-198">Kör *något* av följande skript:</span><span class="sxs-lookup"><span data-stu-id="80608-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="80608-199">Få tillgång till alla kataloger där det kan finnas poster för enheterna.</span><span class="sxs-lookup"><span data-stu-id="80608-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="80608-200">Ta bort poster för varje enhet från *alla* kataloger, inklusive Windows Server Active Directory Domain Services och Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="80608-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="80608-201">Tänk på att denna borttagning kan ta några timmar att helt bearbeta.</span><span class="sxs-lookup"><span data-stu-id="80608-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="80608-202">Åtkomsthanteringstjänster där det kan finnas poster för enheterna.</span><span class="sxs-lookup"><span data-stu-id="80608-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="80608-203">Ta bort poster för varje enhet från *alla* hanteringstjänster, inklusive Microsoft Endpoint Configuration Manager, Microsoft Intune och Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="80608-203">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="80608-204">Tänk på att denna borttagning kan ta några timmar att helt bearbeta.</span><span class="sxs-lookup"><span data-stu-id="80608-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="80608-205">Nu kan du fortsätta att [registrera enheter](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="80608-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="80608-206">Manuell PowerShell-skriptmetod</span><span class="sxs-lookup"><span data-stu-id="80608-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="80608-207">Öppna en PowerShell-prompt med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="80608-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="80608-208">Köra`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="80608-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="80608-209">Köra`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="80608-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="80608-210">Slå samman hash-data.</span><span class="sxs-lookup"><span data-stu-id="80608-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="80608-211">Flash-enhet metod</span><span class="sxs-lookup"><span data-stu-id="80608-211">Flash drive method</span></span>

1. <span data-ttu-id="80608-212">På en annan enhet än den du registrerar sätter du i en USB-enhet.</span><span class="sxs-lookup"><span data-stu-id="80608-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="80608-213">Öppna en PowerShell-prompt med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="80608-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="80608-214">Köra`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="80608-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="80608-215">Slå på enheten du registrerar, men *starta inte installationsupplevelsen*.</span><span class="sxs-lookup"><span data-stu-id="80608-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="80608-216">Om du av misstag startar installationen måste du återställa eller konfigurera om enheten.</span><span class="sxs-lookup"><span data-stu-id="80608-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="80608-217">Sätt i USB-enheten och tryck sedan på SKIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="80608-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="80608-218">Öppna en PowerShell-prompt med administrativa rättigheter och kör sedan `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="80608-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="80608-219">Köra`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="80608-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="80608-220">Köra`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="80608-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="80608-221">Ta bort USB-enheten och stäng sedan av enheten genom att köra`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="80608-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="80608-222">Slå samman hash-data.</span><span class="sxs-lookup"><span data-stu-id="80608-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="80608-223">Slå inte på enheten du registrerar igen förrän du har registrerat dig för den.</span><span class="sxs-lookup"><span data-stu-id="80608-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="80608-224">Sammanfoga hash-data</span><span class="sxs-lookup"><span data-stu-id="80608-224">Merge hash data</span></span>

<span data-ttu-id="80608-225">Om du samlade in maskinvaruhhh-data med de manuella PowerShell- eller flash-enhetsmetoderna måste du nu ha data i CSV-filerna kombinerade till en enda fil för att slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="80608-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="80608-226">Här är ett exempel på PowerShell-skript för att göra det enkelt:</span><span class="sxs-lookup"><span data-stu-id="80608-226">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

<span data-ttu-id="80608-227">Med hash-data sammanslagna till en CSV-fil kan du nu fortsätta att [registrera enheterna](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="80608-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="80608-228">Registrera enheter</span><span class="sxs-lookup"><span data-stu-id="80608-228">Register devices</span></span>

<span data-ttu-id="80608-229">CSV-filen måste vara i ett särskilt format för registrering.</span><span class="sxs-lookup"><span data-stu-id="80608-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="80608-230">Om du själv har samlat in data i föregående steg bör filen redan vara i rätt format. Om du hämtar filen från en leverantör kan du behöva justera formatet.</span><span class="sxs-lookup"><span data-stu-id="80608-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="80608-231">För din bekvämlighet kan du ladda ner en [mall](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) för den här CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="80608-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="80608-232">Filen måste innehålla **exakt samma kolumnrubriker** som exemplet en (tillverkare, modell, etc.), men dina egna data för de andra raderna.</span><span class="sxs-lookup"><span data-stu-id="80608-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="80608-233">Om du använder mallen öppnar du den i ett textredigeringsverktyg som Anteckningar och överväg att lämna alla data enbart på rad 1, och ange bara data i raderna 2 och lägre.</span><span class="sxs-lookup"><span data-stu-id="80608-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="80608-234">Om du glömmer att ändra någon av exempeldata, kommer registreringen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="80608-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="80608-235">Registrera enheter med hjälp av adminportalen</span><span class="sxs-lookup"><span data-stu-id="80608-235">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="80608-236">Välj **Enheter** i det vänstra navigeringsfönstret i Microsoft Managed Desktop [Admin Portal.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="80608-236">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="80608-237">Välj **+ Registrera enheter;** fly-in öppnar:</span><span class="sxs-lookup"><span data-stu-id="80608-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="80608-238">[![Fly-in efter att ha valt Registrera enheter, lista enheter med kolumner för tilldelade användare, serienummer, status, senast sett datum och ålder](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="80608-238">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (Tyvärr är detta inte sant. Vi kan ta bort denna anmärkning - men lämnar det nu tills vi har en chans att prata om det.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="80608-240">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="80608-240">Follow these steps:</span></span>

1. <span data-ttu-id="80608-241">I **Filöverföring**anger du en sökväg till CSV-filen som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="80608-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="80608-242">Du kan också lägga till ett **order-ID** eller **inköps-ID** för dina egna spårningsändamål.</span><span class="sxs-lookup"><span data-stu-id="80608-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="80608-243">Det finns inga formatkrav för dessa värden.</span><span class="sxs-lookup"><span data-stu-id="80608-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="80608-244">Välj **Registrera enheter**.</span><span class="sxs-lookup"><span data-stu-id="80608-244">Select **Register devices**.</span></span> <span data-ttu-id="80608-245">Systemet lägger till enheterna i listan över enheter på **bladet Enheter**, markerade som **Registrering väntar**.</span><span class="sxs-lookup"><span data-stu-id="80608-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="80608-246">Registreringen tar vanligtvis mindre än 10 minuter, och när den lyckas visas enheten som **redo för användaren,** vilket innebär att den är klar och väntar på att en slutanvändare ska börja använda.</span><span class="sxs-lookup"><span data-stu-id="80608-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="80608-247">Du kan övervaka förloppet för enhetsregistrering på sidan **Microsoft Managed Desktop - Devices.**</span><span class="sxs-lookup"><span data-stu-id="80608-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="80608-248">Möjliga tillstånd som rapporteras där inkluderar:</span><span class="sxs-lookup"><span data-stu-id="80608-248">Possible states reported there include:</span></span>

| <span data-ttu-id="80608-249">Statligt</span><span class="sxs-lookup"><span data-stu-id="80608-249">State</span></span> | <span data-ttu-id="80608-250">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="80608-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="80608-251">Registrering väntar</span><span class="sxs-lookup"><span data-stu-id="80608-251">Registration pending</span></span> | <span data-ttu-id="80608-252">Registreringen är inte klar ännu.</span><span class="sxs-lookup"><span data-stu-id="80608-252">Registration is not done yet.</span></span> <span data-ttu-id="80608-253">Kom tillbaka senare.</span><span class="sxs-lookup"><span data-stu-id="80608-253">Check back later.</span></span> |
| <span data-ttu-id="80608-254">Registreringen misslyckades</span><span class="sxs-lookup"><span data-stu-id="80608-254">Registration failed</span></span> | <span data-ttu-id="80608-255">Det gick inte att slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="80608-255">Registration could not be completed.</span></span> <span data-ttu-id="80608-256">Mer information finns i [Registrering av felsökning av enheten.](#troubleshooting-device-registration)</span><span class="sxs-lookup"><span data-stu-id="80608-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="80608-257">Redo för användare</span><span class="sxs-lookup"><span data-stu-id="80608-257">Ready for user</span></span> | <span data-ttu-id="80608-258">Registreringen lyckades och enheten är nu klar att levereras till slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="80608-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="80608-259">Microsoft Managed Desktop guidar dem genom första gången set-up, så det finns ingen anledning för dig att göra några ytterligare förberedelser.</span><span class="sxs-lookup"><span data-stu-id="80608-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="80608-260">Aktiva</span><span class="sxs-lookup"><span data-stu-id="80608-260">Active</span></span> | <span data-ttu-id="80608-261">Enheten har levererats till slutanvändaren och de har registrerat sig hos din klient.</span><span class="sxs-lookup"><span data-stu-id="80608-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="80608-262">Detta indikerar också att de regelbundet använder enheten.</span><span class="sxs-lookup"><span data-stu-id="80608-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="80608-263">Inaktiva</span><span class="sxs-lookup"><span data-stu-id="80608-263">Inactive</span></span> | <span data-ttu-id="80608-264">Enheten har levererats till slutanvändaren och de har registrerat sig hos din klient.</span><span class="sxs-lookup"><span data-stu-id="80608-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="80608-265">De har dock inte använt enheten nyligen (under de senaste 7 dagarna).</span><span class="sxs-lookup"><span data-stu-id="80608-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="80608-266">Felsöka enhetsregistrering</span><span class="sxs-lookup"><span data-stu-id="80608-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="80608-267">Felmeddelande</span><span class="sxs-lookup"><span data-stu-id="80608-267">Error message</span></span> | <span data-ttu-id="80608-268">Information</span><span class="sxs-lookup"><span data-stu-id="80608-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="80608-269">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="80608-269">Device not found</span></span> | <span data-ttu-id="80608-270">Vi kunde inte registrera den här enheten eftersom vi inte kunde hitta en matchning för den angivna tillverkaren, modellen eller serienumret.</span><span class="sxs-lookup"><span data-stu-id="80608-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="80608-271">Bekräfta dessa värden med din enhetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="80608-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="80608-272">Maskinvaruh hash är ogiltigt</span><span class="sxs-lookup"><span data-stu-id="80608-272">Hardware hash not valid</span></span> | <span data-ttu-id="80608-273">Maskinvaruhhingen som du angav för den här enheten har inte formaterats korrekt.</span><span class="sxs-lookup"><span data-stu-id="80608-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="80608-274">Dubbelkolla maskinvaruhhhen och skicka sedan in den igen.</span><span class="sxs-lookup"><span data-stu-id="80608-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="80608-275">Enheten har redan registrerats</span><span class="sxs-lookup"><span data-stu-id="80608-275">Device already registered</span></span> | <span data-ttu-id="80608-276">Den här enheten är redan registrerad i din organisation.</span><span class="sxs-lookup"><span data-stu-id="80608-276">This device is already registered to your organization.</span></span> <span data-ttu-id="80608-277">Inga ytterligare åtgärder krävs.</span><span class="sxs-lookup"><span data-stu-id="80608-277">No further action required.</span></span> |
| <span data-ttu-id="80608-278">Enhet som påstås av en annan organisation</span><span class="sxs-lookup"><span data-stu-id="80608-278">Device claimed by another organization</span></span> | <span data-ttu-id="80608-279">Den här enheten har redan hävdats av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="80608-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="80608-280">Kontrollera med din enhetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="80608-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="80608-281">Oväntat fel</span><span class="sxs-lookup"><span data-stu-id="80608-281">Unexpected error</span></span> | <span data-ttu-id="80608-282">Det gick inte att bearbeta din begäran automatiskt.</span><span class="sxs-lookup"><span data-stu-id="80608-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="80608-283">Kontakta supporten och ange ID:et för begäran:<requestId></span><span class="sxs-lookup"><span data-stu-id="80608-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="80608-284">Kontrollera bilden</span><span class="sxs-lookup"><span data-stu-id="80608-284">Check the image</span></span>

<span data-ttu-id="80608-285">Om enheten kommer från en Microsoft Managed Desktop-partnerleverantör ska avbildningen vara korrekt.</span><span class="sxs-lookup"><span data-stu-id="80608-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="80608-286">Du är också välkommen att använda bilden på egen hand om du föredrar.</span><span class="sxs-lookup"><span data-stu-id="80608-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="80608-287">För att komma igång kontaktar du den Microsoft-representant du arbetar med och de ger dig plats och steg för att tillämpa avbildningen.</span><span class="sxs-lookup"><span data-stu-id="80608-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="80608-288">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="80608-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80608-289">Innan du lämnar över enheten till användaren ska du se till att du har skaffat och tillämpat [lämpliga licenser](../get-ready/prerequisites.md) för den användaren.</span><span class="sxs-lookup"><span data-stu-id="80608-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="80608-290">Om alla licenser tillämpas kan du [göra användarna redo att använda enheter](get-started-devices.md)och sedan kan användaren starta enheten och gå vidare genom installationen av Windows.</span><span class="sxs-lookup"><span data-stu-id="80608-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









