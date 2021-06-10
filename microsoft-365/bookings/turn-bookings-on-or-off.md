---
title: Aktivera eller inaktivera Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Lär dig hur du får tillgång till Microsoft Bookings i Microsoft 365.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913772"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="38ce1-103">Aktivera eller inaktivera Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="38ce1-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="38ce1-104">Bookings kan aktiveras eller inaktiveras för hela organisationen eller för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="38ce1-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="38ce1-105">När du aktiverar Bookings för användare kan de skapa en bookings-sida, skapa en kalender och ge andra möjlighet att boka tid med dem.</span><span class="sxs-lookup"><span data-stu-id="38ce1-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="38ce1-106">Administratörskontrollerna som beskrivs i dessa avsnitt är inte tillgängliga för kunder Office 365 21Vianet (Kina).</span><span class="sxs-lookup"><span data-stu-id="38ce1-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="38ce1-107">Aktivera eller inaktivera Bookings för organisationen via Microsoft 365 administrationscenter</span><span class="sxs-lookup"><span data-stu-id="38ce1-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="38ce1-108">Logga in på Microsoft 365 administrationscenter som global administratör.</span><span class="sxs-lookup"><span data-stu-id="38ce1-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="38ce1-109">I administrationscentret går du till fliken  **Inställningar**   \> **organisation Inställningar** och väljer **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="38ce1-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="38ce1-110">Markera kryssrutan för Tillåt **din organisation att använda Bookings för** att aktivera eller inaktivera Bookings för din organisation.</span><span class="sxs-lookup"><span data-stu-id="38ce1-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="38ce1-111">Om du inaktiverar Bookings inaktiveras all åtkomst till tjänsten, inklusive skapande och hantering av Bookings-sidor.</span><span class="sxs-lookup"><span data-stu-id="38ce1-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="38ce1-112">Välj **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="38ce1-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="38ce1-113">Aktivera eller inaktivera Bookings för din organisation med PowerShell</span><span class="sxs-lookup"><span data-stu-id="38ce1-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="38ce1-114">Så här aktiverar eller inaktiverar du Bookings för organisationen med [PowerShell-cmdleten Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="38ce1-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="38ce1-115">Aktivera eller inaktivera Bookings för enskilda användare</span><span class="sxs-lookup"><span data-stu-id="38ce1-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="38ce1-116">Du kan inaktivera Bookings för enskilda användare.</span><span class="sxs-lookup"><span data-stu-id="38ce1-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="38ce1-117">Gå till Microsoft 365 och välj sedan **Användare aktiva** \> **användare.**</span><span class="sxs-lookup"><span data-stu-id="38ce1-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="38ce1-118">Välj önskad användare och välj sedan **Licenser och appar.**</span><span class="sxs-lookup"><span data-stu-id="38ce1-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="38ce1-119">Expandera **Appar** och avmarkera kryssrutan för Microsoft Bookings.</span><span class="sxs-lookup"><span data-stu-id="38ce1-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="38ce1-120">Kräva godkännande av personal innan du delar ledig/upptagen-information</span><span class="sxs-lookup"><span data-stu-id="38ce1-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="38ce1-121">Administratörer kan kräva att anställda i organisationen anmäler sig innan deras tillgänglighetsinformation delas via Bookings och innan de kan bokas via en bokningssida.</span><span class="sxs-lookup"><span data-stu-id="38ce1-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="38ce1-122">Den här inställningen är tillgänglig i Microsoft 365 administrationscenter under **Inställningar** \> **Inställningar** \> **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="38ce1-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="38ce1-123">När den här inställningen är aktiverad hittar anställda som lagts till som personal i bokningskalendrar länken Godkänn/Avvisa i e-postmeddelandet som de får.</span><span class="sxs-lookup"><span data-stu-id="38ce1-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="38ce1-124">Den här funktionen lanseras gradvis över hela världen till Microsoft 365 kunder.</span><span class="sxs-lookup"><span data-stu-id="38ce1-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="38ce1-125">Om du inte ser det här alternativet i Microsoft 365 administrationscenter kan du komma tillbaka snart.</span><span class="sxs-lookup"><span data-stu-id="38ce1-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="38ce1-126">Blockera alternativ för social delning</span><span class="sxs-lookup"><span data-stu-id="38ce1-126">Block social sharing options</span></span>

<span data-ttu-id="38ce1-127">Administratörer kan styra hur bokningssidor delas i sociala nätverk.</span><span class="sxs-lookup"><span data-stu-id="38ce1-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="38ce1-128">Den här inställningen är tillgänglig i Microsoft 365 administrationscenter under **Inställningar** \> **Inställningar** \> **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="38ce1-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="38ce1-129">Den här funktionen lanseras gradvis över hela världen till Microsoft 365 kunder.</span><span class="sxs-lookup"><span data-stu-id="38ce1-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="38ce1-130">Om du inte ser det här alternativet i Microsoft 365 administrationscenter kan du komma tillbaka snart.</span><span class="sxs-lookup"><span data-stu-id="38ce1-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="38ce1-131">Tillåt endast vissa användare att skapa bookings-kalendrar</span><span class="sxs-lookup"><span data-stu-id="38ce1-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="38ce1-132">Genom att använda principbegränsningar kan du begränsa licensierade användare från att skapa Bookings-kalendrar.</span><span class="sxs-lookup"><span data-stu-id="38ce1-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="38ce1-133">Du måste först aktivera Bookings för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="38ce1-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="38ce1-134">Alla användare i organisationen har bookings-licenser, men endast de som ingår i principen kan skapa Bookings-kalendrar och har full kontroll över vem som kan komma åt kalendrarna som de skapar.</span><span class="sxs-lookup"><span data-stu-id="38ce1-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="38ce1-135">Användare som omfattas av den här principen kan skapa nya Bookings-kalendrar och kan läggas till som personal med alla funktioner (inklusive administratörsrollen) i befintliga Bookings-kalendrar.</span><span class="sxs-lookup"><span data-stu-id="38ce1-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="38ce1-136">Användare som inte omfattas av den här principen kan inte skapa nya Bookings-kalendrar och får ett felmeddelande om de försöker göra det.</span><span class="sxs-lookup"><span data-stu-id="38ce1-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="38ce1-137">Du måste köra följande kommandon med hjälp av Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38ce1-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="38ce1-138">Mer information om hur du kör Exchange Online-cmdlets finns i [Anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="38ce1-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38ce1-139">I stegen nedan förutsätts att inga andra Outlook Web App postlådeprinciper (OWA) har skapats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="38ce1-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="38ce1-140">Skapa en ny postlådeprincip för användare som ska kunna skapa Bookings-kalendrar.</span><span class="sxs-lookup"><span data-stu-id="38ce1-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="38ce1-141">(Som standard tillåts kalenderskapande i Bookings av nya postlådeprinciper.)</span><span class="sxs-lookup"><span data-stu-id="38ce1-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="38ce1-142">Mer information finns i [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="38ce1-142">For more information, see [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="38ce1-143">Tilldela den här principen till relevanta användare genom att köra det här kommandot för varje användare som du vill ge behörighet att skapa Bookings-kalendrar.</span><span class="sxs-lookup"><span data-stu-id="38ce1-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="38ce1-144">Mer information finns i [Set-CASMailbox.](/powershell/module/exchange/set-casmailbox)</span><span class="sxs-lookup"><span data-stu-id="38ce1-144">For more information, see [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="38ce1-145">Valfritt: Kör det här kommandot om du vill inaktivera Bookings för alla andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="38ce1-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="38ce1-146">Mer information finns i [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="38ce1-146">For more information, see [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="38ce1-147">Mer information om OWA-postlådeprinciper finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="38ce1-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="38ce1-148">Skapa en Outlook webbpostlådeprincip i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="38ce1-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="38ce1-149">Använda eller ta bort Outlook webbpostlådeprincip för en postlåda i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="38ce1-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)