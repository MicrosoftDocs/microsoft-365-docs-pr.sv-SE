---
title: Så här konfigurerar du Exchange Server lokalt för användning av hybrid modern
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
description: Lär dig hur du konfigurerar en Exchange-Server lokalt för användning av hybrid modern autentisering (HMA) och ger dig säkrare autentisering och verifiering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8db74c04335e0846666991d74980648cedb4d9d7
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547136"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="45b92-103">Så här konfigurerar du Exchange Server lokalt för användning av hybrid modern</span><span class="sxs-lookup"><span data-stu-id="45b92-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="45b92-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="45b92-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="45b92-105">Hybrid modern autentisering (HMA) är en metod för identitets hantering som erbjuder säkrare användar verifiering och-auktorisering och är tillgängligt för Exchange Server-lokala hybrid installationer.</span><span class="sxs-lookup"><span data-stu-id="45b92-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="45b92-106">Observera</span><span class="sxs-lookup"><span data-stu-id="45b92-106">FYI</span></span>

<span data-ttu-id="45b92-107">Innan vi börjar ringer jag:</span><span class="sxs-lookup"><span data-stu-id="45b92-107">Before we begin, I call:</span></span>

- <span data-ttu-id="45b92-108">Hybrid modern, \> HMA</span><span class="sxs-lookup"><span data-stu-id="45b92-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="45b92-109">Exchange \> lokalt valutakurs</span><span class="sxs-lookup"><span data-stu-id="45b92-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="45b92-110">Exchange Online- \> EXO</span><span class="sxs-lookup"><span data-stu-id="45b92-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="45b92-111">*Om en bild i den här artikeln har ett objekt som är nedtonat eller nedtonat, innebär det att elementet som visas i grått inte ingår i HMA-specifik konfiguration* .</span><span class="sxs-lookup"><span data-stu-id="45b92-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration* .</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="45b92-112">Aktivera hybrid modern</span><span class="sxs-lookup"><span data-stu-id="45b92-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="45b92-113">Att aktivera HMA på medelvärden:</span><span class="sxs-lookup"><span data-stu-id="45b92-113">Turning HMA on means:</span></span>

1. <span data-ttu-id="45b92-114">Det är bara att möta PreReqs innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="45b92-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="45b92-115">Eftersom många **förutsättningar** är vanliga för både Skype för företag och Exchange, är [hybrid modern verifiering och förutsättningar för att använda den med lokala Skype för företag-och Exchange-servrar](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="45b92-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="45b92-116">Gör det innan du följer anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="45b92-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="45b92-117">Lägga till lokala webb tjänst-URL: er som **tjänst huvud namn (SPN)** i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="45b92-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="45b92-118">Kontrol lera att alla virtuella kataloger är aktiverade för HMA</span><span class="sxs-lookup"><span data-stu-id="45b92-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="45b92-119">Söker efter serverobjektet för EvoSTS</span><span class="sxs-lookup"><span data-stu-id="45b92-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="45b92-120">Aktivera HMA i VALUTAKURS.</span><span class="sxs-lookup"><span data-stu-id="45b92-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="45b92-121">**Obs!** Stöder din version av Office MA?</span><span class="sxs-lookup"><span data-stu-id="45b92-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="45b92-122">Se [hur modern inloggningsautentisering fungerar för office 2013-och Office 2016-klient program](modern-auth-for-office-2013-and-2016.md).</span><span class="sxs-lookup"><span data-stu-id="45b92-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="45b92-123">Kontrol lera att du uppfyller alla krav</span><span class="sxs-lookup"><span data-stu-id="45b92-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="45b92-124">Eftersom många förutsättningar är vanliga för både Skype för företag och Exchange bör du läsa [hybridens översikt över modern och förutsättningar för att använda den med lokala Skype för företag-och Exchange-servrar](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="45b92-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="45b92-125">Gör det  *innan*  du följer anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="45b92-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="45b92-126">Lägga till lokala webb tjänst-URL: er som SPN i Azure AD</span><span class="sxs-lookup"><span data-stu-id="45b92-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="45b92-127">Kör kommandona som tilldelar dina lokala webb tjänst-URL: er som Azure AD-SPN.</span><span class="sxs-lookup"><span data-stu-id="45b92-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="45b92-128">SPN används av klient datorer och enheter vid autentisering och auktorisering.</span><span class="sxs-lookup"><span data-stu-id="45b92-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="45b92-129">Alla URL-adresser som kan användas för att ansluta från lokala platser till Azure Active Directory (Azure AD) måste vara registrerade i Azure AD (Detta inkluderar både interna och externa namn områden).</span><span class="sxs-lookup"><span data-stu-id="45b92-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="45b92-130">Först samlar du in alla URL-adresser som du måste lägga till i AAD.</span><span class="sxs-lookup"><span data-stu-id="45b92-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="45b92-131">Kör dessa kommandon lokalt:</span><span class="sxs-lookup"><span data-stu-id="45b92-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="45b92-132">Se till att URL-klienterna kan ansluta till är listade som HTTPS-tjänstens huvud namn i AAD.</span><span class="sxs-lookup"><span data-stu-id="45b92-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="45b92-133">Först ansluter du till AAD med [dessa instruktioner](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="45b92-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="45b92-134">**Obs!** Du måste använda alternativet _Connect-MSOLService_ på den här sidan om du vill kunna använda kommandot nedan.</span><span class="sxs-lookup"><span data-stu-id="45b92-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="45b92-135">För Exchange-relaterade URL-adresser skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="45b92-135">For your Exchange related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="45b92-136">Ta del av (och skärmdump för senare jämförelse) utdata för det här kommandot, vilket bör omfatta en https://  *Autodiscover.yourdomain.com*  och https://  *mail.yourdomain.com* -URL, men i de flesta fall är SPN-namn som börjar med 00000002-0000-0ff1-CE00-000000000000/.</span><span class="sxs-lookup"><span data-stu-id="45b92-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="45b92-137">Om det finns https://URL-adresser från dina lokala platser måste vi lägga till dessa specifika poster i den här listan.</span><span class="sxs-lookup"><span data-stu-id="45b92-137">If there are https:// URLs from your on-premises that are missing we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="45b92-138">Om du inte ser dina interna och externa MAPI/HTTP-, EWS-, ActiveSync-, OAB-och Autodiscover-poster i den här listan måste du lägga till dem med hjälp av kommandot nedan (exempel-URL: erna är " `mail.corp.contoso.com` " och " `owa.contoso.com` ", men du **ersätter exempel URL-adresserna med din egen** ):</span><span class="sxs-lookup"><span data-stu-id="45b92-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own** ):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="45b92-139">Verifiera att de nya posterna har lagts till genom att köra kommandot Get-MsolServicePrincipal från steg 2 igen och titta igenom resultatet.</span><span class="sxs-lookup"><span data-stu-id="45b92-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="45b92-140">Jämför listan/skärm bilden från den nya listan med SPN-namn (du kan också skriva in den nya listan för posterna).</span><span class="sxs-lookup"><span data-stu-id="45b92-140">Compare the list / screenshot from before to the new list of SPNs (you may also screenshot the new list for your records).</span></span> <span data-ttu-id="45b92-141">Om du lyckades ser du de två nya URL-adresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="45b92-141">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="45b92-142">I vårt exempel kommer listan med SPN att inkludera specifika URL: er  `https://mail.corp.contoso.com`  och  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="45b92-142">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="45b92-143">Verifiera att virtuella kataloger är korrekt konfigurerade</span><span class="sxs-lookup"><span data-stu-id="45b92-143">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="45b92-144">Verifiera att OAuth är korrekt aktive rad i Exchange på alla virtuella kataloger som Outlook kan använda genom att köra följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="45b92-144">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="45b92-145">Kontrol lera att **OAuth** är aktiverat på var och en av de här VDirs kommer det att se ut ungefär så här (och de viktigaste att titta på är ' OAuth '):</span><span class="sxs-lookup"><span data-stu-id="45b92-145">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="45b92-146">Om OAuth saknas från någon server och någon av de fyra virtuella katalogerna måste du lägga till den med relevanta kommandon innan du fortsätter ([set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)och [set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="45b92-146">If OAuth is missing from any server and any of the four virtual directories then you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="45b92-147">Bekräfta att EvoSTS-auth-objektet finns</span><span class="sxs-lookup"><span data-stu-id="45b92-147">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="45b92-148">Återvänd till det lokala Exchange Management Shell för det här senaste kommandot.</span><span class="sxs-lookup"><span data-stu-id="45b92-148">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="45b92-149">Nu kan du kontrol lera att din lokala tjänst har en post för evoSTS-autentiseringsprovidern:</span><span class="sxs-lookup"><span data-stu-id="45b92-149">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="45b92-150">Utdata ska visa en AuthServer av namnet EvoSts och läget ' Enabled ' ska vara sant.</span><span class="sxs-lookup"><span data-stu-id="45b92-150">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="45b92-151">Om du inte ser det här ska du ladda ned och köra den senaste versionen av hybrid konfigurations guiden.</span><span class="sxs-lookup"><span data-stu-id="45b92-151">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="45b92-152">**Viktigt** Om du kör Exchange 2010 i din miljö skapas inte EvoSTS.</span><span class="sxs-lookup"><span data-stu-id="45b92-152">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="45b92-153">Aktivera HMA</span><span class="sxs-lookup"><span data-stu-id="45b92-153">Enable HMA</span></span>

<span data-ttu-id="45b92-154">Kör följande kommando i Exchange Management Shell, lokalt:</span><span class="sxs-lookup"><span data-stu-id="45b92-154">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="45b92-155">Kontroll</span><span class="sxs-lookup"><span data-stu-id="45b92-155">Verify</span></span>

<span data-ttu-id="45b92-156">När du har aktiverat HMA använder klientens nästa inloggning det nya trafikflödet.</span><span class="sxs-lookup"><span data-stu-id="45b92-156">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="45b92-157">Observera att när du aktiverar HMA utlöses ingen omauktorisering för någon klient.</span><span class="sxs-lookup"><span data-stu-id="45b92-157">Note that just turning on HMA won't trigger a re-authentication for any client.</span></span> <span data-ttu-id="45b92-158">Klienterna autentiseras på nytt baserat på hur många autentiseringstoken och/eller vilka certifikat de har.</span><span class="sxs-lookup"><span data-stu-id="45b92-158">The clients re-authenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="45b92-159">Du bör även hålla ned CTRL-tangenten samtidigt som du högerklickar på ikonen för Outlook-klienten (även i Windows Notifications) och klickar på "anslutnings status".</span><span class="sxs-lookup"><span data-stu-id="45b92-159">You should also hold down the CTRL key at the same time you right click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="45b92-160">Leta efter klientens SMTP-adress mot "authn" \* -typen, som representerar Bearer-token som används i OAuth.</span><span class="sxs-lookup"><span data-stu-id="45b92-160">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="45b92-161">**Obs!** Behöver du konfigurera Skype för företag med HMA?</span><span class="sxs-lookup"><span data-stu-id="45b92-161">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="45b92-162">Du behöver två artiklar: en som visar en lista med [topologier som stöds](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)och en som visar [hur](configure-skype-for-business-for-hybrid-modern-authentication.md)du konfigurerar.</span><span class="sxs-lookup"><span data-stu-id="45b92-162">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="45b92-163">Använda hybrid modern inloggningsautentisering med Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="45b92-163">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="45b92-164">Om du är lokal kund med Exchange Server på TCP 443 ska du Lägg följande IP-adressintervall:</span><span class="sxs-lookup"><span data-stu-id="45b92-164">If you are an on-premises customer using Exchange server on TCP 443, please whitelist the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="45b92-165">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="45b92-165">Related topics</span></span>

[<span data-ttu-id="45b92-166">Moderna konfigurations krav för inloggningsautentisering för över gång från Office 365 dedikerade/ITAR till vNext</span><span class="sxs-lookup"><span data-stu-id="45b92-166">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
