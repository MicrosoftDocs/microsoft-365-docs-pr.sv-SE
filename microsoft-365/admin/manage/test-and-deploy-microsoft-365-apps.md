---
title: Testa och distribuera Microsoft 365-appar efter partners i portalen För integrerade appar
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Hitta, testa och distribuera Microsoft- och Microsoft-partnerappar för användare och grupper i organisationen från portalen för integrerade appar i administrationscentret för Microsoft 365.
ms.openlocfilehash: da67cbe5f8b6e5f2da42e1f4b57a55d7d4a768fb
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644482"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Testa och distribuera Microsoft 365-appar efter partners i portalen För integrerade appar

I administrationscentret för Microsoft 365 får du flexibiliteten att distribuera appar för enstaka lager, anpassade affärsprogram och Microsoft 365-partnerappar från en enda plats. Du kommer åt platsen i administrationscentret för Microsoft och > inställningar > integrerade appar. Genom att hitta, testa och helt distribuera köpta och licensierade appar av Microsoft-partner från portalen för integrerade appar är det praktiskt och effektivt att hålla företagstjänsterna uppdaterade.

Mer information om att köpa och licensiera Microsoft 365-appar från partner i din organisation finns i Hantera och distribuera [Microsoft 365-appar](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)från administrationscentret för Microsoft 365.

Mer information om hur partners skapar dessa appar finns i Planera [ett SaaS-erbjudande för kommersiella marknadsplatser](https://go.microsoft.com/fwlink/?linkid=2158277)

Portalen för integrerade appar är endast tillgänglig för globala administratörer och endast tillgänglig för kunder över hela världen. Den här funktionen är inte tillgänglig i moln för myndigheter.

I portalen Integrerade appar visas en lista med appar, som innehåller enstaka appar och Microsoft 365-appar från partners som distribueras till din organisation. Endast webbappar, SPFx-appar, Office-tillägg och Teams-appar visas. För webbappar finns det två typer av appar.

- SaaS-appar som är appsource.microsoft.com och kan distribueras av administratörer som ger godkännande för organisationens räkning.
- SAML-galleriprogram som är länkade till Office-tillägg.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Hantera appar i portalen Integrerade appar

Du kan hantera testning och distribution av köpta och licensierade Microsoft 365-appar från partners.

1. I det vänstra navigeringsfältet i administrationscentret väljer **du Inställningar** och sedan **Integrerade appar.**

2. Välj ett program med **Status** för **Fler appar tillgängligt** för att öppna **fönstret** Hantera. Status för fler **tillgängliga appar gör** att du vet att det finns fler integreringar från ISV-enheter som ännu inte har distribuerats.

3. Välj **Distribuera** på fliken **Översikt.** För vissa program måste du lägga till användare innan du kan välja Distribuera.

4. Välj  **Användare**, välj **Är det här en testdistribution** och välj sedan **Hela organisationen**, **Specifika användare/grupper** eller **Bara jag**. Du kan också välja **Testa distribution** om du föredrar att vänta med att distribuera programmet till hela organisationen. Vissa användare eller grupper kan vara en Microsoft 365-grupp, säkerhetsgrupp eller distributionsgrupp.

5. Välj **Uppdatera** och sedan **Klar**. Nu kan du välja Distribuera på fliken Översikt.

6. Granska programinformationen och välj sedan **Distribuera**.

7. Välj **Klar** på sidan Distribution slutförd och granska informationen om testet eller fullständig distribution på **fliken** Översikt.

8. Om programmet har statusen **Uppdatering väntar kan** du klicka på programmet för att öppna fönstret Hantera och uppdatera programmet.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Hitta publicerade appar för testning och fullständig distribution

Du kan söka efter, testa och helt distribuera publicerade program som inte redan visas i listan på sidan Integrerade appar. Genom att köpa och licensiera apparna från administrationscentret kan du lägga till Microsoft- och Microsoft-partnerappar i listan från en enda plats.

1. I det vänstra navigeringsfältet i administrationscentret väljer **du Inställningar** och sedan **Integrerade appar.**

2. Välj **Skaffa appar** för att visa apparna.

3. På sidan **Microsoft 365-appar** publicerade appar väljer du det program du vill distribuera genom att välja **Skaffa nu.** Apparna som visas främst är Word-, PowerPoint-, Excel-, Outlook-tillägg, Teams-appar och SharePoint-appar (byggt på SharePoint Framework-teknik). Godkänn behörigheterna och välj **Fortsätt.**

5. Välj **Distribuera** högst upp på sidan bredvid meddelandet som refererar till att väntar på att distribueras.

    Om den valda appen är länkad till ett SaaS-erbjudande via en ISV visas alla andra appar som är en del av det här länkade erbjudandet på sidan Konfiguration. Om du väljer att distribuera alla program väljer du **Nästa.** Annars väljer du **Redigera** och väljer vilka program du vill distribuera. För vissa program måste du lägga till användare innan du kan välja **Distribuera.**

6. Välj **Lägg till** användare , välj Är det här en **testdistribution** och välj sedan **Hela** organisationen eller **Specifika användare/grupper** eller Bara **jag.**

    Vissa användare/grupper kan vara en Microsoft 365-grupp, säkerhetsgrupp eller distribuerad grupp. Du kan också välja **Testa distribution** om du föredrar att vänta med att distribuera programmet till hela organisationen.

7. Välj **Nästa** för att komma till **sidan Acceptera begäran.** Appfunktionerna och behörigheterna för de olika apparna visas. Om appen behöver medgivande väljer du **Acceptera behörigheter**. Det är bara en global administratör som kan ge medgivande.

8. Välj **Nästa** för att granska distributionen och välj **Slutför distributionen.** Du kan visa distributionen från fliken **Översikt** genom att välja **Visa den här distributionen.** I administrationscentret för Microsoft 365 kan du se status för varje distribuerad app och det datum då du distribuerade programmet.

> [!NOTE]
> Om ett program tidigare har distribuerats från någon annan plats än portalen för integrerade appar är **distributionstypen** **Anpassad.**

## <a name="unsupported-scenarios"></a>Scenarier som inte stöds

Du kommer inte att kunna distribuera en app med en enda butik eller Microsoft 365-appar av partner från portalen för integrerade appar för följande scenarier.

- Samma tillägg är kopplat till mer än ett SaaS-erbjudande.
- SaaS-erbjudandet är länkat till tillägg, men integrerar inte med Microsoft Graph och inget AAD-app-ID tillhandahålls.
- SaaS-erbjudandet är länkat till tillägg, men AAD-app-ID för Microsoft Graph-integrering delas mellan flera SaaS-erbjudanden.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Ladda upp anpassad verksamhetslinje för testning och fullständig distribution

1. I det vänstra navigeringsfältet i administrationscentret väljer **du Inställningar** och sedan **Integrerade appar.**

2. Välj **Ladda upp anpassade appar**. Endast en anpassad programrad för Word, PowerPoint, Excel och Outlook stöds.

3. Ladda upp manifestfilen från din enhet eller lägg till en URL-länk. För vissa program måste du lägga till användare innan du kan välja Distribuera.

4. Välj **Lägg till** användare , välj Är det här en **testdistribution** och välj Hela **organisationen** eller **Specifika användare/grupper** eller Bara **jag.**

    Vissa användare/grupper kan vara en Microsoft 365-grupp, säkerhetsgrupp eller distribuerad grupp. Du kan också välja **Testa distribution** om du vill vänta med att distribuera programmet till hela organisationen.

5. Välj **Nästa** för att komma till **sidan Acceptera begäran.** Appfunktionerna och -behörigheterna för apparna visas. Om appen behöver medgivande väljer du **Acceptera behörigheter**. Det är bara en global administratör som kan ge medgivande.

6. Välj **Nästa** för att granska distributionen och välj **Slutför distributionen.** Du kan visa distributionen från fliken **Översikt** genom att välja **Visa den här distributionen.**

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>Vilken administratörsroll behöver jag för att komma åt integrerade appar?

Endast globala administratörer kan komma åt integrerade appar. Integrerade appar visas inte i det vänstra navigeringsfältet för andra administratörer.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>Varför visas Tillägg i det vänstra navigeringsfältet under Inställning men inte Integrerade appar?

Det kan finnas flera anledningar:

- Den inloggade administratören är en Exchange-administratör.
- Kunden använder molntjänster i en suverän del och integrerade appar finns ännu tillgängliga för molnkunder i en suverän del.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>Vilka appar kan jag distribuera från integrerade appar?

Integrerade appar tillåter distribution av webbappar, Teams-appar, Excel, PowerPoint, Word, Outlook-tillägg och SPFx-appar. För tillägg har integrerade appar stöd för distribution till Exchange Online-postlådor, inte till lokala Exchange-postlådor.

### <a name="can-administrators-delete-or-remove-apps"></a>Kan administratörer ta bort eller ta bort appar?

Ja. Globala administratörer kan ta bort appar.

- Välj en app i listvyn. På fliken **Konfiguration** väljer du vilka appar som ska tas bort.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>Finns integrerade appar i en suverän molntjänst?

Nej. Integrerade appar är inte tillgängliga för molnkunder med en suverän tillgång.

### <a name="is-integrated-apps-available-in-government-clouds"></a>Finns integrerade appar i myndighetsmoln?

Nej. Integrerade appar är inte tillgängliga för kunder i myndighetsmoln.
