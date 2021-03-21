---
title: Hög tillgänglighet federerad autentisering Fas 5 Konfigurera federerad autentisering för Microsoft 365
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
description: Sammanfattning Konfigurera Azure AD Connect för hög tillgänglighet federerad autentisering för Microsoft 365 i Microsoft Azure.
ms.openlocfilehash: 2bca2b758486b85d185870e2e14b495b8f084cb7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929414"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="91b91-103">Fas 5 med hög tillgänglighet för federerad autentisering: Konfigurera federerad autentisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91b91-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="91b91-104">I den här sista fasen av distributionen av federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure-infrastrukturtjänster får du och installerar ett certifikat som utfärdats av en offentlig certifikatutfärdare, verifierar din konfiguration och installerar och kör sedan Azure AD Connect på katalogsynkroniseringsservern.</span><span class="sxs-lookup"><span data-stu-id="91b91-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="91b91-105">Azure AD Connect konfigurerar Microsoft 365-prenumerationen och AD FS-servrar (Active Directory Federation Services) och webbprogramproxyservrar för federerad autentisering.</span><span class="sxs-lookup"><span data-stu-id="91b91-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="91b91-106">Se [Distribuera hög tillgänglighet federerad autentisering för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.</span><span class="sxs-lookup"><span data-stu-id="91b91-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="91b91-107">Skaffa ett offentligt certifikat och kopiera det till katalogsynkroniseringsservern</span><span class="sxs-lookup"><span data-stu-id="91b91-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="91b91-108">Få ett digitalt certifikat från en offentlig certifikatutfärdare med följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="91b91-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="91b91-109">Ett X.509-certifikat som passar för att skapa SSL-anslutningar.</span><span class="sxs-lookup"><span data-stu-id="91b91-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="91b91-110">Den utökade egenskapen Subject Alternative Name (SAN) är inställd på federationstjänstens FQDN (exempel: fs.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="91b91-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="91b91-111">Certifikatet måste ha den privata nyckeln och lagras i PFX-format.</span><span class="sxs-lookup"><span data-stu-id="91b91-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="91b91-112">Dessutom måste datorerna och enheterna i organisationen lita på den offentliga certifikatutfärdare som utfärdar det digitala certifikatet.</span><span class="sxs-lookup"><span data-stu-id="91b91-112">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate.</span></span> <span data-ttu-id="91b91-113">Det här förtroende upprättas genom att ha ett rotcertifikat från den offentliga certifikatutfärdaren som är installerat i arkivet med betrodda rotcertifikatutfärdare på dina datorer och enheter.</span><span class="sxs-lookup"><span data-stu-id="91b91-113">This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices.</span></span> <span data-ttu-id="91b91-114">Datorer med Microsoft Windows har vanligtvis en uppsättning av dessa typer av certifikat installerade från vanliga certifikatutfärdare.</span><span class="sxs-lookup"><span data-stu-id="91b91-114">Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities.</span></span> <span data-ttu-id="91b91-115">Om rotcertifikatet från din offentliga certifikatutfärdare inte redan är installerat måste du distribuera det till datorerna och enheterna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="91b91-115">If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="91b91-116">Mer information om certifikatkrav för federerad autentisering finns i Förutsättningar för installation och [konfiguration av federerad autentisering.](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration)</span><span class="sxs-lookup"><span data-stu-id="91b91-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="91b91-117">När du får certifikatet kopierar du det till en mapp på C:-enheten på katalogsynkroniseringsservern.</span><span class="sxs-lookup"><span data-stu-id="91b91-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="91b91-118">Du kan till exempel ge filen namnet SSL.pfx och lagra den i mappen C: \\ Certs på katalogsynkroniseringsservern.</span><span class="sxs-lookup"><span data-stu-id="91b91-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="91b91-119">Verifiera konfigurationen</span><span class="sxs-lookup"><span data-stu-id="91b91-119">Verify your configuration</span></span>

<span data-ttu-id="91b91-120">Nu bör du vara redo att konfigurera Azure AD Connect och federerad autentisering för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="91b91-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="91b91-121">För att säkerställa att du är det finns här en checklista:</span><span class="sxs-lookup"><span data-stu-id="91b91-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="91b91-122">Organisationens offentliga domän läggs till i Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="91b91-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="91b91-123">Din organisations Microsoft 365-användarkonton är konfigurerade för organisationens offentliga domännamn och kan logga in.</span><span class="sxs-lookup"><span data-stu-id="91b91-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="91b91-124">Du har fastställt en FQDN för en federationstjänst baserat på ditt offentliga domännamn.</span><span class="sxs-lookup"><span data-stu-id="91b91-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="91b91-125">En offentlig DNS A-post för federationstjänstens FQDN pekar på den offentliga IP-adressen för den Internetbaserade Azure-belastningsutjämaren för webbprogramproxyservrarna.</span><span class="sxs-lookup"><span data-stu-id="91b91-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="91b91-126">En privat DNS A-post för federationstjänstens FQDN pekar på den privata IP-adressen för den interna Azure-belastningsutjämaren för AD FS-servrarna.</span><span class="sxs-lookup"><span data-stu-id="91b91-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="91b91-127">En offentlig certifikatutfärdare är ett digitalt certifikat som passar för SSL-anslutningar med SAN-uppsättningen till federationstjänstens FQDN är en PFX-fil som lagras på din katalogsynkroniseringsserver.</span><span class="sxs-lookup"><span data-stu-id="91b91-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="91b91-128">Rotcertifikatet för den offentliga certifikatutfärdaren installeras i arkivet Betrodda rotcertifikatutfärdare på dina datorer och enheter.</span><span class="sxs-lookup"><span data-stu-id="91b91-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="91b91-129">Här är ett exempel för Contoso-organisationen:</span><span class="sxs-lookup"><span data-stu-id="91b91-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="91b91-130">**En exempelkonfiguration för en infrastruktur för federerad autentisering med hög tillgänglighet i Azure**</span><span class="sxs-lookup"><span data-stu-id="91b91-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Ett exempel på en konfiguration av microsoft 365-infrastrukturen för federerad autentisering med hög tillgänglighet i Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="91b91-132">Kör Azure AD Connect för att konfigurera federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="91b91-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="91b91-133">Verktyget Azure AD Connect konfigurerar AD FS-servrarna, webbprogramproxyservrarna och Microsoft 365 för federerad autentisering med följande steg:</span><span class="sxs-lookup"><span data-stu-id="91b91-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="91b91-134">Skapa en anslutning till fjärrskrivbord till katalogsynkroniseringsservern med ett domänkonto som har lokal administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="91b91-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="91b91-135">Öppna Internet Explorer på skrivbordet på katalogsynkroniseringsservern och gå till [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="91b91-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="91b91-136">På sidan **Microsoft Azure Active Directory Connect** klickar du på **Ladda** ned och sedan på **Kör**.</span><span class="sxs-lookup"><span data-stu-id="91b91-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="91b91-137">På sidan **Välkommen till Azure AD Connect** klickar du på Jag **godkänner** och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="91b91-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="91b91-138">På sidan **Expressinställningar klickar** du på **Anpassa**.</span><span class="sxs-lookup"><span data-stu-id="91b91-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="91b91-139">Klicka på **Installera på sidan** Installera nödvändiga **komponenter.**</span><span class="sxs-lookup"><span data-stu-id="91b91-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="91b91-140">På sidan **Användarinloggning** klickar du på **Federation med AD FS** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="91b91-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="91b91-141">På sidan **Anslut till Azure AD** anger du namn och lösenord för ett globalt administratörskonto för Microsoft 365-prenumerationen och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="91b91-142">På  sidan Anslut dina kataloger ser du till att din lokala AD DS-skog (Active Directory Domain Services) är vald i **Skog,** skriver namn och lösenord för ett domänadministratörskonto, klickar på Lägg till katalog och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="91b91-143">På sidan **Konfiguration av Azure AD-inloggning** klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="91b91-144">På sidan **Domän- och OU-filtrering** klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="91b91-145">På sidan **Unikt identifiera dina användare** klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="91b91-146">På sidan **Filtrera användare och enheter** klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="91b91-147">På sidan **Valfria funktioner** klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="91b91-148">På sidan **AD FS-servergrupp** klickar du på **Konfigurera en ny AD FS-servergrupp**.</span><span class="sxs-lookup"><span data-stu-id="91b91-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="91b91-149">Klicka **på** Bläddra och ange plats och namn för SSL-certifikatet från den offentliga certifikatutfärdaren.</span><span class="sxs-lookup"><span data-stu-id="91b91-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="91b91-150">När du uppmanas till det anger du certifikatlösenordet och klickar sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="91b91-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="91b91-151">Kontrollera att **Ämnesnamn** och **Federationstjänstnamn** är inställda på federationstjänstens FQDN och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="91b91-152">På **sidan AD FS-servrar** skriver du den första AD FS-serverns namn (tabell M - objekt 4 – namnkolumn för virtuell dator) och klickar sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="91b91-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="91b91-153">Skriv namnet på den andra AD FS-servern (tabell M - objekt 5 – namnkolumn för virtuell dator), klicka på Lägg till och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="91b91-154">På sidan **Proxyservrar** för webbprogram skriver du det första webbprogrammets proxyservernamn (tabell M - objekt 6 – namnkolumn för virtuell dator) och klickar sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="91b91-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="91b91-155">Skriv namnet på proxyservern för det andra webbprogrammet (tabell M - objekt 7 – namnkolumn för virtuell dator), klicka på Lägg till och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="91b91-156">På sidan **Autentiseringsuppgifter för domänadministratör** anger du användarnamn och lösenord för ett domänadministratörskonto och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="91b91-157">På sidan **AD FS-tjänstkonto** anger du användarnamn och lösenord för ett företagsadministratörskonto och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="91b91-158">Välj din **organisations DNS-domännamn** i **Domän** på sidan Azure AD Domain och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="91b91-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="91b91-159">På sidan **Klart att konfigurera** klickar du på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="91b91-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="91b91-160">På sidan **Installationen är slutförd** klickar du på **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="91b91-160">On the **Installation complete** page, click **Verify**.</span></span> <span data-ttu-id="91b91-161">Du bör se två meddelanden som anger att både intranätet och Internetkonfigurationen har verifierats.</span><span class="sxs-lookup"><span data-stu-id="91b91-161">You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="91b91-162">Intranätmeddelandet ska lista den privata IP-adressen för dina interna Azure-belastningsutjämnare för AD FS-servrarna.</span><span class="sxs-lookup"><span data-stu-id="91b91-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="91b91-163">Internetmeddelandet ska lista den offentliga IP-adressen för din Azure-belastningsutjämnare för dina proxyservrar för webbprogram.</span><span class="sxs-lookup"><span data-stu-id="91b91-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="91b91-164">På sidan **Installationen är slutförd** klickar du på **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="91b91-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="91b91-165">Här är den slutliga konfigurationen, med platshållarnamn för servrarna.</span><span class="sxs-lookup"><span data-stu-id="91b91-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="91b91-166">**Fas 5: Den slutliga konfigurationen av en infrastruktur för federerad autentisering med hög tillgänglighet i Azure**</span><span class="sxs-lookup"><span data-stu-id="91b91-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![Den slutliga konfigurationen av microsoft 365-infrastrukturen för federerad autentisering med hög tillgänglighet i Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="91b91-168">Din hög tillgänglighetsinfrastruktur för federerad autentisering för Microsoft 365 i Azure är klar.</span><span class="sxs-lookup"><span data-stu-id="91b91-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91b91-169">Se även</span><span class="sxs-lookup"><span data-stu-id="91b91-169">See Also</span></span>

[<span data-ttu-id="91b91-170">Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure</span><span class="sxs-lookup"><span data-stu-id="91b91-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="91b91-171">Federerad identitet för din Utvecklings-/testmiljö för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91b91-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="91b91-172">Microsoft 365-lösning och arkitekturcenter</span><span class="sxs-lookup"><span data-stu-id="91b91-172">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)

[<span data-ttu-id="91b91-173">Federerad identitet för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91b91-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)