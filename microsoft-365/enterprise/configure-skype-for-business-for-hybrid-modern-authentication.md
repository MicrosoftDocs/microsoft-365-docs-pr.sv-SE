---
title: Konfigurera Skype för företag för lokal användning av hybrid modern
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Lär dig hur du konfigurerar Skype för företag lokalt för användning av hybrid modern autentisering (HMA) och ger dig säkrare autentisering och verifiering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695032"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="6cbb0-103">Konfigurera Skype för företag för lokal användning av hybrid modern</span><span class="sxs-lookup"><span data-stu-id="6cbb0-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="6cbb0-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6cbb0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6cbb0-105">Modern autentisering, är en metod för identitets hantering som erbjuder säkrare användar verifiering och-auktorisering, och är tillgänglig för Skype för företag-Server lokalt och Exchange Server lokalt samt för delade domän-domäner med hybrider.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>
  
 <span data-ttu-id="6cbb0-106">**Viktigt** Vill du veta mer om modern inloggningsautentisering (MA) och varför du föredrar att använda den i ditt företag eller din organisation?</span><span class="sxs-lookup"><span data-stu-id="6cbb0-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="6cbb0-107">Kontrol lera [detta dokument](hybrid-modern-auth-overview.md) för en översikt.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="6cbb0-108">Om du behöver veta vad topologierna för Skype för företag fungerar tillsammans med MA är det dokumenterat här!</span><span class="sxs-lookup"><span data-stu-id="6cbb0-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>
  
 <span data-ttu-id="6cbb0-109">**Innan vi börjar**följer jag de här villkoren:</span><span class="sxs-lookup"><span data-stu-id="6cbb0-109">**Before we begin**, I use these terms:</span></span>
  
- <span data-ttu-id="6cbb0-110">Modern (MA)</span><span class="sxs-lookup"><span data-stu-id="6cbb0-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="6cbb0-111">Hybrid modern (HMA)</span><span class="sxs-lookup"><span data-stu-id="6cbb0-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="6cbb0-112">Exchange On-premises (VALUTAKURS)</span><span class="sxs-lookup"><span data-stu-id="6cbb0-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="6cbb0-113">Exchange Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="6cbb0-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="6cbb0-114">Skype för företag – lokalt (SFB)</span><span class="sxs-lookup"><span data-stu-id="6cbb0-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="6cbb0-115">Skype för företag – Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="6cbb0-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="6cbb0-116">Om en bild i den här artikeln har ett objekt som är nedtonat eller nedtonat innebär det att elementet som visas i grått **inte** ingår i valfri konfiguration.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>
  
## <a name="read-the-summary"></a><span data-ttu-id="6cbb0-117">Läsa sammanfattningen</span><span class="sxs-lookup"><span data-stu-id="6cbb0-117">Read the summary</span></span>

<span data-ttu-id="6cbb0-118">Den här sammanfattningen delar upp processen i steg som annars skulle förloras under körningen, och det är bra för en övergripande check lista för att hålla reda på var du befinner dig.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>
  
1. <span data-ttu-id="6cbb0-119">Kontrol lera först att du uppfyller alla förutsättningar.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="6cbb0-120">Eftersom många **förutsättningar** är vanliga för både Skype för företag och Exchange kan du [läsa översikts artikeln för din check lista för krav](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="6cbb0-121">Gör det  *innan*  du följer anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="6cbb0-122">Samla in den HMA-specifika information du behöver i en fil eller i OneNote.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="6cbb0-123">Aktivera modern EXO (om den inte redan är aktive rad).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="6cbb0-124">Aktivera modern SFBO (om den inte redan är aktive rad).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="6cbb0-125">Aktivera hybrid modern inloggning för Exchange lokal.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="6cbb0-126">Aktivera hybrid modern inloggning för Skype för företag lokalt.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="6cbb0-127">De här stegen aktiverar MA för SFB, SFBO, VALUTAKURS och EXO-det vill säga alla produkter som kan delta i en HMA-konfiguration för SFB och SFBO (inklusive beroenden på polyEXO).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="6cbb0-128">Med andra ord kommer den färdiga produkten att se ut så här om användarna är hemifrån/har post lådor som har skapats i en del av hybriden (EXO + SFBO, EXO + SFB, Poly+ SFBO eller Poly+ SFB):</span><span class="sxs-lookup"><span data-stu-id="6cbb0-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>
  
![En 6-Topology-topologi med sex Skype för företag har MA på alla fyra möjliga platser.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
<span data-ttu-id="6cbb0-130">Som du ser finns det fyra olika ställen att slå på MA!</span><span class="sxs-lookup"><span data-stu-id="6cbb0-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="6cbb0-131">För att det ska fungera så bra som möjligt rekommenderar vi att du aktiverar MA på alla fyra av dessa platser.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="6cbb0-132">Om du inte kan aktivera MA på alla de här platserna, justera stegen så att endast MA visas på de platser som behövs för din miljö.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>
  
<span data-ttu-id="6cbb0-133">Se [Support för Skype för företag med ma](https://technet.microsoft.com/library/mt803262.aspx) för topologier som stöds.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-133">See the [Supportability topic for Skype for Business with MA](https://technet.microsoft.com/library/mt803262.aspx) for supported topologies.</span></span>
  
 <span data-ttu-id="6cbb0-134">**Viktigt** Kontrol lera att du har uppfyllt alla förutsättningar innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="6cbb0-135">Informationen finns i [hybrid modern verifiering och förutsättningar](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>
  
## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="6cbb0-136">Samla in alla HMA-specifika uppgifter du behöver</span><span class="sxs-lookup"><span data-stu-id="6cbb0-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="6cbb0-137">När du har dubbelt kontrollerat att du uppfyller [kraven](hybrid-modern-auth-overview.md) för att använda modern verifiering (se anvisningarna ovan), bör du skapa en fil som innehåller den information du behöver för att konfigurera HMA i stegen ovan.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="6cbb0-138">Exempel som används i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="6cbb0-138">Examples used in this article:</span></span>
  
- <span data-ttu-id="6cbb0-139">**SIP-domän**</span><span class="sxs-lookup"><span data-stu-id="6cbb0-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="6cbb0-140">Hand.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-140">Ex.</span></span> <span data-ttu-id="6cbb0-141">contoso.com (är sammanslaget med Office 365)</span><span class="sxs-lookup"><span data-stu-id="6cbb0-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="6cbb0-142">**Klient-ID**</span><span class="sxs-lookup"><span data-stu-id="6cbb0-142">**Tenant ID**</span></span>

  - <span data-ttu-id="6cbb0-143">GUID som representerar din Office 365-klient (vid inloggningen på contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="6cbb0-144">**Webb adresser för SFB 2015 CU5**</span><span class="sxs-lookup"><span data-stu-id="6cbb0-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="6cbb0-145">du behöver interna och externa webb tjänst-URL: er för alla SfB 2015-pooler distribuerade.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="6cbb0-146">För att få dessa kan du köra följande från Skype för företag Management Shell:</span><span class="sxs-lookup"><span data-stu-id="6cbb0-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="6cbb0-147">Hand.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-147">Ex.</span></span> <span data-ttu-id="6cbb0-148">Intern https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cbb0-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="6cbb0-149">Hand.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-149">Ex.</span></span> <span data-ttu-id="6cbb0-150">5,25 https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cbb0-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="6cbb0-151">Om du använder en standard server för Edition är den interna URL-adressen tom.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="6cbb0-152">I det här fallet ska du använda pool-FQDN för den interna URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-152">In this case, use the pool fqdn for the internal URL.</span></span>
  
## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="6cbb0-153">Aktivera modern EXO</span><span class="sxs-lookup"><span data-stu-id="6cbb0-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="6cbb0-154">Följ anvisningarna här: [Exchange Online: så här aktiverar du en klient organisation för modern verifikation.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="6cbb0-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>
  
## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="6cbb0-155">Aktivera modern SFBO</span><span class="sxs-lookup"><span data-stu-id="6cbb0-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="6cbb0-156">Följ anvisningarna här: [Skype för företag – online: aktivera din klient organisation för modern verifikation](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="6cbb0-157">Aktivera hybrid modern inloggning för Exchange lokalt</span><span class="sxs-lookup"><span data-stu-id="6cbb0-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="6cbb0-158">Följ anvisningarna här: [så här konfigurerar du Exchange Server lokalt för användning av hybrid modern](configure-exchange-server-for-hybrid-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="6cbb0-159">Aktivera hybrid modern inloggningsautentisering för Skype för företag – lokalt</span><span class="sxs-lookup"><span data-stu-id="6cbb0-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="6cbb0-160">Lägga till lokala webb tjänst-URL-adresser i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6cbb0-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="6cbb0-161">Nu måste du köra kommandon för att lägga till URL-adresserna (samlas in tidigare) som tjänst huvud objekt i SFBO.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>
  
 <span data-ttu-id="6cbb0-162">**Obs!** SPN (tjänstens huvud namn) identifiera webb tjänster och koppla dem till ett säkerhets objekt (till exempel ett konto namn eller en grupp) så att tjänsten kan agera för en behörig användares räkning.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="6cbb0-163">Klienter som autentiserar sig på en server använder information som finns i SPN.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>
  
1. <span data-ttu-id="6cbb0-164">Börja med att ansluta till Azure Active Directory (Azure AD) med [dessa instruktioner](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

2. <span data-ttu-id="6cbb0-165">Kör det här kommandot lokalt för att få en lista med webb adresserna för SFB web service.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="6cbb0-166">Observera att AppPrincipalId börjar med `00000004` .</span><span class="sxs-lookup"><span data-stu-id="6cbb0-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="6cbb0-167">Detta motsvarar Skype för företag – online.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="6cbb0-168">Notera (och skärm bild för senare jämförelse) utdata för det här kommandot, som innehåller ett SE-och en URL-adress, men som till exempel består av de SPN som börjar med `00000004-0000-0ff1-ce00-000000000000/` .</span><span class="sxs-lookup"><span data-stu-id="6cbb0-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="6cbb0-169">Om de interna **eller** externa SFB URL-adresser från lokala användare saknas (till exempel https://lyncwebint01.contoso.com och https://lyncwebext01.contoso.com) vi måste lägga till dessa specifika poster i den här listan.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="6cbb0-170">Se till att du ersätter  *exemplen* nedan med dina faktiska URL-adresser i kommandona Add!</span><span class="sxs-lookup"><span data-stu-id="6cbb0-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. <span data-ttu-id="6cbb0-171">Verifiera att de nya posterna har lagts till genom att köra kommandot **Get-MsolServicePrincipal** från steg 2 igen och titta igenom resultatet.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="6cbb0-172">Jämför listan eller skärm bilden från den nya listan med SPN-objekt.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="6cbb0-173">Du kan också Skärmdumpa den nya listan för posterna.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="6cbb0-174">Om du lyckades ser du de två nya URL-adresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="6cbb0-175">I vårt exempel kommer listan med SPN att inkludera specifika URL: er https://lyncwebint01.contoso.com och https://lyncwebext01.contoso.com/ .</span><span class="sxs-lookup"><span data-stu-id="6cbb0-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="6cbb0-176">Skapa EvoSTS</span><span class="sxs-lookup"><span data-stu-id="6cbb0-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="6cbb0-177">Kör följande kommando i Skype för företag Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-177">Run the following command in the Skype for Business Management Shell.</span></span>
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="6cbb0-178">Aktivera hybrid modern</span><span class="sxs-lookup"><span data-stu-id="6cbb0-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="6cbb0-179">Det här steget vänder sig faktiskt till MA.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="6cbb0-180">Alla föregående steg kan köras i förväg utan att klientens autentiseringspaket ändras.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="6cbb0-181">När du är redo att ändra autentiseringsläget kör du det här kommandot i Skype för företag Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="6cbb0-182">Kontroll</span><span class="sxs-lookup"><span data-stu-id="6cbb0-182">Verify</span></span>

<span data-ttu-id="6cbb0-183">När du har aktiverat HMA använder klientens nästa inloggning det nya trafikflödet.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="6cbb0-184">Observera att när du bara aktiverar HMA utlöses ingen reauktorisering för någon klient.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="6cbb0-185">Klienterna autentiseras baserat på de auth-token och/eller certifikat de har.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="6cbb0-186">Testa att HMA fungerar när du har aktiverat det genom att logga ut från en test SFB Windows-klient och klicka på "ta bort mina autentiseringsuppgifter".</span><span class="sxs-lookup"><span data-stu-id="6cbb0-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="6cbb0-187">Logga in igen.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-187">Sign in again.</span></span> <span data-ttu-id="6cbb0-188">Klienten bör nu använda moderna auth-flödet och din inloggning innehåller nu en **Office 365** -uppmaning för ett "jobb-eller skol konto" som visas direkt innan klienten kontaktar servern och loggar in dig.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>
  
<span data-ttu-id="6cbb0-189">Du bör också kontrol lera "konfigurations information" för Skype för företag-klienter för en "OAuth-auktoritet".</span><span class="sxs-lookup"><span data-stu-id="6cbb0-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="6cbb0-190">Om du vill göra det på klient datorn håller du ned CTRL samtidigt som du högerklickar på ikonen Skype för företag i meddelande fältet i Windows.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="6cbb0-191">Klicka på **konfigurations information** i menyn som visas.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="6cbb0-192">I fönstret Skype för företag-konfigurations information som visas på Skriv bordet letar du upp följande:</span><span class="sxs-lookup"><span data-stu-id="6cbb0-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>
  
![Konfigurations informationen för en Skype för företag-klient med modern autentisering visar en Lync-och EWS OAUTH Authority-URL till https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
<span data-ttu-id="6cbb0-194">Håll ned CTRL-tangenten samtidigt som du högerklickar på ikonen för Outlook-klienten (också i Windows Notifications-fältet) och klicka på "anslutnings status".</span><span class="sxs-lookup"><span data-stu-id="6cbb0-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="6cbb0-195">Leta efter klientens SMTP-adress mot authn-typen "Bearer \* ", som representerar Bearer-token som används i OAuth.</span><span class="sxs-lookup"><span data-stu-id="6cbb0-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="6cbb0-196">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6cbb0-196">Related articles</span></span>

<span data-ttu-id="6cbb0-197">[Länka tillbaka till den moderna verifikations översikten](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>
  
<span data-ttu-id="6cbb0-198">Behöver du veta hur du använder modern inloggningsautentisering (ADAL) för dina Skype för företag-klienter?</span><span class="sxs-lookup"><span data-stu-id="6cbb0-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="6cbb0-199">Det finns anvisningar [här](https://technet.microsoft.com/library/mt710548.aspx).</span><span class="sxs-lookup"><span data-stu-id="6cbb0-199">We've got steps [here](https://technet.microsoft.com/library/mt710548.aspx).</span></span>
