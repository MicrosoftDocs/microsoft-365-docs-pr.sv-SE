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
ms.openlocfilehash: dd9d777798c2c96776a8f9b40a3c4dfe0b95702a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876954"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="8e012-103">Hantera åtkomst inställningar för enheter i grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="8e012-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="8e012-104">Om du använder grundläggande mobilitet och säkerhet kan det finnas enheter som du inte kan hantera med grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="8e012-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="8e012-105">I så fall bör du spärra Exchange ActiveSync-appen till Microsoft 365-e-post för mobila enheter som inte stöds av grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="8e012-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="8e012-106">Det här skyddar organisations informationen på fler enheter.</span><span class="sxs-lookup"><span data-stu-id="8e012-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="8e012-107">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="8e012-107">Use these steps:</span></span>

1. <span data-ttu-id="8e012-108">Logga in på Microsoft 365 med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="8e012-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="8e012-109">I webbläsaren skriver du:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="8e012-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="8e012-110">Om det är första gången du använder grundläggande mobilitet och säkerhet för Microsoft 365 Business Standard, aktiverar du det här: [aktivera grundläggande säkerhet och mobilitet](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="8e012-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="8e012-111">När du har aktiverat den kan du hantera dina enheter med [säkerhets & i Office 365](https://protection.office.com/).</span><span class="sxs-lookup"><span data-stu-id="8e012-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="8e012-112">Gå till skydd mot data förlust >enhets principer för  **enhets hantering**   >  \*\*\*\* och välj **Hantera åtkomst inställningar för hela organisationen**.</span><span class="sxs-lookup"><span data-stu-id="8e012-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="8e012-113">Välj **block**.</span><span class="sxs-lookup"><span data-stu-id="8e012-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Kryss rutan grundläggande mobilitet och säkerhets block":::

5. <span data-ttu-id="8e012-115">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8e012-115">Select **Save**.</span></span>

<span data-ttu-id="8e012-116">För att lära dig vilka enheter grundläggande mobilitet och säkerhet stöder kan du läsa [grundläggande mobilitet och säkerhet](capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="8e012-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>