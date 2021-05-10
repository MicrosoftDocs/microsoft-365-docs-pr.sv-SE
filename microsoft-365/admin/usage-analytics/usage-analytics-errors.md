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
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Felsökning av Microsoft 365 användningsanalyser

Utforska följande lista över felmeddelanden för att få hjälp med de vanligaste problemen med användningsanalyser för Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Vi kan inte att bearbeta din begäran. Du måste först prenumerera på dessa data Microsoft 365 administrationscentret

 **Felkod:** 422 
  
 **Var du kommer att få se det här meddelandet:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIIs. 
  
 **Orsak:** Innan du kan ansluta till appen måste du prenumerera på data från Microsoft 365 administrationscenter. Om du inte först gör det kan du inte ansluta till mallappen, även om du anger ditt Microsoft 365 klientorganisations-ID. 
  
 **Så här åtgärdar du felet:** Om du vill prenumerera på data går du till administrationscentret Rapporterar användning och letar Microsoft 365 panelen för \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> användningsanalys på huvudsidan för instrumentpanelen. Välj knappen **Komma igång.**  I fönstret Rapporter som öppnas aktiverar du inställningen Gör data tillgängliga för **Microsoft 365** användningsanalys för Power BI på och **Spara**.
  
## <a name="we-are-processing-your-data"></a>Vi bearbetar dina data

 **Var du kommer att få se det här meddelandet:** I panelen **Microsoft 365 användningsanalys** på **instrumentpanelen användning** i Microsoft 365 administrationscentret. 
  
 **Orsak:** När du [väljer att visa data](enable-usage-analytics.md) i mallappen via administrationscentret i Microsoft 365 börjar Microsoft 365 att generera historiska användningsdata för organisationen. Beroende på storleken på klientorganisationen kan det här steget ta mellan två till fyrtioåtta timmar. 
  
 **Så här åtgärdar du det:** Ha tålamod, men om meddelandet inte ändras till Your data is ready (Dina data är **klara)** efter 3 dagar kontaktar [Microsoft 365 för företagssupport](../../business-video/get-help-support.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Vi kan för närvarande inte att bearbeta din begäran. Vi förbereder fortfarande data för organisationen

 **Felkod:** 423 
  
 **Var du kommer att få se det här meddelandet:** I Power BI gäller att du ansluter till mallappen Microsoft 365 användningsanalys eller när du anropar rapport-API:er Microsoft 365 direkt. 
  
 **Orsak:** När du [väljer att visa data](enable-usage-analytics.md) i mallappen i administrationscentret börjar Microsoft 365 att generera historiska användningsdata för organisationen. Beroende på storleken på klientorganisationen kan det här steget ta mellan två till 48 timmar. 
  
 **Så här åtgärdar du det:** Ha tålamod, men om meddelandet inte ändras till Your data is ready (Dina data är **klara)** 3 dagar efter initieringen kontaktar [Microsoft 365 för företagssupport.](../../business-video/get-help-support.md)
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>Klientorganisations-ID:t som du angav är inte i rätt format

 **Felkod:** 400 
  
 **Var du kommer att få se det här meddelandet:** I Power BI gäller att du ansluter till mallappen Microsoft 365 användningsanalys eller när du anropar rapport-API:er Microsoft 365 direkt. 
  
 **Orsak:** Klientorganisations-ID:t är ett guid och måste vara i xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Om du anger någon annan sträng i inmatningsrutan för klientorganisationen får du det här felet. 
  
 **Så här åtgärdar du felet:** Gå till administrationscentret Rapporterar \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">användning och leta</a> upp panelen Microsoft 365 användningsanalys på huvudsidan för instrumentpanelen. Klientorganisations-ID:t visas på panelen. Du kan kopiera det härifrån och klistra in det i dialogrutan för att ansluta till mallappen. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>Vårt system känner inte igen klientorganisations-ID:t som du angav

 **Felkod:** 404 
  
 **Var du kommer att få se det här meddelandet:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIIs. 
  
 **Orsak:** Klientorganisations-ID:t som du angav är inte giltigt eller finns inte. 
  
 **Så här åtgärdar du felet:** Gå till administrationscentret Rapporterar \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">användning och leta</a> upp panelen Microsoft 365 användningsanalys på huvudsidan för instrumentpanelen. Klientorganisations-ID:t visas på panelen. Du kan kopiera det härifrån och klistra in det i dialogrutan för att ansluta till mallappen. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Ange dina inloggningsuppgifter för att logga in på Power BI igen

Felkod: 302
  
 **Var du kommer att få se det här meddelandet:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIIs. 
  
 **Orsak:** Auktoriseringskoden fungerade inte. Eventuellt måste du ange dina autentiseringsuppgifter igen. 
  
 **Så här åtgärdar du felet:** Logga ut från Power BI och logga sedan in igen. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Du har inte rätt auktorisering för få åtkomst till dessa data. Om du vill kunna komma åt data från den här tjänsten måste du vara global administratör eller produktadministratör

 **Felkod:** 403 
  
 **Var du kommer att få se det här meddelandet:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIIs. 
  
 **Orsak:** Auktoriseringskoden misslyckades eftersom användaren som försökte ansluta till mallappen inte har rätt auktoriseringsnivå för att komma åt dessa data. 
  
 **Så här åtgärdar du felet:** Ange autentiseringsuppgifter för en användare som är antingen global administratör **,** **Exchange-administratör,** **Skype för företag-administratör,** **SharePoint-administratör,** **global** läsare eller **rapportläsare** för att ansluta till mallappen. Mer information [finns i Om](../add-users/about-admin-roles.md) administratörsroller. 
  
## <a name="refresh-failed"></a>Uppdateringen misslyckades

 **Var du kommer att få se det här meddelandet:** E-post från Power BI eller statusen Misslyckades i uppdateringshistoriken. 
  
 **Orsak:** Ibland återställs autentiseringsuppgifterna för den användare som är ansluten till mallappen och uppdateras inte i anslutningsinställningarna för mallappen, vilket gör att användaren får information om fel vid uppdatering. 
  
 **Så här åtgärdar du felet:** I Power BI du den datauppsättning som motsvarar mallappen Microsoft 365 användningsanalys väljer du Schemalägg uppdatering och anger dina autentiseringsuppgifter som administratör.  
  
Om det inte fungerar rensar du cachen och skapar mallappen igen.
  
  
