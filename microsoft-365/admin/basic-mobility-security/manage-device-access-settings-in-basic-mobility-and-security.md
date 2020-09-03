---
title: Hantera åtkomst inställningar för enheter i grundläggande mobilitet och säkerhet
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Grundläggande mobilitet och säkerhet kan hjälpa dig att skydda och hantera mobila enheter.
ms.openlocfilehash: 0d8f4293c45bcc1dc2a71dbc749641cf3791337e
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337115"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="a89c4-103">Hantera åtkomst inställningar för enheter i grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="a89c4-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="a89c4-104">Om du använder grundläggande mobilitet och säkerhet kan det finnas enheter som du inte kan hantera med grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="a89c4-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="a89c4-105">I så fall bör du spärra Exchange ActiveSync-appen till Microsoft 365-e-post för mobila enheter som inte stöds av grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="a89c4-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="a89c4-106">Det här skyddar organisations informationen på fler enheter.</span><span class="sxs-lookup"><span data-stu-id="a89c4-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="a89c4-107">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="a89c4-107">Use these steps:</span></span>

1. <span data-ttu-id="a89c4-108">Logga in på Microsoft 365 med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="a89c4-108">Sign in to  Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="a89c4-109">I webbläsaren skriver du:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="a89c4-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="a89c4-110">Om det är första gången du använder MDM för Microsoft 365 Business standard kan du aktivera det här: [aktivera hantering av mobila enheter](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="a89c4-110">If this is the first time you're using MDM for Microsoft 365 Business Standard, activate it here: [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="a89c4-111">När du har aktiverat den kan du hantera dina enheter med [säkerhets & i Office 365](https://protection.office.com/).</span><span class="sxs-lookup"><span data-stu-id="a89c4-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="a89c4-112">Gå till skydd mot data förlust >enhets principer för  **enhets hantering**   >  **Device policies**och välj **Hantera åtkomst inställningar för hela organisationen**.</span><span class="sxs-lookup"><span data-stu-id="a89c4-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>
    
4. <span data-ttu-id="a89c4-113">Välj **block**.</span><span class="sxs-lookup"><span data-stu-id="a89c4-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Kryss rutan grundläggande mobilitet och säkerhets block":::

5. <span data-ttu-id="a89c4-115">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a89c4-115">Select **Save**.</span></span> 

<span data-ttu-id="a89c4-116">För att lära dig vilka enheter grundläggande mobilitet och säkerhet stöder kan du läsa [grundläggande mobilitet och säkerhet](capabilities-of-basic-mobility-and-secruity.md).</span><span class="sxs-lookup"><span data-stu-id="a89c4-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).</span></span>