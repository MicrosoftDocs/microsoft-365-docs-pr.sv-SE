---
title: Steg 5 Konfigurera federerad inloggningsautentisering för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: 'Sammanfattning: Konfigurera Azure AD Connect för din högprioriterade federerad verifikation för Microsoft 365 i Microsoft Azure.'
ms.openlocfilehash: f00763487261b62940ac5def38d35158db77a699
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694702"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="5bf82-103">Mellanliggande federerad autentiseringsläge med hög tillgänglighet: Konfigurera federerad auktorisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5bf82-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="5bf82-104">I den här delen av distribuera federerad verifiering med hög tillgänglighet för Microsoft 365 i Azure Infrastructure Services får du och installerar ett certifikat som utfärdats av en offentlig certifikat utfärdare, verifierar din konfiguration och sedan installerar och kör Azure AD Connect på servern för katalogpartition.</span><span class="sxs-lookup"><span data-stu-id="5bf82-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="5bf82-105">Azure AD Connect konfigurerar din Microsoft 365-prenumeration och AD FS (Active Directory Federation Services) och Webbprogramproxy-servrar för federerad-verifikation.</span><span class="sxs-lookup"><span data-stu-id="5bf82-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="5bf82-106">Se [distribuera federerad inloggningsautentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.</span><span class="sxs-lookup"><span data-stu-id="5bf82-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="5bf82-107">Skaffa ett offentligt certifikat och kopiera det till katalogpartitionen för servrar</span><span class="sxs-lookup"><span data-stu-id="5bf82-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="5bf82-108">Skaffa ett digitalt certifikat från en offentlig certifikat utfärdare med följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="5bf82-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="5bf82-109">Ett X. 509-certifikat som passar för att skapa SSL-anslutningar.</span><span class="sxs-lookup"><span data-stu-id="5bf82-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="5bf82-110">Den utökade egenskapen för ämnets alternativa namn (SAN) är inställd på FQDN-namnet på Federations tjänsten (till exempel: fs.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5bf82-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="5bf82-111">Certifikatet måste ha den privata och lagras i PFX-format.</span><span class="sxs-lookup"><span data-stu-id="5bf82-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="5bf82-112">Dessutom måste organisationens datorer och enheter lita på vilken offentlig certifikat utfärdare som utfärdar det digitala certifikatet.</span><span class="sxs-lookup"><span data-stu-id="5bf82-112">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate.</span></span> <span data-ttu-id="5bf82-113">Detta förtroende upprättas genom att ha ett rot certifikat från den offentliga certifikat utfärdare som är installerat i arkivet Betrodda rot certifikat utfärdare på dina datorer och enheter.</span><span class="sxs-lookup"><span data-stu-id="5bf82-113">This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices.</span></span> <span data-ttu-id="5bf82-114">Datorer som kör Microsoft Windows har vanligt vis en uppsättning dessa typer av certifikat installerade från vanliga certifikat utfärdare.</span><span class="sxs-lookup"><span data-stu-id="5bf82-114">Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities.</span></span> <span data-ttu-id="5bf82-115">Om rot certifikatet från din offentliga certifikat utfärdare inte redan är installerat måste du distribuera detta till dator och enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5bf82-115">If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="5bf82-116">För mer information om certifikat krav för federerad verifiering, se [förutsättningar för installation och konfiguration av Federation](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span><span class="sxs-lookup"><span data-stu-id="5bf82-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="5bf82-117">När du får ett certifikat kopierar du det till en mapp på C: s katalog-synkroniseringstjänst.</span><span class="sxs-lookup"><span data-stu-id="5bf82-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="5bf82-118">Du kan till exempel ge filen namnet SSL. pfx och lagra den i mappen C: \\ certifikat på servern för katalogpartition.</span><span class="sxs-lookup"><span data-stu-id="5bf82-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="5bf82-119">Verifiera din konfiguration</span><span class="sxs-lookup"><span data-stu-id="5bf82-119">Verify your configuration</span></span>

<span data-ttu-id="5bf82-120">Du bör nu vara redo att konfigurera Azure AD Connect och federerad inloggningsautentisering för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5bf82-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="5bf82-121">För att vara säker på att du är det här är en check lista:</span><span class="sxs-lookup"><span data-stu-id="5bf82-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="5bf82-122">Din organisations offentliga domän läggs till i din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="5bf82-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="5bf82-123">Organisationens Microsoft 365-användarkonton är konfigurerade till organisationens offentliga domän namn och kan logga in.</span><span class="sxs-lookup"><span data-stu-id="5bf82-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="5bf82-124">Du har fastställt ett FQDN-namn på Federations tjänsten baserat på det offentliga domän namnet.</span><span class="sxs-lookup"><span data-stu-id="5bf82-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="5bf82-125">En offentlig DNS-post för Federations tjänstens FQDN pekar på den offentliga IP-adressen till Internet-Facing Azure Load Balance för webbprogramproxy.</span><span class="sxs-lookup"><span data-stu-id="5bf82-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="5bf82-126">En privat DNS-post för Federations tjänstens FQDN pekar på den privata IP-adressen för den interna Azure-belastningsutjämnaren för AD FS-servrarna.</span><span class="sxs-lookup"><span data-stu-id="5bf82-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="5bf82-127">En offentlig certifikat utfärdare-isssued digitala certifikat som är lämpligt för SSL-anslutningar med SAN-servern som är FQDN-namnet på din Federations tjänst är en PFX-fil som lagras på servern för din katalog.</span><span class="sxs-lookup"><span data-stu-id="5bf82-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="5bf82-128">Rot certifikatet för den offentliga certifikat utfärdaren är installerat i arkivet Betrodda rot certifikat utfärdare på dina datorer och enheter.</span><span class="sxs-lookup"><span data-stu-id="5bf82-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="5bf82-129">Här är ett exempel för organisationen contoso:</span><span class="sxs-lookup"><span data-stu-id="5bf82-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="5bf82-130">**Exempel på konfiguration för en federerad infrastruktur med hög tillgänglighet i Azure**</span><span class="sxs-lookup"><span data-stu-id="5bf82-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Exempel på en konfiguration av infrastrukturen för Microsoft 365 federerad-autentiseringsprocessen i Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="5bf82-132">Kör Azure AD Connect för att konfigurera federerad</span><span class="sxs-lookup"><span data-stu-id="5bf82-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="5bf82-133">Azure AD Connect-verktyget konfigurerar AD FS-servrarna, Webbprogramproxy och Microsoft 365 för federerad behörighet med följande steg:</span><span class="sxs-lookup"><span data-stu-id="5bf82-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="5bf82-134">Skapa en anslutning till fjärr skrivbord till din katalogpartition med ett domän konto med lokala administratörs behörigheter.</span><span class="sxs-lookup"><span data-stu-id="5bf82-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="5bf82-135">Öppna Internet Explorer och gå till på Skriv bordet för katalogpartitionen [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="5bf82-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="5bf82-136">Klicka på **Hämta**på sidan **Microsoft Azure Active Directory Connect** och sedan på **Kör**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="5bf82-137">På sidan **Välkommen till Azure AD Connect** klickar du på **Jag accepterar**och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="5bf82-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="5bf82-138">Klicka på **Anpassa**på sidan **Express inställningar** .</span><span class="sxs-lookup"><span data-stu-id="5bf82-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="5bf82-139">Klicka på **Installera**på sidan **installera nödvändiga komponenter** .</span><span class="sxs-lookup"><span data-stu-id="5bf82-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="5bf82-140">På sidan **Användarinloggning** klickar du på **Federation med AD FS** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5bf82-141">På sidan **Anslut till Azure AD** skriver du in namnet och lösen ordet för ett globalt administratörs konto för Microsoft 365-prenumerationen och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="5bf82-142">På sidan **Anslut dina kataloger** ser du till att din lokala AD DS-skog (Active Directory Domain Services) är markerad i **skogen**, anger namn och lösen ord för ett domän administratörs konto, klickar på **Lägg till katalog**och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="5bf82-143">Klicka på **Nästa**på sidan **konfiguration av inloggning med Azure AD** .</span><span class="sxs-lookup"><span data-stu-id="5bf82-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="5bf82-144">Klicka på **Nästa**på sidan **Domain and ou filter** .</span><span class="sxs-lookup"><span data-stu-id="5bf82-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="5bf82-145">På sidan **unik identifiering av användare** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="5bf82-146">Klicka på **Nästa**på sidan **filtrera användare och enheter** .</span><span class="sxs-lookup"><span data-stu-id="5bf82-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="5bf82-147">På sidan **valfria funktioner** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="5bf82-148">Klicka på **Konfigurera en ny AD FS-servergrupp**på sidan **AD FS-servergrupp** .</span><span class="sxs-lookup"><span data-stu-id="5bf82-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="5bf82-149">Klicka på **Bläddra** och ange plats och namn för SSL-certifikatet från den offentliga certifikat utfärdaren.</span><span class="sxs-lookup"><span data-stu-id="5bf82-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="5bf82-150">Ange lösen ordet för certifikatet när du uppmanas till det och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="5bf82-151">Kontrol lera att **subjekt namnet** och **namn på Federations tjänsten** är inställda på ditt FQDN för Federations tjänsten och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="5bf82-152">På sidan **AD FS-servrar** skriver du in namnet på den första AD FS-servern (tabell M-objekt 4-kolumnen virtuell dator) och klickar sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="5bf82-153">Skriv in namnet på den andra AD FS-servern (tabell M-item 5-namn kolumnen virtuell dator), klicka på **Lägg till**och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="5bf82-154">Skriv in namnet på den första Web Application-proxyservern (tabell M-item 6 – kolumnen Namn på virtuell dator) på sidan **Webbprogramproxy** och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="5bf82-155">Skriv in namnet på den andra webb program servern (tabell M-item 7-namn kolumnen virtuell dator), klicka på **Lägg till**och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="5bf82-156">Ange användar namn och lösen ord för ett domän administratörs konto på sidan **domän administratörs behörighet** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="5bf82-157">På sidan **AD FS-** tjänstkonto anger du användar namn och lösen ord för ett företags administratörs konto och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="5bf82-158">På sidan **Azure AD-domän** i **Domain**väljer du organisationens DNS-domännamn och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="5bf82-159">På sidan **Klart att konfigurera** klickar du på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="5bf82-160">På sidan **Installationen är slutförd** klickar du på **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-160">On the **Installation complete** page, click **Verify**.</span></span> <span data-ttu-id="5bf82-161">Två meddelanden visar att både intranät-och Internet konfigurationen verifierades.</span><span class="sxs-lookup"><span data-stu-id="5bf82-161">You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="5bf82-162">Intranät meddelandet ska ange den privata IP-adressen för din Azure Internal-belastningsutjämnare för dina AD FS-servrar.</span><span class="sxs-lookup"><span data-stu-id="5bf82-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="5bf82-163">Internet meddelandet ska ange den offentliga IP-adressen för din Azure Internet-belastnings balansering för dina Web Application Proxy-servrar.</span><span class="sxs-lookup"><span data-stu-id="5bf82-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="5bf82-164">På sidan **Installationen är slutförd** klickar du på **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="5bf82-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="5bf82-165">Här är den sista konfigurationen med namn på plats hållare för servrarna.</span><span class="sxs-lookup"><span data-stu-id="5bf82-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="5bf82-166">**Fas 5: slutgiltig konfiguration av en federerad infrastruktur med hög tillgänglighet i Azure**</span><span class="sxs-lookup"><span data-stu-id="5bf82-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![Den sista konfigurationen av infrastrukturen för extern tillgänglighet i Microsoft 365 i Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="5bf82-168">Infrastrukturen för federerad infrastruktur med hög tillgänglighet för Microsoft 365 i Azure är klar.</span><span class="sxs-lookup"><span data-stu-id="5bf82-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5bf82-169">Se även</span><span class="sxs-lookup"><span data-stu-id="5bf82-169">See Also</span></span>

[<span data-ttu-id="5bf82-170">Distribuera federerad för hög tillgänglighet för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="5bf82-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="5bf82-171">Federerad identitet för din Microsoft 365-miljö</span><span class="sxs-lookup"><span data-stu-id="5bf82-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="5bf82-172">Microsoft 365-center för lösningar och arkitektur</span><span class="sxs-lookup"><span data-stu-id="5bf82-172">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

[<span data-ttu-id="5bf82-173">Federerad identitet för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5bf82-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)


