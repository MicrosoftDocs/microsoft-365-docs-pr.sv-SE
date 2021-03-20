---
title: Skapa DNS-poster för Microsoft med Windows-baserad DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster hos Windows-baserad DNS för Microsoft.
ms.openlocfilehash: 9e5e42f847e740571944ea3db205282ec9a7a0e6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916052"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a><span data-ttu-id="f2d84-103">Skapa DNS-poster för Microsoft med Windows-baserad DNS</span><span class="sxs-lookup"><span data-stu-id="f2d84-103">Create DNS records for Microsoft using Windows-based DNS</span></span>

 <span data-ttu-id="f2d84-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="f2d84-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="f2d84-105">Om du är värd för dina egna DNS-poster med hjälp av Windows-baserad DNS följer du anvisningarna i den här artikeln för att konfigurera posterna för e-post, Skype för företag - Online och så vidare.</span><span class="sxs-lookup"><span data-stu-id="f2d84-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f2d84-106">För att komma igång måste du hitta [dina DNS-poster i Windows-baserad DNS](#find-your-dns-records-in-windows-based-dns) så att du kan uppdatera dem.</span><span class="sxs-lookup"><span data-stu-id="f2d84-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="f2d84-107">Om du planerar att synkronisera din lokala Active Directory med Microsoft kan du även gå till [Icke-dirigerbar e-postadress](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)som används som UPN i din lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f2d84-107">Also, if you're planning to synchronize your on-premises Active Directory with Microsoft, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="f2d84-108">Problem med e-postflöde eller andra problem när du har lagt till DNS-poster, se [Felsöka problem när du har ändrat domännamn eller DNS-poster.](../get-help-with-domains/find-and-fix-issues.md)</span><span class="sxs-lookup"><span data-stu-id="f2d84-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="f2d84-109">Hitta dina DNS-poster i Windows-baserad DNS</span><span class="sxs-lookup"><span data-stu-id="f2d84-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="f2d84-110"><a name="BKMK_find_your_dns_1"></a> Gå till sidan som innehåller DNS-posterna för din domän.</span><span class="sxs-lookup"><span data-stu-id="f2d84-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="f2d84-111">Om du arbetar i Windows Server 2008 går du till **Starta**  >  **kör.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="f2d84-112">Om du arbetar i Windows Server 2012 trycker du på Windows-tangenten och **r.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="f2d84-113">Skriv **dnsmgmnt.msc** och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="f2d84-114">Expandera Zoner för **\<DNS server name\> \> framåtuppslag i DNS-hanteraren.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="f2d84-115">Välj din domän.</span><span class="sxs-lookup"><span data-stu-id="f2d84-115">Select your domain.</span></span> <span data-ttu-id="f2d84-116">Nu är du redo att skapa DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="f2d84-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="f2d84-117">Lägga till MX-post</span><span class="sxs-lookup"><span data-stu-id="f2d84-117">Add MX record</span></span>
<span data-ttu-id="f2d84-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f2d84-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="f2d84-119">Lägg till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2d84-119">Add an MX record so email for your domain will come to Microsoft.</span></span>
- <span data-ttu-id="f2d84-120">MX-posten du lägger till innehåller  ett värde (värdet Pekar på adress) som ser ut ungefär så här: .mail.protection.outlook.com, där är ett värde som \<MX token\> \<MX token\> MSxxxxxxx.</span><span class="sxs-lookup"><span data-stu-id="f2d84-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="f2d84-121">Kopiera värdet som visas under Pekar på adress från MX-raden i avsnittet Exchange Online på sidan Add DNS records i Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2d84-121">From the MX row in the Exchange Online section of the Add DNS records page in Microsoft, copy the value listed under Points to address.</span></span> <span data-ttu-id="f2d84-122">Du ska använda det här värdet i den post som du skapar i den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="f2d84-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="f2d84-123">Gå till **Action** Mail Exchanger (MX) på sidan  >  **DNS-hanteraren för domänen.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="f2d84-124">Information om hur du hittar den här sidan för domänen finns i [Hitta dina DNS-poster i Windows-baserad DNS.](#find-your-dns-records-in-windows-based-dns)</span><span class="sxs-lookup"><span data-stu-id="f2d84-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="f2d84-125">I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:</span><span class="sxs-lookup"><span data-stu-id="f2d84-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="f2d84-126">Värdnamn: </span><span class="sxs-lookup"><span data-stu-id="f2d84-126">Host Name:</span></span> 
    - <span data-ttu-id="f2d84-127">@Address: Klistra in värdet Pekar på-adress som du just kopierade från Microsoft här.</span><span class="sxs-lookup"><span data-stu-id="f2d84-127">@Address: Paste the Points to address  value that you just copied from Microsoft here.</span></span>  
    - <span data-ttu-id="f2d84-128">Pref:</span><span class="sxs-lookup"><span data-stu-id="f2d84-128">Pref:</span></span> 
- <span data-ttu-id="f2d84-129">Välj **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="f2d84-130">Ta bort eventuella gamla MX-poster.</span><span class="sxs-lookup"><span data-stu-id="f2d84-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="f2d84-131">Om du har några gamla MX-poster för den här domänen som dirigerar e-post till någon annan plats markerar du kryssrutan bredvid varje gammal post och väljer sedan Ta **bort**  >  **OK.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="f2d84-132">Lägga till CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="f2d84-132">Add CNAME records</span></span>
<span data-ttu-id="f2d84-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f2d84-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="f2d84-134">Lägg till de CNAME-poster som krävs för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2d84-134">Add the CNAME records that are required for Microsoft.</span></span> <span data-ttu-id="f2d84-135">Om det finns ytterligare CNAME-poster i Microsoft lägger du till dem genom att följa samma allmänna anvisningar som visas här.</span><span class="sxs-lookup"><span data-stu-id="f2d84-135">If additional CNAME records are listed in Microsoft, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f2d84-136">Om du har MDM (Mobile Device Management) för Microsoft måste du skapa ytterligare två CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="f2d84-136">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="f2d84-137">Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f2d84-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="f2d84-138">(Om du inte har MDM kan du hoppa över det här steget.)</span><span class="sxs-lookup"><span data-stu-id="f2d84-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="f2d84-139">Gå till Åtgärd   >  **CNAME (CNAME) på sidan DNS-hanteraren för domänen.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="f2d84-140">I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:</span><span class="sxs-lookup"><span data-stu-id="f2d84-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="f2d84-141">Värdnamn: autodiscover</span><span class="sxs-lookup"><span data-stu-id="f2d84-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="f2d84-142">Typ:</span><span class="sxs-lookup"><span data-stu-id="f2d84-142">Type:</span></span> 
    - <span data-ttu-id="f2d84-143">CNAMEAddress: autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f2d84-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="f2d84-144">Välj **O** K.</span><span class="sxs-lookup"><span data-stu-id="f2d84-144">Select **O** K.</span></span>

<span data-ttu-id="f2d84-145">Lägga till SIP CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="f2d84-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="f2d84-146">Gå till Åtgärd  \> **CNAME (CNAME) på sidan DNS-hanteraren för domänen.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="f2d84-147">I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:</span><span class="sxs-lookup"><span data-stu-id="f2d84-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="f2d84-148">Värdnamn: sip</span><span class="sxs-lookup"><span data-stu-id="f2d84-148">Host Name: sip</span></span>
    - <span data-ttu-id="f2d84-149">Skriv: CNAME</span><span class="sxs-lookup"><span data-stu-id="f2d84-149">Type: CNAME</span></span>
    - <span data-ttu-id="f2d84-150">Adress: sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f2d84-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="f2d84-151">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-151">Select **OK**.</span></span>

<span data-ttu-id="f2d84-152">Lägga till Autodiscover CNAME-posten för Skype för företag - Online.</span><span class="sxs-lookup"><span data-stu-id="f2d84-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="f2d84-153">Gå till Åtgärd  \> **CNAME (CNAME) på sidan DNS-hanteraren för domänen.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="f2d84-154">I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:</span><span class="sxs-lookup"><span data-stu-id="f2d84-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="f2d84-155">Värdnamn: lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f2d84-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="f2d84-156">Skriv: CNAME</span><span class="sxs-lookup"><span data-stu-id="f2d84-156">Type: CNAME</span></span>
    - <span data-ttu-id="f2d84-157">Adress: webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f2d84-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="f2d84-158">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a><span data-ttu-id="f2d84-159">Lägga till två CNAME-poster för MDM (Mobile Device Management) för Microsoft</span><span class="sxs-lookup"><span data-stu-id="f2d84-159">Add two CNAME records for Mobile Device Management (MDM) for Microsoft</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2d84-160">Om du har MDM (Mobile Device Management) för Microsoft måste du skapa ytterligare två CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="f2d84-160">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="f2d84-161">Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f2d84-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="f2d84-162">>(Om du inte har MDM kan du hoppa över det här steget.)</span><span class="sxs-lookup"><span data-stu-id="f2d84-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="f2d84-163">Lägga till MDM Enterpriseregistration CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="f2d84-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="f2d84-164">Gå till Åtgärd  \> **CNAME (CNAME) på sidan DNS-hanteraren för domänen.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="f2d84-165">I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:</span><span class="sxs-lookup"><span data-stu-id="f2d84-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="f2d84-166">Värdnamn: enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f2d84-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="f2d84-167">Skriv: CNAME</span><span class="sxs-lookup"><span data-stu-id="f2d84-167">Type: CNAME</span></span>
- <span data-ttu-id="f2d84-168">Adress: enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f2d84-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="f2d84-169">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-169">Select **OK**.</span></span> 

<span data-ttu-id="f2d84-170">Lägga till MDM Enterpriseenrollment CNAME-posten.</span><span class="sxs-lookup"><span data-stu-id="f2d84-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="f2d84-171">Gå till Åtgärd  \> **CNAME (CNAME) på sidan DNS-hanteraren för domänen.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="f2d84-172">I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:</span><span class="sxs-lookup"><span data-stu-id="f2d84-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="f2d84-173">Värdnamn: enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f2d84-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="f2d84-174">Skriv: CNAME</span><span class="sxs-lookup"><span data-stu-id="f2d84-174">Type: CNAME</span></span>
    - <span data-ttu-id="f2d84-175">Adress: enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f2d84-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="f2d84-176">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f2d84-177">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="f2d84-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f2d84-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f2d84-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2d84-179">Du kan inte ha fler än en TXT-post för SPF för en domän.</span><span class="sxs-lookup"><span data-stu-id="f2d84-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f2d84-180">Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering.</span><span class="sxs-lookup"><span data-stu-id="f2d84-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f2d84-181">Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2d84-181">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="f2d84-182">Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten så att du har  *en*  enda SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="f2d84-182">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="f2d84-183">Lägg till SPF TXT-posten för din domän för att förhindra skräp i e-posten.</span><span class="sxs-lookup"><span data-stu-id="f2d84-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="f2d84-p111">Du kanske redan har andra strängar i TXT-värdet för den här posten (t.ex. strängar för reklamutskick) och det är ok. Låt dessa strängar vara kvar och lägg till den här. Sätt dubbla citattecken runt varje sträng för att separera dem.</span><span class="sxs-lookup"><span data-stu-id="f2d84-p111">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="f2d84-186">På sidan DNS-hanteraren för din domän går du till **Action** \> **Text (TXT)**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="f2d84-187">I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden.</span><span class="sxs-lookup"><span data-stu-id="f2d84-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="f2d84-188">I vissa versioner av Windows DNS-hanteraren kan domänen ha ställts in så att när du skapar en txt-post blir startdomänens standardnamn den överordnade domänen.</span><span class="sxs-lookup"><span data-stu-id="f2d84-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="f2d84-189">När du lägger till en TXT-post i det här fallet ska du ange värdnamnet till tomt (inget värde) i stället för att ange det till @ eller domännamnet.</span><span class="sxs-lookup"><span data-stu-id="f2d84-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="f2d84-190">Värdtyp: @</span><span class="sxs-lookup"><span data-stu-id="f2d84-190">Host type: @</span></span>
-  <span data-ttu-id="f2d84-191">Posttyp: TXT</span><span class="sxs-lookup"><span data-stu-id="f2d84-191">Record Type: TXT</span></span>
-  <span data-ttu-id="f2d84-192">Adress: v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f2d84-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="f2d84-193">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="f2d84-194">Lägga till SRV-poster</span><span class="sxs-lookup"><span data-stu-id="f2d84-194">Add SRV records</span></span>
<span data-ttu-id="f2d84-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f2d84-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="f2d84-196">Lägg till de två SRV-posterna som krävs för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2d84-196">Add the two SRV records that are required for Microsoft.</span></span>

<span data-ttu-id="f2d84-197">Lägga till SIP SRV-posten för webbkonferens i Skype för företag - Online.</span><span class="sxs-lookup"><span data-stu-id="f2d84-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="f2d84-198">På sidan DNS-hanteraren för din domän går du till **Action** \> **Other New Records**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="f2d84-199">I fönstret **Typ av resurspost** väljer du **Tjänstplats (SRV)** och väljer sedan **Skapa post.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="f2d84-200">I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:</span><span class="sxs-lookup"><span data-stu-id="f2d84-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="f2d84-201">Tjänst: _sip</span><span class="sxs-lookup"><span data-stu-id="f2d84-201">Service: _sip</span></span>
    -  <span data-ttu-id="f2d84-202">Protokoll: _tls</span><span class="sxs-lookup"><span data-stu-id="f2d84-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="f2d84-203">Prioritet: 100</span><span class="sxs-lookup"><span data-stu-id="f2d84-203">Priority: 100</span></span>
    -  <span data-ttu-id="f2d84-204">Vikt: 1</span><span class="sxs-lookup"><span data-stu-id="f2d84-204">Weight: 1</span></span>
    -  <span data-ttu-id="f2d84-205">Port: 443</span><span class="sxs-lookup"><span data-stu-id="f2d84-205">Port: 443</span></span>
    -  <span data-ttu-id="f2d84-206">Target (Hostname): sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f2d84-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="f2d84-207">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-207">Select **OK**.</span></span> 


<span data-ttu-id="f2d84-208">Lägga till SIP SRV-posten för Skype för företag - Online-federation.</span><span class="sxs-lookup"><span data-stu-id="f2d84-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="f2d84-209">På sidan DNS-hanteraren för din domän går du till **Action** \> **Other New Records**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="f2d84-210">I fönstret **Typ av resurspost** väljer du **Tjänstplats (SRV)** och väljer sedan **Skapa post.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="f2d84-211">I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:</span><span class="sxs-lookup"><span data-stu-id="f2d84-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="f2d84-212">Tjänst: _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f2d84-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="f2d84-213">Protokoll: _tcp</span><span class="sxs-lookup"><span data-stu-id="f2d84-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="f2d84-214">Prioritet: 100</span><span class="sxs-lookup"><span data-stu-id="f2d84-214">Priority: 100</span></span>
    -  <span data-ttu-id="f2d84-215">Vikt: 1</span><span class="sxs-lookup"><span data-stu-id="f2d84-215">Weight: 1</span></span>
    -  <span data-ttu-id="f2d84-216">Port: 5061</span><span class="sxs-lookup"><span data-stu-id="f2d84-216">Port: 5061</span></span>
    -  <span data-ttu-id="f2d84-217">Target (Hostname): sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f2d84-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="f2d84-218">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="f2d84-219">Lägg till en post för att verifiera att du äger domänen, om du inte redan har gjort det</span><span class="sxs-lookup"><span data-stu-id="f2d84-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="f2d84-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f2d84-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f2d84-221">Innan du lägger till DNS-posterna för att konfigurera dina Microsoft-tjänster måste Microsoft bekräfta att du äger den domän som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="f2d84-221">Before you add the DNS records to set up your Microsoft services, Microsoft has to confirm that you own the domain you're adding.</span></span> <span data-ttu-id="f2d84-222">Det här gör du genom att lägga till en post enligt stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="f2d84-222">To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2d84-223">Den här posten används endast för att verifiera att du äger domänen, den påverkar ingenting annat.</span><span class="sxs-lookup"><span data-stu-id="f2d84-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="f2d84-224">Samla in information från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2d84-224">Gather information from Microsoft.</span></span>  <br/> 
2. <span data-ttu-id="f2d84-225">I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="f2d84-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="f2d84-226">Välj **Start setup** i **kolumnen Actions** för den domän du verifierar på sidan **Domains.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="f2d84-227">På sidan **Lägg till en domän i Microsoft** väljer du Starta steg **1.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-227">On the **Add a domain to Microsoft** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="f2d84-228">Välj **Allmänna instruktioner i listrutan** Se  anvisningar för att utföra det här steget med på sidan Bekräfta att du äger **domänen.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="f2d84-229">Kopiera värdet för Mål eller pekar på-adress i tabellen.</span><span class="sxs-lookup"><span data-stu-id="f2d84-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="f2d84-230">Du behöver det i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="f2d84-230">You'll need it for the next step.</span></span> <span data-ttu-id="f2d84-231">Vi rekommenderar att du kopierar och klistrar in det här värdet så att alla avstånd förblir korrekta.</span><span class="sxs-lookup"><span data-stu-id="f2d84-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="f2d84-232">Lägga till en TXT-post.</span><span class="sxs-lookup"><span data-stu-id="f2d84-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="f2d84-233">På sidan DNS-hanteraren för din domän går du till **Action** \> **Text (TXT)**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="f2d84-234">Välj **Redigera i dialogrutan Ny** **resurspost.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="f2d84-235">I området **För namn på** anpassade värdar i dialogrutan **Ny** resurspost kontrollerar du att fälten är inställda på exakt följande värden.</span><span class="sxs-lookup"><span data-stu-id="f2d84-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="f2d84-236">I vissa versioner av Windows DNS-hanteraren kan domänen ha ställts in så att när du skapar en txt-post blir startdomänens standardnamn den överordnade domänen.</span><span class="sxs-lookup"><span data-stu-id="f2d84-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="f2d84-237">När du lägger till en TXT-post i det här fallet ska du ange värdnamnet till tomt (inget värde) i stället för att ange det till @ eller domännamnet.</span><span class="sxs-lookup"><span data-stu-id="f2d84-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="f2d84-238">Värdnamn: @</span><span class="sxs-lookup"><span data-stu-id="f2d84-238">Host Name: @</span></span>
- <span data-ttu-id="f2d84-239">Typ: TXT</span><span class="sxs-lookup"><span data-stu-id="f2d84-239">Type: TXT</span></span>
- <span data-ttu-id="f2d84-240">Adress: Klistra in värdet för Mål eller pekar på-adress som du just kopierade från Microsoft här.</span><span class="sxs-lookup"><span data-stu-id="f2d84-240">Address: Paste the Destination or Points to Address value that you just copied from Microsoft here.</span></span>  
- <span data-ttu-id="f2d84-241">Välj **OK**  >  **Klar**.</span><span class="sxs-lookup"><span data-stu-id="f2d84-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="f2d84-242">Verifiera din domän i Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2d84-242">Verify your domain in Microsoft.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="f2d84-243">Vänta cirka 15 minuter innan du gör detta så att den post som du nyss skapade kan uppdateras på Internet.</span><span class="sxs-lookup"><span data-stu-id="f2d84-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="f2d84-244">Gå tillbaka till Microsoft och följ stegen nedan för att begära en verifieringskontroll.</span><span class="sxs-lookup"><span data-stu-id="f2d84-244">Go back to Microsoft and follow the steps below to request a verification check.</span></span> <span data-ttu-id="f2d84-245">Kontrollen används för TXT-posten du lade till i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="f2d84-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="f2d84-246">När den hittar rätt TXT-post är domänen verifierad.</span><span class="sxs-lookup"><span data-stu-id="f2d84-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="f2d84-247">I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Konfigurera</a> domäner.</span><span class="sxs-lookup"><span data-stu-id="f2d84-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="f2d84-248">På sidan **Domains,** i kolumnen **Action** för den domän du verifierar, väljer du **Start setup.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="f2d84-249">På sidan **Bekräfta att du äger domänen** väljer du **klar, verifiera** nu och väljer sedan Slutför i **bekräftelsedialogrutan.**</span><span class="sxs-lookup"><span data-stu-id="f2d84-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="f2d84-p117">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f2d84-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="f2d84-253">Icke-dirigerbar e-postadress som används som UPN i din lokala Active Directory</span><span class="sxs-lookup"><span data-stu-id="f2d84-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="f2d84-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="f2d84-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="f2d84-255">Om du planerar att synkronisera din lokala Active Directory med Microsoft bör du se till att UPN-suffixet i Active Directory är ett giltigt domänsuffix och inte ett domänsuffix som inte stöds, till exempel @contoso.local.</span><span class="sxs-lookup"><span data-stu-id="f2d84-255">If you're planning to synchronize your on-premises Active Directory with Microsoft, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="f2d84-256">Om du behöver ändra ditt UPN-suffix kan du gå [till Så här förbereder du en icke-dirigerbar domän för katalogsynkronisering.](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="f2d84-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f2d84-p119">Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f2d84-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
