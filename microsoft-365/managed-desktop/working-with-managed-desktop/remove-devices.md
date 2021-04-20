---
title: Ta bort enheter
description: Ta bort enheter från Microsoft Hanterad skrivbordshantering
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893929"
---
# <a name="remove-devices"></a><span data-ttu-id="25203-103">Ta bort enheter</span><span class="sxs-lookup"><span data-stu-id="25203-103">Remove devices</span></span>

<span data-ttu-id="25203-104">Du kan ta bort enheter från Microsoft Hanterad dator med hjälp av administrationsportalen.</span><span class="sxs-lookup"><span data-stu-id="25203-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="25203-105">Den här åtgärden är permanent, men du kan registrera dem i Microsoft Managed Desktop igen genom att följa [registreringsstegen.](../get-started/register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="25203-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="25203-106">När du tar bort en enhet inträffar följande:</span><span class="sxs-lookup"><span data-stu-id="25203-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="25203-107">Vi tar bort enheten från Autopilot.</span><span class="sxs-lookup"><span data-stu-id="25203-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="25203-108">Vi tar bort enheten från alla enhetsgrupper på "Modern Workplace".</span><span class="sxs-lookup"><span data-stu-id="25203-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="25203-109">Vi tar bort enheten från **bladet** Enheter i administrationsportalen.</span><span class="sxs-lookup"><span data-stu-id="25203-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="25203-110">När du tar bort en enhet kan du även ta bort den från Azure Active Directory (Azure AD) och Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="25203-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="25203-111">Borttagning av objekt relaterade till en enhet från Azure AD och Microsoft Intune är permanent.</span><span class="sxs-lookup"><span data-stu-id="25203-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="25203-112">Om du tar bort objekten kan du inte visa eller hantera enheter från Intune- och Azure-portalerna.</span><span class="sxs-lookup"><span data-stu-id="25203-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="25203-113">Enheterna kommer inte att kunna komma åt företagets resurser.</span><span class="sxs-lookup"><span data-stu-id="25203-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="25203-114">Företagsdata kan tas bort från dem om enheterna försöker logga in efter att de tagits bort.</span><span class="sxs-lookup"><span data-stu-id="25203-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="25203-115">I [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)väljer du **Enheter** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="25203-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="25203-116">Titta efter avsnittet **Microsoft Managed Desktop** på menyn och välj **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="25203-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="25203-117">I arbetsytan Microsoft Hanterade skrivbordsenheter väljer du de enheter du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="25203-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="25203-118">Välj **Enhetsåtgärder** och välj sedan Ta **bort enhet som** öppnar en flyg in för att ta bort enheterna.</span><span class="sxs-lookup"><span data-stu-id="25203-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="25203-119">Kontrollera de valda enheterna i infället och välj sedan Ta **bort enheter**.</span><span class="sxs-lookup"><span data-stu-id="25203-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="25203-120">Om du även vill ta bort Azure AD- och Intune-objekten samtidigt markerar du kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="25203-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="25203-121">Borttagning av enheter kan ta några minuter att slutföra.</span><span class="sxs-lookup"><span data-stu-id="25203-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="25203-122">Du kan inte ta bort enheter som har ett **väntande** registreringstillstånd.</span><span class="sxs-lookup"><span data-stu-id="25203-122">You can't remove devices that are in a **pending** registration state.</span></span>