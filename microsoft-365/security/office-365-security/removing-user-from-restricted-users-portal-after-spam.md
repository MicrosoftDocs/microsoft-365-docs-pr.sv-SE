---
title: Ta bort blockerade användare från portalen med åtkomstbegränsade användare
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Administratörer kan få information om hur de tar bort användare från portalen för åtkomstbegränsade användare i Office 365. Användare läggs till i portalen med åtkomstbegränsade användare för att de skickat utgående skräppost, oftast som ett resultat av kontointrång.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 43312ee6eff9b56ac4faf8173666a1ba79b9e067
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726726"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="81960-104">Ta bort blockerade användare från portalen med åtkomstbegränsade användare i Office 365</span><span class="sxs-lookup"><span data-stu-id="81960-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="81960-105">Om en användare överskrider någon av de utgående sändningsgränserna som anges i [tjänstbegränsningarna](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) eller i [utgående skräppostprinciper](configure-the-outbound-spam-policy.md), begränsas användaren från att skicka e-post, men de kan fortfarande ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="81960-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="81960-106">Användaren läggs till i portalen med åtkomstbegränsade användare i säkerhets- och efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="81960-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="81960-107">När de försöker skicka e-post returneras meddelandet i en rapport om utebliven leverans (kallas även för ett NDR eller icke-leveranskvitto) med felkoden [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) och följande text:</span><span class="sxs-lookup"><span data-stu-id="81960-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="81960-108">“Det gick inte att leverera meddelandet eftersom du inte godkändes som en giltig avsändare.</span><span class="sxs-lookup"><span data-stu-id="81960-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="81960-109">Vanligtvis beror detta på att din e-postadress är misstänkt för att skicka skräppost och det är inte längre tillåten att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="81960-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="81960-110">Kontakta e-postadministratören om du behöver hjälp.</span><span class="sxs-lookup"><span data-stu-id="81960-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="81960-111">Fjärrservern returnerade '550 5.1.8 åtkomst nekad, felaktig utgående avsändare”.</span><span class="sxs-lookup"><span data-stu-id="81960-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="81960-112">Administratörer kan ta bort användare från portalen med åtkomstbegränsade avsändare i säkerhets- och efterlevnadscentret eller i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81960-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="81960-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="81960-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="81960-114">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="81960-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="81960-115">Använd <https://protection.office.com/restrictedusers> för att gå direkt till sidan med **åtkomstbegränsade användare**.</span><span class="sxs-lookup"><span data-stu-id="81960-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="81960-116">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="81960-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="81960-117">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="81960-117">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="81960-118">Om du vill ta bort användare från portalen för åtkomstbegränsade användare måste du vara medlem i en av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="81960-118">To remove users from the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="81960-119">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="81960-119">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="81960-120">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="81960-120">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="81960-121">För skrivskyddad behörighet till portalen för åtkomstbegränsade användare måste du vara medlem i en av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="81960-121">For read-only access to the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="81960-122">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="81960-122">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="81960-123">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="81960-123">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="81960-124">En avsändare som överskrider gränsen för utgående e-post är ett bevis på ett komprometterat konto.</span><span class="sxs-lookup"><span data-stu-id="81960-124">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="81960-125">Innan du tar bort användaren från portalen för åtkomstbegränsade användare måste du följa de nödvändiga stegen för att återfå kontroll över kontot.</span><span class="sxs-lookup"><span data-stu-id="81960-125">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="81960-126">Mer information finns i [Svara på ett komprometterat e-postkonto i Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="81960-126">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="81960-127">Använda Säkerhets- och efterlevnadscentret för att ta bort en användare från listan med begränsade användare</span><span class="sxs-lookup"><span data-stu-id="81960-127">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="81960-128">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Begränsade användare**.</span><span class="sxs-lookup"><span data-stu-id="81960-128">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="81960-129">Leta rätt på och markera den användare som du vill avblockera.</span><span class="sxs-lookup"><span data-stu-id="81960-129">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="81960-130">I kolumnen **Åtgärder** klickar du på **Avblockera**.</span><span class="sxs-lookup"><span data-stu-id="81960-130">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="81960-131">En utfällbar meny kommer att visa information om det konto vars sändning är begränsad.</span><span class="sxs-lookup"><span data-stu-id="81960-131">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="81960-132">Vi rekommenderar att du går igenom rekommendationerna för att se till att du vidtar lämpliga åtgärder om kontot faktiskt är komprometterat.</span><span class="sxs-lookup"><span data-stu-id="81960-132">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="81960-133">Välj **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="81960-133">Click **Next** when done.</span></span>

4. <span data-ttu-id="81960-134">På nästa skärm finns rekommendationer för att förhindra framtida intrång.</span><span class="sxs-lookup"><span data-stu-id="81960-134">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="81960-135">Att aktivera multifaktorautentisering (MFA) och ändra lösenord är ett bra skydd.</span><span class="sxs-lookup"><span data-stu-id="81960-135">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="81960-136">Klicka **Avblockera användare** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="81960-136">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="81960-137">Bekräfta ändringen genom att klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="81960-137">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="81960-138">Det kan ta 30 minuter eller mer innan restriktioner tas bort.</span><span class="sxs-lookup"><span data-stu-id="81960-138">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="81960-139">Verifiera aviseringsinställningarna för begränsade användare</span><span class="sxs-lookup"><span data-stu-id="81960-139">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="81960-140">Standardaviseringsprincipen med namnet **Användare med restriktioner för att skicka e-post** meddelar automatiskt administratörer när användare hindras från att skicka utgående e-post.</span><span class="sxs-lookup"><span data-stu-id="81960-140">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="81960-141">Du kan kontrollera inställningarna och lägga till fler användare som ska meddelas.</span><span class="sxs-lookup"><span data-stu-id="81960-141">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="81960-142">Gå till [Varningsregler i Säkerhets- och efterlevnadscentret](../../compliance/alert-policies.md) om du vill ha mer information om varningsprinciper.</span><span class="sxs-lookup"><span data-stu-id="81960-142">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81960-143">För att varningar ska fungera måste Granskningsloggsökning aktiveras.</span><span class="sxs-lookup"><span data-stu-id="81960-143">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="81960-144">Du kan läsa mer i [Aktivera och inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="81960-144">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="81960-145">Gå till **Aviseringar** \> **Aviseringsprinciper** i Säkerhets- och efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="81960-145">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="81960-146">Sök efter och välj principen **Användare som begränsas från att skicka e-postavisering**.</span><span class="sxs-lookup"><span data-stu-id="81960-146">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="81960-147">I den utfällbara meny som visas kan du verifiera eller konfigurera följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="81960-147">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="81960-148">**Status**: verifiera att meddelandet är aktiverat ![Aktivera](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span><span class="sxs-lookup"><span data-stu-id="81960-148">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="81960-149">**E-postmottagare**: Klicka på **Redigera** och verifiera eller konfigurera följande inställningar i den utfällbara menyn **Redigera mottagare** som visas:</span><span class="sxs-lookup"><span data-stu-id="81960-149">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="81960-150">**Skicka e-postmeddelanden**: kontrollera att kryssrutan är markerad (**På**).</span><span class="sxs-lookup"><span data-stu-id="81960-150">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="81960-151">**E-postmottagare**: standardvärdet är **TenantAdmins** (d.v.s. **Globala administratör**medlemmar).</span><span class="sxs-lookup"><span data-stu-id="81960-151">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="81960-152">Klicka i ett tomt område i rutan om du vill lägga till fler mottagare.</span><span class="sxs-lookup"><span data-stu-id="81960-152">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="81960-153">En lista med mottagare visas, och du kan börja skriva ett namn för att filtrera och välja en mottagare.</span><span class="sxs-lookup"><span data-stu-id="81960-153">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="81960-154">Du kan ta bort en befintlig mottagare från rutan genom att klicka på ![Ta bort ikon](../../media/scc-remove-icon.png) bredvid namnet.</span><span class="sxs-lookup"><span data-stu-id="81960-154">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="81960-155">**Daglig aviseringsgräns**: standardvärdet är **Ingen gräns**, men du kan välja en gräns för max antal aviseringar per dag.</span><span class="sxs-lookup"><span data-stu-id="81960-155">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="81960-156">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="81960-156">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="81960-157">När du är tillbaka vid den utfällbara menyn **Användare som begränsats från att skicka e-post** klickar du på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="81960-157">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="81960-158">Använd Exchange Online PowerShell för att visa och ta bort användare från listan med åtkomstbegränsade användare</span><span class="sxs-lookup"><span data-stu-id="81960-158">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="81960-159">Om du vill visa en lista med användare som begränsas från att skicka e-post kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="81960-159">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="81960-160">Om du vill visa information om särskilda användare ersätter du \<emailaddress\> med deras e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="81960-160">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="81960-161">Se [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress) för detaljerad information om syntax och parametrar.</span><span class="sxs-lookup"><span data-stu-id="81960-161">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="81960-162">Om du vill ta bort användare från listan med åtkomstbegränsade användare ersätter du \<emailaddress\> med deras e-postadress och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="81960-162">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="81960-163">Se [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress) för detaljerad information om syntax och parametrar.</span><span class="sxs-lookup"><span data-stu-id="81960-163">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
