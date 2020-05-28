---
title: Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Lär dig hur du konfigurerar Windows-enheter som kör Windows 10 Pro för Microsoft 365 Business Premium-användare, vilket aktiverar centraliserad hantering och säkerhetskontroller.
ms.openlocfilehash: ecd9f5aa348d29d34e77061657619c015b09c41a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402967"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="b9095-103">Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare</span><span class="sxs-lookup"><span data-stu-id="b9095-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="b9095-104">Förutsättningar för att konfigurera Windows-enheter för Microsoft 365 Business Premium-användare</span><span class="sxs-lookup"><span data-stu-id="b9095-104">Prerequisites for setting up Windows devices for Microsoft 365 Business Premium users</span></span>

<span data-ttu-id="b9095-105">Innan du kan konfigurera Windows-enheter för Microsoft 365 Business Premium-användare kontrollerar du att alla Windows-enheter kör Windows 10 Pro, version 1703 (Creators Update).</span><span class="sxs-lookup"><span data-stu-id="b9095-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="b9095-106">Windows 10 Pro är en förutsättning för distribution av Windows 10 Business, som är en uppsättning molntjänster och enhetshanteringsfunktioner som kompletterar Windows 10 Pro och aktiverar centraliserade hanterings- och säkerhetskontroller av Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b9095-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="b9095-107">Om du har Windows-enheter som kör Windows 7 Pro, Windows 8 Pro eller Windows 8.1 Pro ger din Microsoft 365 Business Premium-prenumeration dig rätt till en Windows 10-uppgradering.</span><span class="sxs-lookup"><span data-stu-id="b9095-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="b9095-108">Följ stegen i det här avsnittet för att få mer information om hur du uppgraderar Windows-enheter till Windows 10 Pro Creators Update: [Uppgradera Windows-enheter till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="b9095-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="b9095-109">Se [Verifiera att enheten är ansluten till Azure AD](#verify-the-device-is-connected-to-azure-ad) för att verifiera att du har uppgraderingen eller för att se till att uppgraderingen fungerade.</span><span class="sxs-lookup"><span data-stu-id="b9095-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="b9095-110">Titta på en kort video om hur du ansluter Windows till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9095-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="b9095-111">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="b9095-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="b9095-112">Anslut Windows 10-enheter till organisationens Azure AD</span><span class="sxs-lookup"><span data-stu-id="b9095-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="b9095-113">När alla Windows-enheter i organisationen antingen har uppgraderats till Windows 10 Pro Creators Update eller redan kör Windows 10 Pro Creators Update kan du ansluta dessa enheter till organisationens Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9095-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="b9095-114">När enheterna har anslutits uppgraderas de automatiskt till Windows 10 Business, som ingår i din Microsoft 365 Business Premium-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="b9095-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="b9095-115">En helt ny eller nyligen uppgraderad Windows 10 Pro-enhet</span><span class="sxs-lookup"><span data-stu-id="b9095-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="b9095-116">Följ de här stegen för helt nya enheter som kör Windows 10 Pro Creators Update eller för enheter som uppgraderats till Windows 10 Pro Creators Update men som inte utfört konfiguration för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="b9095-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="b9095-117">Gå igenom konfigurationen av Windows 10-enheter tills du kommer till sidan **Hur vill du konfigurera?**</span><span class="sxs-lookup"><span data-stu-id="b9095-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="b9095-119">Här väljer du **Konfigurera för en organisation** och anger sedan ditt användarnamn och lösenord för Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b9095-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="b9095-120">Slutför konfigurationen av Windows 10-enhet.</span><span class="sxs-lookup"><span data-stu-id="b9095-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="b9095-p103">När du är klar är användaren ansluten till organisationens Azure AD. Kontrollera att allt är korrekt genom att läsa [Kontrollera att enheten är ansluten till Azure AD](#verify-the-device-is-connected-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="b9095-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="b9095-123">Enheter som redan är konfigurerade och använder Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="b9095-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="b9095-124">**Ansluta användare till Azure AD:**</span><span class="sxs-lookup"><span data-stu-id="b9095-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="b9095-125">Klicka på Windows-logotypen och sedan på inställningsikonen på användarens dator med Windows 10 Pro, version 1703 (Creators Update) (se [förutsättningar](pre-requisites-for-data-protection.md)).</span><span class="sxs-lookup"><span data-stu-id="b9095-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="b9095-127">I **Inställningar** går du till **Konton**.</span><span class="sxs-lookup"><span data-stu-id="b9095-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="b9095-129">På sidan **Din information** klickar du på **Åtkomst till arbete eller skola** \> **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="b9095-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="b9095-131">I dialogrutan **Konfigurera ett arbets- eller skolkonto** dialogrutan väljer du **Anslut den här enheten till Azure Active Directory** under **Alternativa åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="b9095-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="b9095-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="b9095-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="b9095-134">On the **Enter password** page, enter your password \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="b9095-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="b9095-136">Kontrollera att informationen är korrekt på sidan Kontrollera att **informationen är** korrekt och klicka på Gå **med**.</span><span class="sxs-lookup"><span data-stu-id="b9095-136">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="b9095-p104">På sidan **Klart!** klickar du på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="b9095-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="b9095-140">Om du laddade upp filer till OneDrive för företag, synkroniserar du dem med datorn.</span><span class="sxs-lookup"><span data-stu-id="b9095-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="b9095-141">Om du använde ett verktyg från tredje part för att migrera profil och filer synkroniserar du även dem med den nya profilen.</span><span class="sxs-lookup"><span data-stu-id="b9095-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="b9095-142">Kontrollera att enheten är ansluten till Azure AD</span><span class="sxs-lookup"><span data-stu-id="b9095-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="b9095-143">Om du vill verifiera synkroniseringsstatus klickar du i området **Anslut till** _ _ på sidan Access för arbete eller **skola** i **Inställningar**för att \<organization name\> visa knapparna **Info** och **Koppla från**.</span><span class="sxs-lookup"><span data-stu-id="b9095-143">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="b9095-144">Klicka på **Info** för att få din synkroniseringsstatus.</span><span class="sxs-lookup"><span data-stu-id="b9095-144">Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="b9095-145">Klicka på Synkronisera på sidan Synkroniseringsstatus synkronisering för att hämta de senaste hanteringsprinciperna för mobila enheter till datorn.</span><span class="sxs-lookup"><span data-stu-id="b9095-145">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="b9095-146">Om du vill börja använda Microsoft 365 Business Premium-kontot går du till **Start-knappen i** Windows, högerklickar på din aktuella kontobild och byter sedan **konto**.</span><span class="sxs-lookup"><span data-stu-id="b9095-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="b9095-147">Logga in med din e-postadress och lösenord hos organisationen.</span><span class="sxs-lookup"><span data-stu-id="b9095-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="b9095-149">Kontrollera att enheten uppgraderats till Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="b9095-149">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="b9095-150">Kontrollera att dina Azure AD-anslutna Windows 10-enheter har uppgraderats till Windows 10 Business som en del av din Microsoft 365 Business Premium-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="b9095-150">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="b9095-151">Gå till **Inställningar** \> **System** \> **Om**.</span><span class="sxs-lookup"><span data-stu-id="b9095-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="b9095-152">Kontrollera att **Version** är **Windows 10 Business**.</span><span class="sxs-lookup"><span data-stu-id="b9095-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="b9095-154">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b9095-154">Next steps</span></span>

<span data-ttu-id="b9095-155">Information om hur du konfigurerar dina mobila enheter finns i [Konfigurera mobila enheter för Microsoft 365 Business Premium-användare](set-up-mobile-devices.md), Så här anger du principer för enhetsskydd eller appskydd, Hantera Microsoft [365 för företag](manage.md).</span><span class="sxs-lookup"><span data-stu-id="b9095-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a><span data-ttu-id="b9095-156">Mer information om hur du konfigurerar och använder Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b9095-156">For more on setting up and using Microsoft 365 Business Premium</span></span>

[<span data-ttu-id="b9095-157">Utbildningsvideor för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b9095-157">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
