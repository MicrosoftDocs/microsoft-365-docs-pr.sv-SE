---
title: Planera för multifaktorautentisering för Office 365-distributioner
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig mer om multifaktorautentisering i Office 365 och de steg du behöver följa för att konfigurera den.
ms.openlocfilehash: 2e2cbc9d6d966a9858fafb62f08d26893c9f4353
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807579"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a><span data-ttu-id="af169-103">Planera för multifaktorautentisering för Office 365-distributioner</span><span class="sxs-lookup"><span data-stu-id="af169-103">Plan for multi-factor authentication for Office 365 Deployments</span></span>

<span data-ttu-id="af169-p101">Multifaktorautentisering (MFA) är en autentiseringsmetod som kräver att fler än en metod för verifiering används och lägger till ytterligare en säkerhetsnivå vid användarinloggningar och transaktioner. Den kräver två eller flera av följande verifieringsmetoder:</span><span class="sxs-lookup"><span data-stu-id="af169-p101">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions. It works by requiring any two or more of the following verification methods:</span></span>
  
- <span data-ttu-id="af169-106">Ett slumpmässigt genererad kod</span><span class="sxs-lookup"><span data-stu-id="af169-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="af169-107">Ett telefonsamtal</span><span class="sxs-lookup"><span data-stu-id="af169-107">A phone call</span></span>
    
- <span data-ttu-id="af169-108">Ett smartkort (virtuellt eller fysiskt)</span><span class="sxs-lookup"><span data-stu-id="af169-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="af169-109">En biometrisk enhet</span><span class="sxs-lookup"><span data-stu-id="af169-109">A biometric device</span></span> 
    
## <a name="multi-factor-authentication-in-office-365"></a><span data-ttu-id="af169-110">Multifaktorautentisering i Office 365</span><span class="sxs-lookup"><span data-stu-id="af169-110">Multi-factor authentication in Office 365</span></span>

<span data-ttu-id="af169-111">Office 365 använder multifaktorautentisering för att ge extra säkerhet och hanteras från Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="af169-111">Office 365 uses multi-factor authentication to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="af169-112">Office 365 erbjuder följande delmängd av funktionerna i Azure-multifaktorautentisering som en del av prenumerationen:</span><span class="sxs-lookup"><span data-stu-id="af169-112">Office 365 offers the following subset of Azure multi-factor authentication capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="af169-113">Möjligheten att aktivera och kräva multifaktorautentisering för slutanvändare</span><span class="sxs-lookup"><span data-stu-id="af169-113">The ability to enable and enforce multi-factor authentication for end users</span></span>
    
- <span data-ttu-id="af169-114">Användningen av en mobilapp (online och enstaka lösenord [OTP]) som en andra autentiseringsfaktor</span><span class="sxs-lookup"><span data-stu-id="af169-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="af169-115">Användningen av ett telefonsamtal som en andra autentiseringsfaktor</span><span class="sxs-lookup"><span data-stu-id="af169-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="af169-116">Användningen av ett sms-meddelande som en andra autentiseringsfaktor</span><span class="sxs-lookup"><span data-stu-id="af169-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="af169-117">Programlösenord för andra klienter än webbläsarklienter (t.ex. Microsoft Lync 2013-kommunikationsprogram)</span><span class="sxs-lookup"><span data-stu-id="af169-117">Application passwords for non browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="af169-118">Microsoft-standardhälsningar under telefonsamtal för autentisering</span><span class="sxs-lookup"><span data-stu-id="af169-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="af169-p103">En fullständiga lista över tillagda funktioner finns i [jämförelsen av Azure Multi-Factor Authentication-versioner](https://go.microsoft.com/fwlink/?LinkId=506927). Du kan alltid få den fullständiga uppsättningen funktioner genom att köpa Azure Multi-Factor Authentication-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="af169-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="af169-121">Du får en annan delmängd av funktionerna beroende på om du har en Endast molnet-distribution för Office 365 eller en hybridkonfiguration med enkel inloggning och Active Directory Federation Services (AD FS).</span><span class="sxs-lookup"><span data-stu-id="af169-121">You get a different subset of capabilities depending on whether you have a cloud-only deployment for Office 365 or a hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="af169-122">**Var hanterar du din Office 365-klientorganisation?**</span><span class="sxs-lookup"><span data-stu-id="af169-122">**Where do you manage your Office 365 tenant?**</span></span>|<span data-ttu-id="af169-123">**Alternativ för andra MFA-faktor**</span><span class="sxs-lookup"><span data-stu-id="af169-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af169-124">Endast molnet</span><span class="sxs-lookup"><span data-stu-id="af169-124">Cloud only</span></span>  <br/> |<span data-ttu-id="af169-125">Azure Active Directory MFA (text eller telefonsamtal)</span><span class="sxs-lookup"><span data-stu-id="af169-125">Azure Active Directory MFA (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="af169-126">Hybridkonfiguration som hanteras lokalt</span><span class="sxs-lookup"><span data-stu-id="af169-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="af169-127">Om du hanterar användaridentitet lokalt har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="af169-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="af169-128">Fysiskt eller virtuellt smartkort (AD FS)</span><span class="sxs-lookup"><span data-stu-id="af169-128">Physical or virtual smart card (AD FS)</span></span>  <br/> <span data-ttu-id="af169-129">[Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677) (modul för AD FS)</span><span class="sxs-lookup"><span data-stu-id="af169-129">[Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="af169-130">Azure AD MFA</span><span class="sxs-lookup"><span data-stu-id="af169-130">Azure AD MFA</span></span>  <br/> |
   
  
<span data-ttu-id="af169-p104">Följande bild visar hur de uppdaterade Office 2013-enhetsapparna (i Windows) gör det möjligt för användare att logga in med MFA. Office 2013-enhetsapparna har stöd för multifaktorautentisering genom användning av [ADAL (Active Directory Authentication Library)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure AD är värd för en webbsida där användarna kan logga in. Identitetsleverantören kan vara Azure AD eller en federerad identitetsleverantör som AD FS. Autentiseringen av federerade användare består av följande steg:</span><span class="sxs-lookup"><span data-stu-id="af169-p104">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA. TheOffice 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure AD hosts a webpage where users can sign in. The identity provider can be Azure AD or a federated identity provider like AD FS. The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="af169-p105">Azure AD omdirigerar användaren till den inloggningswebbsida som identitetsleverantören för Office 365-klientorganisationen är värd för. Identitetsleverantören fastställs av den domän som anges i användarens inloggningsnamn.</span><span class="sxs-lookup"><span data-stu-id="af169-p105">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the Office 365 tenant. The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="af169-138">Användaren loggar in på inloggningswebbsidan från sin enhet.</span><span class="sxs-lookup"><span data-stu-id="af169-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="af169-139">Identitetsleverantören returnerar en token till Azure AD när användaren har loggats in.</span><span class="sxs-lookup"><span data-stu-id="af169-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="af169-140">Azure AD returnerar en JSON-webbtoken (JWT) till Office-enhetsappen och enhetsappen autentiseras med hjälp av en JWT med Office 365.</span><span class="sxs-lookup"><span data-stu-id="af169-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Office 365.</span></span> 
    
<span data-ttu-id="af169-141">Det här visas detaljerat i följande bild:</span><span class="sxs-lookup"><span data-stu-id="af169-141">This is detailed in the following figure:</span></span>
  
![Modern autentisering för Office 2013-enhetsprogram.](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a><span data-ttu-id="af169-143">Programvarukrav</span><span class="sxs-lookup"><span data-stu-id="af169-143">Software requirements</span></span>

<span data-ttu-id="af169-144">Om du vill aktivera MFA för Office 2013-klientprogram måste du ha följande program installerade (versionen nedan eller en senare version) beroende på om du har en [Klicka-och-kör-baserade installationer](#click-to-run-based-installations) eller en [MSI-baserade installationer](#msi-based-installations).</span><span class="sxs-lookup"><span data-stu-id="af169-144">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="af169-145">Så här tar du reda på om Office-installationen är Klicka-och-kör- eller MSI-baserad:</span><span class="sxs-lookup"><span data-stu-id="af169-145">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="af169-146">Starta Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="af169-146">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="af169-147">Välj **Office-konto**på **Arkiv-menyn** .</span><span class="sxs-lookup"><span data-stu-id="af169-147">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="af169-p106">För Klicka-och-kör-baserade installationer av Outlook 2013 visas alternativet **Uppdateringsalternativ**. Alternativet **Uppdateringsalternativ** visas inte för MSI-baserade installationer.</span><span class="sxs-lookup"><span data-stu-id="af169-p106">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed. For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="af169-151">Klicka-och-kör-baserade installationer</span><span class="sxs-lookup"><span data-stu-id="af169-151">Click-to-run based installations</span></span>

<span data-ttu-id="af169-p107">För Klicka-och-kör-baserade installationer måste du ha följande program installerade, med filversionen som anges nedan eller en senare filversion. Om din filversion inte är lika med eller senare än den filversion som anges nedan uppdaterar du den genom att utföra följande steg.</span><span class="sxs-lookup"><span data-stu-id="af169-p107">For Click-to-run based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="af169-154">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="af169-154">**File name**</span></span>|<span data-ttu-id="af169-155">**Installationssökväg på datorn**</span><span class="sxs-lookup"><span data-stu-id="af169-155">**Install path on your computer**</span></span>|<span data-ttu-id="af169-156">**Filversion**</span><span class="sxs-lookup"><span data-stu-id="af169-156">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af169-157">Mso. Dll</span><span class="sxs-lookup"><span data-stu-id="af169-157">MSO.DLL</span></span>  <br/> |<span data-ttu-id="af169-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="af169-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="af169-159">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="af169-159">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="af169-160">Csi. Dll</span><span class="sxs-lookup"><span data-stu-id="af169-160">CSI.DLL</span></span>  <br/> |<span data-ttu-id="af169-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="af169-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="af169-162">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="af169-162">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="af169-163">Groove.EXE</span><span class="sxs-lookup"><span data-stu-id="af169-163">Groove.EXE</span></span>  <br/> |<span data-ttu-id="af169-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="af169-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="af169-165">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="af169-165">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="af169-166">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="af169-166">Outlook.exe</span></span>  <br/> |<span data-ttu-id="af169-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="af169-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="af169-168">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="af169-168">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="af169-169">ADAL. Dll</span><span class="sxs-lookup"><span data-stu-id="af169-169">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="af169-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="af169-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="af169-171">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="af169-171">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="af169-172">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="af169-172">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="af169-173">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="af169-173">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="af169-174">varierar</span><span class="sxs-lookup"><span data-stu-id="af169-174">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="af169-175">MSI-baserade installationer</span><span class="sxs-lookup"><span data-stu-id="af169-175">MSI-based installations</span></span>

<span data-ttu-id="af169-p108">För MSI-baserade installationer måste du ha följande program installerade, med filversionen som anges nedan eller en senare filversion. Om din filversion inte är lika med eller senare än den filversion som anges nedan uppdaterar du den med länken i kolumnen med KB-uppdateringsartikeln.</span><span class="sxs-lookup"><span data-stu-id="af169-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="af169-178">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="af169-178">**File name**</span></span>|<span data-ttu-id="af169-179">**Installationssökväg på datorn**</span><span class="sxs-lookup"><span data-stu-id="af169-179">**Install path on your computer**</span></span>|<span data-ttu-id="af169-180">**Här hämtar du uppdateringen**</span><span class="sxs-lookup"><span data-stu-id="af169-180">**Where to get the update**</span></span>|<span data-ttu-id="af169-181">**Version**</span><span class="sxs-lookup"><span data-stu-id="af169-181">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af169-182">Mso. Dll</span><span class="sxs-lookup"><span data-stu-id="af169-182">MSO.DLL</span></span>  <br/> |<span data-ttu-id="af169-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="af169-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="af169-184">KB3085480</span><span class="sxs-lookup"><span data-stu-id="af169-184">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="af169-185">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="af169-185">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="af169-186">Csi. Dll</span><span class="sxs-lookup"><span data-stu-id="af169-186">CSI.DLL</span></span>  <br/> |<span data-ttu-id="af169-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="af169-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="af169-188">KB3085504</span><span class="sxs-lookup"><span data-stu-id="af169-188">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="af169-189">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="af169-189">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="af169-190">Groove.exe</span><span class="sxs-lookup"><span data-stu-id="af169-190">Groove.exe</span></span>  <br/> |<span data-ttu-id="af169-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="af169-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="af169-192">KB3085509</span><span class="sxs-lookup"><span data-stu-id="af169-192">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="af169-193">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="af169-193">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="af169-194">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="af169-194">Outlook.exe</span></span>  <br/> |<span data-ttu-id="af169-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="af169-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="af169-196">KB3085495</span><span class="sxs-lookup"><span data-stu-id="af169-196">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="af169-197">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="af169-197">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="af169-198">ADAL. Dll</span><span class="sxs-lookup"><span data-stu-id="af169-198">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="af169-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="af169-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="af169-200">KB3055000</span><span class="sxs-lookup"><span data-stu-id="af169-200">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="af169-201">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="af169-201">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="af169-202">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="af169-202">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="af169-203">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="af169-203">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="af169-204">MS14-052</span><span class="sxs-lookup"><span data-stu-id="af169-204">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="af169-205">Ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="af169-205">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="af169-206">Aktivera MFA</span><span class="sxs-lookup"><span data-stu-id="af169-206">Enable MFA</span></span>

<span data-ttu-id="af169-207">Om du vill aktivera MFA måste du slutföra följande:</span><span class="sxs-lookup"><span data-stu-id="af169-207">To enable MFA, you have to complete the following:</span></span>
  
1. <span data-ttu-id="af169-208">Aktivera klienter för modern autentisering:</span><span class="sxs-lookup"><span data-stu-id="af169-208">Enable clients for modern authentication:</span></span>
    
  - <span data-ttu-id="af169-209">[Aktivera modern autentisering för Office 2013 på Windows-enheter](enable-modern-authentication.md) .</span><span class="sxs-lookup"><span data-stu-id="af169-209">[Enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md) .</span></span> 
    
  - <span data-ttu-id="af169-210">Konfigurera Azure MFA med katalogtjänster från tredje part.</span><span class="sxs-lookup"><span data-stu-id="af169-210">Set up Azure MFA with third-party directory services.</span></span>
    
    <span data-ttu-id="af169-211">Se [avancerade scenarier med Azure Multi-Factor Authentication och VPN-lösningar](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) från tredje part för information om specifika identitetsleverantörer som godkänts för det här programmet.</span><span class="sxs-lookup"><span data-stu-id="af169-211">See the [Advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. [<span data-ttu-id="af169-212">Konfigurera multifaktorautentisering för Office 365</span><span class="sxs-lookup"><span data-stu-id="af169-212">Set up multi-factor authentication for Office 365</span></span>](set-up-multi-factor-authentication.md)
    
3. <span data-ttu-id="af169-213">Förklara för enskilda användare hur de ska logga in med MFA: [Logga in på Office 365 med tvåstegsverifiering](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).</span><span class="sxs-lookup"><span data-stu-id="af169-213">Tell individual users how to sign in by MFA: [Sign in to Office 365 with 2-step verification](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="af169-p109">Om du har aktiverat dina användare för Azure AD MFA och de har enheter med Office 2013 som inte är aktiverade för modern autentisering, kommer de att behöva använda applösenord på de enheterna. Mer information om applösenord and när, var och hur de ska användas hittar du här: [Applösenord med Azure-multifaktorautentisering](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span><span class="sxs-lookup"><span data-stu-id="af169-p109">If you have enabled your users for Azure AD MFA and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use AppPasswords on those devices. More information on AppPasswords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span> 
  
## <a name="faq"></a><span data-ttu-id="af169-216">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="af169-216">FAQ</span></span>

[<span data-ttu-id="af169-217">Wikiartikel med vanliga frågor och svar om modern autentisering</span><span class="sxs-lookup"><span data-stu-id="af169-217">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 <span data-ttu-id="af169-218">**Kända problem:**</span><span class="sxs-lookup"><span data-stu-id="af169-218">**Known issues:**</span></span>
  
[<span data-ttu-id="af169-219">Modern autentisering för Office 2013 och Office 365 ProPlus: Bra att veta före integration</span><span class="sxs-lookup"><span data-stu-id="af169-219">Office 2013 and Office 365 ProPlus modern authentication : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="af169-220">**Felsöka Azure-multifaktorautentisering:**</span><span class="sxs-lookup"><span data-stu-id="af169-220">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="af169-221">Se [Felsöka Azure MFA](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span><span class="sxs-lookup"><span data-stu-id="af169-221">See [Troubleshoot Azure MFA](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="af169-222">Felsöka inloggningsproblem med modern autentisering för Office 2013 när du använder AD FS</span><span class="sxs-lookup"><span data-stu-id="af169-222">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="af169-223">**När alternativa ID:n inte fungerar:**</span><span class="sxs-lookup"><span data-stu-id="af169-223">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="af169-224">Så här använder du PowerShell för att åtgärda UPN-dubbletter</span><span class="sxs-lookup"><span data-stu-id="af169-224">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[<span data-ttu-id="af169-225">Skript för att åtgärda dubbletter av UPN-namn</span><span class="sxs-lookup"><span data-stu-id="af169-225">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 <span data-ttu-id="af169-226">**Filtrering av klientåtkomst:**</span><span class="sxs-lookup"><span data-stu-id="af169-226">**Client access filtering:**</span></span>
  
[<span data-ttu-id="af169-227">Principer för filtrering av klientåtkomst med modern autentisering för Office 2013 och Office 365: Bra att veta före integration</span><span class="sxs-lookup"><span data-stu-id="af169-227">Office 2013 and Office 365 ProPlus modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="af169-228">**Vilka program har stöd för MFA?**</span><span class="sxs-lookup"><span data-stu-id="af169-228">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="af169-229">**Windows**</span><span class="sxs-lookup"><span data-stu-id="af169-229">**Windows**</span></span>|<span data-ttu-id="af169-230">**Mac**</span><span class="sxs-lookup"><span data-stu-id="af169-230">**Mac**</span></span>|<span data-ttu-id="af169-231">**Ios**</span><span class="sxs-lookup"><span data-stu-id="af169-231">**iOS**</span></span>|<span data-ttu-id="af169-232">**Android-telefon**</span><span class="sxs-lookup"><span data-stu-id="af169-232">**Android phone**</span></span>|<span data-ttu-id="af169-233">**Android-surfplatta**</span><span class="sxs-lookup"><span data-stu-id="af169-233">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af169-234">Den här versionen har stöd för modern autentisering för Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016 Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 och Skype för företag.</span><span class="sxs-lookup"><span data-stu-id="af169-234">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="af169-235">Den här versionen har stöd för modern autentisering för Word 2016 för Mac, Excel 2016 för Mac och PowerPoint 2016 för Mac.</span><span class="sxs-lookup"><span data-stu-id="af169-235">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="af169-236">Den här versionen har stöd för modern autentisering för Word för iPad, Excel för iPad och PowerPoint för iPad.</span><span class="sxs-lookup"><span data-stu-id="af169-236">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="af169-237">Den här versionen har stöd för modern autentisering för Word för Android, Excel för Android och PowerPoint för Android.</span><span class="sxs-lookup"><span data-stu-id="af169-237">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="af169-238">Den här versionen har stöd för modern autentisering för Word för Android, Excel för Android och PowerPoint för Android.</span><span class="sxs-lookup"><span data-stu-id="af169-238">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="af169-239">Den här versionen har stöd för modern autentisering för Outlook 2013 och Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="af169-239">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="af169-240">Den här versionen har stöd för modern autentisering för Outlook 2016 för Mac.</span><span class="sxs-lookup"><span data-stu-id="af169-240">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="af169-241">Den här versionen har stöd för modern autentisering för Outlook för iPad.</span><span class="sxs-lookup"><span data-stu-id="af169-241">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

