---
title: Hantera principer för Windows 10 Pro-enheter med Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Lär dig hur du hanterar principer för Windows 10 Pro-enheter med Microsoft 365 Business Premium.
ms.openlocfilehash: 0f7cfff227e1ab4ea992414b513e341adbd9ef22
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578693"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="2f788-103">Hantera principer för Windows 10 Pro-enheter</span><span class="sxs-lookup"><span data-stu-id="2f788-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="2f788-104">Du kan använda Microsoft 365 Business för att säkerställa att Windows Defender Antivirus är aktiverat på Windows 10-enheter och Microsoft-uppdateringar laddas automatiskt ned till användarnas enheter.</span><span class="sxs-lookup"><span data-stu-id="2f788-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="2f788-105">Prova!</span><span class="sxs-lookup"><span data-stu-id="2f788-105">Try it!</span></span>

1. <span data-ttu-id="2f788-106">Logga in på administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f788-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="2f788-107">Välj **Lägg** till princip under Principer.</span><span class="sxs-lookup"><span data-stu-id="2f788-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="2f788-108">I fönstret **Lägg till** princip anger du ett namn under **Principnamn** och väljer sedan **Windows 10-enhetskonfiguration** under **Principtyp.**</span><span class="sxs-lookup"><span data-stu-id="2f788-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="2f788-109">Välj **Skydda Windows 10-enheter** om du vill se underinställningarna.</span><span class="sxs-lookup"><span data-stu-id="2f788-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="2f788-110">Se till att **Skydda PC-datorer** mot virus och andra hot med Windows Defender Antivirus och Håll **Windows 10-enheter** uppdaterade automatiskt är påslagna.</span><span class="sxs-lookup"><span data-stu-id="2f788-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="2f788-111">Under **Vem får de här inställningarna?** är alla användare  markerade som standard, men du kan välja Ändra och välja de säkerhetsgrupper som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="2f788-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="2f788-112">Välj Lägg till för att slutföra **principen.**</span><span class="sxs-lookup"><span data-stu-id="2f788-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="2f788-113">På sidan **Lägg till princip** väljer du **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="2f788-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="2f788-114">På startsidan för administrationscentret bekräftar du att den nya principen har lagts till genom att välja **Principer** och granska principen på **sidan** Principer.</span><span class="sxs-lookup"><span data-stu-id="2f788-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="2f788-115">Kontrollera att principen har verkställts genom att gå till Windows Update på en användares Windows 10-enhet, välja Avancerade alternativ och kontrollera att inställningarna är nedtonade.</span><span class="sxs-lookup"><span data-stu-id="2f788-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="2f788-116">Klicka sedan på **Välj hur** uppdateringar levereras och kontrollera att inställningarna är nedtonade och att följande meddelande visas: Vissa inställningar är dolda eller hanteras av **din organisation.**</span><span class="sxs-lookup"><span data-stu-id="2f788-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

