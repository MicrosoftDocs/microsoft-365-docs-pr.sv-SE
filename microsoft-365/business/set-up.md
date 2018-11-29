---
title: Konfigurera Microsoft 365 Business med hjälp av installationsguiden
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Lär dig hur du konfigurerar Microsoft 365 Business genom att fylla i fyra steg.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982199"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="47412-103">Konfigurera Microsoft 365 Business med hjälp av installationsguiden</span><span class="sxs-lookup"><span data-stu-id="47412-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="47412-104">Slutför steg 1 – 4 nedan.</span><span class="sxs-lookup"><span data-stu-id="47412-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="47412-105">Konfigurera Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="47412-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="47412-106">Titta på en video om hur du konfigurerar Microsoft 365 Business när du inte har en lokal Active Directory:</span><span class="sxs-lookup"><span data-stu-id="47412-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="47412-p101">Installation steg innehåller information för inställningar som inkluderar lokala Active Directory. Om du vill fortsätta använda domänanslutna enheter läser följande artiklar för två olika sätt att aktivera som och slutför stegen innan du kör guiden:</span><span class="sxs-lookup"><span data-stu-id="47412-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="47412-109">Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="47412-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="47412-110">-Detta är det rekommenderade sättet.</span><span class="sxs-lookup"><span data-stu-id="47412-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="47412-111">Åtkomst på lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="47412-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="47412-112">Steg 1: Anpassa logga in</span><span class="sxs-lookup"><span data-stu-id="47412-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="47412-p102">Logga in på [Microsoft 365 Business](https://portal.microsoft.com) som global administratör. Välj panelen **Administratör** för att gå till administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="47412-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="47412-115">Välj **Påbörja installationen** (beroende på din region visas kanske **Fortsätt installationen** i stället) i administrationscentret för att starta guiden.</span><span class="sxs-lookup"><span data-stu-id="47412-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="47412-116">Ange domännamnet du vill använda (t.ex. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="47412-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="47412-p103">Gå vidare och ange din domän, även om du har verifierat när du använder Azure AD Connect, t.ex. Följande två steg gäller inte för dig om du har använt Azure AD Anslut för att verifiera din domän.</span><span class="sxs-lookup"><span data-stu-id="47412-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="47412-119">Följ stegen i guiden för att [Skapa DNS-poster på en DNS-värd leverantör för Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="47412-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="47412-p104">Du kan se en film som exempel [Video: installationsprogrammet för Office 365 i nya Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Observera att den här videon inte innehåller data protection stegen i Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="47412-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="47412-123">Steg 2: Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="47412-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="47412-124">Du kan lägga till användare här eller också kan du [lägga till användare senare](add-users-m365b.md) i administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="47412-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="47412-125">Alla användare tilldelas automatiskt en Microsoft 365 Business-licens.</span><span class="sxs-lookup"><span data-stu-id="47412-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="47412-p105">Om ditt Microsoft 365 Business-abonnemang har befintliga användare (till exempel om du använde Azure AD Connect), får du möjlighet att tilldela licenser till dem nu. Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="47412-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="47412-p106">Du får också möjlighet att dela autentiseringsuppgifter med de nya användarna som du har lagt till. Du kan välja att skriva ut, e-posta eller ladda ned.</span><span class="sxs-lookup"><span data-stu-id="47412-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="47412-130">Hoppa över steget att föra över e-postmeddelanden och välj **Nästa** på sidan **Migrera e-postmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="47412-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="47412-131">Om du flyttar från en annan leverantör av e-post och vill kopiera data senare, kan du [migrera e-post och kontakter till Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="47412-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="47412-133">Steg 3: Anslut din domän</span><span class="sxs-lookup"><span data-stu-id="47412-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="47412-134">Om du väljer att använda .onmicrosoft-domän eller Azure AD Connect, visas inte det här steget.</span><span class="sxs-lookup"><span data-stu-id="47412-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="47412-135">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="47412-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="47412-p107">Installationsguiden identifierar domänregistreraren normalt och ger en länk till stegvisa instruktioner för uppdatering av NS-poster via webbplatsen justitiesekreterare. Om den inte [Ändra nameservers att ställa in Office 365 med något domänregistrerare](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="47412-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="47412-138">E-post och andra tjänster konfigureras automatiskt</span><span class="sxs-lookup"><span data-stu-id="47412-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="47412-139">Steg 4: Hantera enheter och arbeta med filer</span><span class="sxs-lookup"><span data-stu-id="47412-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="47412-p108">Sidan Ange på **skydda arbete filer på dina mobila enheter** **hantera hur användare kan komma åt Office-filer på mobila enheter** inställningar och **skydda arbete filer går förlorade eller stulna enheter** **på**. Du kan också använda varje underordnad inställning genom att klicka på sparrarna vid varje inställning.</span><span class="sxs-lookup"><span data-stu-id="47412-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="47412-142">Alla licensierade användarnas arbete filer nu skyddas på iOS- och Android-enheter, så snart som de [installerar Office apps](set-up-mobile-devices.md) (och autentisera med sina autentiseringsuppgifter i Microsoft 365 Business).</span><span class="sxs-lookup"><span data-stu-id="47412-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="47412-144">På sidan **Ange Windows 10 enhetskonfigurationen** ställa **Säker Windows 10 enheter** **på**.</span><span class="sxs-lookup"><span data-stu-id="47412-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="47412-145">Du kan också använda varje underordnad inställning genom att klicka på ikonen bredvid den.</span><span class="sxs-lookup"><span data-stu-id="47412-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="47412-p109">Ange inställningen **Installera Office på Windows 10 enheter** till **Ja** om alla användare har Windows 10-datorer och inga befintliga Office installerar eller klicka-och-kör Office installeras. Om så inte är fallet kan du ange det här alternativet **Nej**. Du kan [installera Office automatiskt](auto-install-or-uninstall-office.md) senare från administratörscenter när du har förberett användarnas datorer. Instruktioner finns i [förbereda för installation av Office-klient](prepare-for-office-client-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="47412-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="47412-150">Licensierade användare arbetsfält på Windows 10 enheter kommer att projiceras så snart som de [ansluta sina Windows 10-enhet](set-up-windows-devices.md) till en Microsoft 365 Business Azure AD-domän eller [installera Windows 10 på en ny dator](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) medan du samtidigt ansluta till Microsoft 365 Business Azure AD-domänen.</span><span class="sxs-lookup"><span data-stu-id="47412-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="47412-151">Klicka på **Nästa** och du är klar med installationen.</span><span class="sxs-lookup"><span data-stu-id="47412-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="47412-152">Lämna oss feedback i det här steget för att hjälpa oss att förbättra upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="47412-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="47412-154">Ytterligare säkerhetsinställningar</span><span class="sxs-lookup"><span data-stu-id="47412-154">Additional security settings</span></span>

<span data-ttu-id="47412-155">Förutom säkerhet och regelefterlevnad inställning i guiden kan du också ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="47412-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="47412-p110">Ställa in skydd mot osäkra bifogade filer. **Avancerat skydd** (ATP) identifierar skadligt innehåll och blockerar leverans av osäkra bifogade filer, skydda mot phishing system och ransomware infektioner. Om du vill aktivera skydd för bifogade filer finns i [ställa in principer för Office 365 ATP säkra bifogade filer](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span><span class="sxs-lookup"><span data-stu-id="47412-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="47412-p111">Skydda när användaren klickar på skadliga länkar. ATP undersöker länkar i e-post när en användare klickar på dem.. Om en länk är osäkra, inte att besöka webbplatsen för användaren eller informeras om att webbplatsen har blockerats. Detta skyddar mot phishing system. [Konfigurera Office 365 ATP Safe länkar principer](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) eller [Konfigurera Office 365 ATP Safe länkar principer](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span><span class="sxs-lookup"><span data-stu-id="47412-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="47412-p112">Du kan behålla alla innehållet inklusive borttagna objekt genom att infoga hela postlådan för en användare i en **rättstvist håller**. Instruktioner finns i</span><span class="sxs-lookup"><span data-stu-id="47412-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="47412-166">[Ställ in e-lagring med Exchange Online-arkivering](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span><span class="sxs-lookup"><span data-stu-id="47412-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="47412-p113">Ställ in anpassade **principer för bevarande**, till exempel att bevara under en viss tid eller permanent ta bort innehåll i slutet av loggperioden. Du kan aktivera anpassade lagringsprinciper i regelefterlevnadscentret, gå till **Data-styre** och värdepapper \> **bevarande**och följ sedan stegen i guiden. Mer information finns i [Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="47412-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="47412-170">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="47412-170">Next steps</span></span>

<span data-ttu-id="47412-171">För de användare som har licenser, är nästa steg att konfigurera enheter.</span><span class="sxs-lookup"><span data-stu-id="47412-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="47412-172">Se [Konfigurera Windows-enheter för Microsoft 365 Business-användare](set-up-windows-devices.md) och [Konfigurera mobila enheter för Microsoft 365 Business-användare](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="47412-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="47412-173">Se [Hantera Microsoft 365 Business](manage.md) för länkar till information om hur du anger enhets- och programskyddsprinciper och hur du tar bort data från användares enheter.</span><span class="sxs-lookup"><span data-stu-id="47412-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


