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
ms.openlocfilehash: 46646f35d3b41821424269f66721fbf829d339f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928208"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="9a274-103">Konfigurera lokal Exchange Server för användning av modern hybridautentisering</span><span class="sxs-lookup"><span data-stu-id="9a274-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="9a274-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9a274-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9a274-105">HMA (Hybrid Modern Authentication) är en metod för identitetshantering som ger säkrare användarautentisering och auktorisering, och är tillgänglig för lokala Exchange-hybriddistributioner.</span><span class="sxs-lookup"><span data-stu-id="9a274-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="9a274-106">OBS</span><span class="sxs-lookup"><span data-stu-id="9a274-106">FYI</span></span>

<span data-ttu-id="9a274-107">Innan vi börjar ringer jag:</span><span class="sxs-lookup"><span data-stu-id="9a274-107">Before we begin, I call:</span></span>

- <span data-ttu-id="9a274-108">HMA (Hybrid Modern \> Authentication)</span><span class="sxs-lookup"><span data-stu-id="9a274-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="9a274-109">Exchange lokalt \> EXCH</span><span class="sxs-lookup"><span data-stu-id="9a274-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="9a274-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="9a274-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="9a274-111">Om en bild i den här artikeln har ett objekt som är nedtonat eller nedtonat innebär det att elementet som visas med grått inte ingår i *HMA-specifik konfiguration.*</span><span class="sxs-lookup"><span data-stu-id="9a274-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="9a274-112">Aktivera modern hybridautentisering</span><span class="sxs-lookup"><span data-stu-id="9a274-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="9a274-113">Om du slår på HMA innebär det att:</span><span class="sxs-lookup"><span data-stu-id="9a274-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="9a274-114">Att vara säker på att du uppfyller kraven innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="9a274-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="9a274-115">Eftersom det **finns många** krav som är gemensamma för både Skype för företag och Exchange, översikt över hybrid modern autentisering och förutsättningar för att använda det med Skype för företag och [Exchange-servrar lokalt.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9a274-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="9a274-116">Gör detta innan du påbörjar något av stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="9a274-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="9a274-117">Lägga till lokala webbtjänst-URL:er som **servicehuvudnamn (SPN)** i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9a274-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="9a274-118">Kontrollera att alla virtuella kataloger är aktiverade för HMA</span><span class="sxs-lookup"><span data-stu-id="9a274-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="9a274-119">Söka efter objektet Enth Auth Server</span><span class="sxs-lookup"><span data-stu-id="9a274-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="9a274-120">Aktivera HMA i EXCH.</span><span class="sxs-lookup"><span data-stu-id="9a274-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="9a274-121">**Obs!** Stöder din version av Office MA?</span><span class="sxs-lookup"><span data-stu-id="9a274-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="9a274-122">Se [Hur modern autentisering fungerar för Office 2013- och Office 2016-klientprogram.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="9a274-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="9a274-123">Se till att du uppfyller alla krav</span><span class="sxs-lookup"><span data-stu-id="9a274-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="9a274-124">Eftersom det finns många krav som är gemensamma för både Skype för företag och Exchange bör du läsa Översikt över modern hybridautentisering och förutsättningar för att använda det med Skype för företag och [Exchange-servrar lokalt.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9a274-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="9a274-125">Gör detta  *innan*  du påbörjar något av stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="9a274-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="9a274-126">Lägga till lokala webbtjänst-URL:er som SPN i Azure AD</span><span class="sxs-lookup"><span data-stu-id="9a274-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="9a274-127">Kör kommandona som tilldelar lokala webbtjänstwebbadresser som Azure AD SPN.</span><span class="sxs-lookup"><span data-stu-id="9a274-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="9a274-128">SPN används av klientdatorer och enheter under autentisering och auktorisering.</span><span class="sxs-lookup"><span data-stu-id="9a274-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="9a274-129">Alla URL:er som kan användas för att ansluta från den lokala platsen till Azure Active Directory (Azure AD) måste vara registrerade i Azure AD (detta omfattar både interna och externa namnområden).</span><span class="sxs-lookup"><span data-stu-id="9a274-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="9a274-130">Först måste du samla in alla URL-adresser som du behöver lägga till i AAD.</span><span class="sxs-lookup"><span data-stu-id="9a274-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="9a274-131">Kör följande kommandon lokalt:</span><span class="sxs-lookup"><span data-stu-id="9a274-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="9a274-132">Kontrollera att URL-klienterna kanske ansluter till visas som HTTPS-tjänstens huvudnamn i AAD.</span><span class="sxs-lookup"><span data-stu-id="9a274-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="9a274-133">Börja med att ansluta till AAD med [de här instruktionerna.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9a274-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="9a274-134">**Obs!** Du måste använda alternativet _Connect-MsolService_ från den här sidan för att kunna använda kommandot nedan.</span><span class="sxs-lookup"><span data-stu-id="9a274-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="9a274-135">För dina Exchange-relaterade URL:er skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="9a274-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="9a274-136">Notera (och skärmbilder för senare jämförelser) utdata för det här kommandot, som bör innehålla en URL för https://  *autodiscover.yourdomain.com*  och https://  *mail.yourdomain.com,* men består oftast av SPN som börjar med 00000002-0000-0ff1-ce00-000000000000/.</span><span class="sxs-lookup"><span data-stu-id="9a274-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="9a274-137">Om det https:// url:er från din lokala plats som saknas måste vi lägga till de specifika posterna i den här listan.</span><span class="sxs-lookup"><span data-stu-id="9a274-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="9a274-138">Om du inte ser dina interna och externa MAPI/HTTP-, EWS-, ActiveSync-, OAB- och automatisk upptäckt-poster i den här listan måste du lägga till dem med hjälp av kommandot nedan (exempeladresserna är ' ' och ' men du kan ersätta exempeladresserna med dina `mail.corp.contoso.com` `owa.contoso.com` **egna**):</span><span class="sxs-lookup"><span data-stu-id="9a274-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="9a274-139">Kontrollera att de nya posterna har lagts till genom att köra kommandot Get-MsolServicePrincipal från steg 2 igen och titta igenom utdata.</span><span class="sxs-lookup"><span data-stu-id="9a274-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="9a274-140">Jämför listan/skärmbilden före med den nya listan med SPN.</span><span class="sxs-lookup"><span data-stu-id="9a274-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="9a274-141">Du kan också ta en skärmbild av den nya listan för dina poster.</span><span class="sxs-lookup"><span data-stu-id="9a274-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="9a274-142">Om det lyckades visas de två nya webbadresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="9a274-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="9a274-143">Om vi går igenom exemplet innehåller listan med SPN nu specifika URL:er  `https://mail.corp.contoso.com`  och  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="9a274-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="9a274-144">Kontrollera att virtuella kataloger är korrekt konfigurerade</span><span class="sxs-lookup"><span data-stu-id="9a274-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="9a274-145">Kontrollera nu att OAuth är korrekt aktiverat i Exchange i alla virtuella kataloger Outlook kan använda genom att köra följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="9a274-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="9a274-146">Kontrollera resultatet för att kontrollera att **OAuth** är aktiverat för var och en av dessa VDirs, det ser ut ungefär så här (och det viktiga att titta på är "OAuth"):</span><span class="sxs-lookup"><span data-stu-id="9a274-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="9a274-147">Om OAuth saknas på en server och någon av de fyra virtuella katalogerna måste du lägga till den med relevanta kommandon innan du fortsätter ([Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)och [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="9a274-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="9a274-148">Bekräfta att The Ents Auth Server-objektet finns</span><span class="sxs-lookup"><span data-stu-id="9a274-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="9a274-149">Återgå till det lokala Exchange Management Shell för det senaste kommandot.</span><span class="sxs-lookup"><span data-stu-id="9a274-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="9a274-150">Nu kan du verifiera att din lokala tjänst har en post för autentiseringsprovidern för windows-säkerhet:</span><span class="sxs-lookup"><span data-stu-id="9a274-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="9a274-151">Dina utdata bör visa autentiseringsservern för Name EllerSts och statusen "Enabled" ska vara True.</span><span class="sxs-lookup"><span data-stu-id="9a274-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="9a274-152">Om du inte ser det bör du ladda ned och köra den senaste versionen av hybridkonfigurationsguiden.</span><span class="sxs-lookup"><span data-stu-id="9a274-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="9a274-153">**Viktigt** Om du kör Exchange 2010 i din miljö skapas inte autentiseringsprovidern För företagsautentisering.</span><span class="sxs-lookup"><span data-stu-id="9a274-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="9a274-154">Aktivera HMA</span><span class="sxs-lookup"><span data-stu-id="9a274-154">Enable HMA</span></span>

<span data-ttu-id="9a274-155">Kör följande kommando lokalt i Exchange Management Shell:</span><span class="sxs-lookup"><span data-stu-id="9a274-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="9a274-156">Verifiera</span><span class="sxs-lookup"><span data-stu-id="9a274-156">Verify</span></span>

<span data-ttu-id="9a274-157">När du har aktiverat HMA används det nya autentiseringsflödet för klientens nästa inloggning.</span><span class="sxs-lookup"><span data-stu-id="9a274-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="9a274-158">Observera att endast aktivera HMA utlöser inte en nyauthentication för någon klient.</span><span class="sxs-lookup"><span data-stu-id="9a274-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="9a274-159">Klienterna återauthenticate baserat på livslängden för autentiseringstoken och/eller certifikat de har.</span><span class="sxs-lookup"><span data-stu-id="9a274-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="9a274-160">Du bör också hålla ned CTRL-tangenten samtidigt som du högerklickar på ikonen för Outlook-klienten (även i systemfältet Windows-meddelanden) och klickar på "Anslutningsstatus".</span><span class="sxs-lookup"><span data-stu-id="9a274-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="9a274-161">Leta efter klientens SMTP-adress mot typen "Authn" av typen "Bearer", som representerar den bearer-token som används \* i OAuth.</span><span class="sxs-lookup"><span data-stu-id="9a274-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="9a274-162">**Obs!** Behöver du konfigurera Skype för företag med HMA?</span><span class="sxs-lookup"><span data-stu-id="9a274-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="9a274-163">Du behöver två artiklar: en som innehåller [topologier](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)som stöds och en som visar [hur du gör konfigurationen.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="9a274-163">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="9a274-164">Använda modern hybridautentisering med Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="9a274-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="9a274-165">Om du är en lokal kund som använder Exchange-server på TCP 443 kringgår du trafikbearbetning för följande IP-intervall:</span><span class="sxs-lookup"><span data-stu-id="9a274-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="9a274-166">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9a274-166">Related topics</span></span>

[<span data-ttu-id="9a274-167">Konfigurationskrav för modern autentisering för övergång från dedikerad/ITAR för Office 365 till vNext</span><span class="sxs-lookup"><span data-stu-id="9a274-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)