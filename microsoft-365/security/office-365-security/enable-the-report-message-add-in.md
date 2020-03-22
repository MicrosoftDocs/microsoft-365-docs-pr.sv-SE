---
title: Aktivera tillägget Rapportmeddelande
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Lär dig hur du aktiverar tillägget Report Message för Outlook och Outlook på webben, för enskilda användare eller hela organisationen.
ms.openlocfilehash: 32b4ab318237ca220b63c87bd4a664cfb69d0b45
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893760"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="d8fcb-103">Aktivera tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="d8fcb-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="d8fcb-104">Tillägget Rapportmeddelande för Outlook och Outlook på webben är inte exakt samma sak som [skräppostfiltret](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)i Outlook, även om båda kan användas för att markera e-post som skräppost, inte skräppost eller ett nätfiskeförsök.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="d8fcb-105">Skillnaden är att tillägget Report Message för Outlook och Outlook på webben meddelar Microsoft om felklassificerad e-post, medan skräppostfiltret i Outlook används för att ordna e-postmeddelanden i en användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span>

## <a name="overview"></a><span data-ttu-id="d8fcb-106">Översikt</span><span class="sxs-lookup"><span data-stu-id="d8fcb-106">Overview</span></span>

<span data-ttu-id="d8fcb-107">Tillägget Report Message för Outlook och Outlook på webben (tidigare kallat Outlook Web App) gör det möjligt för personer att enkelt rapportera felklassificerad e-post, oavsett om den är säker eller skadlig, till Microsoft och dess dotterbolag för analys.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-107">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="d8fcb-108">Microsoft använder dessa inlämningar för att förbättra effektiviteten i e-postskyddstekniker.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="d8fcb-109">Om din organisation använder [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) eller [Plan 2](office-365-ti.md)ger tillägget Rapportmeddelande dessutom organisationens säkerhetsteam användbar information som de kan använda för att granska och uppdatera säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="d8fcb-110">Anta till exempel att andra rapporterar många meddelanden som nätfiske.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="d8fcb-111">Den här informationen visas i [säkerhetsinstrumentpanelen](security-dashboard.md) och andra rapporter.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="d8fcb-112">Organisationens säkerhetsteam kan använda den här informationen som en indikation på att anti-phishing-principer kan behöva uppdateras.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="d8fcb-113">Om personer rapporterar många meddelanden som har flaggats som skräppost som Inte skräppost med tillägget Rapportera meddelande kan organisationens säkerhetsteam behöva justera [principer mot skräppost.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d8fcb-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d8fcb-114">Tillägget Rapportmeddelande fungerar med de flesta Office 365-prenumerationer och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="d8fcb-114">The Report Message add-in works with most Office 365 subscriptions and the following products:</span></span>

- <span data-ttu-id="d8fcb-115">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="d8fcb-115">Outlook on the web</span></span>
- <span data-ttu-id="d8fcb-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="d8fcb-116">Outlook 2013 SP1</span></span>
- <span data-ttu-id="d8fcb-117">Utsikter 2016</span><span class="sxs-lookup"><span data-stu-id="d8fcb-117">Outlook 2016</span></span>
- <span data-ttu-id="d8fcb-118">Outlook 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="d8fcb-118">Outlook 2016 for Mac</span></span>
- <span data-ttu-id="d8fcb-119">Outlook ingår i Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="d8fcb-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="d8fcb-120">Tillägget Rapportmeddelande är inte tillgängligt för:</span><span class="sxs-lookup"><span data-stu-id="d8fcb-120">The Report Message add-in is currently not available for:</span></span>

- <span data-ttu-id="d8fcb-121">Postlådor i lokala Exchange-organisationer</span><span class="sxs-lookup"><span data-stu-id="d8fcb-121">Mailboxes in on-premises Exchange organizations</span></span>
- <span data-ttu-id="d8fcb-122">GCC-, GCC HIGH- eller DoD-prenumerationer</span><span class="sxs-lookup"><span data-stu-id="d8fcb-122">GCC, GCC HIGH, or DoD subscriptions</span></span>

<span data-ttu-id="d8fcb-123">Din befintliga webbläsare bör räcka för att tillägget Rapportmeddelande ska fungera. Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat provar du en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-123">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

<span data-ttu-id="d8fcb-124">Om du är en enskild användare kan du [aktivera tillägget Rapportmeddelande själv](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="d8fcb-124">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="d8fcb-125">Om du är global Office 365-administratör eller Exchange [Online-administratör](#get-and-enable-the-report-message-add-in-for-your-organization)och Exchange är konfigurerat för att använda OAuth-autentisering kan du aktivera tillägget Rapportmeddelande för din organisation .</span><span class="sxs-lookup"><span data-stu-id="d8fcb-125">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="d8fcb-126">Tillägget Rapportmeddelande är nu tillgängligt via [centraliserad distribution](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="d8fcb-126">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="d8fcb-127">Hämta tillägget Rapportmeddelande själv</span><span class="sxs-lookup"><span data-stu-id="d8fcb-127">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="d8fcb-128">Sök efter [tillägget Rapportmeddelande i](https://appsource.microsoft.com/product/office/wa104381180) [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps).</span><span class="sxs-lookup"><span data-stu-id="d8fcb-128">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>

2. <span data-ttu-id="d8fcb-129">Välj **HÄMTA DEN NU.**</span><span class="sxs-lookup"><span data-stu-id="d8fcb-129">Choose **GET IT NOW**.</span></span>

   ![Rapportera meddelande - Hämta det nu](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="d8fcb-131">Läs användarvillkoren och sekretesspolicyn.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-131">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="d8fcb-132">Välj sedan **Continue** (fortsätt).</span><span class="sxs-lookup"><span data-stu-id="d8fcb-132">Then choose **Continue**.</span></span>

4. <span data-ttu-id="d8fcb-133">Logga in på Office 365 med ditt arbets- eller skolkonto (för företagsbruk) eller ditt Microsoft-konto (för personligt bruk).</span><span class="sxs-lookup"><span data-stu-id="d8fcb-133">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="d8fcb-134">När tillägget har installerats och aktiverats visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="d8fcb-134">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="d8fcb-135">I Outlook ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="d8fcb-135">In Outlook, the icon looks like this:</span></span>

  ![Rapportmeddelandetillägg för Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="d8fcb-137">I Outlook på webben (tidigare kallat Outlook Web App) ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="d8fcb-137">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span>

  ![Outlook på ikonen För webbrapportmeddelande](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="d8fcb-139">Som ett nästa steg kan du läsa om hur [du använder tillägget Rapportmeddelande](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="d8fcb-139">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="d8fcb-140">Hämta och aktivera tillägget Rapportmeddelande för din organisation</span><span class="sxs-lookup"><span data-stu-id="d8fcb-140">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8fcb-141">Du måste vara global Office 365-administratör eller Exchange Online-administratör för att kunna utföra den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-141">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="d8fcb-142">Dessutom måste Exchange konfigureras för att använda OAuth-autentisering Om du vill veta mer finns [i Exchange-krav (centraliserad distribution av tillägg).](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="d8fcb-142">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

1. <span data-ttu-id="d8fcb-143">Gå till [sidan Tjänster & tillägg i administrationscentret](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-143">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![Sidan Tjänster och tillägg i det nya administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="d8fcb-145">Välj **+ Distribuera tillägg**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-145">Choose **+ Deploy Add-in**.</span></span>

   ![Välj distribuera tillägg](../../media/ServicesAddIns-ChooseDeployAddIn.png)

3. <span data-ttu-id="d8fcb-147">På skärmen **Nytt tillägg** granskar du informationen och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-147">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span>

   ![Ny information om tillägg](../../media/NewAddInScreen1.png)

4. <span data-ttu-id="d8fcb-149">Välj **Jag vill lägga till ett tillägg i Office Store**och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-149">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span>

   ![Jag vill lägga till ett nytt tillägg](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="d8fcb-151">Sök efter **rapportmeddelande**och välj **Lägg**till i listan med resultat bredvid **tillägget Rapportmeddelande.**</span><span class="sxs-lookup"><span data-stu-id="d8fcb-151">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span>

   ![Sök efter rapportmeddelande och välj sedan Lägg till](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="d8fcb-153">Granska informationen på skärmen **Rapportmeddelande** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-153">On the **Report Message** screen, review the information, and then choose **Next**.</span></span>

   ![Information om rapportmeddelande](../../media/ReportMessageAdd-InNewScreen4.png)

7. <span data-ttu-id="d8fcb-155">Ange standardinställningarna för användaren för Outlook och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-155">Specify the user default settings for Outlook, and  then choose **Next**.</span></span>

   ![Standardinställningar för Rapportmeddelande för Outlook](../../media/ReportMessageOptionsScreen5.png)

8. <span data-ttu-id="d8fcb-157">Ange vem som får tillägget Rapportmeddelande och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-157">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span>

   ![Vem får tillägget Rapportmeddelande](../../media/ReportMessageOptionsScreen6.png)

> [!TIP]
> <span data-ttu-id="d8fcb-159">Vi rekommenderar att [du konfigurerar en regel för att få en kopia av e-postmeddelanden som rapporterats av användarna](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span><span class="sxs-lookup"><span data-stu-id="d8fcb-159">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="d8fcb-160">Beroende på vad du valde när du konfigurerade tillägget (steg 7-8 ovan) har personer i organisationen [tillägget Report Message](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-160">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="d8fcb-161">Personer i organisationen ser följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="d8fcb-161">People in your organization will see the following icons:</span></span>

- <span data-ttu-id="d8fcb-162">I Outlook ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="d8fcb-162">In Outlook, the icon looks like this:</span></span>

  ![Ikonen För rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="d8fcb-164">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="d8fcb-164">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook i ikonen För webbrapportmeddelande](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="d8fcb-166">När du meddelar användarna om tillägget Rapportmeddelande ska du inkludera en länk till [Använda tillägget Rapportmeddelande](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="d8fcb-166">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="d8fcb-167">Konfigurera en regel för att få en kopia av e-postmeddelanden som rapporterats av användarna</span><span class="sxs-lookup"><span data-stu-id="d8fcb-167">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8fcb-168">Du måste vara Exchange Online-administratör för att kunna utföra den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-168">You must be an Exchange Online Administrator to perform this task.</span></span>

<span data-ttu-id="d8fcb-169">Du kan ställa in en regel för att få en kopia av e-postmeddelanden som rapporterats av användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-169">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="d8fcb-170">Du gör detta när du har hämtat och aktiverat tillägget Rapportmeddelande för din organisation.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-170">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>

1. <span data-ttu-id="d8fcb-171">Välj **regler**för **e-postflöde** \> i administrationscentret för Exchange .</span><span class="sxs-lookup"><span data-stu-id="d8fcb-171">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span>

2. <span data-ttu-id="d8fcb-172">Välj **+** \> **Skapa en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-172">Choose **+** \> **Create a new rule**.</span></span>

3. <span data-ttu-id="d8fcb-173">Skriv ett namn i rutan **Namn,** till exempel Inlämningar.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-173">In the **Name** box, type a name, such as Submissions.</span></span>

4. <span data-ttu-id="d8fcb-174">I listan **Använd den här regeln** väljer du **Mottagaradressen innehåller...**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-174">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span>

5. <span data-ttu-id="d8fcb-175">I skärmen **Ange ord eller** `junk@office365.microsoft.com` fraser `phish@office365.microsoft.com`lägger du till och och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-175">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span>

   ![Ange skräppost- och phish-e-postadresser för regeln](../../media/018c1833-f336-4333-a45c-f2e8b75cd698.png)

6. <span data-ttu-id="d8fcb-177">I listan **Gör följande...** väljer du **Bcc meddelandet till...**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-177">In the **Do the following...** list, choose **Bcc the message to...**.</span></span>

7. <span data-ttu-id="d8fcb-178">Lägg till en global administratör, säkerhetsadministratör och/eller säkerhetsläsare som ska få en kopia av varje e-postmeddelande som användarna rapporterar till Microsoft och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-178">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span>

   ![Lägga till en global administratör eller säkerhetsadministratör för att få en kopia av varje rapporterat meddelande](../../media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)

8. <span data-ttu-id="d8fcb-180">Välj **Granska den här regeln med allvarlighetsgrad**och välj **Medel**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-180">Select **Audit this rule with severity level**, and choose **Medium**.</span></span>

9. <span data-ttu-id="d8fcb-181">Under **Välj ett läge för den här regeln**väljer du **Verkställ**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-181">Under **Choose a mode for this rule**, choose **Enforce**.</span></span>

   ![Konfigurera en regel för att hämta en kopia av varje rapporterat meddelande](../../media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)

10. <span data-ttu-id="d8fcb-183">Välj **Save**.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-183">Choose **Save**.</span></span>

<span data-ttu-id="d8fcb-184">När någon i organisationen rapporterar ett e-postmeddelande med tillägget Rapportera meddelande får den globala administratören, säkerhetsadministratören och/eller säkerhetsläsaren en kopia av meddelandet när någon i organisationen rapporterar ett e-postmeddelande med tillägget Rapportera meddelande.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-184">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="d8fcb-185">Med den här informationen kan du ställa in eller justera principer, till exempel [office 365 ATP-principer](atp-safe-links.md) för säkra länkar eller dina [inställningar mot skräppost.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d8fcb-185">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span>

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="d8fcb-186">Läs om hur du använder tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="d8fcb-186">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="d8fcb-187">Se [Använda tillägget Rapportmeddelande](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="d8fcb-187">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="d8fcb-188">Granska eller redigera inställningar för tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="d8fcb-188">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="d8fcb-189">Du kan granska och redigera standardinställningarna för tillägget Rapportmeddelande på [sidan Tjänster & tillägg](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span><span class="sxs-lookup"><span data-stu-id="d8fcb-189">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8fcb-190">Du måste vara global Office 365-administratör eller Exchange Online-administratör för att kunna utföra den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-190">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>

1. <span data-ttu-id="d8fcb-191">Gå till [sidan Tjänster & tillägg i administrationscentret](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-191">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![Sidan Tjänster och tillägg i det nya administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="d8fcb-193">Sök efter och välj tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-193">Find and select the Report Message add-in.</span></span>

   ![Söka efter och markera tillägget Rapportmeddelande](../../media/FindReportMessageAddIn.png)

3. <span data-ttu-id="d8fcb-195">Granska och redigera inställningar på skärmen Rapportera meddelanden efter behov för din organisation.</span><span class="sxs-lookup"><span data-stu-id="d8fcb-195">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span>

   ![Inställningar för tillägget Rapportmeddelande](../../media/EditReportMessageAddIn.png)

## <a name="related-topics"></a><span data-ttu-id="d8fcb-197">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d8fcb-197">Related topics</span></span>

[<span data-ttu-id="d8fcb-198">Använda tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="d8fcb-198">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

[<span data-ttu-id="d8fcb-199">Visa säkerhetsrapporter för &amp; e-post i Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="d8fcb-199">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="d8fcb-200">Visa rapporter för avancerat hotskydd för Office 365</span><span class="sxs-lookup"><span data-stu-id="d8fcb-200">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="d8fcb-201">Använda Explorer i &amp; Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="d8fcb-201">Use Explorer in the Security &amp; Compliance Center</span></span>](threat-explorer.md)
