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
description: Lär dig hur du felsöker problem med mallappen Microsoft 365 användningsanalys.
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580744"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Felsökning av Microsoft 365 användningsanalyser

Utforska följande lista över felmeddelanden för att få hjälp med de vanligaste problemen med användningsanalyser för Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Vi kan inte att bearbeta din begäran. Du måste först prenumerera på dessa data från administrationscentret för Microsoft 365

 **Felkod:** 422 
  
 **Var du kommer att få se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 användningsanalys eller när du anropar rapport-API:er för Microsoft 365 direkt. 
  
 **Orsak:** Innan du kan ansluta till appen måste du prenumerera på data från administrationscentret för Microsoft 365. Om du inte först gör det här steget kan du inte ansluta till mallappen, även om du anger ditt klientorganisations-ID för Microsoft 365. 
  
 **Så här åtgärdar du felet:** Om du vill prenumerera på data går du till administrationscentret Rapporterar användning och letar upp \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> panelen Microsoft 365 användningsanalyser på huvudsidan för instrumentpanelen. Välj knappen **Komma igång.**  I fönstret Rapporter som öppnas aktiverar du inställningen Gör data tillgängliga för **Microsoft 365** användningsanalyser för Power BI och **Spara**.
  
## <a name="we-are-processing-your-data"></a>Vi bearbetar dina data

 **Var du kommer att få se det här meddelandet:** I panelen **Microsoft 365 användningsanalyser** på **instrumentpanelen** för användning i administrationscentret för Microsoft 365. 
  
 **Orsak:** När du väljer att visa [data](enable-usage-analytics.md) i mallappen från administrationscentret för Microsoft 365 börjar Microsoft 365-systemet generera historiska användningsdata för organisationen. Beroende på storleken på klientorganisationen kan det här steget ta mellan två till fyrtioåtta timmar. 
  
 **Så här åtgärdar du det:** Ha tålamod, men om meddelandet inte ändras till Your data is ready (Dina data är **klara)** efter 3 dagar bör du kontakta supporten [för Microsoft 365 för företag.](../contact-support-for-business-products.md)
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Vi kan för närvarande inte att bearbeta din begäran. Vi förbereder fortfarande data för organisationen

 **Felkod:** 423 
  
 **Var du kommer att få se det här meddelandet:** När du ansluter till mallappen Microsoft 365 användningsanalys i Power BI eller när du anropar Rapport-API:er för Microsoft 365 direkt. 
  
 **Orsak:** När du [väljer att visa data](enable-usage-analytics.md) i mallappen i administrationscentret börjar Microsoft 365-systemet generera historiska användningsdata för organisationen. Beroende på storleken på klientorganisationen kan det här steget ta mellan två till 48 timmar. 
  
 **Så här åtgärdar du det:** Ha tålamod, men om meddelandet inte ändras till Your **data is ready** (Dina data är klara) 3 dagar efter initieringen bör du kontakta supporten för Microsoft [365 för företag.](../contact-support-for-business-products.md)
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>Klientorganisations-ID:t som du angav är inte i rätt format

 **Felkod:** 400 
  
 **Var du kommer att få se det här meddelandet:** När du ansluter till mallappen Microsoft 365 användningsanalys i Power BI eller när du anropar Rapport-API:er för Microsoft 365 direkt. 
  
 **Orsak:** Klientorganisations-ID:t är ett guid och måste vara i xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Om du anger någon annan sträng i inmatningsrutan för klientorganisationen får du det här felet. 
  
 **Så här åtgärdar du felet:** Gå till administrationscentret Rapporterar användning \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">och leta</a> reda på panelen Microsoft 365 användningsanalys på huvudsidan för instrumentpanelen. Klientorganisations-ID:t visas på panelen. Du kan kopiera det härifrån och klistra in det i dialogrutan för att ansluta till mallappen. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>Vårt system känner inte igen klientorganisations-ID:t som du angav

 **Felkod:** 404 
  
 **Var du kommer att få se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 användningsanalys eller när du anropar rapport-API:er för Microsoft 365 direkt. 
  
 **Orsak:** Klientorganisations-ID:t som du angav är inte giltigt eller finns inte. 
  
 **Så här åtgärdar du felet:** Gå till administrationscentret Rapporterar användning \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">och leta</a> reda på panelen Microsoft 365 användningsanalys på huvudsidan för instrumentpanelen. Klientorganisations-ID:t visas på panelen. Du kan kopiera det härifrån och klistra in det i dialogrutan för att ansluta till mallappen. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Ange dina inloggningsuppgifter för att logga in på Power BI igen

Felkod: 302
  
 **Var du kommer att få se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 användningsanalys eller när du anropar rapport-API:er för Microsoft 365 direkt. 
  
 **Orsak:** Auktoriseringskoden fungerade inte. Eventuellt måste du ange dina autentiseringsuppgifter igen. 
  
 **Så här åtgärdar du felet:** Logga ut från Power BI och logga sedan in igen. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Du har inte rätt auktorisering för få åtkomst till dessa data. Om du vill kunna komma åt data från den här tjänsten måste du vara global administratör eller produktadministratör

 **Felkod:** 403 
  
 **Var du kommer att få se det här meddelandet:** I Power BI när du ansluter till mallappen Microsoft 365 användningsanalys eller när du anropar rapport-API:er för Microsoft 365 direkt. 
  
 **Orsak:** Auktoriseringskoden misslyckades eftersom användaren som försökte ansluta till mallappen inte har rätt auktoriseringsnivå för att komma åt dessa data. 
  
 **Så här åtgärdar du felet:** Ange autentiseringsuppgifter för en användare som är antingen  global administratör **,** **Exchange-administratör,** Skype för **företag-administratör,** **SharePoint-administratör,** **global** läsare eller rapportläsare för att ansluta till mallappen. Mer information [finns i Om](../add-users/about-admin-roles.md) administratörsroller. 
  
## <a name="refresh-failed"></a>Uppdateringen misslyckades

 **Var du kommer att få se det här meddelandet:** E-post från Power BI eller statusen Misslyckades i uppdateringshistoriken. 
  
 **Orsak:** Ibland återställs autentiseringsuppgifterna för den användare som är ansluten till mallappen och uppdateras inte i anslutningsinställningarna för mallappen, vilket gör att användaren får information om fel vid uppdatering. 
  
 **Så här åtgärdar du felet:** Hitta den datauppsättning i Power BI som motsvarar mallappen  för Microsoft 365 användningsanalyser, välj Schemalägg uppdatering och ange dina autentiseringsuppgifter som administratör. 
  
Om det inte fungerar rensar du cachen och skapar mallappen igen.
  
  
