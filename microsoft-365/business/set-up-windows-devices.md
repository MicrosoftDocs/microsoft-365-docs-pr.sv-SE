---
title: Konfigurera Windows-enheter för Microsoft 365 Business-användare
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Lär dig hur du ställer in Windows-enheter som kör Windows 10 Pro för Microsoft 365 företagsanvändare. '
ms.openlocfilehash: 482199b175c568bfae420619aa02024303894789
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982859"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="aa776-103">Konfigurera Windows-enheter för Microsoft 365 Business-användare</span><span class="sxs-lookup"><span data-stu-id="aa776-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa776-104">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="aa776-104">Prerequisites</span></span>

<span data-ttu-id="aa776-p101">Innan du kan konfigurera Windows-enheter för Microsoft 365 Business-användare ska du se till att alla Windows-enheter använder Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro är en förutsättning för att använda Windows 10 Business, vilket är en uppsättning molntjänster och funktioner för enhetshantering som kompletterar Windows 10 Pro och ger tillgång till centraliserad hantering och säkerhetskontroller i Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="aa776-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="aa776-107">Om du har Windows-enheter som kör Windows 7 Pro, Windows 8 Pro eller Windows 8.1 Pro ger Microsoft 365 Business-prenumerationen dig rätt att uppgradera till Windows 10.</span><span class="sxs-lookup"><span data-stu-id="aa776-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="aa776-108">Följ stegen i det här avsnittet för att få mer information om hur du uppgraderar Windows-enheter till Windows 10 Pro Creators Update: [Uppgradera Windows-enheter till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="aa776-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="aa776-109">Läs [Kontrollera att enheten uppgraderats till Windows 10 Business](set-up-windows-devices.md#bkmk_verifywin10) och kontrollera att du har uppgraderingen och att uppgraderingen fungerade.</span><span class="sxs-lookup"><span data-stu-id="aa776-109">See [Verify the device is upgraded to Windows 10 Business](set-up-windows-devices.md#bkmk_verifywin10) to verify you have the upgrade, or to make sure the upgrade worked.</span></span> 
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="aa776-110">Anslut Windows 10-enheter till organisationens Azure AD</span><span class="sxs-lookup"><span data-stu-id="aa776-110">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="aa776-p102">När alla Windows-enheter i organisationen har uppgraderats till Windows 10 Pro Creators Update eller redan använder Windows 10 Pro Creators Update kan du lägga till enheterna i organisationens Azure Active Directory. När enheterna läggs till uppgraderas de automatiskt till Windows 10 Business som är en del av Microsoft 365 Business-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="aa776-p102">Once all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory. Once the devices are joined, they will automatically be upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="aa776-113">En helt ny eller nyligen uppgraderad Windows 10 Pro-enhet</span><span class="sxs-lookup"><span data-stu-id="aa776-113">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="aa776-114">Följ de här stegen för helt nya enheter som kör Windows 10 Pro Creators Update eller för enheter som uppgraderats till Windows 10 Pro Creators Update men som inte utfört konfiguration för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="aa776-114">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="aa776-115">Gå igenom konfigurationen av Windows 10-enheter tills du kommer till sidan **Hur vill du konfigurera?**</span><span class="sxs-lookup"><span data-stu-id="aa776-115">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="aa776-117">Välj **Konfigurera för en organisation** och ange användarnamn och lösenord för Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="aa776-117">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="aa776-118">Slutför konfigurationen av Windows 10-enhet.</span><span class="sxs-lookup"><span data-stu-id="aa776-118">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="aa776-p103">När du är klar är användaren ansluten till organisationens Azure AD. Kontrollera att allt är korrekt genom att läsa [Kontrollera att enheten är ansluten till Azure AD](set-up-windows-devices.md#bkmk_verifyaad).</span><span class="sxs-lookup"><span data-stu-id="aa776-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](set-up-windows-devices.md#bkmk_verifyaad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="aa776-121">Enheter som redan är konfigurerade och använder Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="aa776-121">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="aa776-122">**Ansluta användare till Azure AD:**</span><span class="sxs-lookup"><span data-stu-id="aa776-122">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="aa776-123">Klicka på Windows-logotypen och sedan på inställningsikonen på användarens dator med Windows 10 Pro, version 1703 (Creators Update) (se [förutsättningar](pre-requisites-for-data-protection.md)).</span><span class="sxs-lookup"><span data-stu-id="aa776-123">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="aa776-125">I **Inställningar** går du till **Konton**.</span><span class="sxs-lookup"><span data-stu-id="aa776-125">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="aa776-127">På sidan **Din information** klickar du på **Åtkomst till arbete eller skola** \> **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="aa776-127">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="aa776-129">I dialogrutan **Konfigurera ett arbets- eller skolkonto** dialogrutan väljer du **Anslut den här enheten till Azure Active Directory** under **Alternativa åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="aa776-129">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="aa776-131">**Dags att du är inloggad** på sidan Ange ditt arbete eller skolan konto \> **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="aa776-131">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="aa776-132">Ange ditt lösenord på sidan **Ange lösenord** \> **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="aa776-132">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="aa776-134">På den \*\* kontrollera att detta är din organisation \*\* sidan, kontrollera att informationen är korrekt och klicka på **Anslut till**.</span><span class="sxs-lookup"><span data-stu-id="aa776-134">On the \*\* Make sure this is your organization \*\* page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="aa776-p104">På sidan **Klart!** klickar du på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="aa776-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="aa776-p105">Om du laddade upp filer till OneDrive för företag, synkroniserar du dem med datorn. Om du använde ett verktyg från tredje part för migrering av profil och filer, synkroniserar du även med den nya profilen.</span><span class="sxs-lookup"><span data-stu-id="aa776-p105">If you uploaded files to OneDrive for Business, sync them back down. If you used a third party tool to migrate profile and files, sync those also to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="aa776-140">Kontrollera att enheten är ansluten till Azure AD</span><span class="sxs-lookup"><span data-stu-id="aa776-140">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="aa776-p106">Om du vill verifiera din synkroniseringsstatus, klickar du i området **Ansluten till** _ \*\*\*\* organization name\*\*\*\* _ på sidan \< i \> för att visa knapparna **Info** och **Koppla från**. Klicka på **Info** för att visa din synkroniseringsstatus.</span><span class="sxs-lookup"><span data-stu-id="aa776-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="aa776-143">Klicka på Synkronisera på sidan Synkroniseringsstatus synkronisering för att hämta de senaste hanteringsprinciperna för mobila enheter till datorn.</span><span class="sxs-lookup"><span data-stu-id="aa776-143">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="aa776-p107">Om du vill börjar använda Microsoft 365 Business-kontot klickar du på **Start**-knappen i Windows, högerklickar på den aktuella kontobilden och klickar sedan på **Växla konto**. Logga in med din e-postadress och lösenord hos organisationen.</span><span class="sxs-lookup"><span data-stu-id="aa776-p107">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture and then **Switch account**. Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="aa776-147">Kontrollera att enheten uppgraderats till Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="aa776-147">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="aa776-148">Kontrollera att de Windows 10-enheter som anslöts till Azure AD uppgraderats till Windows 10 Business som en del av Microsoft 365 Business-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="aa776-148">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="aa776-149">Gå till **Inställningar** \> **System** \> **Om**.</span><span class="sxs-lookup"><span data-stu-id="aa776-149">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="aa776-150">Kontrollera att **Version** är **Windows 10 Business**.</span><span class="sxs-lookup"><span data-stu-id="aa776-150">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="aa776-152">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="aa776-152">Next steps</span></span>

<span data-ttu-id="aa776-153">Konfigurera mobila enheter med informationen i [Konfigurera mobila enheter för Microsoft 365 Business-användare](set-up-mobile-devices.md) och ställ in principer för enhetsskydd eller programskydd med informationen i [Hantera Microsoft 365 Business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="aa776-153">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
