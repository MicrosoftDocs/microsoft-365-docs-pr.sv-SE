---
title: Kom igång med Microsoft 365 lokal skanner för dataförlustskydd (förhandsversion)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Använd Microsoft 365 lokal skanner för dataförlustskydd
ms.openlocfilehash: 0390ac48b351b30b75109a3e3a5d18c80847c9d2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289205"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="ce393-103">Kom igång med lokal skanner för dataförlustskydd (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="ce393-103">Get started with the data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="ce393-104">Den här artikeln beskriver förutsättningar och konfiguration för Microsoft 365 lokal skanner för dataförlustskydd.</span><span class="sxs-lookup"><span data-stu-id="ce393-104">This article walks you through the prerequisites and configuration for the Microsoft 365 data loss prevention on-premises scanner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ce393-105">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="ce393-105">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="ce393-106">Licensiering av SKU/prenumerationer</span><span class="sxs-lookup"><span data-stu-id="ce393-106">SKU/subscriptions licensing</span></span>

<span data-ttu-id="ce393-107">Innan du börjar med den lokala DLP-skannern måste du bekräfta din [Microsoft 365-prenumeration](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) och eventuella tillägg.</span><span class="sxs-lookup"><span data-stu-id="ce393-107">Before you get started with DLP on-premises scanner, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="ce393-108">Om du vill delta i förhandsversionen av administratörskontot som konfigurerar DLP-regler, måste någon av följande licenser tilldelas:</span><span class="sxs-lookup"><span data-stu-id="ce393-108">To participate in the preview the admin account that sets up the DLP rules must be assigned one of the following licenses:</span></span>

- <span data-ttu-id="ce393-109">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ce393-109">Microsoft 365 E5</span></span>
- <span data-ttu-id="ce393-110">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="ce393-110">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="ce393-111">Microsoft 365 E5 – Informationsskydd och styrning</span><span class="sxs-lookup"><span data-stu-id="ce393-111">Microsoft 365 E5 Information Protection & Governance</span></span> 


<span data-ttu-id="ce393-112">Fullständig licensinformation finns i: [Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="ce393-112">For full licensing details see: [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span></span>

### <a name="permissions"></a><span data-ttu-id="ce393-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="ce393-113">Permissions</span></span>


<span data-ttu-id="ce393-114">Data från den lokala DLP-skannern kan visas i [aktivitetsutforskaren](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="ce393-114">Data from DLP on-premises scanner can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="ce393-115">Det finns fyra roller som ger behörighet till aktivitetsutforskaren och det konto som du använder för att komma åt datan måste vara medlem i någon av dem.</span><span class="sxs-lookup"><span data-stu-id="ce393-115">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="ce393-116">Global administratör</span><span class="sxs-lookup"><span data-stu-id="ce393-116">Global administrator</span></span>
- <span data-ttu-id="ce393-117">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="ce393-117">Compliance administrator</span></span>
- <span data-ttu-id="ce393-118">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="ce393-118">Security administrator</span></span>
- <span data-ttu-id="ce393-119">Administratör för efterlevnadsdata</span><span class="sxs-lookup"><span data-stu-id="ce393-119">Compliance data administrator</span></span>

### <a name="dlp-on-premises-scanner-prerequisites"></a><span data-ttu-id="ce393-120">Förutsättningar för lokal DLP-skanner</span><span class="sxs-lookup"><span data-stu-id="ce393-120">DLP on-premises scanner prerequisites</span></span>

- <span data-ttu-id="ce393-p103">Azure Information Protection-skannern implementerar DLP-principsmatchning och -principåtgärder. Skannern installeras som en del av AIP-klienten. Installationen måste därför uppfylla alla krav för AIP, AIP-klienten och AIP-skannern för enhetliga etiketter.</span><span class="sxs-lookup"><span data-stu-id="ce393-p103">The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement. The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.</span></span>
- <span data-ttu-id="ce393-123">Distribuera AIP-klienten och skannern.</span><span class="sxs-lookup"><span data-stu-id="ce393-123">Deploy the AIP  client and scanner.</span></span> <span data-ttu-id="ce393-124">Mer information finns i [Installera AIP-klienten för enhetliga etiketter](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) och []. Se [Konfigurera och installera Azure Information Protection-skannern för enhetliga etiketter](/azure/information-protection/deploy-aip-scanner-configure-install).</span><span class="sxs-lookup"><span data-stu-id="ce393-124">For more information [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install).</span></span>
- <span data-ttu-id="ce393-125">Minst en etikett och princip måste ha publicerats i klientorganisationen, även om alla identifieringsregler endast baseras på typerna av känslig information.</span><span class="sxs-lookup"><span data-stu-id="ce393-125">There must be at least one label and policy published in the tenant, even if all your detection rules are based on sensitive information types only.</span></span>

## <a name="deploy-the-dlp-on-premises-scanner"></a><span data-ttu-id="ce393-126">Distribuera den lokala DLP-skannern</span><span class="sxs-lookup"><span data-stu-id="ce393-126">Deploy the DLP on-premises scanner</span></span>

1. <span data-ttu-id="ce393-127">Följ metoderna i [Installera AIP-klienten för enhetliga etiketter](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span><span class="sxs-lookup"><span data-stu-id="ce393-127">Follow the procedures in [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> 
2. <span data-ttu-id="ce393-128">Följ metoderna i [Konfigurera och installera Azure Information Protection-skannern för enhetliga etiketter](/azure/information-protection/deploy-aip-scanner-configure-install) för att slutföra skannerinstallationen.</span><span class="sxs-lookup"><span data-stu-id="ce393-128">Follow the procedures in [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install) to complete the scanner installation.</span></span>
    1. <span data-ttu-id="ce393-129">Konfigurationen av nätverksidentifieringsjobb är ett valfritt steg.</span><span class="sxs-lookup"><span data-stu-id="ce393-129">Network discovery jobs configuration is an optional step.</span></span> <span data-ttu-id="ce393-130">Du kan hoppa över det och definiera specifika lagringsplatser som ska genomsökas i innehållssökningsjobbet.</span><span class="sxs-lookup"><span data-stu-id="ce393-130">You can skip it and define specific repositories to be scanned in your content scan job.</span></span>
    2. <span data-ttu-id="ce393-131">Du måste skapa ett innehållssökningsjobb och ange de lagringsplatser som är värd för filerna som ska utvärderas av DLP-motorn.</span><span class="sxs-lookup"><span data-stu-id="ce393-131">You must create content scan job and specify the repositories that host files that need to be evaluated by the DLP engine.</span></span>
    3. <span data-ttu-id="ce393-132">Aktivera DLP-regler i det skapade innehållssökningsjobbet och ange alternativet **Tillämpa** som **Av**, såvida du inte vill gå direkt till DLP-tillämpningsfasen.</span><span class="sxs-lookup"><span data-stu-id="ce393-132">Enable DLP rules in the created Content scan job, and set the **Enforce** option to **Off**, unless you want to proceed directly to the DLP enforcement stage.</span></span>
3. <span data-ttu-id="ce393-p106">Bekräfta att innehållssökningsjobbet har tilldelats till rätt kluster. Om du ännu inte har skapat något innehållssökningsjobb, skapar du ett nytt och tilldelar det till det kluster som innehåller skannernoderna som kör den allmänt tillgängliga förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="ce393-p106">Verify that you content scan job is assigned to the right cluster. If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes that run the public preview version.</span></span>

4. <span data-ttu-id="ce393-135">Anslut till [Azure Information Protection-tillägget i Azure-portalen](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) och lägg till dina lagringsplatser i det innehållssökningsjobb som ska utföra genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="ce393-135">Connect to the [Azure Information Protection extension in Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) and add your repositories to the content scan job that will perform the scan.</span></span>

5. <span data-ttu-id="ce393-136">Kör genomsökningen på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="ce393-136">Do one of the following to run your scan:</span></span>
    1. <span data-ttu-id="ce393-137">ange skannerschemat</span><span class="sxs-lookup"><span data-stu-id="ce393-137">set the scanner schedule</span></span>
    1. <span data-ttu-id="ce393-138">använd det manuella alternativet **Genomsök nu** i portalen</span><span class="sxs-lookup"><span data-stu-id="ce393-138">use the manual **Scan Now** option in the portal</span></span>
    1. <span data-ttu-id="ce393-139">eller kör PowerShell-cmdleten **Start-AIPScan**</span><span class="sxs-lookup"><span data-stu-id="ce393-139">or run **Start-AIPScan** PowerShell cmdlet</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ce393-140">Kom ihåg att skannern kör en deltagenomsökning av lagringsplatsen som standard och att filer som redan genomsökts i föregående genomsökningscykel hoppas över, om inte filen har ändrats eller om du har initierat en fullständig ny genomsökning.</span><span class="sxs-lookup"><span data-stu-id="ce393-140">Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan.</span></span> <span data-ttu-id="ce393-141">En fullständig ny genomsökning kan initieras med alternativet **Genomsök alla filer på nytt** i användargränssnittet eller genom att köra **Start-AIPScan-Reset**.</span><span class="sxs-lookup"><span data-stu-id="ce393-141">Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.</span></span>

6.  <span data-ttu-id="ce393-142">Öppna [sidan Dataförlustskydd](https://compliance.microsoft.com/datalossprevention?viewid=policies) i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="ce393-142">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center.</span></span>

7. <span data-ttu-id="ce393-143">Välj **Skapa princip** och skapa ett test av DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="ce393-143">Choose **Create policy** and create a test DLP policy.</span></span> <span data-ttu-id="ce393-144">Se [Skapa en DLP-princip från en mall](create-a-dlp-policy-from-a-template.md) om du behöver hjälp med att skapa en princip.</span><span class="sxs-lookup"><span data-stu-id="ce393-144">See [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md) if you need help creating a policy.</span></span> <span data-ttu-id="ce393-145">Kör den som ett test tills du känner dig bekväm med funktionen.</span><span class="sxs-lookup"><span data-stu-id="ce393-145">Be sure to run it in test until you are comfortable with this feature.</span></span> <span data-ttu-id="ce393-146">Använd följande parametrar till principen:</span><span class="sxs-lookup"><span data-stu-id="ce393-146">Use these parameters for your policy:</span></span>
    1. <span data-ttu-id="ce393-147">Begränsa den lokala DLP-skannerregeln till specifika platser om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ce393-147">Scope the DLP on-premises scanner rule to specific locations if needed.</span></span> <span data-ttu-id="ce393-148">Om du anger **Platser** till **Alla**, kommer alla filer som genomsöks av skannern att omfattas av matchningen och tillämpningen av DLP-regeln.</span><span class="sxs-lookup"><span data-stu-id="ce393-148">If you scope **locations** to **All**, all files scanned by the scanner will be subject to the DLP rule matching and enforcement.</span></span>
    1. <span data-ttu-id="ce393-149">När du anger platserna kan du antingen använda en undantagslista eller en inkluderingslista.</span><span class="sxs-lookup"><span data-stu-id="ce393-149">When specifying the locations, you can use either exclusion or inclusion list.</span></span> <span data-ttu-id="ce393-150">I den allmänt tillgängliga förhandsversionen kan du inte ange båda.</span><span class="sxs-lookup"><span data-stu-id="ce393-150">During public preview you cannot set both of them.</span></span> <span data-ttu-id="ce393-151">Du kan antingen definiera att regeln endast är relevant för sökvägar som matchar ett av mönstren som anges i inkluderingslistan, eller alla filer förutom de filer som matchar mönstret i inkluderingslistan.</span><span class="sxs-lookup"><span data-stu-id="ce393-151">You can either define that the rule is relevant only to paths matching one of the patterns listed in inclusion list or, all files, except the files matching the pattern listed in inclusion list.</span></span> <span data-ttu-id="ce393-152">Inga lokala sökvägar stöds.</span><span class="sxs-lookup"><span data-stu-id="ce393-152">No local paths are supported.</span></span> <span data-ttu-id="ce393-153">Här är några exempel på giltiga sökvägar:</span><span class="sxs-lookup"><span data-stu-id="ce393-153">Here are some examples of valid paths:</span></span>
      - <span data-ttu-id="ce393-154">\\\server\share</span><span class="sxs-lookup"><span data-stu-id="ce393-154">\\\server\share</span></span>
      - <span data-ttu-id="ce393-155">\\\server\share\folder1\subfolderabc</span><span class="sxs-lookup"><span data-stu-id="ce393-155">\\\server\share\folder1\subfolderabc</span></span>
      - <span data-ttu-id="ce393-156">\*\\folder1</span><span class="sxs-lookup"><span data-stu-id="ce393-156">\*\\folder1</span></span>
      - <span data-ttu-id="ce393-157">\*secret\*.docx</span><span class="sxs-lookup"><span data-stu-id="ce393-157">\*secret\*.docx</span></span>
      - <span data-ttu-id="ce393-158">\*secret\*.\*</span><span class="sxs-lookup"><span data-stu-id="ce393-158">\*secret\*.\*</span></span>
      - <span data-ttu-id="ce393-159"> https:// sp2010.local/sites/HR</span><span class="sxs-lookup"><span data-stu-id="ce393-159">https:// sp2010.local/sites/HR</span></span>
      - <span data-ttu-id="ce393-160"> https://\*/HR</span><span class="sxs-lookup"><span data-stu-id="ce393-160">https://\*/HR</span></span> 
    3. <span data-ttu-id="ce393-161">Här är några exempel på otillåtna värden:</span><span class="sxs-lookup"><span data-stu-id="ce393-161">Here are some examples of unacceptable values use:</span></span>
      - \*
      - <span data-ttu-id="ce393-162">\*\\a</span><span class="sxs-lookup"><span data-stu-id="ce393-162">\*\\a</span></span>
      - <span data-ttu-id="ce393-163">Aaa</span><span class="sxs-lookup"><span data-stu-id="ce393-163">Aaa</span></span>
      - <span data-ttu-id="ce393-164">c:</span><span class="sxs-lookup"><span data-stu-id="ce393-164">c:</span></span>\
      - <span data-ttu-id="ce393-165">C:\test</span><span class="sxs-lookup"><span data-stu-id="ce393-165">C:\test</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce393-166">Undantagslistan har företräde framför inkluderingslistan.</span><span class="sxs-lookup"><span data-stu-id="ce393-166">The exclusion list takes precedence over the inclusions list.</span></span>

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="ce393-167">Visa lokala DLP-skanneraviseringar i instrumentpanelen för hantering av DLP-aviseringar</span><span class="sxs-lookup"><span data-stu-id="ce393-167">Viewing DLP on-premises scanner alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="ce393-168">Öppna [sidan Dataförlustskydd](https://compliance.microsoft.com/datalossprevention?viewid=policies) i Microsoft 365 Efterlevnadscenter och välj **Varningar**.</span><span class="sxs-lookup"><span data-stu-id="ce393-168">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center and select **Alerts**.</span></span>

2. <span data-ttu-id="ce393-169">Se procedurerna i [Konfigurera och visa aviseringar för dina DLP-principer](dlp-configure-view-alerts-policies.md) om du vill se aviseringarna för dina slutpunkts-DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="ce393-169">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a><span data-ttu-id="ce393-170">Visa den lokala DLP-skannern i aktivitetsutforskaren och granskningsloggen</span><span class="sxs-lookup"><span data-stu-id="ce393-170">Viewing DLP on-premises scanner in activity explorer and audit log</span></span>

> [!NOTE]
> <span data-ttu-id="ce393-171">Granskning måste vara aktiverad i den lokala skannern.</span><span class="sxs-lookup"><span data-stu-id="ce393-171">The on-premises scanner requires that auditing be enabled.</span></span> <span data-ttu-id="ce393-172">I Microsoft 365 är granskning aktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="ce393-172">In Microsoft 365 auditing is enabled by default.</span></span>

1. <span data-ttu-id="ce393-173">Öppna [sidan Dataklassificering](https://compliance.microsoft.com/dataclassification?viewid=overview) för din domän i Microsoft 365 Efterlevnadscenter och välj aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="ce393-173">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and select Activity explorer.</span></span>

2. <span data-ttu-id="ce393-174">Se procedurerna i [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md) för att komma åt och filtrera alla data för dina lokala skannerplatser.</span><span class="sxs-lookup"><span data-stu-id="ce393-174">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your on-premises scanner locations.</span></span>

3. <span data-ttu-id="ce393-175">Öppna [Granskningslogg i efterlevnadscentret](https://security.microsoft.com/auditlogsearch).</span><span class="sxs-lookup"><span data-stu-id="ce393-175">Open the [Audit log in the Compliance center](https://security.microsoft.com/auditlogsearch).</span></span> <span data-ttu-id="ce393-176">I den allmänt tillgängliga förhandsversionen är DLP-regelmatchningar tillgängliga i granskningsloggens användargränssnitt eller kan nås av [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) i PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce393-176">During the public preview the DLP rule matches are available in Audit log UI or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell</span></span> 


## <a name="next-steps"></a><span data-ttu-id="ce393-177">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ce393-177">Next steps</span></span>
<span data-ttu-id="ce393-178">Nu när du har distribuerat en testprincip för lokala DLP-platser och kan se aktivitetsdata i aktivitetsutforskaren, kan du gå vidare till nästa steg där du skapar DLP-principer som skyddar dina känsliga objekt.</span><span class="sxs-lookup"><span data-stu-id="ce393-178">Now that you have deployed a test policy for DLP on-premises locations and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="ce393-179">Använda DLP lokalt (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="ce393-179">Using DLP on-premises (preview)</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="ce393-180">Se även</span><span class="sxs-lookup"><span data-stu-id="ce393-180">See also</span></span>

- [<span data-ttu-id="ce393-181">Mer information om lokal DLP-skanner (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="ce393-181">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="ce393-182">Använda lokal DLP-skanner (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="ce393-182">Use DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="ce393-183">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="ce393-183">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="ce393-184">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="ce393-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="ce393-185">Kom igång med aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="ce393-185">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="ce393-186">Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="ce393-186">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)