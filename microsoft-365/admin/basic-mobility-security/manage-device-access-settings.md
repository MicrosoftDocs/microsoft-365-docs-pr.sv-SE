---
title: Hantera inställningar för enhetsåtkomst i Basic Mobility and Security
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
description: Basic Mobility and Security kan hjälpa dig att skydda och hantera mobila enheter.
ms.openlocfilehash: dd9d777798c2c96776a8f9b40a3c4dfe0b95702a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876954"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="21367-103">Hantera inställningar för enhetsåtkomst i Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="21367-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="21367-104">Om du använder Basic Mobility and Security kan det finnas enheter som du inte kan hantera med Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="21367-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="21367-105">I så fall bör du blockera Exchange ActiveSync appåtkomst till Microsoft 365 e-post för mobila enheter som inte stöds av Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="21367-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="21367-106">På så sätt kan du skydda organisationens information på fler enheter.</span><span class="sxs-lookup"><span data-stu-id="21367-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="21367-107">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="21367-107">Use these steps:</span></span>

1. <span data-ttu-id="21367-108">Logga in på Microsoft 365 ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="21367-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="21367-109">I webbläsaren skriver du:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="21367-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="21367-110">Om det här är första gången du använder Basic Mobility and Security för Microsoft 365 Business Standard du det här: [Aktivera Grundläggande säkerhet och mobilitet.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)</span><span class="sxs-lookup"><span data-stu-id="21367-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="21367-111">När du har aktiverat den kan du hantera dina enheter med [Office 365 säkerhet & efterlevnad.](https://protection.office.com/)</span><span class="sxs-lookup"><span data-stu-id="21367-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="21367-112">Gå till Dataförlustskydd > **Principer för**   >  **enhetshantering** och välj **Hantera enhetsåtkomstinställningar för hela organisationen.**</span><span class="sxs-lookup"><span data-stu-id="21367-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="21367-113">Välj **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="21367-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Kryssrutan Åtkomst för enkel rörlighet och säkerhetsblock":::

5. <span data-ttu-id="21367-115">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="21367-115">Select **Save**.</span></span>

<span data-ttu-id="21367-116">Mer information om vilka enheter som stöder basic rörlighet och säkerhet [finns i Funktioner för grundläggande rörlighet och säkerhet.](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="21367-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>