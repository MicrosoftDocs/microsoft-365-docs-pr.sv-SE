---
title: Ta bort blockerade användare från portalen med åtkomstbegränsade användare
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
description: Administratörer kan få information om hur de tar bort användare från portalen för åtkomstbegränsade användare i Office 365. Användare läggs till i portalen med åtkomstbegränsade användare för att de skickat utgående skräppost, oftast som ett resultat av kontointrång.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e08ed835a39fd687664b9325541c2a3f44644679
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289191"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="16fd3-104">Ta bort blockerade användare från portalen med åtkomstbegränsade användare i Office 365</span><span class="sxs-lookup"><span data-stu-id="16fd3-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="16fd3-105">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="16fd3-105">**Applies to**</span></span>
- [<span data-ttu-id="16fd3-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="16fd3-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="16fd3-107">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="16fd3-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="16fd3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16fd3-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="16fd3-109">Om en användare överskrider någon av de utgående sändningsgränserna som anges i [tjänstbegränsningarna](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) eller i [utgående skräppostprinciper](configure-the-outbound-spam-policy.md), begränsas användaren från att skicka e-post, men de kan fortfarande ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="16fd3-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="16fd3-110">Användaren läggs till i portalen med åtkomstbegränsade användare i säkerhets- och efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="16fd3-110">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="16fd3-111">När de försöker skicka e-post returneras meddelandet i en rapport om utebliven leverans (kallas även för ett NDR eller icke-leveranskvitto) med felkoden [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) och följande text:</span><span class="sxs-lookup"><span data-stu-id="16fd3-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="16fd3-112">“Det gick inte att leverera meddelandet eftersom du inte godkändes som en giltig avsändare.</span><span class="sxs-lookup"><span data-stu-id="16fd3-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="16fd3-113">Vanligtvis beror detta på att din e-postadress är misstänkt för att skicka skräppost och det är inte längre tillåten att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="16fd3-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="16fd3-114">Kontakta e-postadministratören om du behöver hjälp.</span><span class="sxs-lookup"><span data-stu-id="16fd3-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="16fd3-115">Fjärrservern returnerade '550 5.1.8 åtkomst nekad, felaktig utgående avsändare”.</span><span class="sxs-lookup"><span data-stu-id="16fd3-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="16fd3-116">Administratörer kan ta bort användare från portalen med åtkomstbegränsade avsändare i säkerhets- och efterlevnadscentret eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16fd3-116">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="16fd3-117">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="16fd3-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="16fd3-118">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="16fd3-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="16fd3-119">Använd <https://protection.office.com/restrictedusers> för att gå direkt till sidan med **åtkomstbegränsade användare**.</span><span class="sxs-lookup"><span data-stu-id="16fd3-119">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="16fd3-120">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="16fd3-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="16fd3-121">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="16fd3-121">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="16fd3-122">Om du vill ta bort användare från Portalen för begränsade användare måste du vara medlem i rollgruppen **Organisationsledning** eller **Säkerhetsadministratörer**.</span><span class="sxs-lookup"><span data-stu-id="16fd3-122">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="16fd3-123">För skrivskyddad behörighet till Portalen för begränsade användare måste du vara medlem i rollgruppen **Global läsare** eller **Säkerhetsläsare**.</span><span class="sxs-lookup"><span data-stu-id="16fd3-123">For read-only access to the Restricted Users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="16fd3-124">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="16fd3-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="16fd3-125">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="16fd3-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="16fd3-126">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="16fd3-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="16fd3-127">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="16fd3-127">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="16fd3-128">En avsändare som överskrider gränsen för utgående e-post är ett bevis på ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="16fd3-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="16fd3-129">Innan du tar bort användaren från portalen för åtkomstbegränsade användare måste du följa de nödvändiga stegen för att återfå kontroll över kontot.</span><span class="sxs-lookup"><span data-stu-id="16fd3-129">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="16fd3-130">Mer information finns i [Svara på ett komprometterat e-postkonto i Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="16fd3-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="16fd3-131">Använda Säkerhets- och efterlevnadscentret för att ta bort en användare från listan med begränsade användare</span><span class="sxs-lookup"><span data-stu-id="16fd3-131">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="16fd3-132">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Begränsade användare**.</span><span class="sxs-lookup"><span data-stu-id="16fd3-132">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="16fd3-133">Leta rätt på och markera den användare som du vill avblockera.</span><span class="sxs-lookup"><span data-stu-id="16fd3-133">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="16fd3-134">I kolumnen **Åtgärder** klickar du på **Avblockera**.</span><span class="sxs-lookup"><span data-stu-id="16fd3-134">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="16fd3-135">En utfällbar meny kommer att visa information om det konto vars sändning är begränsad.</span><span class="sxs-lookup"><span data-stu-id="16fd3-135">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="16fd3-136">Vi rekommenderar att du går igenom rekommendationerna för att se till att du vidtar lämpliga åtgärder om kontot faktiskt är komprometterat.</span><span class="sxs-lookup"><span data-stu-id="16fd3-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="16fd3-137">Välj **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="16fd3-137">Click **Next** when done.</span></span>

4. <span data-ttu-id="16fd3-138">På nästa skärm finns rekommendationer för att förhindra framtida intrång.</span><span class="sxs-lookup"><span data-stu-id="16fd3-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="16fd3-139">Att aktivera multifaktorautentisering (MFA) och ändra lösenord är ett bra skydd.</span><span class="sxs-lookup"><span data-stu-id="16fd3-139">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="16fd3-140">Klicka **Avblockera användare** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="16fd3-140">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="16fd3-141">Bekräfta ändringen genom att klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="16fd3-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="16fd3-142">Det kan ta upp till 24 timmar innan alla begränsningar tas bort från användaren.</span><span class="sxs-lookup"><span data-stu-id="16fd3-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="16fd3-143">Verifiera aviseringsinställningarna för begränsade användare</span><span class="sxs-lookup"><span data-stu-id="16fd3-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="16fd3-144">Standardaviseringsprincipen med namnet **Användare med restriktioner för att skicka e-post** meddelar automatiskt administratörer när användare hindras från att skicka utgående e-post.</span><span class="sxs-lookup"><span data-stu-id="16fd3-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="16fd3-145">Du kan kontrollera inställningarna och lägga till fler användare som ska meddelas.</span><span class="sxs-lookup"><span data-stu-id="16fd3-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="16fd3-146">Gå till [Varningsregler i Säkerhets- och efterlevnadscentret](../../compliance/alert-policies.md) om du vill ha mer information om varningsprinciper.</span><span class="sxs-lookup"><span data-stu-id="16fd3-146">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16fd3-147">För att varningar ska fungera måste Granskningsloggsökning aktiveras.</span><span class="sxs-lookup"><span data-stu-id="16fd3-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="16fd3-148">Du kan läsa mer i [Aktivera och inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="16fd3-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="16fd3-149">Gå till **Aviseringar** \> **Aviseringsprinciper** i Säkerhets- och efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="16fd3-149">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="16fd3-150">Sök efter och välj principen **Användare som begränsas från att skicka e-postavisering**.</span><span class="sxs-lookup"><span data-stu-id="16fd3-150">Find and select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="16fd3-151">I den utfällbara meny som visas kan du verifiera eller konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="16fd3-151">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="16fd3-152">**Status**: verifiera att meddelandet är aktiverat ![Aktivera](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="16fd3-152">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="16fd3-153">**E-postmottagare**: Klicka på **Redigera** och verifiera eller konfigurera följande inställningar i den utfällbara menyn **Redigera mottagare** som visas:</span><span class="sxs-lookup"><span data-stu-id="16fd3-153">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="16fd3-154">**Skicka e-postmeddelanden**: kontrollera att kryssrutan är markerad (**På**).</span><span class="sxs-lookup"><span data-stu-id="16fd3-154">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="16fd3-155">**E-postmottagare**: standardvärdet är **TenantAdmins** (d.v.s. **Globala administratör** medlemmar).</span><span class="sxs-lookup"><span data-stu-id="16fd3-155">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="16fd3-156">Klicka i ett tomt område i rutan om du vill lägga till fler mottagare.</span><span class="sxs-lookup"><span data-stu-id="16fd3-156">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="16fd3-157">En lista med mottagare visas, och du kan börja skriva ett namn för att filtrera och välja en mottagare.</span><span class="sxs-lookup"><span data-stu-id="16fd3-157">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="16fd3-158">Du kan ta bort en befintlig mottagare från rutan genom att klicka på ![Ta bort ikon](../../media/scc-remove-icon.png) bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="16fd3-158">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="16fd3-159">**Daglig aviseringsgräns**: standardvärdet är **Ingen gräns**, men du kan välja en gräns för max antal aviseringar per dag.</span><span class="sxs-lookup"><span data-stu-id="16fd3-159">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="16fd3-160">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="16fd3-160">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="16fd3-161">När du är tillbaka vid den utfällbara menyn **Användare som begränsats från att skicka e-post** klickar du på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="16fd3-161">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="16fd3-162">Använd Exchange Online PowerShell för att visa och ta bort användare från listan med åtkomstbegränsade användare</span><span class="sxs-lookup"><span data-stu-id="16fd3-162">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="16fd3-163">Om du vill visa en lista med användare som begränsas från att skicka e-post kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="16fd3-163">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="16fd3-164">Om du vill visa information om särskilda användare ersätter du \<emailaddress\> med deras e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="16fd3-164">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="16fd3-165">Se [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress) för detaljerad information om syntax och parametrar.</span><span class="sxs-lookup"><span data-stu-id="16fd3-165">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="16fd3-166">Om du vill ta bort användare från listan med åtkomstbegränsade användare ersätter du \<emailaddress\> med deras e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="16fd3-166">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="16fd3-167">Se [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress) för detaljerad information om syntax och parametrar.</span><span class="sxs-lookup"><span data-stu-id="16fd3-167">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
