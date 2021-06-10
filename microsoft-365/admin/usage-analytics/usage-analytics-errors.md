---
title: Felsökning av Microsoft 365 användningsanalyser
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Lär dig hur du felsöker problem Microsoft 365 mallappen Användningsanalys.
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293741"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="75d61-103">Felsökning av Microsoft 365 användningsanalyser</span><span class="sxs-lookup"><span data-stu-id="75d61-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="75d61-104">Utforska följande lista över felmeddelanden för att få hjälp med de vanligaste problemen med användningsanalyser för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75d61-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="75d61-105">Vi kan inte att bearbeta din begäran.</span><span class="sxs-lookup"><span data-stu-id="75d61-105">We are unable to process your request.</span></span> <span data-ttu-id="75d61-106">Du måste först prenumerera på dessa data Microsoft 365 administrationscentret</span><span class="sxs-lookup"><span data-stu-id="75d61-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="75d61-107">**Felkod:** 422</span><span class="sxs-lookup"><span data-stu-id="75d61-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="75d61-108">**Var du kommer att få se det här meddelandet:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIIs.</span><span class="sxs-lookup"><span data-stu-id="75d61-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="75d61-109">**Orsak:** Innan du kan ansluta till appen måste du prenumerera på data från Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="75d61-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="75d61-110">Om du inte först gör det kan du inte ansluta till mallappen, även om du anger ditt Microsoft 365 klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="75d61-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="75d61-111">**Så här åtgärdar du felet:** Om du vill prenumerera på data går du till administrationscentret Rapporterar användning och letar Microsoft 365 panelen för \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> användningsanalys på huvudsidan för instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="75d61-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="75d61-112">Välj knappen **Komma igång.**  I fönstret Rapporter som öppnas aktiverar du inställningen Gör data tillgängliga för **Microsoft 365** användningsanalys för Power BI på och **Spara**.</span><span class="sxs-lookup"><span data-stu-id="75d61-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="75d61-113">Vi bearbetar dina data</span><span class="sxs-lookup"><span data-stu-id="75d61-113">We are processing your data</span></span>

 <span data-ttu-id="75d61-114">**Var du kommer att få se det här meddelandet:** I panelen **Microsoft 365 användningsanalys** på **instrumentpanelen användning** i Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="75d61-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="75d61-115">**Orsak:** När du [väljer att visa data](enable-usage-analytics.md) i mallappen via administrationscentret i Microsoft 365 börjar Microsoft 365 att generera historiska användningsdata för organisationen.</span><span class="sxs-lookup"><span data-stu-id="75d61-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="75d61-116">Beroende på storleken på klientorganisationen kan det här steget ta mellan två till fyrtioåtta timmar.</span><span class="sxs-lookup"><span data-stu-id="75d61-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="75d61-117">**Så här åtgärdar du det:** Ha tålamod, men om meddelandet inte ändras till Your data is ready (Dina data är **klara)** efter 3 dagar kontaktar [Microsoft 365 för företagssupport](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="75d61-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="75d61-p105">Vi kan för närvarande inte att bearbeta din begäran. Vi förbereder fortfarande data för organisationen</span><span class="sxs-lookup"><span data-stu-id="75d61-p105">We are unable to process your request at this time. We are still preparing the data for your organization</span></span>

 <span data-ttu-id="75d61-120">**Felkod:** 423</span><span class="sxs-lookup"><span data-stu-id="75d61-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="75d61-121">**Var du kommer att få se det här meddelandet:** I Power BI gäller att du ansluter till mallappen Microsoft 365 användningsanalys eller när du anropar rapport-API:er Microsoft 365 direkt.</span><span class="sxs-lookup"><span data-stu-id="75d61-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="75d61-122">**Orsak:** När du [väljer att visa data](enable-usage-analytics.md) i mallappen i administrationscentret börjar Microsoft 365 att generera historiska användningsdata för organisationen.</span><span class="sxs-lookup"><span data-stu-id="75d61-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="75d61-123">Beroende på storleken på klientorganisationen kan det här steget ta mellan två till 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="75d61-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="75d61-124">**Så här åtgärdar du det:** Ha tålamod, men om meddelandet inte ändras till Your data is ready (Dina data är **klara)** 3 dagar efter initieringen kontaktar [Microsoft 365 för företagssupport.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="75d61-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../../business-video/get-help-support.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="75d61-125">Klientorganisations-ID:t som du angav är inte i rätt format</span><span class="sxs-lookup"><span data-stu-id="75d61-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="75d61-126">**Felkod:** 400</span><span class="sxs-lookup"><span data-stu-id="75d61-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="75d61-127">**Var du kommer att få se det här meddelandet:** I Power BI gäller att du ansluter till mallappen Microsoft 365 användningsanalys eller när du anropar rapport-API:er Microsoft 365 direkt.</span><span class="sxs-lookup"><span data-stu-id="75d61-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="75d61-128">**Orsak:** Klientorganisations-ID:t är ett guid och måste vara i xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span><span class="sxs-lookup"><span data-stu-id="75d61-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="75d61-129">Om du anger någon annan sträng i inmatningsrutan för klientorganisationen får du det här felet.</span><span class="sxs-lookup"><span data-stu-id="75d61-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="75d61-130">**Så här åtgärdar du felet:** Gå till administrationscentret Rapporterar \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">användning och leta</a> upp panelen Microsoft 365 användningsanalys på huvudsidan för instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="75d61-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="75d61-131">Klientorganisations-ID:t visas på panelen.</span><span class="sxs-lookup"><span data-stu-id="75d61-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="75d61-132">Du kan kopiera det härifrån och klistra in det i dialogrutan för att ansluta till mallappen.</span><span class="sxs-lookup"><span data-stu-id="75d61-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="75d61-133">Vårt system känner inte igen klientorganisations-ID:t som du angav</span><span class="sxs-lookup"><span data-stu-id="75d61-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="75d61-134">**Felkod:** 404</span><span class="sxs-lookup"><span data-stu-id="75d61-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="75d61-135">**Var du kommer att få se det här meddelandet:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIIs.</span><span class="sxs-lookup"><span data-stu-id="75d61-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="75d61-136">**Orsak:** Klientorganisations-ID:t som du angav är inte giltigt eller finns inte.</span><span class="sxs-lookup"><span data-stu-id="75d61-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="75d61-137">**Så här åtgärdar du felet:** Gå till administrationscentret Rapporterar \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">användning och leta</a> upp panelen Microsoft 365 användningsanalys på huvudsidan för instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="75d61-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="75d61-138">Klientorganisations-ID:t visas på panelen.</span><span class="sxs-lookup"><span data-stu-id="75d61-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="75d61-139">Du kan kopiera det härifrån och klistra in det i dialogrutan för att ansluta till mallappen.</span><span class="sxs-lookup"><span data-stu-id="75d61-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="75d61-140">Ange dina inloggningsuppgifter för att logga in på Power BI igen</span><span class="sxs-lookup"><span data-stu-id="75d61-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="75d61-141">Felkod: 302</span><span class="sxs-lookup"><span data-stu-id="75d61-141">Error Code: 302</span></span>
  
 <span data-ttu-id="75d61-142">**Var du kommer att få se det här meddelandet:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIIs.</span><span class="sxs-lookup"><span data-stu-id="75d61-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="75d61-143">**Orsak:** Auktoriseringskoden fungerade inte. Eventuellt måste du ange dina autentiseringsuppgifter igen.</span><span class="sxs-lookup"><span data-stu-id="75d61-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="75d61-144">**Så här åtgärdar du felet:** Logga ut från Power BI och logga sedan in igen.</span><span class="sxs-lookup"><span data-stu-id="75d61-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="75d61-p110">Du har inte rätt auktorisering för få åtkomst till dessa data. Om du vill kunna komma åt data från den här tjänsten måste du vara global administratör eller produktadministratör</span><span class="sxs-lookup"><span data-stu-id="75d61-p110">You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="75d61-147">**Felkod:** 403</span><span class="sxs-lookup"><span data-stu-id="75d61-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="75d61-148">**Var du kommer att få se det här meddelandet:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIIs.</span><span class="sxs-lookup"><span data-stu-id="75d61-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="75d61-149">**Orsak:** Auktoriseringskoden misslyckades eftersom användaren som försökte ansluta till mallappen inte har rätt auktoriseringsnivå för att komma åt dessa data.</span><span class="sxs-lookup"><span data-stu-id="75d61-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="75d61-150">**Så här åtgärdar du felet:** Ange autentiseringsuppgifter för en användare som är antingen global administratör **,** **Exchange-administratör,** **Skype för företag-administratör,** **SharePoint-administratör,** **global** läsare eller **rapportläsare** för att ansluta till mallappen.</span><span class="sxs-lookup"><span data-stu-id="75d61-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="75d61-151">Mer information [finns i Om](../add-users/about-admin-roles.md) administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="75d61-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="75d61-152">Uppdateringen misslyckades</span><span class="sxs-lookup"><span data-stu-id="75d61-152">Refresh failed</span></span>

 <span data-ttu-id="75d61-153">**Var du kommer att få se det här meddelandet:** E-post från Power BI eller statusen Misslyckades i uppdateringshistoriken.</span><span class="sxs-lookup"><span data-stu-id="75d61-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="75d61-154">**Orsak:** Ibland återställs autentiseringsuppgifterna för den användare som är ansluten till mallappen och uppdateras inte i anslutningsinställningarna för mallappen, vilket gör att användaren får information om fel vid uppdatering.</span><span class="sxs-lookup"><span data-stu-id="75d61-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="75d61-155">**Så här åtgärdar du felet:** I Power BI du den datauppsättning som motsvarar mallappen Microsoft 365 användningsanalys väljer du Schemalägg uppdatering och anger dina autentiseringsuppgifter som administratör. </span><span class="sxs-lookup"><span data-stu-id="75d61-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="75d61-156">Om det inte fungerar rensar du cachen och skapar mallappen igen.</span><span class="sxs-lookup"><span data-stu-id="75d61-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
