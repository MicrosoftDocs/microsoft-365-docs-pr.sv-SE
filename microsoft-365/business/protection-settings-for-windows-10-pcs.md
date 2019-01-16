---
title: Ange inställningar för enhetsskydd för Windows 10
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
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Mer information om standard och andra inställningar som är tillgängliga i Microsoft 365 Business att skydda Windows 10 enheter.
ms.openlocfilehash: ebfe5f59e544b67e5a4f2ecd990031e9221ff8e5
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982149"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="191f6-103">Ange inställningar för enhetsskydd för Windows 10</span><span class="sxs-lookup"><span data-stu-id="191f6-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="191f6-104">Skydda Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="191f6-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="191f6-105">Titta på en video om hur du skyddar Windows 10-enheter med Microsoft 365 Business:</span><span class="sxs-lookup"><span data-stu-id="191f6-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="191f6-106">Logga in på [Microsoft 365 Business](https://portal.office.com) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="191f6-106">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="191f6-107">I Administrationscenter väljer du **Lägg till princip** från kortet **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="191f6-107">in the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="191f6-109">I fönstret **Lägg till princip** anger du ett unikt namn för principen.</span><span class="sxs-lookup"><span data-stu-id="191f6-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="191f6-110">Under **Typ av princip** väljer du **Konfiguration av Windows 10-enhet**.</span><span class="sxs-lookup"><span data-stu-id="191f6-110">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="191f6-p101">Expandera **Skydda Windows 10-enheter** \> konfigurera inställningar enligt eget önskemål. Se [Tillgängliga inställningar](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings) för mer information.</span><span class="sxs-lookup"><span data-stu-id="191f6-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="191f6-113">Du kan alltid använda länken **Återställ standardinställningar** för att återgå till standardinställningar.</span><span class="sxs-lookup"><span data-stu-id="191f6-113">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="191f6-p102">**Vem får de här inställningarna?** Om du inte vill använda säkerhetsgruppen **Alla användare** (standard) väljer du **Ändra** och anger vilka säkerhetsgrupper som får dessa inställningar \> **Välj**.</span><span class="sxs-lookup"><span data-stu-id="191f6-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="191f6-117">Välj **Klar** för att spara principen och tilldela den till enheter.</span><span class="sxs-lookup"><span data-stu-id="191f6-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="191f6-118">Tillgängliga inställningar</span><span class="sxs-lookup"><span data-stu-id="191f6-118">Available settings</span></span>

<span data-ttu-id="191f6-p103">Som standard är alla inställningar **På**. Följande inställningar är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="191f6-p103">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="191f6-121">Mer information finns i artikeln om [hur skyddsfunktioner i Microsoft 365 Business mappas till Intune-inställningarna](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="191f6-121">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="191f6-122">Inställning</span><span class="sxs-lookup"><span data-stu-id="191f6-122">Setting</span></span>  <br/> |<span data-ttu-id="191f6-123">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="191f6-123">Description</span></span>  <br/> |
|<span data-ttu-id="191f6-124">Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="191f6-124">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="191f6-125">Kräver att antivirusprogrammet Windows Defender är aktiverat för att skydda datorer från fara vid uppkoppling till internet.</span><span class="sxs-lookup"><span data-stu-id="191f6-125">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="191f6-126">Skydda datorer från webbaserade hot i Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="191f6-126">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="191f6-127">Aktiverar inställningarna Microsoft i Edge som hjälper till att skydda användare från skadliga webbplatser och nedladdningar.</span><span class="sxs-lookup"><span data-stu-id="191f6-127">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="191f6-128">Använd regler som minskar enheternas attackytor</span><span class="sxs-lookup"><span data-stu-id="191f6-128">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="191f6-p104">När inställningen är aktiv bidrar minskningen av attackytan till att blockera åtgärder och program som vanligtvis används av skadlig programvara för att smitta enheter. Inställningen är bara tillgänglig om Windows Defender Antivirus är aktiverad. Mer information finns i [Minska attackytor](https://go.microsoft.com/fwlink/?linkid=870417).  </span><span class="sxs-lookup"><span data-stu-id="191f6-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="191f6-132">Skydda mappar från hot som utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="191f6-132">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="191f6-p105">Den här inställningen använder kontrollerad mappåtkomst för att skydda företagsdata från att ändras av misstänkta eller skadliga program, till exempel utpressningstrojaner. Dessa typer av program blockeras från att göra ändringar i skyddade mappar. Inställningen är bara tillgänglig om Windows Defender Antivirus är aktiverad. Mer information finns i [Skydda filer med kontrollerad mappåtkomst](https://go.microsoft.com/fwlink/?linkid=870418).  </span><span class="sxs-lookup"><span data-stu-id="191f6-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="191f6-137">Förhindra nätverksåtkomst till potentiellt skadlig innehåll på Internet</span><span class="sxs-lookup"><span data-stu-id="191f6-137">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="191f6-p106">Använda den här inställningen för att blockera utgående användaranslutningar till beryktade Internetplatser som kan vara värdar för nätfiske, trojaner eller annat skadligt innehåll. Inställningen är bara tillgänglig om Windows Defender Antivirus är aktiverad. Mer information finns i [Skydda ditt nätverk](https://go.microsoft.com/fwlink/?linkid=870419).  </span><span class="sxs-lookup"><span data-stu-id="191f6-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="191f6-141">Skydda filer och mappar på PC-datorer från obehörig åtkomst med BitLocker</span><span class="sxs-lookup"><span data-stu-id="191f6-141">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="191f6-p107">BitLocker skyddar data genom att kryptera datorhårddiskar samt skyddar mot exponering av data om en dator försvinner eller blir stulen. Mer information finns i [Vanliga frågor och svar om Bitlocker ](https://go.microsoft.com/fwlink/?linkid=871000).  </span><span class="sxs-lookup"><span data-stu-id="191f6-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="191f6-144">Tillåt användare att hämta appar från Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="191f6-144">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="191f6-p108">Låter användare ladda ned och installera appar från Microsoft Store. Appar inbegriper allt från spel till produktivitetsverktyg, så vi lämnar den här inställningen **På**, men du kan inaktivera den för extra säkerhet.  </span><span class="sxs-lookup"><span data-stu-id="191f6-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="191f6-147">Tillåt användare att använda Cortana</span><span class="sxs-lookup"><span data-stu-id="191f6-147">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="191f6-p109">Cortana kan vara mycket användbar! Hon kan aktivera eller inaktivera inställningar åt dig, ge vägbeskrivningar och kontrollera att du håller avtalade tider, så vi lämnar inställningen **På** som standard.  </span><span class="sxs-lookup"><span data-stu-id="191f6-p109">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="191f6-150">Tillåt användare att ta emot Windows-tips och reklam från Microsoft</span><span class="sxs-lookup"><span data-stu-id="191f6-150">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="191f6-151">Windows-tips kan vara praktiskt eftersom de informerar användare när nya funktioner blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="191f6-151">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="191f6-152">Håll Windows 10-enheter uppdaterade automatiskt</span><span class="sxs-lookup"><span data-stu-id="191f6-152">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="191f6-153">Säkerställer att Windows 10-enheter automatiskt får de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="191f6-153">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="191f6-154">Stäng av enhetens skärm efter en viss tids inaktivitet</span><span class="sxs-lookup"><span data-stu-id="191f6-154">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="191f6-p110">Säkerställer att företagsdata skyddas om en användare är inaktiv. En användare som befinner sig på en offentlig plats, till exempel ett café, kan göra ett ärende eller låter sig distraheras för ett ögonblick, vilket gör att obehöriga kan få tillgång till enheten. Med den här inställningen kan du bestämma hur länge användaren kan vara inaktiv innan skärmen stängs av.</span><span class="sxs-lookup"><span data-stu-id="191f6-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

