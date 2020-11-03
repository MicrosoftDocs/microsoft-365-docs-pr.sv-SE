---
title: Felsökning av Microsoft 365 användningsanalyser
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Lär dig hur du felsöker problem med programmet Microsoft 365 användnings analys.
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841441"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="6e838-103">Felsökning av Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="6e838-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="6e838-104">Utforska följande lista över felmeddelanden för att få hjälp med de vanligaste problemen med användningsanalyser för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e838-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="6e838-105">Vi kan inte att bearbeta din begäran.</span><span class="sxs-lookup"><span data-stu-id="6e838-105">We are unable to process your request.</span></span> <span data-ttu-id="6e838-106">Du måste först abonnera på dessa data från administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6e838-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="6e838-107">**Felkod:** 422</span><span class="sxs-lookup"><span data-stu-id="6e838-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="6e838-108">**Här visas det här meddelandet:** I Power BI när du ansluter till Microsoft 365 användnings analys Template-programmet eller när du direkt anropar API: erna Microsoft 365 repor ting.</span><span class="sxs-lookup"><span data-stu-id="6e838-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="6e838-109">**Orsak:** Innan du kan ansluta till appen måste du abonnera på data från administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e838-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="6e838-110">Om det här steget inte är först kan du inte ansluta till programmet, även om du tillhandahåller ditt Microsoft 365-klient-ID.</span><span class="sxs-lookup"><span data-stu-id="6e838-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="6e838-111">**Så här åtgärdar du felet:** Om du vill abonnera på data går du till administrations centrets \> **rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> och letar reda på Microsoft 365 användnings analys panelen på huvud instrument panelen.</span><span class="sxs-lookup"><span data-stu-id="6e838-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="6e838-112">Välj knappen **Kom igång** och sedan, i fönstret **rapporter** som öppnas, aktiverar du inställningen **gör data tillgängliga för Microsoft 365 användnings analys för Power BI** på och **Spara** .</span><span class="sxs-lookup"><span data-stu-id="6e838-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save** .</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="6e838-113">Vi bearbetar dina data</span><span class="sxs-lookup"><span data-stu-id="6e838-113">We are processing your data</span></span>

 <span data-ttu-id="6e838-114">**Här visas det här meddelandet:** I panelen **microsoft 365 användnings analys** på instrument panelen för **användning** i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e838-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="6e838-115">**Orsak:** När du [väljer att visa data i programmet](enable-usage-analytics.md) från administrations centret för Microsoft 365 börjar Microsoft 365-systemet att generera historiska data för din organisation.</span><span class="sxs-lookup"><span data-stu-id="6e838-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="6e838-116">Beroende på storleken på klientorganisationen kan det här steget ta mellan två till fyrtioåtta timmar.</span><span class="sxs-lookup"><span data-stu-id="6e838-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="6e838-117">**Så här löser du det:** Det är bara tålamod, men om meddelandet inte ändras till **dina data är klara** efter tre dagar kontaktar du [Microsoft 365 för företag-support](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="6e838-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="6e838-118">Vi kan för närvarande inte att bearbeta din begäran.</span><span class="sxs-lookup"><span data-stu-id="6e838-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="6e838-119">Vi förbereder fortfarande data för organisationen</span><span class="sxs-lookup"><span data-stu-id="6e838-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="6e838-120">**Felkod:** 423</span><span class="sxs-lookup"><span data-stu-id="6e838-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="6e838-121">**Här visas det här meddelandet:** När du ansluter till Microsoft 365 användnings analys mal len i Power BI eller när du direkt anropar API: erna Microsoft 365 repor ting.</span><span class="sxs-lookup"><span data-stu-id="6e838-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="6e838-122">**Orsak:** När du [väljer att visa data i programmet](enable-usage-analytics.md) från administrations centret börjar Microsoft 365-systemet att generera historiska data för din organisation.</span><span class="sxs-lookup"><span data-stu-id="6e838-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="6e838-123">Det här steget kan ta mellan två timmar och 48 timmar beroende på klient organisationens storlek.</span><span class="sxs-lookup"><span data-stu-id="6e838-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="6e838-124">**Så här löser du det:** Det är bara tålamod, men om meddelandet inte ändras till **dina uppgifter** kan du [kontakta Microsoft 365 för företag-supporten](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="6e838-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="6e838-125">Klientorganisations-ID:t som du angav är inte i rätt format</span><span class="sxs-lookup"><span data-stu-id="6e838-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="6e838-126">**Felkod:** 400</span><span class="sxs-lookup"><span data-stu-id="6e838-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="6e838-127">**Här visas det här meddelandet:** När du ansluter till Microsoft 365 användnings analys mal len i Power BI eller när du direkt anropar API: erna Microsoft 365 repor ting.</span><span class="sxs-lookup"><span data-stu-id="6e838-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="6e838-128">**Orsak:** Klient-ID är ett GUID och måste ha formatet XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX.</span><span class="sxs-lookup"><span data-stu-id="6e838-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="6e838-129">Om du anger en annan sträng i rutan för innehavaradministration visas det här fel meddelandet.</span><span class="sxs-lookup"><span data-stu-id="6e838-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="6e838-130">**Så här åtgärdar du felet:** Gå till administrations centrets \> **rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> och leta reda på Microsoft 365 användnings analys panelen på huvud instrument panelen.</span><span class="sxs-lookup"><span data-stu-id="6e838-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="6e838-131">Klient-ID visas på panelen.</span><span class="sxs-lookup"><span data-stu-id="6e838-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="6e838-132">Du kan kopiera den härifrån och klistra in den i dialog rutan för att ansluta till programmet.</span><span class="sxs-lookup"><span data-stu-id="6e838-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="6e838-133">Vårt system känner inte igen klientorganisations-ID:t som du angav</span><span class="sxs-lookup"><span data-stu-id="6e838-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="6e838-134">**Felkod:** 404</span><span class="sxs-lookup"><span data-stu-id="6e838-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="6e838-135">**Här visas det här meddelandet:** I Power BI när du ansluter till Microsoft 365 användnings analys Template-programmet eller när du direkt anropar API: erna Microsoft 365 repor ting.</span><span class="sxs-lookup"><span data-stu-id="6e838-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="6e838-136">**Orsak:** Klient organisationens ID är ogiltigt eller finns inte.</span><span class="sxs-lookup"><span data-stu-id="6e838-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="6e838-137">**Så här åtgärdar du felet:** Gå till administrations centrets \> **rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> och leta reda på Microsoft 365 användnings analys panelen på huvud instrument panelen.</span><span class="sxs-lookup"><span data-stu-id="6e838-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="6e838-138">Klient-ID visas på panelen.</span><span class="sxs-lookup"><span data-stu-id="6e838-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="6e838-139">Du kan kopiera den härifrån och klistra in den i dialog rutan för att ansluta till programmet.</span><span class="sxs-lookup"><span data-stu-id="6e838-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="6e838-140">Ange dina inloggningsuppgifter för att logga in på Power BI igen</span><span class="sxs-lookup"><span data-stu-id="6e838-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="6e838-141">Felkod: 302</span><span class="sxs-lookup"><span data-stu-id="6e838-141">Error Code: 302</span></span>
  
 <span data-ttu-id="6e838-142">**Här visas det här meddelandet:** I Power BI när du ansluter till Microsoft 365 användnings analys Template-programmet eller när du direkt anropar API: erna Microsoft 365 repor ting.</span><span class="sxs-lookup"><span data-stu-id="6e838-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="6e838-143">**Orsak:** Auktoriseringskoden fungerade inte. Eventuellt måste du ange dina autentiseringsuppgifter igen.</span><span class="sxs-lookup"><span data-stu-id="6e838-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="6e838-144">**Så här åtgärdar du felet:** Logga ut från Power BI och logga sedan in igen.</span><span class="sxs-lookup"><span data-stu-id="6e838-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="6e838-145">Du har inte rätt auktorisering för få åtkomst till dessa data.</span><span class="sxs-lookup"><span data-stu-id="6e838-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="6e838-146">Om du vill kunna komma åt data från den här tjänsten måste du vara global administratör eller produktadministratör</span><span class="sxs-lookup"><span data-stu-id="6e838-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="6e838-147">**Felkod:** 403</span><span class="sxs-lookup"><span data-stu-id="6e838-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="6e838-148">**Här visas det här meddelandet:** I Power BI när du ansluter till Microsoft 365 användnings analys Template-programmet eller när du direkt anropar API: erna Microsoft 365 repor ting.</span><span class="sxs-lookup"><span data-stu-id="6e838-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="6e838-149">**Orsak:** Auktoriseringskod misslyckades eftersom den användare som försökte ansluta till mallgalleriet inte har rätt behörighet för att komma åt dessa data.</span><span class="sxs-lookup"><span data-stu-id="6e838-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="6e838-150">**Så här åtgärdar du felet:** Ange autentiseringsuppgifter för en användare som är **Global administratör** , **Exchange-administratör** , **Skype för företag-administratör** , SharePoint- **administratör** , **global läsare** eller **rapport läsare** för att ansluta till programmet mall.</span><span class="sxs-lookup"><span data-stu-id="6e838-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin** , **Exchange admin** , **Skype for Business admin** , **SharePoint admin** , **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="6e838-151">Mer information finns i [om administratörs roller](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="6e838-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="6e838-152">Uppdateringen misslyckades</span><span class="sxs-lookup"><span data-stu-id="6e838-152">Refresh failed</span></span>

 <span data-ttu-id="6e838-153">**Var du kommer att få se det här meddelandet:** E-post från Power BI eller statusen Misslyckades i uppdateringshistoriken.</span><span class="sxs-lookup"><span data-stu-id="6e838-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="6e838-154">**Orsak:** Ibland återställs autentiseringsuppgifterna för den användare som anslöt till malldokument och uppdateras inte i anslutnings inställningarna för den mall som gör att användaren kan se uppdaterings fel.</span><span class="sxs-lookup"><span data-stu-id="6e838-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="6e838-155">**Så här åtgärdar du felet:** I Power BI hittar du den data uppsättning som motsvarar Microsoft 365 användnings analys-mallen, väljer **Schemalägg uppdatering** och uppger dina administratörsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="6e838-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="6e838-156">Om det inte fungerar avmarkerar du cachen och skapar sedan programmet igen.</span><span class="sxs-lookup"><span data-stu-id="6e838-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
