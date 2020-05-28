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
description: Lär dig hur du felsöker problem med mallappen Microsoft 365 Usage Analytics.
ms.openlocfilehash: 4696dd0c5140cdc110781c226819fc64a90fae1b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402040"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="1874a-103">Felsökning av Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="1874a-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="1874a-104">Utforska följande lista över felmeddelanden för att få hjälp med de vanligaste problemen med användningsanalyser för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1874a-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="1874a-105">Vi kan inte att bearbeta din begäran.</span><span class="sxs-lookup"><span data-stu-id="1874a-105">We are unable to process your request.</span></span> <span data-ttu-id="1874a-106">Du måste först prenumerera på dessa data från Microsoft 365 admin center</span><span class="sxs-lookup"><span data-stu-id="1874a-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="1874a-107">**Felkod:** 422</span><span class="sxs-lookup"><span data-stu-id="1874a-107">**Error Code :** 422</span></span> 
  
 <span data-ttu-id="1874a-108">**Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt.</span><span class="sxs-lookup"><span data-stu-id="1874a-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1874a-109">**Orsak:** Innan du kan ansluta till appen måste du prenumerera på data från administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1874a-109">**Cause:** Before you can connect to the app you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="1874a-110">Om det här steget inte görs först kan du inte ansluta till mallappen, även om du anger ditt Microsoft 365-klient-ID.</span><span class="sxs-lookup"><span data-stu-id="1874a-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant id.</span></span> 
  
 <span data-ttu-id="1874a-111">**Så här åtgärdar du det här felet:** Om du vill prenumerera på data går du till administrationscentret \> **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">användning</a> och letar reda på Microsoft 365-panelen för användningsanalys på huvudpanelsidan.</span><span class="sxs-lookup"><span data-stu-id="1874a-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="1874a-112">Välj knappen **Kom igång** och vrid sedan på inställningen Gör data tillgängliga för **Microsoft 365-användningsanalys för Power BI** och **Spara**i fönstret **Rapporter** som öppnas.</span><span class="sxs-lookup"><span data-stu-id="1874a-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="1874a-113">Vi bearbetar dina data</span><span class="sxs-lookup"><span data-stu-id="1874a-113">We are processing your data</span></span>

 <span data-ttu-id="1874a-114">**Var du kommer att se det här meddelandet:** I panelen **Microsoft 365-användningsanalys** på instrumentpanelen **Användning** i Microsoft 365-administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1874a-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="1874a-115">**Orsak:** När du [väljer att visa data i mallappen](enable-usage-analytics.md) från administrationscentret för Microsoft 365 börjar Microsoft 365-systemet generera historiska användningsdata för din organisation.</span><span class="sxs-lookup"><span data-stu-id="1874a-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="1874a-116">Beroende på storleken på klientorganisationen kan det här steget ta mellan två till fyrtioåtta timmar.</span><span class="sxs-lookup"><span data-stu-id="1874a-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="1874a-117">**Så här åtgärdar du detta:** Ha bara tålamod, men om meddelandet inte ändras till **Dina data är klar** efter 3 dagar, kontakta Microsoft [365 för företagssupport](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="1874a-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="1874a-118">Vi kan för närvarande inte att bearbeta din begäran.</span><span class="sxs-lookup"><span data-stu-id="1874a-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="1874a-119">Vi förbereder fortfarande data för organisationen</span><span class="sxs-lookup"><span data-stu-id="1874a-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="1874a-120">**Felkod:** 423</span><span class="sxs-lookup"><span data-stu-id="1874a-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="1874a-121">**Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt.</span><span class="sxs-lookup"><span data-stu-id="1874a-121">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1874a-122">**Orsak:** När du [väljer att visa data i mallappen](enable-usage-analytics.md) från administrationscentret börjar Microsoft 365-systemet generera historiska användningsdata för din organisation.</span><span class="sxs-lookup"><span data-stu-id="1874a-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="1874a-123">Beroende på storleken på klientorganisationen kan det här steget ta mellan två till fyrtioåtta timmar.</span><span class="sxs-lookup"><span data-stu-id="1874a-123">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="1874a-124">**Så här åtgärdar du detta:** Ha bara tålamod, men om meddelandet inte ändras till **Dina data är klar** även 3 dagar sedan initiering, kontakta Microsoft [365 för företagssupport](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="1874a-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="1874a-125">Klientorganisations-ID:t som du angav är inte i rätt format</span><span class="sxs-lookup"><span data-stu-id="1874a-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="1874a-126">**Felkod:** 400</span><span class="sxs-lookup"><span data-stu-id="1874a-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="1874a-127">**Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt.</span><span class="sxs-lookup"><span data-stu-id="1874a-127">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1874a-p107">**Orsak:** Klientorganisations-ID:t är ett GUID och måste vara i xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Om du anger någon annan sträng i inmatningsrutan för klientorganisationen får du det här felet.</span><span class="sxs-lookup"><span data-stu-id="1874a-p107">**Cause:** The tenant id is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. If you enter any other string in the tenant input box you will get this error.</span></span> 
  
 <span data-ttu-id="1874a-130">**Så här åtgärdar du det här felet:** Gå till administrationscentret \> **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">användning</a> och leta reda på Microsoft 365 användning analytics panel på huvudpanelen sidan.</span><span class="sxs-lookup"><span data-stu-id="1874a-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="1874a-131">Klientorganisations-ID:t visas på panelen.</span><span class="sxs-lookup"><span data-stu-id="1874a-131">The tenant id is listed on the tile.</span></span> <span data-ttu-id="1874a-132">Du kan kopiera den härifrån och klistra in den i dialogrutan för att ansluta till mallappen.</span><span class="sxs-lookup"><span data-stu-id="1874a-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="1874a-133">Vårt system känner inte igen klientorganisations-ID:t som du angav</span><span class="sxs-lookup"><span data-stu-id="1874a-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="1874a-134">**Felkod:** 404</span><span class="sxs-lookup"><span data-stu-id="1874a-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="1874a-135">**Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt.</span><span class="sxs-lookup"><span data-stu-id="1874a-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1874a-136">**Orsak:** Klientorganisations-ID:t som du angav är inte giltigt eller finns inte.</span><span class="sxs-lookup"><span data-stu-id="1874a-136">**Cause:** The tenant id you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="1874a-137">**Så här åtgärdar du det här felet:** Gå till administrationscentret \> **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">användning</a> och leta reda på Microsoft 365 användning analytics panel på huvudpanelen sidan.</span><span class="sxs-lookup"><span data-stu-id="1874a-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="1874a-138">Klientorganisations-ID:t visas på panelen.</span><span class="sxs-lookup"><span data-stu-id="1874a-138">The tenant id is listed on the tile.</span></span> <span data-ttu-id="1874a-139">Du kan kopiera den härifrån och klistra in den i dialogrutan för att ansluta till mallappen.</span><span class="sxs-lookup"><span data-stu-id="1874a-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="1874a-140">Ange dina inloggningsuppgifter för att logga in på Power BI igen</span><span class="sxs-lookup"><span data-stu-id="1874a-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="1874a-141">Felkod: 302</span><span class="sxs-lookup"><span data-stu-id="1874a-141">Error Code: 302</span></span>
  
 <span data-ttu-id="1874a-142">**Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt.</span><span class="sxs-lookup"><span data-stu-id="1874a-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1874a-143">**Orsak:** Auktoriseringskoden fungerade inte. Eventuellt måste du ange dina autentiseringsuppgifter igen.</span><span class="sxs-lookup"><span data-stu-id="1874a-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="1874a-144">**Så här åtgärdar du felet:** Logga ut från Power BI och logga sedan in igen.</span><span class="sxs-lookup"><span data-stu-id="1874a-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="1874a-145">Du har inte rätt auktorisering för få åtkomst till dessa data.</span><span class="sxs-lookup"><span data-stu-id="1874a-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="1874a-146">Om du vill kunna komma åt data från den här tjänsten måste du vara global administratör eller produktadministratör</span><span class="sxs-lookup"><span data-stu-id="1874a-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="1874a-147">**Felkod:** 403</span><span class="sxs-lookup"><span data-stu-id="1874a-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="1874a-148">**Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt.</span><span class="sxs-lookup"><span data-stu-id="1874a-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="1874a-149">**Orsak:** Auktoriseringskoden misslyckades eftersom användaren som försökte ansluta till mallappen inte har rätt behörighetsnivå för att komma åt dessa data.</span><span class="sxs-lookup"><span data-stu-id="1874a-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="1874a-150">**Så här åtgärdar du det här felet:** Ange autentiseringsuppgifter för en användare som antingen är global **administratör,** **Exchange-administratör**, **Skype för företag-administratör,** **SharePoint-administratör,** **Global läsare** eller **Rapportläsare** för att ansluta till mallappen.</span><span class="sxs-lookup"><span data-stu-id="1874a-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="1874a-151">Mer information finns i [Om administratörsroller.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="1874a-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="1874a-152">Uppdateringen misslyckades</span><span class="sxs-lookup"><span data-stu-id="1874a-152">Refresh failed</span></span>

 <span data-ttu-id="1874a-153">**Var du kommer att få se det här meddelandet:** E-post från Power BI eller statusen Misslyckades i uppdateringshistoriken.</span><span class="sxs-lookup"><span data-stu-id="1874a-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="1874a-154">**Orsak:** Ibland återställs autentiseringsuppgifterna för den användare som är ansluten till mallappen och uppdateras inte i anslutningsinställningarna för mallappen, vilket gör att användaren ser fel vid uppdateringsfel.</span><span class="sxs-lookup"><span data-stu-id="1874a-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="1874a-155">**Så här åtgärdar du det här felet:** I Power BI hittar du den datauppsättning som motsvarar mallappen Microsoft 365 Usage Analytics, väljer **uppdatering av schema** och anger administratörsuppgifterna.</span><span class="sxs-lookup"><span data-stu-id="1874a-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="1874a-156">Om det inte fungerar rensar du cacheminnet och återskapar mallappen.</span><span class="sxs-lookup"><span data-stu-id="1874a-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
