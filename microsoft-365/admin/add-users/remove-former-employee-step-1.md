---
title: Steg 1 – Hindra en anställd från att logga in på Microsoft 365
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
description: Blockera en tidigare anställd från att logga in och blockera åtkomst till Microsoft 365 tjänster.
ms.openlocfilehash: 60f4cf6b5c9a0b5dc2023b3ef7b6460685142d07
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244300"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="ee906-103">Steg 1 – Förhindra en tidigare anställd från att logga in och blockera åtkomst Microsoft 365 tjänster</span><span class="sxs-lookup"><span data-stu-id="ee906-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="ee906-104">Om du omedelbart behöver förhindra en användares inloggningsåtkomst ska du återställa användarens lösenord.</span><span class="sxs-lookup"><span data-stu-id="ee906-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="ee906-105">I det här steget tvingar du användaren att logga ut från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee906-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

1. <span data-ttu-id="ee906-106">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ee906-106">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="ee906-107">Markera rutan bredvid användarens namn och välj sedan **Återställ lösenord**.</span><span class="sxs-lookup"><span data-stu-id="ee906-107">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="ee906-108">Ange ett nytt lösenord och välj sedan **Återställ**.</span><span class="sxs-lookup"><span data-stu-id="ee906-108">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="ee906-109">(Skicka det inte till dem.)</span><span class="sxs-lookup"><span data-stu-id="ee906-109">(Don't send it to them.)</span></span>
4. <span data-ttu-id="ee906-110">Välj användarens namn för att gå till egenskapsfönstret och välj Initiera ut logga **ut på fliken Konto.** </span><span class="sxs-lookup"><span data-stu-id="ee906-110">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="ee906-111">Inom en timme – eller efter att han eller hon lämnar den Microsoft 365 aktuella sidan de befinner sig på – uppmanas de att logga in igen.</span><span class="sxs-lookup"><span data-stu-id="ee906-111">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="ee906-112">En åtkomsttoken är bra i en timme, så tidslinjen beror på hur mycket tid som återstår för den tokenen och om de navigerar från den aktuella webbsidan.</span><span class="sxs-lookup"><span data-stu-id="ee906-112">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ee906-113">Om användaren är i Outlook på webben, bara klickar runt i postlådan, kanske han/hon inte sparkas ut direkt.</span><span class="sxs-lookup"><span data-stu-id="ee906-113">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="ee906-114">Så snart de väljer en annan panel, till OneDrive, eller uppdaterar sin webbläsare initieras ut logga ut.</span><span class="sxs-lookup"><span data-stu-id="ee906-114">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="ee906-115">Om du vill använda PowerShell för att logga ut en användare direkt går du till cmdleten [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="ee906-115">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="ee906-116">Mer information om hur lång tid det tar att avsluta en persons e-post finns i [Vad du behöver veta om att avsluta en anställds e-postsession](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="ee906-116">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="ee906-117">Blockera en tidigare anställds åtkomst till Microsoft 365 tjänster</span><span class="sxs-lookup"><span data-stu-id="ee906-117">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="ee906-118">Det kan ta upp till 24 timmar innan blockeringen av ett konto verkställs.</span><span class="sxs-lookup"><span data-stu-id="ee906-118">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="ee906-119">Om du omedelbart behöver förhindra en användares inloggningsåtkomst följer du stegen ovan och återställer deras lösenord.</span><span class="sxs-lookup"><span data-stu-id="ee906-119">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="ee906-120">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ee906-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="ee906-121">Markera namnet på den anställda som du vill blockera och välj symbolen för Blockera den här användaren under **användarnamnet.**</span><span class="sxs-lookup"><span data-stu-id="ee906-121">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="ee906-122">Välj **Blockera användaren från att logga in** och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ee906-122">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="ee906-123">Blockera en tidigare anställds åtkomst till e-post (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="ee906-123">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="ee906-124">Om du har e-post som en del av Microsoft 365-prenumerationen loggar du in på Exchange-administrationscentret och följer de här stegen för att blockera den tidigare anställda från att komma åt sin e-post.</span><span class="sxs-lookup"><span data-stu-id="ee906-124">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="ee906-125">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="ee906-125">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="ee906-126">I Administrationscenter för Exchange går du till **Mottagare** \> **Postlådor**.</span><span class="sxs-lookup"><span data-stu-id="ee906-126">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="ee906-127">Dubbelklicka på användaren och gå till sidan **Postlådefunktioner.**</span><span class="sxs-lookup"><span data-stu-id="ee906-127">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="ee906-128">Under **Mobila enheter** väljer du Inaktivera **Exchange ActiveSync** inaktivera **OWA** för enheter och svarar **Ja** på båda när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="ee906-128">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="ee906-129">Under **E-postanslutning** väljer **du Inaktivera** och svarar Ja **när** du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="ee906-129">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
