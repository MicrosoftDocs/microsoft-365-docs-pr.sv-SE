---
title: Integrerade appar och Azure AD för Microsoft 365 administratörer
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection: M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: Lär dig hur du registrerar och administrerar Office 365 integrerade appar i Azure AD, så att appauktoriseringar tillåts på global administratörsnivå.
ms.openlocfilehash: 0b7392984b77b01abb0992fea5db62b80ed9fb6c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909780"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Integrerade appar och Azure AD för Microsoft 365 administratörer

Hantering av integrerade appar är mer än att bara hantera [användarnas medgivande för appar](../admin/misc/user-consent.md). Med nya nya MICROSOFT 365 REST API:er kan användare nu ge appar åtkomst till sina Microsoft 365-data, till exempel e-post, kalendrar, kontakter, användare, grupper, filer och mappar. Som standard måste användarna tilldela enskilda behörigheter till varje app. 

Men det här går inte så bra om du vill auktorisera en app en gång på global administratörsnivå och distribuera den till hela organisationen via startprogrammet. Om du vill göra det måste du registrera appen i Azure Active Directory (Azure AD). Det finns några åtgärder du måste vidta innan du kan registrera en app i Azure AD och viss bakgrundsinformation som du bör känna till som kan hjälpa dig att hantera appar i Microsoft 365 organisation.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD-resurser för Microsoft 365 administratörer

Du måste utföra de här två uppgifterna innan du kan hantera dina Microsoft 365-appar i Azure AD.
  
|Förutsättningar|Kommentarer|
|:-----|:-----|
|[Använd din kostnadsfria Azure AD-prenumeration](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Varje betald prenumeration på Microsoft 365 levereras med en kostnadsfri prenumeration på Azure AD. Du kan använda Azure AD för att hantera dina appar och för att skapa och hantera användar- och gruppkonton. Om du vill använda Azure AD går du bara till Azure-portalen [https://portal.azure.com](https://portal.azure.com) och loggar in med ditt Microsoft 365.  <br/> |
|[Hantera användarmedgivande för appar](../admin/misc/user-consent.md) <br/> |Du måste hantera användarens medgivande till appar för att tillåta appar från tredje part att komma åt Microsoft 365 och för att du ska registrera appar i Azure AD. Till exempel tredjepartsprogram som använder informationen i kalendern eller kan användas för att redigera filer i en OneDrive-mapp.  <br/> |
   
Hantering Microsoft 365 appar kräver att du har kunskaper om appar i Azure AD. Använd de här artiklarna för att ge dig den bakgrund du behöver.
  
|Artikel|Kommentarer|
|:-----|:-----|
|[Möt Microsoft 365 startprogrammet](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Om du inte har tillgång till startprogrammet för appar undrar du kanske vad det är och hur det fungerar. Startprogrammet har utformats för att hjälpa dig att komma åt dina appar överallt i Microsoft 365.  <br/> |
|[Office 365 för hanterings-API:er – översikt](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Med API:Microsoft 365 för hantering kan du ge åtkomst till dina Microsoft 365-data, inklusive det som är viktigast – e-post, kalendrar, kontakter, användare och grupper, filer och mappar. <br/> |
|[Integrera program i Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Läs mer om program som är integrerade med Azure AD, hur du registrerar din app, begreppen bakom en registrerad app och om varumärkesriktlinjer för appar med flera innehavare.  <br/> |
|[Lägga till anpassade paneler i startprogrammet](/office365/admin/manage/customize-the-app-launcher)  <br/> |Startprogrammet för appar i Microsoft 365 gör det enklare för användare att hitta och komma åt sina appar. I den här artikeln beskrivs hur du som utvecklare kan visa dina appar i startprogrammet för appar och även hur du kan ge dem en enkel inloggningsupplevelse (SSO) med hjälp av Microsoft 365 autentiseringsuppgifter.  <br/> |
|[Självstudiekurser om Azure AD-integrering](/azure/active-directory/saas-apps/tutorial-list) <br/> |Med de här självstudiekurserna får du veta hur du konfigurerar Azure AD SSO för SaaS-appar från tredje part.  <br/> |
|[Autentiseringsscenarier för Azure AD](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD förenklar autentisering för utvecklare genom att tillhandahålla identitet som en tjänst med stöd för standardiserade protokoll som OAuth 2.0 och OpenID Anslut, samt bibliotek för öppen källkod för olika plattformar så att du snabbt kan börja programmera. Det här dokumentet hjälper dig att förstå de olika scenarier som Azure AD stöder och visar hur du kommer igång.  <br/> |
|[Programåtkomst](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Med Azure AD är det enkelt att integrera många av dagens populära SaaS-program(programvara som en tjänst). Det tillhandahåller identitets- och åtkomsthantering och tillhandahåller en åtkomstpanel för användare där de kan upptäcka vilken programåtkomst de har och var de kan använda SSO för att komma åt programmen. Den här artikeln innehåller länkar till relaterade resurser där du kan läsa mer om förbättringar för programåtkomst för Azure AD och hur du kan bidra till dem.  <br/> |
|[Anpassa din Office 365 upplevelse](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Du kan få snabb åtkomst till de appar du använder varje dag genom att lägga till eller ta bort Microsoft 365 i startprogrammet.  <br/> |