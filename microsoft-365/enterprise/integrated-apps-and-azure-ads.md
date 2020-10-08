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
ms.openlocfilehash: 1e84b5e6f82848bf1d100004bcd2711ad2e9ed39
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384905"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Integrerade appar och Azure AD för Microsoft 365-administratörer

Det finns mer att hantera integrerade program än [att bara hantera användares medgivande till appar](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps). Med samband av Microsoft 365 REST-API: er kan användare ge appar åtkomst till sina Microsoft 365-data, till exempel e-post, kalendrar, kontakter, användare, grupper, filer och mappar. Som standard måste användare individuellt bevilja behörigheter till varje app. 

Men det här kan inte skalas bra om du vill auktorisera ett program en gång på global administratörs nivå och lyfta ut det till hela organisationen via Start programmet. För att göra detta måste du registrera programmet i Azure Active Directory (Azure AD). Det finns några steg som du måste vidta innan du kan registrera ett program i Azure AD och viss bakgrunds information som kan hjälpa dig att hantera program i din Microsoft 365-organisation.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD-resurser för Microsoft 365-administratörer

Du måste göra de här två uppgifterna innan du kan hantera Microsoft 365-programmen i Azure AD.
  
|Förutsättningar|Anteckningar|
|:-----|:-----|
|[Använd din gratis Azure AD-prenumeration](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Alla betalda abonnemang till Microsoft 365 kommer med ett kostnads fritt abonnemang till Azure AD. Du kan använda Azure AD för att hantera dina appar och för att skapa och hantera användar-och grupp konton. För att använda Azure AD är det bara att gå till Azure Portal på [https://portal.azure.com](https://portal.azure.com) och logga in med ditt Microsoft 365-konto.  <br/> |
|[Hantera användarens medgivande till appar](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) <br/> |Du måste hantera användar medgivande till appar för att tillåta att tredjepartsprogram får till gång till Microsoft 365-informationen och du kan registrera appar i Azure AD. Till exempel tredjepartsprogram som använder informationen i kalendern eller kan användas för att redigera filer i en OneDrive-mapp.  <br/> |
   
För att hantera Microsoft 365-appar måste du ha kunskap om appar i Azure AD. Använd dessa artiklar för att ge dig den bakgrund du behöver.
  
|Artiklar|Anteckningar|
|:-----|:-----|
|[Möt start ikonen för Microsoft 365](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Om du är nybörjare i Start programmet kanske du undrar vad det är och hur du använder det. Start programmet är utformat för att hjälpa dig att komma åt dina appar var som helst i Microsoft 365.  <br/> |
|[Översikt över API för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |Med Microsoft 365 Management API: er kan du ge till gång till dina Microsoft 365-data, inklusive de saker de bryr dig om – deras e-post, kalendrar, kontakter, användare och grupper, filer och mappar. <br/> |
|[Integrera program i Azure AD](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Lär dig mer om program som är integrerade med Azure AD och hur du registrerar programmet, förstår koncepten bakom ett registrerat program och lär dig mer om varumärkes regler för program med flera innehavare.  <br/> |
|[Lägga till anpassade paneler i Start programmet](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |Med Start programmet i Microsoft 365 blir det enklare för användare att hitta och komma åt sina appar. I den här artikeln beskrivs hur du som utvecklare kan få dina appar att visas i användarnas program starter och ger dem en enkel inloggning (SSO) med sina Microsoft 365-autentiseringsuppgifter.  <br/> |
|[Vägledning för Azure AD-integrering](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |Syftet med dessa själv studie kurser är att visa dig hur du konfigurerar Azure AD SSO för SaaS-program från tredje part.  <br/> |
|[Autentiseringskrav för Azure AD](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |Azure AD fören klar autentisering för utvecklare genom att tillhandahålla identitet som en tjänst, med stöd för branschstandardiserade protokoll som OAuth 2,0 och OpenID Connect, samt öppna käll bibliotek för olika plattformar för att snabbt komma igång med kodning. Det här dokumentet hjälper dig att förstå de olika scenarierna för Azure AD och visar hur du kommer igång.  <br/> |
|[Program åtkomst](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD gör det enkelt att integrera många av dagens populära program vara (SaaS). Det ger identitets-och åtkomst hantering, och den levererar en åtkomst panel för användare där de kan identifiera vilken program åtkomst de har och var de kan använda SSO för att få åtkomst till sina program. Den här artikeln innehåller länkar till relaterade resurser som gör det möjligt för dig att få mer information om förbättringar av program åtkomst för Azure AD och hur du kan bidra till dem.  <br/> |
|[Anpassa Office 365-upplevelsen](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Du får snabb åtkomst till de program du använder varje dag genom att lägga till eller ta bort program i Microsoft 365-startprogrammet.  <br/> |

