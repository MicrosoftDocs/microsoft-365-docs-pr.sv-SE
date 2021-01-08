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
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780290"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="f4b9a-103">Så här konfigurerar du Exchange Server lokalt för användning av hybrid modern</span><span class="sxs-lookup"><span data-stu-id="f4b9a-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="f4b9a-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f4b9a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f4b9a-105">Hybrid modern autentisering (HMA) är en metod för identitets hantering som erbjuder säkrare användar verifiering och-auktorisering och är tillgängligt för Exchange Server-lokala hybrid installationer.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="f4b9a-106">Observera</span><span class="sxs-lookup"><span data-stu-id="f4b9a-106">FYI</span></span>

<span data-ttu-id="f4b9a-107">Innan vi börjar ringer jag:</span><span class="sxs-lookup"><span data-stu-id="f4b9a-107">Before we begin, I call:</span></span>

- <span data-ttu-id="f4b9a-108">Hybrid modern, \> HMA</span><span class="sxs-lookup"><span data-stu-id="f4b9a-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="f4b9a-109">Exchange \> lokalt valutakurs</span><span class="sxs-lookup"><span data-stu-id="f4b9a-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="f4b9a-110">Exchange Online- \> EXO</span><span class="sxs-lookup"><span data-stu-id="f4b9a-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="f4b9a-111">*Om en bild i den här artikeln har ett objekt som är nedtonat eller nedtonat, innebär det att elementet som visas i grått inte ingår i HMA-specifik konfiguration*.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="f4b9a-112">Aktivera hybrid modern</span><span class="sxs-lookup"><span data-stu-id="f4b9a-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="f4b9a-113">Att slå på HMA betyder:</span><span class="sxs-lookup"><span data-stu-id="f4b9a-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="f4b9a-114">Det är bara att möta PreReqs innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="f4b9a-115">Eftersom många **förutsättningar** är vanliga för både Skype för företag och Exchange, är [hybrid modern verifiering och förutsättningar för att använda den med lokala Skype för företag-och Exchange-servrar](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4b9a-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="f4b9a-116">Gör det innan du följer anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="f4b9a-117">Lägga till lokala webb tjänst-URL: er som **tjänst huvud namn (SPN)** i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="f4b9a-118">Kontrol lera att alla virtuella kataloger är aktiverade för HMA</span><span class="sxs-lookup"><span data-stu-id="f4b9a-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="f4b9a-119">Söker efter serverobjektet för EvoSTS</span><span class="sxs-lookup"><span data-stu-id="f4b9a-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="f4b9a-120">Aktivera HMA i VALUTAKURS.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="f4b9a-121">**Obs!** Stöder din version av Office MA?</span><span class="sxs-lookup"><span data-stu-id="f4b9a-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="f4b9a-122">Se [hur modern inloggningsautentisering fungerar för office 2013-och Office 2016-klient program](modern-auth-for-office-2013-and-2016.md).</span><span class="sxs-lookup"><span data-stu-id="f4b9a-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="f4b9a-123">Kontrol lera att du uppfyller alla krav</span><span class="sxs-lookup"><span data-stu-id="f4b9a-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="f4b9a-124">Eftersom många förutsättningar är vanliga för både Skype för företag och Exchange bör du läsa [hybridens översikt över modern och förutsättningar för att använda den med lokala Skype för företag-och Exchange-servrar](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4b9a-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="f4b9a-125">Gör det  *innan*  du följer anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="f4b9a-126">Lägga till lokala webb tjänst-URL: er som SPN i Azure AD</span><span class="sxs-lookup"><span data-stu-id="f4b9a-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="f4b9a-127">Kör kommandona som tilldelar dina lokala webb tjänst-URL: er som Azure AD-SPN.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="f4b9a-128">SPN används av klient datorer och enheter vid autentisering och auktorisering.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="f4b9a-129">Alla URL-adresser som kan användas för att ansluta från lokala platser till Azure Active Directory (Azure AD) måste vara registrerade i Azure AD (Detta inkluderar både interna och externa namn områden).</span><span class="sxs-lookup"><span data-stu-id="f4b9a-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="f4b9a-130">Först samlar du in alla URL-adresser som du måste lägga till i AAD.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="f4b9a-131">Kör dessa kommandon lokalt:</span><span class="sxs-lookup"><span data-stu-id="f4b9a-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="f4b9a-132">Se till att URL-klienterna kan ansluta till är listade som HTTPS-tjänstens huvud namn i AAD.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="f4b9a-133">Först ansluter du till AAD med [dessa instruktioner](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f4b9a-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="f4b9a-134">**Obs!** Du måste använda alternativet _Connect-MSOLService_ på den här sidan om du vill kunna använda kommandot nedan.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="f4b9a-135">För dina Exchange-relaterade URL-adresser skriver du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f4b9a-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="f4b9a-136">Ta del av (och skärmdump för senare jämförelse) utdata för det här kommandot, vilket bör omfatta en https://  *Autodiscover.yourdomain.com*  och https://  *mail.yourdomain.com* -URL, men i de flesta fall är SPN-namn som börjar med 00000002-0000-0ff1-CE00-000000000000/.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="f4b9a-137">Om det finns https://URL-adresser från dina lokala platser måste vi lägga till dessa specifika poster i den här listan.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="f4b9a-138">Om du inte ser dina interna och externa MAPI/HTTP-, EWS-, ActiveSync-, OAB-och Autodiscover-poster i den här listan måste du lägga till dem med hjälp av kommandot nedan (exempel-URL: erna är " `mail.corp.contoso.com` " och " `owa.contoso.com` ", men du **ersätter exempel URL-adresserna med din egen**):</span><span class="sxs-lookup"><span data-stu-id="f4b9a-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="f4b9a-139">Verifiera att de nya posterna har lagts till genom att köra kommandot Get-MsolServicePrincipal från steg 2 igen och titta igenom resultatet.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="f4b9a-140">Jämför listan/skärm bilden från den nya listan med SPN-namn.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="f4b9a-141">Du kan också ta en skärm bild av den nya listan för posterna.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="f4b9a-142">Om du lyckades ser du de två nya URL-adresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="f4b9a-143">I vårt exempel kommer listan med SPN att inkludera specifika URL: er  `https://mail.corp.contoso.com`  och  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f4b9a-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="f4b9a-144">Verifiera att virtuella kataloger är korrekt konfigurerade</span><span class="sxs-lookup"><span data-stu-id="f4b9a-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="f4b9a-145">Verifiera att OAuth är korrekt aktive rad i Exchange på alla virtuella kataloger som Outlook kan använda genom att köra följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="f4b9a-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="f4b9a-146">Kontrol lera att **OAuth** är aktiverat på var och en av de här VDirs kommer det att se ut ungefär så här (och de viktigaste att titta på är ' OAuth '):</span><span class="sxs-lookup"><span data-stu-id="f4b9a-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="f4b9a-147">Om OAuth saknas från någon server och någon av de fyra virtuella katalogerna måste du lägga till den med relevanta kommandon innan du fortsätter ([set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)och [set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="f4b9a-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="f4b9a-148">Bekräfta att EvoSTS-auth-objektet finns</span><span class="sxs-lookup"><span data-stu-id="f4b9a-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="f4b9a-149">Återvänd till det lokala Exchange Management Shell för det här senaste kommandot.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="f4b9a-150">Nu kan du kontrol lera att din lokala tjänst har en post för evoSTS-autentiseringsprovidern:</span><span class="sxs-lookup"><span data-stu-id="f4b9a-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="f4b9a-151">Utdata ska visa en AuthServer av namnet EvoSts och läget ' Enabled ' ska vara sant.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="f4b9a-152">Om du inte ser det här ska du ladda ned och köra den senaste versionen av hybrid konfigurations guiden.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="f4b9a-153">**Viktigt** Om du kör Exchange 2010 i din miljö skapas inte EvoSTS.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="f4b9a-154">Aktivera HMA</span><span class="sxs-lookup"><span data-stu-id="f4b9a-154">Enable HMA</span></span>

<span data-ttu-id="f4b9a-155">Kör följande kommando i Exchange Management Shell, lokalt:</span><span class="sxs-lookup"><span data-stu-id="f4b9a-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="f4b9a-156">Kontroll</span><span class="sxs-lookup"><span data-stu-id="f4b9a-156">Verify</span></span>

<span data-ttu-id="f4b9a-157">När du har aktiverat HMA använder klientens nästa inloggning det nya trafikflödet.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="f4b9a-158">Observera att när du bara aktiverar HMA utlöses ingen reauktorisering för någon klient.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="f4b9a-159">Klienterna autentiseras baserat på de auth-token och/eller certifikat de har.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="f4b9a-160">Håll ned CTRL-tangenten samtidigt som du högerklickar på ikonen för Outlook-klienten (också i Windows Notifications-fältet) och klicka på "anslutnings status".</span><span class="sxs-lookup"><span data-stu-id="f4b9a-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="f4b9a-161">Leta efter klientens SMTP-adress mot "authn" \* -typen, som representerar Bearer-token som används i OAuth.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="f4b9a-162">**Obs!** Behöver du konfigurera Skype för företag med HMA?</span><span class="sxs-lookup"><span data-stu-id="f4b9a-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="f4b9a-163">Du behöver två artiklar: en som visar en lista med [topologier som stöds](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)och en som visar [hur](configure-skype-for-business-for-hybrid-modern-authentication.md)du konfigurerar.</span><span class="sxs-lookup"><span data-stu-id="f4b9a-163">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="f4b9a-164">Använda hybrid modern inloggningsautentisering med Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="f4b9a-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="f4b9a-165">Om du är en lokal kund med Exchange Server i TCP 443 ska du kringgå trafik bearbetning för följande IP-intervall:</span><span class="sxs-lookup"><span data-stu-id="f4b9a-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="f4b9a-166">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f4b9a-166">Related topics</span></span>

[<span data-ttu-id="f4b9a-167">Moderna konfigurations krav för inloggningsautentisering för över gång från Office 365 dedikerade/ITAR till vNext</span><span class="sxs-lookup"><span data-stu-id="f4b9a-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
