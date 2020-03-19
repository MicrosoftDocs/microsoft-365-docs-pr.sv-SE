---
title: Felsökning av Microsoft 365 användningsanalyser
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Lär dig hur du felsöker problem med mallappen Microsoft 365 Usage Analytics.
ms.openlocfilehash: a9da79a6d7760f7876de7a6321554545d411f6be
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807212"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Felsökning av Microsoft 365 användningsanalyser

Utforska följande lista över felmeddelanden för att få hjälp med de vanligaste problemen med användningsanalyser för Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Vi kan inte att bearbeta din begäran. Du måste först prenumerera på dessa data från Microsoft 365 admin center

 **Felkod:** 422 
  
 **Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt. 
  
 **Orsak:** Innan du kan ansluta till appen måste du prenumerera på data från administrationscentret för Microsoft 365. Om det här steget inte görs först kan du inte ansluta till mallappen, även om du anger ditt Microsoft 365-klient-ID. 
  
 **Så här åtgärdar du det här felet:** Om du vill prenumerera på data \> går du till administrationscentret **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">användning</a> och letar reda på Microsoft 365-panelen för användningsanalys på huvudpanelsidan. Välj knappen **Kom igång** och vrid sedan på inställningen Gör data tillgängliga för **Microsoft 365-användningsanalys för Power BI** och **Spara**i fönstret **Rapporter** som öppnas.
  
## <a name="we-are-processing-your-data"></a>Vi bearbetar dina data

 **Var du kommer att se det här meddelandet:** I panelen **Microsoft 365-användningsanalys** på instrumentpanelen **Användning** i Microsoft 365-administrationscentret. 
  
 **Orsak:** När du [väljer att visa data i mallappen](enable-usage-analytics.md) från administrationscentret för Microsoft 365 börjar Microsoft 365-systemet generera historiska användningsdata för din organisation. Beroende på storleken på klientorganisationen kan det här steget ta mellan två till fyrtioåtta timmar. 
  
 **Så här åtgärdar du detta:** Ha bara tålamod, men om meddelandet inte ändras till **Dina data är klar** efter 3 dagar, kontakta Microsoft [365 för företagssupport](../contact-support-for-business-products.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Vi kan för närvarande inte att bearbeta din begäran. Vi förbereder fortfarande data för organisationen

 **Felkod:** 423 
  
 **Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt. 
  
 **Orsak:** När du [väljer att visa data i mallappen](enable-usage-analytics.md) från administrationscentret börjar Microsoft 365-systemet generera historiska användningsdata för din organisation. Beroende på storleken på klientorganisationen kan det här steget ta mellan två till fyrtioåtta timmar. 
  
 **Så här åtgärdar du detta:** Ha bara tålamod, men om meddelandet inte ändras till **Dina data är klar** även 3 dagar sedan initiering, kontakta Microsoft [365 för företagssupport](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>Klientorganisations-ID:t som du angav är inte i rätt format

 **Felkod:** 400 
  
 **Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt. 
  
 **Orsak:** Klientorganisations-ID:t är ett GUID och måste vara i xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Om du anger någon annan sträng i inmatningsrutan för klientorganisationen får du det här felet. 
  
 **Så här åtgärdar du det här felet:** Gå \> till administrationscentret **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">användning</a> och leta reda på Microsoft 365 användning analytics panel på huvudpanelen sidan. Klientorganisations-ID:t visas på panelen. Du kan kopiera den härifrån och klistra in den i dialogrutan för att ansluta till mallappen. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>Vårt system känner inte igen klientorganisations-ID:t som du angav

 **Felkod:** 404 
  
 **Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt. 
  
 **Orsak:** Klientorganisations-ID:t som du angav är inte giltigt eller finns inte. 
  
 **Så här åtgärdar du det här felet:** Gå \> till administrationscentret **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">användning</a> och leta reda på Microsoft 365 användning analytics panel på huvudpanelen sidan. Klientorganisations-ID:t visas på panelen. Du kan kopiera den härifrån och klistra in den i dialogrutan för att ansluta till mallappen. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Ange dina inloggningsuppgifter för att logga in på Power BI igen

Felkod: 302
  
 **Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt. 
  
 **Orsak:** Auktoriseringskoden fungerade inte. Eventuellt måste du ange dina autentiseringsuppgifter igen. 
  
 **Så här åtgärdar du felet:** Logga ut från Power BI och logga sedan in igen. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Du har inte rätt auktorisering för få åtkomst till dessa data. Om du vill kunna komma åt data från den här tjänsten måste du vara global administratör eller produktadministratör

 **Felkod:** 403 
  
 **Var du kommer att se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 Usage Analytics eller när du ringer Microsoft 365 Reporting API:er direkt. 
  
 **Orsak:** Auktoriseringskoden misslyckades eftersom användaren som försökte ansluta till mallappen inte har rätt behörighetsnivå för att komma åt dessa data. 
  
 **Så här åtgärdar du det här felet:** Ange autentiseringsuppgifter för en användare som antingen är global **administratör,** **Exchange-administratör**, **Skype för företag-administratör,** **SharePoint-administratör,** **Global läsare** eller **Rapportläsare** för att ansluta till mallappen. Mer information finns i [Om administratörsroller.](../add-users/about-admin-roles.md) 
  
## <a name="refresh-failed"></a>Uppdateringen misslyckades

 **Var du kommer att få se det här meddelandet:** E-post från Power BI eller statusen Misslyckades i uppdateringshistoriken. 
  
 **Orsak:** Ibland återställs autentiseringsuppgifterna för den användare som är ansluten till mallappen och uppdateras inte i anslutningsinställningarna för mallappen, vilket gör att användaren ser fel vid uppdateringsfel. 
  
 **Så här åtgärdar du det här felet:** I Power BI hittar du den datauppsättning som motsvarar mallappen Microsoft 365 Usage Analytics, väljer **uppdatering av schema** och anger administratörsuppgifterna. 
  
Om det inte fungerar rensar du cacheminnet och återskapar mallappen.
  
  
