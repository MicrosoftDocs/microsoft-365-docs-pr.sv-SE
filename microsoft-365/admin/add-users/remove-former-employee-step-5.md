---
title: Steg 5 – Rensa och blockera en tidigare anställds mobila enhet
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Följ dessa steg för att blockera en tidigare anställds åtkomst till mobila enheter.
ms.openlocfilehash: 1ce12b06b6a0a74615ff8ac43b8f333456a469bb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244294"
---
# <a name="step-5---wipe-and-block-a-former-employees-mobile-device"></a><span data-ttu-id="fa38f-103">Steg 5 – Rensa och blockera en tidigare anställds mobila enhet</span><span class="sxs-lookup"><span data-stu-id="fa38f-103">Step 5 - Wipe and block a former employee's mobile device</span></span>

<span data-ttu-id="fa38f-104">Om den tidigare anställde hade en organisationstelefon kan du använda administrationscentret för Exchange för att rensa och blockera enheten så att alla organisationsdata tas bort från enheten och den kan inte längre ansluta till Office 365.</span><span class="sxs-lookup"><span data-stu-id="fa38f-104">If your former employee had an organization phone, you can use the Exchange admin center to wipe and block that device so that all organization data is removed from the device and it can no longer connect to Office 365.</span></span> <span data-ttu-id="fa38f-105">Om din organisation använder Basic Mobility and Security för att hantera mobila enheter kan du rensa och blockera dessa enheter med hjälp av Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="fa38f-105">If your organization uses Basic Mobility and Security to manage mobile devices, you can wipe and block those devices using Basic Mobility and Security.</span></span>

## <a name="wipe-mobile-device-using-the-exchange-admin-center"></a><span data-ttu-id="fa38f-106">Rensa mobil enhet med Exchange administrationscenter</span><span class="sxs-lookup"><span data-stu-id="fa38f-106">Wipe mobile device using the Exchange admin center</span></span>

1. <span data-ttu-id="fa38f-107">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="fa38f-107">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="fa38f-108">I Administrationscenter för Exchange går du till **Mottagare** \> **Postlådor**.</span><span class="sxs-lookup"><span data-stu-id="fa38f-108">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="fa38f-109">Markera användaren och välj Visa **information** under Mobila **enheter.**</span><span class="sxs-lookup"><span data-stu-id="fa38f-109">Select the user, and under **Mobile Devices**, select **View details**.</span></span>
4. <span data-ttu-id="fa38f-110">På sidan **Information om mobil** enhet under Mobila **enheter** väljer du den mobila enheten, sedan Rensa dataruteenhet och sedan  ![ ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="fa38f-110">On the **Mobile Device Details** page, under **Mobile devices**, select the mobile device, select **Wipe Data**![Wipe Device](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), and then select **Block**.</span></span>
5. <span data-ttu-id="fa38f-111">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fa38f-111">Select **Save**.</span></span>
   > [!TIP]
   > <span data-ttu-id="fa38f-112">Se till att du tar bort eller inaktiverar användaren från din lokala Blackberry Enterprise Service.</span><span class="sxs-lookup"><span data-stu-id="fa38f-112">Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service.</span></span> <span data-ttu-id="fa38f-113">Du bör dessutom inaktivera alla Blackberry-enheter för användaren.</span><span class="sxs-lookup"><span data-stu-id="fa38f-113">You should also disable any Blackberry devices for the user.</span></span> <span data-ttu-id="fa38f-114">Läs i Blackberry Business Cloud Services Administration Guide om du behöver specifika anvisningar om hur du inaktiverar användaren.</span><span class="sxs-lookup"><span data-stu-id="fa38f-114">Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user.</span></span>
