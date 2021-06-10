---
title: Stäng av grundläggande Mobility and Security
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
description: Ta bort grupper eller principer för att inaktivera Grundläggande rörlighet och säkerhet.
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023875"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="ee51a-103">Stäng av grundläggande Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="ee51a-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="ee51a-104">För att effektivt inaktivera Grundläggande rörlighet och säkerhet tar du bort grupper av personer som definieras av säkerhetsgrupper från principer för enhetshantering eller tar bort principerna själva.</span><span class="sxs-lookup"><span data-stu-id="ee51a-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="ee51a-105">Ta bort grupper av användare genom att ta bort användarsäkerhetsgrupper från enhetsprinciperna som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="ee51a-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="ee51a-106">Inaktivera grundläggande rörlighet och säkerhet för alla genom att ta bort alla principer för grundläggande rörlighet och säkerhetsenhet.</span><span class="sxs-lookup"><span data-stu-id="ee51a-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="ee51a-107">Med de här alternativen tas tillämpning av Basic Mobility och Security bort för enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ee51a-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="ee51a-108">Tyvärr kan du inte bara "återkalla" Basic Mobility and Security när du har konfigurerat den.</span><span class="sxs-lookup"><span data-stu-id="ee51a-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="ee51a-109">Tänk på hur användarnas enheter påverkas när du tar bort användarnas säkerhetsgrupper från principerna eller tar bort principerna.</span><span class="sxs-lookup"><span data-stu-id="ee51a-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="ee51a-110">Till exempel kan e-postprofiler och cachelagrade e-postmeddelanden tas bort, beroende på enhet.</span><span class="sxs-lookup"><span data-stu-id="ee51a-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="ee51a-111">Mer information finns i Vad  [händer när du tar bort en princip eller tar bort en användare från principen?](../../admin/basic-mobility-security/create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ee51a-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="ee51a-112">Ta bort användarsäkerhetsgrupper från principer för grundläggande rörlighet och säkerhetsenhet</span><span class="sxs-lookup"><span data-stu-id="ee51a-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="ee51a-113">Skriv följande i webbläsaren:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="ee51a-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="ee51a-114">Välj en enhetsprincip och sedan **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="ee51a-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="ee51a-115">Välj  **Ta bort**   på sidan **Distribution.**</span><span class="sxs-lookup"><span data-stu-id="ee51a-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="ee51a-116">Välj  **en** säkerhetsgrupp under Grupper.</span><span class="sxs-lookup"><span data-stu-id="ee51a-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="ee51a-117">Välj  **Ta** bort och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ee51a-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="ee51a-118">Ta bort principer för grundläggande rörlighet och säkerhetsenhet</span><span class="sxs-lookup"><span data-stu-id="ee51a-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="ee51a-119">Skriv följande i webbläsaren:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="ee51a-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="ee51a-120">Välj en enhetsprincip och välj sedan Ta  **bort princip**.</span><span class="sxs-lookup"><span data-stu-id="ee51a-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="ee51a-121">Välj Ja i dialogrutan **Varning.**</span><span class="sxs-lookup"><span data-stu-id="ee51a-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="ee51a-122">Mer information om hur du tar bort blockering av enheter om organisationens enheter fortfarande är blockerade finns i blogginlägget Ta bort åtkomstkontroll [från Mobile Device Management för Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span><span class="sxs-lookup"><span data-stu-id="ee51a-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
