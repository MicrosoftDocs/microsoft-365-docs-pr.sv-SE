---
title: Hantera principer för Windows 10 Pro-enheter med Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig att hantera principer för Windows 10 Pro-enheter med Microsoft 365 Business Premium.
ms.openlocfilehash: 9052859f03035a76bf69b7c8c23c75ae00353846
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703193"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="bd434-103">Hantera principer för Windows 10 Pro-enheter</span><span class="sxs-lookup"><span data-stu-id="bd434-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="bd434-104">Du kan använda Microsoft 365 Business för att kontrol lera att Windows Defender Antivirus är aktiverat på Windows 10-enheter och att Microsoft Updates laddas ned automatiskt till användarnas enheter.</span><span class="sxs-lookup"><span data-stu-id="bd434-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="bd434-105">Prova!</span><span class="sxs-lookup"><span data-stu-id="bd434-105">Try it!</span></span>

1. <span data-ttu-id="bd434-106">Logga in på administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd434-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="bd434-107">Under **principer** väljer du Lägg till princip.</span><span class="sxs-lookup"><span data-stu-id="bd434-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="bd434-108">Ange ett namn under **princip namn** i fönstret **Lägg till policy** och välj sedan **Windows 10-enhets konfiguration** under **princip typ**.</span><span class="sxs-lookup"><span data-stu-id="bd434-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="bd434-109">Välj **säkra Windows 10-enheter** för att se under Inställningar.</span><span class="sxs-lookup"><span data-stu-id="bd434-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="bd434-110">Se till att **skydda datorer mot virus och andra hot med Windows Defender Antivirus** och **hålla Windows 10-enheter uppdaterade automatiskt** .</span><span class="sxs-lookup"><span data-stu-id="bd434-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="bd434-111">Under **vem får de här inställningarna?** är alla användare **markerade som standard** , men du kan välja att välja vilka säkerhets grupper du har skapat.</span><span class="sxs-lookup"><span data-stu-id="bd434-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="bd434-112">Klicka på **Lägg till** för att slutföra skapandet av principen.</span><span class="sxs-lookup"><span data-stu-id="bd434-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="bd434-113">På sidan **Lägg till princip** väljer du **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="bd434-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="bd434-114">På Start sidan för administrations centret kontrollerar du att den nya principen har lagts till genom att välja **principer** och granska din policy på sidan **policys** .</span><span class="sxs-lookup"><span data-stu-id="bd434-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="bd434-115">Verifiera att principen har verkställts genom att gå till Windows Update på en användares Windows 10-enhet, välja **Avancerade alternativ** och bekräfta att inställningarna är nedtonade.</span><span class="sxs-lookup"><span data-stu-id="bd434-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="bd434-116">Klicka sedan på **Välj hur uppdateringar levereras** och kontrol lera att inställningarna är nedtonade och att följande meddelande visas: **vissa inställningar är dolda eller hanteras av din organisation**.</span><span class="sxs-lookup"><span data-stu-id="bd434-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

