---
title: Konfigurera lokal Exchange Server för användning av modern hybridautentisering
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Lär dig hur du konfigurerar en lokal Exchange-server för användning av modern hybridautentisering (HMA), som ger dig säkrare användarautentisering och auktorisering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9393b457c219fb03ae2e8a35c3f795c324919f27
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579728"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="e59ba-103">Konfigurera lokal Exchange Server för användning av modern hybridautentisering</span><span class="sxs-lookup"><span data-stu-id="e59ba-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="e59ba-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e59ba-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e59ba-105">HMA (Hybrid Modern Authentication) är en metod för identitetshantering som ger säkrare användarautentisering och auktorisering, och är tillgänglig för lokala Exchange-hybriddistributioner.</span><span class="sxs-lookup"><span data-stu-id="e59ba-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="e59ba-106">OBS</span><span class="sxs-lookup"><span data-stu-id="e59ba-106">FYI</span></span>

<span data-ttu-id="e59ba-107">Innan vi börjar ringer jag:</span><span class="sxs-lookup"><span data-stu-id="e59ba-107">Before we begin, I call:</span></span>

- <span data-ttu-id="e59ba-108">HMA (Hybrid Modern \> Authentication)</span><span class="sxs-lookup"><span data-stu-id="e59ba-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="e59ba-109">Exchange lokalt \> EXCH</span><span class="sxs-lookup"><span data-stu-id="e59ba-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="e59ba-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="e59ba-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="e59ba-111">Om en bild i den här artikeln har ett objekt som är nedtonat eller nedtonat innebär det att elementet som visas med grått inte ingår i *HMA-specifik konfiguration.*</span><span class="sxs-lookup"><span data-stu-id="e59ba-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="e59ba-112">Aktivera modern hybridautentisering</span><span class="sxs-lookup"><span data-stu-id="e59ba-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="e59ba-113">Om du slår på HMA innebär det att:</span><span class="sxs-lookup"><span data-stu-id="e59ba-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="e59ba-114">Att vara säker på att du uppfyller kraven innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="e59ba-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="e59ba-115">Eftersom det **finns många** krav som är gemensamma för både Skype för företag och Exchange, översikt över hybrid modern autentisering och förutsättningar för att använda det med Skype för företag och [Exchange-servrar lokalt.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e59ba-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="e59ba-116">Gör detta innan du påbörjar något av stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e59ba-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="e59ba-117">Lägga till lokala webbtjänst-URL:er som **servicehuvudnamn (SPN)** i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e59ba-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="e59ba-118">Om EXCH är i hybrid med flera innehavare måste dessa lokala webbtjänstwebbadresser läggas till som SPN i Azure AD för alla klientorganisationen som finns i hybrid med EXCH.</span><span class="sxs-lookup"><span data-stu-id="e59ba-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="e59ba-119">Kontrollera att alla virtuella kataloger är aktiverade för HMA</span><span class="sxs-lookup"><span data-stu-id="e59ba-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="e59ba-120">Söka efter objektet Enth Auth Server</span><span class="sxs-lookup"><span data-stu-id="e59ba-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="e59ba-121">Aktivera HMA i EXCH.</span><span class="sxs-lookup"><span data-stu-id="e59ba-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="e59ba-122">Stöder din version av Office MA?</span><span class="sxs-lookup"><span data-stu-id="e59ba-122">Does your version of Office support MA?</span></span> <span data-ttu-id="e59ba-123">Se [Hur modern autentisering fungerar för Office 2013- och Office 2016-klientprogram.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="e59ba-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="e59ba-124">Se till att du uppfyller alla krav</span><span class="sxs-lookup"><span data-stu-id="e59ba-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="e59ba-125">Eftersom det finns många krav som är gemensamma för både Skype för företag och Exchange bör du läsa Översikt över modern hybridautentisering och förutsättningar för att använda det med Skype för företag och [Exchange-servrar lokalt.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e59ba-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="e59ba-126">Gör detta  *innan*  du påbörjar något av stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="e59ba-126">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="e59ba-127">Lägga till lokala webbtjänst-URL:er som SPN i Azure AD</span><span class="sxs-lookup"><span data-stu-id="e59ba-127">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="e59ba-128">Kör kommandona som tilldelar lokala webbtjänstwebbadresser som Azure AD SPN.</span><span class="sxs-lookup"><span data-stu-id="e59ba-128">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="e59ba-129">SPN används av klientdatorer och enheter under autentisering och auktorisering.</span><span class="sxs-lookup"><span data-stu-id="e59ba-129">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="e59ba-130">Alla URL:er som kan användas för att ansluta från den lokala platsen till Azure Active Directory (Azure AD) måste vara registrerade i Azure AD (detta omfattar både interna och externa namnområden).</span><span class="sxs-lookup"><span data-stu-id="e59ba-130">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="e59ba-131">Först måste du samla in alla URL-adresser som du behöver lägga till i AAD.</span><span class="sxs-lookup"><span data-stu-id="e59ba-131">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="e59ba-132">Kör följande kommandon lokalt:</span><span class="sxs-lookup"><span data-stu-id="e59ba-132">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="e59ba-133">Kontrollera att URL-klienterna kanske ansluter till visas som HTTPS-tjänstens huvudnamn i AAD.</span><span class="sxs-lookup"><span data-stu-id="e59ba-133">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="e59ba-134">Om EXCH är i hybrid med flera innehavare **,** ska dessa HTTPS-SPN läggas till i AAD för alla klientorganisationen i hybrid med EXCH.</span><span class="sxs-lookup"><span data-stu-id="e59ba-134">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="e59ba-135">Börja med att ansluta till AAD med [de här instruktionerna.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="e59ba-135">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e59ba-136">Du måste använda alternativet _Connect-MsolService_ från den här sidan för att kunna använda kommandot nedan.</span><span class="sxs-lookup"><span data-stu-id="e59ba-136">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="e59ba-137">För dina Exchange-relaterade URL:er skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="e59ba-137">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="e59ba-138">Notera (och skärmbilder för senare jämförelser) utdata för det här kommandot, som bör innehålla en URL för https://  *autodiscover.yourdomain.com*  och https://  *mail.yourdomain.com,* men består oftast av SPN som börjar med 00000002-0000-0ff1-ce00-000000000000/.</span><span class="sxs-lookup"><span data-stu-id="e59ba-138">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="e59ba-139">Om det https:// url:er från din lokala plats som saknas måste vi lägga till de specifika posterna i den här listan.</span><span class="sxs-lookup"><span data-stu-id="e59ba-139">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="e59ba-140">Om du inte ser dina interna och externa MAPI/HTTP-, EWS-, ActiveSync-, OAB- och automatisk upptäckt-poster i den här listan måste du lägga till dem med hjälp av kommandot nedan (exempeladresserna är ' ' och ' men du kan ersätta exempeladresserna med dina `mail.corp.contoso.com` `owa.contoso.com` **egna**):</span><span class="sxs-lookup"><span data-stu-id="e59ba-140">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="e59ba-141">Kontrollera att de nya posterna har lagts till genom att köra kommandot Get-MsolServicePrincipal från steg 2 igen och titta igenom utdata.</span><span class="sxs-lookup"><span data-stu-id="e59ba-141">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="e59ba-142">Jämför listan/skärmbilden före med den nya listan med SPN.</span><span class="sxs-lookup"><span data-stu-id="e59ba-142">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="e59ba-143">Du kan också ta en skärmbild av den nya listan för dina poster.</span><span class="sxs-lookup"><span data-stu-id="e59ba-143">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="e59ba-144">Om det lyckades visas de två nya webbadresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="e59ba-144">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="e59ba-145">Om vi går igenom exemplet innehåller listan med SPN nu specifika URL:er  `https://mail.corp.contoso.com`  och  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="e59ba-145">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="e59ba-146">Kontrollera att virtuella kataloger är korrekt konfigurerade</span><span class="sxs-lookup"><span data-stu-id="e59ba-146">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="e59ba-147">Kontrollera nu att OAuth är korrekt aktiverat i Exchange i alla virtuella kataloger Outlook kan använda genom att köra följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="e59ba-147">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="e59ba-148">Kontrollera resultatet för att kontrollera att **OAuth** är aktiverat för var och en av dessa VDirs, det ser ut ungefär så här (och det viktiga att titta på är "OAuth"):</span><span class="sxs-lookup"><span data-stu-id="e59ba-148">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="e59ba-149">Om OAuth saknas på en server och någon av de fyra virtuella katalogerna måste du lägga till den med relevanta kommandon innan du fortsätter ([Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)och [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="e59ba-149">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="e59ba-150">Bekräfta att The Ents Auth Server-objektet finns</span><span class="sxs-lookup"><span data-stu-id="e59ba-150">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="e59ba-151">Återgå till det lokala Exchange Management Shell för det senaste kommandot.</span><span class="sxs-lookup"><span data-stu-id="e59ba-151">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="e59ba-152">Nu kan du verifiera att din lokala tjänst har en post för autentiseringsprovidern för windows-säkerhet:</span><span class="sxs-lookup"><span data-stu-id="e59ba-152">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="e59ba-153">Dina utdata bör visa autentiseringsservern för Name EllerSts och statusen "Enabled" ska vara True.</span><span class="sxs-lookup"><span data-stu-id="e59ba-153">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="e59ba-154">Om du inte ser det bör du ladda ned och köra den senaste versionen av hybridkonfigurationsguiden.</span><span class="sxs-lookup"><span data-stu-id="e59ba-154">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="e59ba-155">Om EXCH är i hybridläge med flera klientorganisationsklienter bör utdata visa en **autentiseringsserver** för namnkvitterna – {GUID} för varje klientorganisation i hybrid med EXCH och "Aktiverad"-läget ska vara Sant för alla dessa AuthServer-objekt.</span><span class="sxs-lookup"><span data-stu-id="e59ba-155">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="e59ba-156">**Viktigt** Om du kör Exchange 2010 i din miljö skapas inte autentiseringsprovidern För företagsautentisering.</span><span class="sxs-lookup"><span data-stu-id="e59ba-156">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="e59ba-157">Aktivera HMA</span><span class="sxs-lookup"><span data-stu-id="e59ba-157">Enable HMA</span></span>

<span data-ttu-id="e59ba-158">Kör följande kommando lokalt i Exchange Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e59ba-158">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="e59ba-159">Om EXCH-versionen är Exchange 2016 (CU18 eller senare) eller Exchange 2019 (CU7 eller senare) och hybrid konfigurerades med HCW som laddats ned efter september 2020 kör du följande kommando i Exchange Management Shell lokalt:</span><span class="sxs-lookup"><span data-stu-id="e59ba-159">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="e59ba-160">Om EXCH är i hybrid **med** flera innehavare finns det flera AuthServer-objekt i EXCH med domäner som motsvarar varje klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="e59ba-160">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="e59ba-161">Flaggan **IsDefaultAuthorizationEndpoint** ska vara inställd på true (med hjälp av cmdleten **IsDefaultAuthorizationEndpoint)** för något av dessa AuthServer-objekt.</span><span class="sxs-lookup"><span data-stu-id="e59ba-161">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="e59ba-162">Den här flaggan kan inte ställas in på sant för alla Authserver-objekt och HMA aktiveras även om ett av authServer-objektets **IsDefaultAuthorizationEndpoint-flagga** är satt till true.</span><span class="sxs-lookup"><span data-stu-id="e59ba-162">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="e59ba-163">Verifiera</span><span class="sxs-lookup"><span data-stu-id="e59ba-163">Verify</span></span>

<span data-ttu-id="e59ba-164">När du har aktiverat HMA används det nya autentiseringsflödet för klientens nästa inloggning.</span><span class="sxs-lookup"><span data-stu-id="e59ba-164">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="e59ba-165">Observera att endast aktivera HMA utlöser inte en nyauthentication för någon klient.</span><span class="sxs-lookup"><span data-stu-id="e59ba-165">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="e59ba-166">Klienterna återauthenticate baserat på livslängden för autentiseringstoken och/eller certifikat de har.</span><span class="sxs-lookup"><span data-stu-id="e59ba-166">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="e59ba-167">Du bör också hålla ned CTRL-tangenten samtidigt som du högerklickar på ikonen för Outlook-klienten (även i systemfältet Windows-meddelanden) och klickar på "Anslutningsstatus".</span><span class="sxs-lookup"><span data-stu-id="e59ba-167">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="e59ba-168">Leta efter klientens SMTP-adress mot typen "Authn" av typen "Bearer", som representerar den bearer-token som används \* i OAuth.</span><span class="sxs-lookup"><span data-stu-id="e59ba-168">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="e59ba-169">Behöver du konfigurera Skype för företag med HMA?</span><span class="sxs-lookup"><span data-stu-id="e59ba-169">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="e59ba-170">Du behöver två artiklar: en som innehåller [topologier](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)som stöds och en som visar [hur du gör konfigurationen.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="e59ba-170">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="e59ba-171">Använda modern hybridautentisering med Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="e59ba-171">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="e59ba-172">Om du är en lokal kund som använder Exchange-server på TCP 443 kringgår du trafikbearbetning för följande IP-adressintervall:</span><span class="sxs-lookup"><span data-stu-id="e59ba-172">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="e59ba-173">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e59ba-173">Related topics</span></span>

[<span data-ttu-id="e59ba-174">Konfigurationskrav för modern autentisering för övergång från dedikerad/ITAR för Office 365 till vNext</span><span class="sxs-lookup"><span data-stu-id="e59ba-174">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
