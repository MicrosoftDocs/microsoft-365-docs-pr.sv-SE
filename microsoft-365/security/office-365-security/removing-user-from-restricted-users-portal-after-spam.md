---
title: Ta bort blockerade användare från portalen med begränsade användare
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Administratörer kan få information om hur de tar bort användare från sidan för begränsade användare i Microsoft 365 Defender-portalen. Användare läggs till i portalen med begränsade användare för att de har skickat skräppost, oftast som ett resultat av kontointrång.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082858"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a><span data-ttu-id="93ce0-104">Ta bort blockerade användare från portalen med begränsade användare i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93ce0-104">Remove blocked users from the Restricted users portal in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="93ce0-105">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="93ce0-105">**Applies to**</span></span>
- [<span data-ttu-id="93ce0-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="93ce0-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="93ce0-107">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="93ce0-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="93ce0-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93ce0-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="93ce0-109">Om en användare överskrider någon av de utgående sändningsgränserna som anges i [tjänstbegränsningarna](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) eller i [utgående skräppostprinciper](configure-the-outbound-spam-policy.md), begränsas användaren från att skicka e-post, men de kan fortfarande ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="93ce0-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="93ce0-110">Användaren läggs till på sidan **Begränsade användare** i Microsoft 365 Defender-portalen.</span><span class="sxs-lookup"><span data-stu-id="93ce0-110">The user is added to the **Restricted users** page in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="93ce0-111">När de försöker skicka e-post returneras meddelandet i en rapport om utebliven leverans (kallas även för ett NDR eller icke-leveranskvitto) med felkoden [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) och följande text:</span><span class="sxs-lookup"><span data-stu-id="93ce0-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="93ce0-112">“Det gick inte att leverera meddelandet eftersom du inte godkändes som en giltig avsändare.</span><span class="sxs-lookup"><span data-stu-id="93ce0-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="93ce0-113">Vanligtvis beror detta på att din e-postadress är misstänkt för att skicka skräppost och det är inte längre tillåten att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="93ce0-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="93ce0-114">Kontakta e-postadministratören om du behöver hjälp.</span><span class="sxs-lookup"><span data-stu-id="93ce0-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="93ce0-115">Fjärrservern returnerade '550 5.1.8 åtkomst nekad, felaktig utgående avsändare”.</span><span class="sxs-lookup"><span data-stu-id="93ce0-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="93ce0-116">Administratörer kan ta bort användare från sidan för begränsade användare i Microsoft 365 Defender eller Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93ce0-116">Admins can remove users from the Restricted users page in the Microsoft 365 Defender or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="93ce0-117">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="93ce0-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="93ce0-118">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="93ce0-118">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="93ce0-119">Om du vill gå direkt till sidan med **Begränsade användare** använder du <https://security.microsoft.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="93ce0-119">Too go directly to the **Restricted users** page, use <https://security.microsoft.com/restrictedusers>.</span></span>

- <span data-ttu-id="93ce0-120">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="93ce0-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="93ce0-121">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="93ce0-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="93ce0-122">Om du vill ta bort användare från portalen med begränsade användare måste du vara medlem i en av rollgrupperna **Organisationsledning** eller **Säkerhetsadministratör**.</span><span class="sxs-lookup"><span data-stu-id="93ce0-122">To remove users from the Restricted users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="93ce0-123">För skrivskyddad åtkomst till portalen med begränsade användare måste du vara medlem i en av rollgrupperna **Global läsare** eller **Säkerhetsläsare**.</span><span class="sxs-lookup"><span data-stu-id="93ce0-123">For read-only access to the Restricted users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="93ce0-124">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="93ce0-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="93ce0-125">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93ce0-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="93ce0-126">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="93ce0-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="93ce0-127">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="93ce0-127">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="93ce0-128">En avsändare som överskrider gränsen för utgående e-post är ett bevis på ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="93ce0-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="93ce0-129">Innan du tar bort användaren från portalen med begränsade användare måste du följa de nödvändiga stegen för att återfå kontrollen över deras konto.</span><span class="sxs-lookup"><span data-stu-id="93ce0-129">Before you remove the user from the Restricted users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="93ce0-130">Mer information finns i [Åtgärda ett komprometterat e-postkonto i Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="93ce0-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="93ce0-131">Använd Microsoft 365 Defender-portalen för att ta bort en användare från listan med begränsade användare</span><span class="sxs-lookup"><span data-stu-id="93ce0-131">Use the Microsoft 365 Defender portal to remove a user from the Restricted users list</span></span>

1. <span data-ttu-id="93ce0-132">I Microsoft 365 Defender-portalen går du till **E-post och samarbete** > **Granska** > **Begränsade användare**.</span><span class="sxs-lookup"><span data-stu-id="93ce0-132">In the Microsoft 365 Defender portal, go to **Email & collaboration** > **Review** > **Restricted users**.</span></span>

2. <span data-ttu-id="93ce0-133">På sidan **Begränsade användare** letar du upp och väljer den användare som du vill avblockera genom att klicka på användaren.</span><span class="sxs-lookup"><span data-stu-id="93ce0-133">On the **Restricted users** page, find and select the user that you want to unblock by clicking on the user.</span></span>

3. <span data-ttu-id="93ce0-134">Klicka på åtgärden **Avblockera** som visas.</span><span class="sxs-lookup"><span data-stu-id="93ce0-134">Click the **Unblock** action that appears.</span></span>

4. <span data-ttu-id="93ce0-135">I den utfällbara menyn **Avblockera användare** som visas kan du läsa information om det begränsade kontot.</span><span class="sxs-lookup"><span data-stu-id="93ce0-135">In the **Unblock user** flyout that appears, read the details about the restricted account.</span></span> <span data-ttu-id="93ce0-136">Du bör gå igenom rekommendationerna för att se till att du vidtar rätt åtgärder om kontot har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="93ce0-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is compromised.</span></span>

   <span data-ttu-id="93ce0-137">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="93ce0-137">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="93ce0-138">På nästa skärm finns rekommendationer för att förhindra framtida intrång.</span><span class="sxs-lookup"><span data-stu-id="93ce0-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="93ce0-139">Att aktivera multifaktorautentisering (MFA) och återställa lösenordet är ett bra skydd.</span><span class="sxs-lookup"><span data-stu-id="93ce0-139">Enabling multi-factor authentication (MFA) and resetting the password are a good defense.</span></span>

   <span data-ttu-id="93ce0-140">Klicka på **Skicka in** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="93ce0-140">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="93ce0-141">Bekräfta ändringen genom att klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="93ce0-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="93ce0-142">Det kan ta upp till 24 timmar innan alla begränsningar tas bort från användaren.</span><span class="sxs-lookup"><span data-stu-id="93ce0-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="93ce0-143">Verifiera aviseringsinställningarna för begränsade användare</span><span class="sxs-lookup"><span data-stu-id="93ce0-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="93ce0-144">Standardaviseringsprincipen med namnet **Användare med restriktioner för att skicka e-post** meddelar automatiskt administratörer när användare hindras från att skicka utgående e-post.</span><span class="sxs-lookup"><span data-stu-id="93ce0-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="93ce0-145">Du kan kontrollera inställningarna och lägga till fler användare som ska meddelas.</span><span class="sxs-lookup"><span data-stu-id="93ce0-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="93ce0-146">Mer information om aviseringsprinciper finns i [Principer för aviseringar i Microsoft 365](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="93ce0-146">For more information about alert policies, see [Alert policies in Microsoft 365](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93ce0-147">För att varningar ska fungera måste Granskningsloggsökning aktiveras.</span><span class="sxs-lookup"><span data-stu-id="93ce0-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="93ce0-148">Du kan läsa mer i [Aktivera och inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="93ce0-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="93ce0-149">I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Principer och regler** \> **Varningsprincip**.</span><span class="sxs-lookup"><span data-stu-id="93ce0-149">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Alert policy**.</span></span>

2. <span data-ttu-id="93ce0-150">På sidan **Varningsprincip** letar du upp och väljer varningen med namnet **Användare som inte kan skicka e-post**.</span><span class="sxs-lookup"><span data-stu-id="93ce0-150">On the **Alert policy** page, find and select the alert named **User restricted from sending email**.</span></span> <span data-ttu-id="93ce0-151">Du kan sortera principerna efter namn eller använda **Sökrutan** för att hitta principen.</span><span class="sxs-lookup"><span data-stu-id="93ce0-151">You can sort the policies by name, or use the **Search box** to find the policy.</span></span>

3. <span data-ttu-id="93ce0-152">I den utfällbara menyn **Användare som inte kan skicka e-post** som visas kontrollerar eller konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="93ce0-152">In the **User restricted from sending email** flyout that appears, verify or configure the following settings:</span></span>
   - <span data-ttu-id="93ce0-153">**Status**: verifiera att meddelandet är aktiverat ![Aktivera](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="93ce0-153">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="93ce0-154">**E-postmottagare**: Klicka på **Redigera** och verifiera eller konfigurera följande inställningar i den utfällbara menyn **Redigera mottagare** som visas:</span><span class="sxs-lookup"><span data-stu-id="93ce0-154">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>
     - <span data-ttu-id="93ce0-155">**Skicka e-postmeddelanden**: Kontrollera att kryssrutan är markerad (**På**).</span><span class="sxs-lookup"><span data-stu-id="93ce0-155">**Send email notifications**: Verify this is selected (**On**).</span></span>
     - <span data-ttu-id="93ce0-156">**E-postmottagare**: standardvärdet är **TenantAdmins** (d.v.s. **Globala administratör** medlemmar).</span><span class="sxs-lookup"><span data-stu-id="93ce0-156">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="93ce0-157">Klicka i ett tomt område i rutan om du vill lägga till fler mottagare.</span><span class="sxs-lookup"><span data-stu-id="93ce0-157">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="93ce0-158">En lista med mottagare visas, och du kan börja skriva ett namn för att filtrera och välja en mottagare.</span><span class="sxs-lookup"><span data-stu-id="93ce0-158">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="93ce0-159">Du kan ta bort en befintlig mottagare från rutan genom att klicka på ![Ta bort ikon](../../media/m365-cc-sc-remove-selection-icon.png) bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="93ce0-159">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to their name.</span></span>
     - <span data-ttu-id="93ce0-160">**Daglig aviseringsgräns**: standardvärdet är **Ingen gräns**, men du kan välja en gräns för max antal aviseringar per dag.</span><span class="sxs-lookup"><span data-stu-id="93ce0-160">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="93ce0-161">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="93ce0-161">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="93ce0-162">När du är tillbaka vid den utfällbara menyn **Användare som begränsats från att skicka e-post** klickar du på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="93ce0-162">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="93ce0-163">Använd Exchange Online PowerShell för att visa och ta bort användare från listan med begränsade användare</span><span class="sxs-lookup"><span data-stu-id="93ce0-163">Use Exchange Online PowerShell to view and remove users from the Restricted users list</span></span>

<span data-ttu-id="93ce0-164">Om du vill visa en lista med användare som begränsas från att skicka e-post kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="93ce0-164">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="93ce0-165">Om du vill visa information om särskilda användare ersätter du \<emailaddress\> med deras e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="93ce0-165">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="93ce0-166">Se [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress) för detaljerad information om syntax och parametrar.</span><span class="sxs-lookup"><span data-stu-id="93ce0-166">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="93ce0-167">Om du vill ta bort användare från listan med begränsade användare ersätter du \<emailaddress\> med deras e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="93ce0-167">To remove a user from the Restricted users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="93ce0-168">Se [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress) för detaljerad information om syntax och parametrar.</span><span class="sxs-lookup"><span data-stu-id="93ce0-168">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
