---
title: Ta bort en användare från portalen med åtkomstbegränsade användare efter att användaren har skickat skräppost
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
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
description: Om en användare kontinuerligt skickar e-postmeddelanden från Office 365 som klassificeras som skräppost, begränsas de från att skicka fler meddelanden.
ms.openlocfilehash: 6fad4b9d3554228bdbf474bce2b4b2d0f29f7e2b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812251"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="39055-103">Ta bort en användare från portalen med åtkomstbegränsade användare efter att användaren har skickat skräppost</span><span class="sxs-lookup"><span data-stu-id="39055-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="39055-104">Om en användare regelbundet skickar e-postmeddelanden som klassificeras som skräppost från Office 365, kommer de att begränsas från att skicka e-post, men de kan fortfarande ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="39055-104">If a user continuously sends emails that are classified as spam from Office 365, they will be restricted from sending email, but will still be able to receive it.</span></span> <span data-ttu-id="39055-105">Användaren visas i tjänsten som olämplig utgående avsändare och får en rapport om utebliven leverans (NDR) som anger:</span><span class="sxs-lookup"><span data-stu-id="39055-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

> <span data-ttu-id="39055-106">“Det gick inte att leverera meddelandet eftersom du inte godkändes som en giltig avsändare.</span><span class="sxs-lookup"><span data-stu-id="39055-106">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="39055-107">Vanligtvis beror detta på att din e-postadress är misstänkt för att skicka skräppost och det är inte längre tillåten att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="39055-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="39055-108">Kontakta e-postadministratören om du behöver hjälp.</span><span class="sxs-lookup"><span data-stu-id="39055-108">Contact  your email admin for assistance.</span></span> <span data-ttu-id="39055-109">Fjärrservern returnerade '550 5.1.8 åtkomst nekad, felaktig utgående avsändare”.</span><span class="sxs-lookup"><span data-stu-id="39055-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="39055-110">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="39055-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="39055-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="39055-111"><a name="sectionSection0"> </a></span></span>

<span data-ttu-id="39055-112">Beräknad tid: 5 minuter</span><span class="sxs-lookup"><span data-stu-id="39055-112">Estimated time to complete: 5 minutes</span></span>

<span data-ttu-id="39055-113">Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna.</span><span class="sxs-lookup"><span data-stu-id="39055-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="39055-114">Om du vill se vilka behörigheter du behöver kan du läsa avsnittet “Skydd mot skräppost i [Funktionsbehörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions).</span><span class="sxs-lookup"><span data-stu-id="39055-114">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span>

<span data-ttu-id="39055-115">Följande procedur kan även utföras via fjärransluten PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39055-115">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="39055-116">Använd cmdleten Get-BlockedSenderAddress för att få listan med begränsade användare och Remove-BlockedSenderAddress för att ta bort begränsningen.</span><span class="sxs-lookup"><span data-stu-id="39055-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="39055-117">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="39055-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="39055-118">Ta bort begränsningar för ett blockerat Office 365-e-postkonto</span><span class="sxs-lookup"><span data-stu-id="39055-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="39055-119">Du slutför den här uppgiften i Säkerhets- och efterlevnadscentret (SCC).</span><span class="sxs-lookup"><span data-stu-id="39055-119">You complete this task in the Security & Compliance Center (SCC).</span></span> <span data-ttu-id="39055-120">[Gå till Säkerhets- och efterlevnadscentret](../../compliance/go-to-the-securitycompliance-center.md) om du vill ha mer information om SCC.</span><span class="sxs-lookup"><span data-stu-id="39055-120">[Go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="39055-121">Du måste vara med i rollgrupperna**Organisationshantering** eller **Säkerhetsadministratör** för att kunna utföra de här funktionerna.</span><span class="sxs-lookup"><span data-stu-id="39055-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="39055-122">[Gå till Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md) om du vill ha mer information om SCC-rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="39055-122">[Go to Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="39055-123">Använd ett arbets- eller skolkonto som har globala åtkomstbehörigheter för administratörer i Office 365, logga in i Säkerhets- och efterlevnadscentret i Office 365 och visa **Hothantering** i listan till vänster, välj **Granska**och välj sedan **Begränsade användare**.</span><span class="sxs-lookup"><span data-stu-id="39055-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>

    > [!TIP]
    > <span data-ttu-id="39055-124">Om du vill gå direkt till sidan **Begränsad användare** (tidigare kallat Aktivitetscentret) i Säkerhets-&amp; och efterlevnadscentret använder du följande URL: [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="39055-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="39055-125">Den här sidan innehåller en lista med användare som har blockerats från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="39055-125">This page will contain the list of users that have been blocked from sending email.</span></span>  <span data-ttu-id="39055-126">Leta rätt på den användare som du vill ta bort restriktioner från och välj **Avblockera**.</span><span class="sxs-lookup"><span data-stu-id="39055-126">Find the user you wish to remove restrictions from, and select **Unblock**.</span></span>

3. <span data-ttu-id="39055-127">En utfällbar meny kommer att visa information om det konto vars sändning är begränsad.</span><span class="sxs-lookup"><span data-stu-id="39055-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="39055-128">Vi rekommenderar att du går igenom rekommendationerna för att se till att du vidtar lämpliga åtgärder om kontot faktiskt är komprometterat.</span><span class="sxs-lookup"><span data-stu-id="39055-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="39055-129">Välj **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="39055-129">Click **Next** when done.</span></span>

4. <span data-ttu-id="39055-130">På nästa skärm finns rekommendationer för att förhindra framtida intrång.</span><span class="sxs-lookup"><span data-stu-id="39055-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="39055-131">Att aktivera multifaktorautentisering (MFA) och ändra lösenord är ett bra skydd.</span><span class="sxs-lookup"><span data-stu-id="39055-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="39055-132">Klicka **Avblockera användare** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="39055-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="39055-133">Bekräfta ändringen genom att klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="39055-133">Click **Yes** to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="39055-134">Det kan ta 30 minuter eller mer innan restriktioner tas bort.</span><span class="sxs-lookup"><span data-stu-id="39055-134">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="39055-135">Att se till att administratörer varnas när detta händer</span><span class="sxs-lookup"><span data-stu-id="39055-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="39055-136">Varningen "Användare begränsas från att skicka e-post" är tillgänglig som policy på sidan med säkerhets- och aviseringsprinciper för Office 365.</span><span class="sxs-lookup"><span data-stu-id="39055-136">A "User restricted from sending email" alert is available as a policy under the Office 365 Security & Compliance Alert policies page.</span></span> <span data-ttu-id="39055-137">Detta var tidigare den utgående skräppostprincipen, men är nu inbyggd i varningsplattformen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="39055-137">This was formerly the outbound spam policy but is now native to the Office 365 alerting platform.</span></span> <span data-ttu-id="39055-138">Gå till [Varningsregler i Säkerhets- och efterlevnadscentret](../../compliance/alert-policies.md) om du vill ha mer information om varningar.</span><span class="sxs-lookup"><span data-stu-id="39055-138">Go to [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md) for more information on alerts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39055-139">För att varningar ska fungera måste Granskningsloggsökning aktiveras.</span><span class="sxs-lookup"><span data-stu-id="39055-139">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="39055-140">Du kan läsa hur man gör i [Aktivera och inaktivera granskningsloggsökning för Office 365](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="39055-140">See how to [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md) for more information.</span></span>

<span data-ttu-id="39055-141">Principen för den här varningen är en standardprincip och medföljer alla Office 365-klientorganisationer och behöver inte konfigureras.</span><span class="sxs-lookup"><span data-stu-id="39055-141">The policy for this alert is a default one and comes with every Office 365 tenant and does not need to be set up.</span></span> <span data-ttu-id="39055-142">Det anses vara ett varningsmeddelande med hög allvarlighetsgrad och kommer att skickas till den konfigurerade TenantAdmins-gruppen när meddelandet skickas då en användare har begränsats från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="39055-142">It is considered a High severity alert and will email the configured TenantAdmins group when the alert is fired whenever a user has been restricted from sending mail.</span></span> <span data-ttu-id="39055-143">Administratörer kan uppdatera den grupp som meddelas när denna varning görs genom att gå till varningen under SCC-portalen > Varningar > Varningsregler > Användare som begränsats från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="39055-143">Admins can update the group notified when this alert happens by going to the alert under the SCC portal > Alerts > Alert policies > Users restricted from sending email.</span></span>

<span data-ttu-id="39055-144">Du kan redigera varningen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="39055-144">You will be able to Edit the alert to:</span></span>
- <span data-ttu-id="39055-145">Aktivera/inaktivera e-postaviseringar</span><span class="sxs-lookup"><span data-stu-id="39055-145">Turn email notifications On/Off</span></span>
- <span data-ttu-id="39055-146">Skicka e-post till nödvändiga mottagare</span><span class="sxs-lookup"><span data-stu-id="39055-146">Email the required recipients</span></span>
- <span data-ttu-id="39055-147">Begränsa antalet dagliga aviseringar du tar emot</span><span class="sxs-lookup"><span data-stu-id="39055-147">Limit the notifications you get per day</span></span>

## <a name="checking-for-and-removing-restrictions-using-powershell"></a><span data-ttu-id="39055-148">Söka efter och ta bort restriktioner med PowerShell</span><span class="sxs-lookup"><span data-stu-id="39055-148">Checking for and removing restrictions using PowerShell</span></span>
<span data-ttu-id="39055-149">PowerShell-kommandon för begränsade användare är:</span><span class="sxs-lookup"><span data-stu-id="39055-149">The PowerShell commands for Restricted Users are:</span></span>
- <span data-ttu-id="39055-150">`Get-BlockedSenderAddress`: Kör för att hämta listan över användare som begränsas från att skicka e-post</span><span class="sxs-lookup"><span data-stu-id="39055-150">`Get-BlockedSenderAddress`: Run to retrieve the list of users that are restricted from sending email</span></span>
- <span data-ttu-id="39055-151">`Remove-BlockedSenderAddress`: Kör för att ta bort användare från att begränsas</span><span class="sxs-lookup"><span data-stu-id="39055-151">`Remove-BlockedSenderAddress`: Run to remove user(s) from being restricted</span></span>

## <a name="for-more-information"></a><span data-ttu-id="39055-152">Mer information</span><span class="sxs-lookup"><span data-stu-id="39055-152">For more information</span></span>

[<span data-ttu-id="39055-153">Svara på ett komprometterat e-postkonto</span><span class="sxs-lookup"><span data-stu-id="39055-153">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="39055-154">Information om användaren som begränsas från att skicka e-postavisering</span><span class="sxs-lookup"><span data-stu-id="39055-154">Understanding the User restricted from sending email alert</span></span>](https://docs.microsoft.com/office365/securitycompliance/alert-policies)

[<span data-ttu-id="39055-155">Pool med hög riskleverans för utgående meddelanden</span><span class="sxs-lookup"><span data-stu-id="39055-155">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="39055-156">Behörigheter i Säkerhets- och efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="39055-156">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

[<span data-ttu-id="39055-157">Aviseringsregler i Säkerhets- och efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="39055-157">Alert policies in the Security & Compliance Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/alert-policies)
