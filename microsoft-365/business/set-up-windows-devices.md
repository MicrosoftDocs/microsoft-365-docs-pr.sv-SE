---
title: Konfigurera Windows enheter för Microsoft 365 Business Premium användare
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
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
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Konfigurera Windows enheter med Windows 10 Pro för Microsoft 365 Business Premium och aktivera centraliserad hantering och säkerhetskontroller.
ms.openlocfilehash: 7a9c75f6ec14605225d40c103c18e62937e773bf
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635883"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="15fd3-103">Konfigurera Windows enheter för Microsoft 365 Business Premium användare</span><span class="sxs-lookup"><span data-stu-id="15fd3-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="15fd3-104">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="15fd3-104">Before you begin</span></span>

<span data-ttu-id="15fd3-105">Innan du kan konfigurera Windows-enheter för Microsoft 365 Business Premium-användare ska du se till att alla Windows-enheter kör Windows 10 Pro, version 1703 (Creators Update).</span><span class="sxs-lookup"><span data-stu-id="15fd3-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="15fd3-106">Windows 10 Pro är en förutsättning för att distribuera Windows 10 Business, vilket är en uppsättning molntjänster och funktioner för enhetshantering som kompletterar Windows 10 Pro och aktiverar centraliserad hantering och säkerhetskontroller i Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="15fd3-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="15fd3-107">Om du har Windows enheter med Windows 7 Pro, Windows 8 Pro eller Windows 8.1 Pro ger din Microsoft 365 Business Premium-prenumeration dig rätt att uppgradera Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="15fd3-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="15fd3-108">Följ stegen i det här avsnittet för att få mer information om hur du uppgraderar Windows-enheter till Windows 10 Pro Creators Update: [Uppgradera Windows-enheter till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="15fd3-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="15fd3-109">Se [Kontrollera att enheten är ansluten till Azure AD för](#verify-the-device-is-connected-to-azure-ad) att kontrollera att du har uppgraderingen eller om uppgraderingen fungerade.</span><span class="sxs-lookup"><span data-stu-id="15fd3-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

## <a name="watch-connect-your-pc-to-microsoft-365-business"></a><span data-ttu-id="15fd3-110">Titta: Anslut datorn till Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="15fd3-110">Watch: Connect your PC to Microsoft 365 Business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="15fd3-111">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="15fd3-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../business-video/index.yml).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="15fd3-112">Anslut Windows 10-enheter till organisationens Azure AD</span><span class="sxs-lookup"><span data-stu-id="15fd3-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="15fd3-113">När alla Windows-enheter i organisationen har uppgraderats till Windows 10 Pro Creators Update eller redan kör Windows 10 Pro Creators Update kan du ansluta de här enheterna till organisationens Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="15fd3-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="15fd3-114">När enheterna har anslutits uppgraderas de automatiskt till Windows 10 Business, som är en del av Microsoft 365 Business Premium prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="15fd3-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="15fd3-115">En helt ny eller nyligen uppgraderad Windows 10 Pro-enhet</span><span class="sxs-lookup"><span data-stu-id="15fd3-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="15fd3-116">Följ de här stegen för helt nya enheter som kör Windows 10 Pro Creators Update eller för enheter som uppgraderats till Windows 10 Pro Creators Update men som inte utfört konfiguration för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="15fd3-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="15fd3-117">Gå igenom konfigurationen av Windows 10-enheter tills du kommer till sidan **Hur vill du konfigurera?**</span><span class="sxs-lookup"><span data-stu-id="15fd3-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="15fd3-119">Välj Konfigurera **för en organisation och ange ditt** användarnamn och lösenord för att Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="15fd3-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="15fd3-120">Slutför konfigurationen av Windows 10-enhet.</span><span class="sxs-lookup"><span data-stu-id="15fd3-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="15fd3-p103">När du är klar är användaren ansluten till organisationens Azure AD. Kontrollera att allt är korrekt genom att läsa [Kontrollera att enheten är ansluten till Azure AD](#verify-the-device-is-connected-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="15fd3-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="15fd3-123">Enheter som redan är konfigurerade och använder Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="15fd3-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="15fd3-124">**Ansluta användare till Azure AD:**</span><span class="sxs-lookup"><span data-stu-id="15fd3-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="15fd3-125">Klicka på Windows-logotypen och sedan på inställningsikonen på användarens dator med Windows 10 Pro, version 1703 (Creators Update) (se [förutsättningar](pre-requisites-for-data-protection.md)).</span><span class="sxs-lookup"><span data-stu-id="15fd3-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="15fd3-127">I **Inställningar** går du till **Konton**.</span><span class="sxs-lookup"><span data-stu-id="15fd3-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="15fd3-129">På sidan **Din information** klickar du på **Åtkomst till arbete eller skola** \> **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="15fd3-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="15fd3-131">I dialogrutan **Konfigurera ett arbets- eller skolkonto** dialogrutan väljer du **Anslut den här enheten till Azure Active Directory** under **Alternativa åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="15fd3-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="15fd3-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="15fd3-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="15fd3-134">On the **Enter password** page, enter your password \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="15fd3-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="15fd3-136">Kontrollera **att informationen är korrekt på** sidan Kontrollera att detta är din organisation och välj **Anslut.**</span><span class="sxs-lookup"><span data-stu-id="15fd3-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.</span></span>
  
   <span data-ttu-id="15fd3-137">På sidan **Klart!**</span><span class="sxs-lookup"><span data-stu-id="15fd3-137">On the **You're all set!**</span></span> <span data-ttu-id="15fd3-138">väljer du **Chosse Done**.</span><span class="sxs-lookup"><span data-stu-id="15fd3-138">page, chosse **Done**.</span></span>
  
   ![På skärmen Kontrollera att detta är din organisation väljer du Anslut](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="15fd3-140">Om du laddade upp filer till OneDrive för företag, synkroniserar du dem med datorn.</span><span class="sxs-lookup"><span data-stu-id="15fd3-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="15fd3-141">Om du använde ett verktyg från tredje part för migrering av profil och filer, synkroniserar du även med den nya profilen.</span><span class="sxs-lookup"><span data-stu-id="15fd3-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="15fd3-142">Kontrollera att enheten är ansluten till Azure AD</span><span class="sxs-lookup"><span data-stu-id="15fd3-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="15fd3-143">Om du vill verifiera  din synkroniseringsstatus väljer du i området Ansluten till **_** _ på sidan Åtkomst till arbete eller skola i **Inställningar** för att visa knapparna \<organization name\> **Info** och Koppla **från.**</span><span class="sxs-lookup"><span data-stu-id="15fd3-143">To verify your sync status, on the **Access work or school** page in **Settings**, select the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="15fd3-144">Välj **Info för** att få din synkroniseringsstatus.</span><span class="sxs-lookup"><span data-stu-id="15fd3-144">Choose **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="15fd3-145">På sidan **Synkroniseringsstatus** väljer du **Synkronisera för** att få de senaste principerna för hantering av mobila enheter till datorn.</span><span class="sxs-lookup"><span data-stu-id="15fd3-145">On the **Sync status** page, choose **Sync** to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="15fd3-146">Om du vill Microsoft 365 Business Premium konto går du till Windows **Start,** högerklickar på den aktuella kontobilden och klickar sedan **på Växla konto.**</span><span class="sxs-lookup"><span data-stu-id="15fd3-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="15fd3-147">Logga in med din e-postadress och lösenord hos organisationen.</span><span class="sxs-lookup"><span data-stu-id="15fd3-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a><span data-ttu-id="15fd3-149">Kontrollera att datorn har uppgraderats till Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="15fd3-149">Verify the PC is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="15fd3-150">Kontrollera att dina Azure AD-Windows 10 enheter uppgraderas till Windows 10 Business som en del av Microsoft 365 Business Premium-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="15fd3-150">Verify that your Azure AD joined Windows 10 devices are upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="15fd3-151">Gå till **Inställningar** \> **System** \> **Om**.</span><span class="sxs-lookup"><span data-stu-id="15fd3-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="15fd3-152">Kontrollera att **Version** är **Windows 10 Business**.</span><span class="sxs-lookup"><span data-stu-id="15fd3-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="15fd3-154">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="15fd3-154">Next steps</span></span>

<span data-ttu-id="15fd3-155">Om du vill konfigurera dina mobila enheter kan du gå till Konfigurera mobila enheter för [Microsoft 365 Business Premium](set-up-mobile-devices.md)användare , Information om hur du anger principer för enhetsskydd eller programskydd finns i [Hantera Microsoft 365 för företag.](manage.md)</span><span class="sxs-lookup"><span data-stu-id="15fd3-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="related-content"></a><span data-ttu-id="15fd3-156">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="15fd3-156">Related content</span></span>

<span data-ttu-id="15fd3-157">[Microsoft 365 om utbildningsvideor för företag](../business-video/index.yml) (länksida)</span><span class="sxs-lookup"><span data-stu-id="15fd3-157">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>
