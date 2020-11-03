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
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Felsökning av Microsoft 365 användningsanalyser

Utforska följande lista över felmeddelanden för att få hjälp med de vanligaste problemen med användningsanalyser för Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Vi kan inte att bearbeta din begäran. Du måste först abonnera på dessa data från administrations centret för Microsoft 365

 **Felkod:** 422 
  
 **Här visas det här meddelandet:** I Power BI när du ansluter till Microsoft 365 användnings analys Template-programmet eller när du direkt anropar API: erna Microsoft 365 repor ting. 
  
 **Orsak:** Innan du kan ansluta till appen måste du abonnera på data från administrations centret för Microsoft 365. Om det här steget inte är först kan du inte ansluta till programmet, även om du tillhandahåller ditt Microsoft 365-klient-ID. 
  
 **Så här åtgärdar du felet:** Om du vill abonnera på data går du till administrations centrets \> **rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> och letar reda på Microsoft 365 användnings analys panelen på huvud instrument panelen. Välj knappen **Kom igång** och sedan, i fönstret **rapporter** som öppnas, aktiverar du inställningen **gör data tillgängliga för Microsoft 365 användnings analys för Power BI** på och **Spara** .
  
## <a name="we-are-processing-your-data"></a>Vi bearbetar dina data

 **Här visas det här meddelandet:** I panelen **microsoft 365 användnings analys** på instrument panelen för **användning** i administrations centret för Microsoft 365. 
  
 **Orsak:** När du [väljer att visa data i programmet](enable-usage-analytics.md) från administrations centret för Microsoft 365 börjar Microsoft 365-systemet att generera historiska data för din organisation. Beroende på storleken på klientorganisationen kan det här steget ta mellan två till fyrtioåtta timmar. 
  
 **Så här löser du det:** Det är bara tålamod, men om meddelandet inte ändras till **dina data är klara** efter tre dagar kontaktar du [Microsoft 365 för företag-support](../contact-support-for-business-products.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Vi kan för närvarande inte att bearbeta din begäran. Vi förbereder fortfarande data för organisationen

 **Felkod:** 423 
  
 **Här visas det här meddelandet:** När du ansluter till Microsoft 365 användnings analys mal len i Power BI eller när du direkt anropar API: erna Microsoft 365 repor ting. 
  
 **Orsak:** När du [väljer att visa data i programmet](enable-usage-analytics.md) från administrations centret börjar Microsoft 365-systemet att generera historiska data för din organisation. Det här steget kan ta mellan två timmar och 48 timmar beroende på klient organisationens storlek. 
  
 **Så här löser du det:** Det är bara tålamod, men om meddelandet inte ändras till **dina uppgifter** kan du [kontakta Microsoft 365 för företag-supporten](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>Klientorganisations-ID:t som du angav är inte i rätt format

 **Felkod:** 400 
  
 **Här visas det här meddelandet:** När du ansluter till Microsoft 365 användnings analys mal len i Power BI eller när du direkt anropar API: erna Microsoft 365 repor ting. 
  
 **Orsak:** Klient-ID är ett GUID och måste ha formatet XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX. Om du anger en annan sträng i rutan för innehavaradministration visas det här fel meddelandet. 
  
 **Så här åtgärdar du felet:** Gå till administrations centrets \> **rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> och leta reda på Microsoft 365 användnings analys panelen på huvud instrument panelen. Klient-ID visas på panelen. Du kan kopiera den härifrån och klistra in den i dialog rutan för att ansluta till programmet. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>Vårt system känner inte igen klientorganisations-ID:t som du angav

 **Felkod:** 404 
  
 **Här visas det här meddelandet:** I Power BI när du ansluter till Microsoft 365 användnings analys Template-programmet eller när du direkt anropar API: erna Microsoft 365 repor ting. 
  
 **Orsak:** Klient organisationens ID är ogiltigt eller finns inte. 
  
 **Så här åtgärdar du felet:** Gå till administrations centrets \> **rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> och leta reda på Microsoft 365 användnings analys panelen på huvud instrument panelen. Klient-ID visas på panelen. Du kan kopiera den härifrån och klistra in den i dialog rutan för att ansluta till programmet. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Ange dina inloggningsuppgifter för att logga in på Power BI igen

Felkod: 302
  
 **Här visas det här meddelandet:** I Power BI när du ansluter till Microsoft 365 användnings analys Template-programmet eller när du direkt anropar API: erna Microsoft 365 repor ting. 
  
 **Orsak:** Auktoriseringskoden fungerade inte. Eventuellt måste du ange dina autentiseringsuppgifter igen. 
  
 **Så här åtgärdar du felet:** Logga ut från Power BI och logga sedan in igen. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Du har inte rätt auktorisering för få åtkomst till dessa data. Om du vill kunna komma åt data från den här tjänsten måste du vara global administratör eller produktadministratör

 **Felkod:** 403 
  
 **Här visas det här meddelandet:** I Power BI när du ansluter till Microsoft 365 användnings analys Template-programmet eller när du direkt anropar API: erna Microsoft 365 repor ting. 
  
 **Orsak:** Auktoriseringskod misslyckades eftersom den användare som försökte ansluta till mallgalleriet inte har rätt behörighet för att komma åt dessa data. 
  
 **Så här åtgärdar du felet:** Ange autentiseringsuppgifter för en användare som är **Global administratör** , **Exchange-administratör** , **Skype för företag-administratör** , SharePoint- **administratör** , **global läsare** eller **rapport läsare** för att ansluta till programmet mall. Mer information finns i [om administratörs roller](../add-users/about-admin-roles.md) . 
  
## <a name="refresh-failed"></a>Uppdateringen misslyckades

 **Var du kommer att få se det här meddelandet:** E-post från Power BI eller statusen Misslyckades i uppdateringshistoriken. 
  
 **Orsak:** Ibland återställs autentiseringsuppgifterna för den användare som anslöt till malldokument och uppdateras inte i anslutnings inställningarna för den mall som gör att användaren kan se uppdaterings fel. 
  
 **Så här åtgärdar du felet:** I Power BI hittar du den data uppsättning som motsvarar Microsoft 365 användnings analys-mallen, väljer **Schemalägg uppdatering** och uppger dina administratörsautentiseringsuppgifter. 
  
Om det inte fungerar avmarkerar du cachen och skapar sedan programmet igen.
  
  
