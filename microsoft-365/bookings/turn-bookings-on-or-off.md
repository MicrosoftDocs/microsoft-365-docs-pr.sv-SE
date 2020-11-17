---
title: Aktivera eller inaktivera Microsoft-bokningar
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Lär dig hur du får till gång till Microsoft-bokningar i Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126606"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="b358e-103">Aktivera eller inaktivera Microsoft-bokningar</span><span class="sxs-lookup"><span data-stu-id="b358e-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="b358e-104">Du kan aktivera eller inaktivera bokningar för hela organisationen eller för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="b358e-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="b358e-105">När du aktiverar bokningar för användare kan de skapa en sida med information, skapa en kalender och låta andra boka tid med dem.</span><span class="sxs-lookup"><span data-stu-id="b358e-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="b358e-106">Administratörs kontrollerna som beskrivs i dessa avsnitt är inte tillgängliga för Office 365 som drivs av 21Vianet-kunder (Kina).</span><span class="sxs-lookup"><span data-stu-id="b358e-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="b358e-107">Aktivera eller inaktivera bokningar för organisationen med hjälp av administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b358e-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="b358e-108">Logga in på administrations centret för Microsoft 365 som global administratör.</span><span class="sxs-lookup"><span data-stu-id="b358e-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="b358e-109">I administrations centret går du till  **Inställningar**   \> **organisations inställningar** och väljer **bokningar**.</span><span class="sxs-lookup"><span data-stu-id="b358e-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="b358e-110">Markera kryss rutan för **Låt organisationen använda bokningar** för att aktivera eller inaktivera bokningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="b358e-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b358e-111">Om du stänger av bokningarna inaktive ras all åtkomst till tjänsten, inklusive skapande och hantering av boknings sidor.</span><span class="sxs-lookup"><span data-stu-id="b358e-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="b358e-112">Välj **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="b358e-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="b358e-113">Aktivera eller inaktivera bokningar för organisationen med hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="b358e-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="b358e-114">Om du vill aktivera eller inaktivera bokningar för din organisation med PowerShell-cmdleten [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) [ansluter du till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b358e-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="b358e-115">Aktivera eller inaktivera bokningar för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="b358e-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="b358e-116">Du kan inaktivera bokningar för enskilda användare.</span><span class="sxs-lookup"><span data-stu-id="b358e-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="b358e-117">Gå till administrations centret för Microsoft 365 och välj **användare** \> **aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="b358e-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="b358e-118">Välj önskad användare och sedan **licenser och appar**.</span><span class="sxs-lookup"><span data-stu-id="b358e-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="b358e-119">Expandera **appar** och avmarkera kryss rutan för Microsoft-bokningar.</span><span class="sxs-lookup"><span data-stu-id="b358e-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="b358e-120">Kräv godkännande från personalen innan du delar ledig/upptagen-information</span><span class="sxs-lookup"><span data-stu-id="b358e-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="b358e-121">Administratörer kan kräva att de anställda deltar i sin organisation innan de kan använda sin tillgänglighets information för att bli bookable via en boknings sida.</span><span class="sxs-lookup"><span data-stu-id="b358e-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="b358e-122">Den här inställningen är tillgänglig i administrations centret för Microsoft 365 under **Inställningar** \> **Settings** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="b358e-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="b358e-123">När den här inställningen är aktive rad kommer anställda som har lagts till som personal i boknings kalendrar att hitta en av länkarna acceptera/avvisa i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="b358e-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="b358e-124">Den här funktionen lanseras gradvis till Microsoft 365-kunder.</span><span class="sxs-lookup"><span data-stu-id="b358e-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="b358e-125">Om det här alternativet inte visas i administrations centret för Microsoft 365, kom tillbaka snart.</span><span class="sxs-lookup"><span data-stu-id="b358e-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="b358e-126">Blockera alternativ för sociala delning</span><span class="sxs-lookup"><span data-stu-id="b358e-126">Block social sharing options</span></span>

<span data-ttu-id="b358e-127">Administratörer kan styra hur boknings sidor delas i sociala nätverk.</span><span class="sxs-lookup"><span data-stu-id="b358e-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="b358e-128">Den här inställningen är tillgänglig i administrations centret för Microsoft 365 under **Inställningar** \> **Settings** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="b358e-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="b358e-129">Den här funktionen lanseras gradvis till Microsoft 365-kunder.</span><span class="sxs-lookup"><span data-stu-id="b358e-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="b358e-130">Om det här alternativet inte visas i administrations centret för Microsoft 365, kom tillbaka snart.</span><span class="sxs-lookup"><span data-stu-id="b358e-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="b358e-131">Tillåt endast valda användare att skapa kalender kalendrar</span><span class="sxs-lookup"><span data-stu-id="b358e-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="b358e-132">Genom att använda princip begränsningar kan du begränsa licensierade användare från att kunna skapa kalender kalendrar.</span><span class="sxs-lookup"><span data-stu-id="b358e-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="b358e-133">Du måste först aktivera bokningar för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="b358e-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="b358e-134">Alla användare i organisationen får boka licenser, men bara de som ingår i policyn kan skapa kalender kalendrar och ha fullständig kontroll över vem som får till gång till de kalendrar de skapar.</span><span class="sxs-lookup"><span data-stu-id="b358e-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="b358e-135">Användare som ingår i den här principen kan skapa nya kalender kalendrar och kan läggas till som personal i valfri kapacitet (inklusive administratörs rollen) för befintliga kalender kalendrar.</span><span class="sxs-lookup"><span data-stu-id="b358e-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="b358e-136">Användare som inte ingår i den här principen kan inte skapa nya kalender kalendrar och får ett fel meddelande om de försöker göra det.</span><span class="sxs-lookup"><span data-stu-id="b358e-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="b358e-137">Du måste köra följande kommandon med Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b358e-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="b358e-138">Mer information om hur du kör Exchange Online-cmdlets finns i [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b358e-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b358e-139">I stegen nedan förutsätts det att inga andra principer för Outlook Web App (OWA)-postlådor har skapats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b358e-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="b358e-140">Skapa en ny post låda för användare som ska få tillåtelse att skapa kalender kalendrar.</span><span class="sxs-lookup"><span data-stu-id="b358e-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="b358e-141">(Det går att skapa en ny post låda i kalendern i kalendrar).</span><span class="sxs-lookup"><span data-stu-id="b358e-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="b358e-142">Mer information finns i [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="b358e-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="b358e-143">Koppla den här principen till relevanta användare genom att köra det här kommandot för varje användare som du vill ge behörighet att skapa kalender kalendrar.</span><span class="sxs-lookup"><span data-stu-id="b358e-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="b358e-144">Mer information finns i [set-CASMailbox cmdlethttps](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="b358e-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="b358e-145">Valfritt: kör det här kommandot om du vill inaktivera bokningar för alla andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b358e-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="b358e-146">Mer information finns i [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="b358e-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="b358e-147">Mer information om principer för OWA-postlådor finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="b358e-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="b358e-148">Skapa en Outlook-princip för en post låda i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b358e-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="b358e-149">Använda eller ta bort en Outlook-princip på en post låda i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b358e-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
