---
title: Integrerade appar och Azure AD för Microsoft 365-administratörer
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
description: Lär dig hur du registrerar och administrerar integrerade Office 365-appar i Azure AD, som tillåter program godkännanden på global administratörs nivå.
ms.openlocfilehash: 3d9ded2ba2819d0e957586b6c49811ec932dee31
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694849"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Integrerade appar och Azure AD för Microsoft 365-administratörer

Det finns mer att hantera integrerade program än att bara [Aktivera och inaktivera integrerade appar](https://support.office.com/article/7e453a40-66df-44ab-92a1-96786cb7fb34#__toc379982114). Med samband av Microsoft 365 REST-API: er kan användare ge appar åtkomst till sina Microsoft 365-data, som e-post, kalendrar, kontakter, användare, grupper, filer och mappar. Som standard måste användare individuellt bevilja behörigheter till varje app, men det går inte att skala dem så att du kan auktorisera ett program en gång på global administratörs nivå och lyfta fram den till hela organisationen via Start programmet. För att göra detta måste du registrera programmet i Azure AD. Det finns några steg som du måste vidta innan du kan registrera ett program i Azure AD och viss bakgrunds information som kan hjälpa dig att hantera program i din Microsoft 365-organisation. I den här artikeln hänvisas du till resurserna.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD-resurser för Microsoft 365-administratörer

För att kunna hantera dina Microsoft 365-appar i Azure AD måste du göra detta.
  
|**Krav**|**Anteckningar**|
|:-----|:-----|
|[Använda din kostnadsfria Azure Active Directory-prenumeration](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Alla betalda abonnemang till Microsoft 365 kommer med ett kostnads fritt abonnemang till Azure Active Directory (Azure AD). Du kan använda Azure AD för att hantera dina appar och för att skapa och hantera användar-och grupp konton. För att använda Azure AD är det bara att gå till Azure-portalen och logga in med ditt Microsoft 365-konto.  <br/> |
|[Aktivera eller inaktivera integrerade appar](https://support.office.com/article/7e453a40-66df-44ab-92a1-96786cb7fb34#__toc379982114) <br/> |Du måste aktivera integrerade program för att användarna ska få åtkomst till Microsoft 365-informationen och för att registrera program i Azure AD. När någon till exempel använder en app från tredje part, kan programmet be om tillstånd att komma åt sin kalender och redigera filer som finns i en OneDrive för företag-mapp.  <br/> |
   
För att hantera Microsoft 365-appar måste du ha kunskap om appar i Azure AD. De här artiklarna hjälper dig att få den bakgrund du behöver.
  
|**Bakgrunds artikel**|**Anteckningar**|
|:-----|:-----|
|[Möt start ikonen för Microsoft 365](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Om du är nybörjare i Start programmet kanske du undrar vad det är och hur du använder det. Start programmet är utformat för att hjälpa dig att komma åt dina appar var som helst i Microsoft 365.  <br/> |
|[Översikt över API för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |Med Microsoft 365 API: er kan du ge åtkomst till dina Microsoft 365-data, inklusive de saker de bryr dig om – deras e-post, kalendrar, kontakter, användare och grupper, filer och mappar. Det finns ett diagram i den här artikeln som illustrerar förhållandet mellan Microsoft 365-appar, Azure AD och de data som apparna har åtkomst till.  <br/> |
|[Integrera program i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Lär dig mer om program som är integrerade med Azure AD och hur du registrerar programmet, förstår koncepten bakom ett registrerat program och får reda på rikt linjer för flera klient program.  <br/> |
|[Lägga till anpassade paneler i Start programmet](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |Med Start programmet i Microsoft 365 blir det enklare för användare att hitta och komma åt sina appar. I den här artikeln beskrivs hur du som utvecklare kan få dina appar att visas i användarnas program starter och ger dem en enkel inloggning (SSO) med sina Microsoft 365-autentiseringsuppgifter.  <br/> |
|[Själv studie kurser för Azure Active Directory-integrering](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |Syftet med dessa själv studie kurser är att visa dig hur du konfigurerar Azure AD SSO för SaaS-program från tredje part.  <br/> |
|[Autentiseringskrav för Azure AD](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |Azure AD fören klar autentisering för utvecklare genom att tillhandahålla identitet som en tjänst, med stöd för branschstandardiserade protokoll som OAuth 2,0 och OpenID Connect, samt öppna käll bibliotek för olika plattformar för att snabbt komma igång med kodning. Det här dokumentet hjälper dig att förstå de olika scenarierna för Azure AD och visar hur du kommer igång.  <br/> |
|[Program åtkomst](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD gör det enkelt att integrera många av dagens populära program som tjänst program (SaaS). Det ger identitets-och åtkomst hantering, och den levererar en åtkomst panel för användare där de kan identifiera vilken program åtkomst de har och var de kan använda SSO för att få åtkomst till sina program. Den här artikeln innehåller länkar till relaterade resurser som gör det möjligt för dig att få mer information om förbättringar av program åtkomst för Azure AD och hur du kan bidra till dem.  <br/> |
|[Anpassa Office 365-upplevelsen](https://support.office.com/article/eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Du får snabb åtkomst till de program du använder varje dag genom att lägga till eller ta bort program i Microsoft 365-startprogrammet.  <br/> |
   

