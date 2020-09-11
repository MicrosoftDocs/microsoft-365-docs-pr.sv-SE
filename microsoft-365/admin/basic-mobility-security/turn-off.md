---
title: Stänga av grundläggande mobilitet och säkerhet
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: Ta bort grupper eller principer för att stänga av grundläggande mobilitet och säkerhet.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430318"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="7d9c0-103">Stänga av grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="7d9c0-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="7d9c0-104">För att effektivt stänga av grundläggande mobilitet och säkerhet tar du bort grupper av personer som definieras av säkerhets grupper från enhets hanterings principer eller tar bort själva principer.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="7d9c0-105">Ta bort grupper med användare genom att ta bort säkerhets grupper för användare från de enheter som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>
    
- <span data-ttu-id="7d9c0-106">Inaktivera grundläggande mobilitet och säkerhet för alla genom att ta bort alla grundläggande principer för mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>
    
<span data-ttu-id="7d9c0-107">De här alternativen tar bort grundläggande mobilitet och säkerhet för enheter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="7d9c0-108">Tyvärr kan du inte helt enkelt "avetablera" grundläggande mobilitet och säkerhet när du har konfigurerat det.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="7d9c0-109">Observera att det påverkar användarnas enheter när du tar bort säkerhets grupper för användare från principer eller tar bort själva principer.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="7d9c0-110">E-postprofiler och cachelagrade e-postmeddelanden kan till exempel tas bort beroende på enheten.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="7d9c0-111">Mer information finns i  [vad som händer när du tar bort en princip eller tar bort en användare från policyn?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="7d9c0-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="7d9c0-112">Ta bort säkerhets grupper för användare från grundläggande principer för mobilitet och säkerhets enheter</span><span class="sxs-lookup"><span data-stu-id="7d9c0-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="7d9c0-113">I webbläsaren:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="7d9c0-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="7d9c0-114">Välj en enhets princip och välj sedan **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="7d9c0-115"> *\*Deployment**   Välj *\*ta bort*\*på sidan distribution.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-115">On the  **Deployment**  page, select **Remove**.</span></span>
    
4. <span data-ttu-id="7d9c0-116">Under  **grupper**väljer du en säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="7d9c0-117">Välj  **ta bort**och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-117">Select  **Remove**, and select **Save**.</span></span>
    

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="7d9c0-118">Ta bort principer för mobilitet och säkerhets enheter</span><span class="sxs-lookup"><span data-stu-id="7d9c0-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="7d9c0-119">I webbläsaren:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="7d9c0-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="7d9c0-120">Välj en enhets princip och välj sedan  **ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="7d9c0-121">I dialog rutan varning väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7d9c0-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE] 
><span data-ttu-id="7d9c0-122">Om du vill veta mer om hur du avblockerar enheter om dina organisations enheter fortfarande är spärrade kan du läsa blogg inlägget [ta bort åtkomst kontroll från hantering av mobila enheter för Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span><span class="sxs-lookup"><span data-stu-id="7d9c0-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
