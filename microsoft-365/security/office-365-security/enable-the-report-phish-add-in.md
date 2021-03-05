---
title: Aktivera tillägget Rapportt phish
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Läs om hur du aktiverar tillägget Rapport nätfiske för Outlook och Outlook på webben för enskilda användare eller hela organisationen.
ms.openlocfilehash: 12543364943321689d0efa2c2942351b3d3ec6f9
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453771"
---
# <a name="enable-the-report-phishing-add-in"></a>Aktivera tillägget för att rapportera nätfiske

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter. Mer information finns i Använda [administrationsinskick för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)

Med tilläggen Rapportmeddelande och Rapport nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva meddelanden (bra e-postmeddelanden som markerats som dåliga) eller falska negativa (felaktig e-post tillåts) till Microsoft och dess dotterbolag för analys.

Microsoft använder dessa inskickade e-postmeddelanden för att göra e-postskyddstekniken mer effektiv. Anta till exempel att personer rapporterar många meddelanden med hjälp av tillägget Rapport nätfiske. Den här informationen visas i [säkerhetspanelen](security-dashboard.md) och andra rapporter. Din organisations säkerhetsgrupp kan använda den här informationen som en indikation på att skydd mot nätfiskeprinciper kan behöva uppdateras.

Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske. Om du vill att användarna ska rapportera både skräppost och nätfiske ska du distribuera tillägget Rapportmeddelande i organisationen. Mer information finns i [Aktivera tillägget Rapportmeddelande.](enable-the-report-message-add-in.md)

Med tillägget Rapport nätfiske kan du endast rapportera nätfiskemeddelanden. Administratörer kan aktivera tillägget Rapport nätfiske för organisationen och enskilda användare kan installera det själva.

Om du är enskild användare kan du aktivera tillägget Nätfiske för [dig själv.](#get-the-report-phishing-add-in-for-yourself)

Om du är global administratör eller Exchange [Online-administratör](#get-and-enable-the-report-phishing-add-in-for-your-organization)och Exchange är konfigurerat att använda OAuth-autentisering kan du aktivera tillägget Rapport nätfiske för din organisation. Rapportens nätfiskeAdd-In är nu tillgänglig via [centraliserad distribution.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Tillägget Nätfiskerapport fungerar med de flesta Microsoft 365-prenumerationer och följande produkter:

  - Outlook på webben
  - Outlook 2013 SP1 eller senare
  - Outlook 2016 för Mac eller senare
  - Outlook ingår i Microsoft 365-appar för företag
  - Outlook-appen för iOS och Android

- Tillägget Rapportfiske är inte tillgängligt för delade postlådor eller postlådor i lokala Exchange-organisationer.

- Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i principer [för användarinskick.](user-submission.md)

- Din befintliga webbläsare bör fungera med tillägget Rapport nätfiske. Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova med en annan webbläsare.

- För organisationsinstallationer måste organisationen vara konfigurerad för att använda OAuth-autentisering. Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Administratörer måste vara medlemmar i rollgruppen globala administratörer. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-phishing-add-in-for-yourself"></a>Skaffa tillägget Nätfiske för dig själv

1. Gå till Microsoft AppSource och <https://appsource.microsoft.com/marketplace/apps> sök efter tillägget Rapportfiske.

2. Klicka **på HÄMTA NU.**

3. I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**

4. Logga in med ditt arbets- eller skolkonto (för företag) eller ditt Microsoft-konto (för personlig användning).

När tillägget är installerat och aktiverat visas följande ikoner:

- Ikonen ser ut så här i Outlook:

  ![Ikon för tillägget Rapport om nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- Ikonen ser ut så här i Outlook på webben:

  ![Outlook på webben- och nätfiskeikonen](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>Skaffa och aktivera tillägget Rapport nätfiske för din organisation

> [!NOTE]
> Det kan ta upp till 12 timmar innan tillägget visas i organisationen.

1. I administrationscentret för Microsoft 365 går  du till sidan Inställningar för tillägg. Om tilläggssidan inte visas går du till länken Inställningar integrerade appar tillägg högst upp på sidan Integrerade \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  appar. 

2. Välj **Distribuera tillägg överst** på sidan och välj sedan **Nästa.**

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Granska informationen **i den utfällbaserade menyn** Distribuera ett nytt tillägg som visas och klicka sedan på **Nästa.**

4. Klicka på Välj från **Store på nästa sida.**

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. På sidan Välj **tillägg som visas** klickar  du i sökrutan, anger nätfiskerapport och klickar sedan på  ![ sökikonen. ](../../media/search-icon.png) I listan med resultat går du till **Rapport nätfiske** och klickar sedan på **Lägg till.**

6. I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**

7. På **sidan Konfigurera tillägg som** visas konfigurerar du följande inställningar:

   - **Tilldelade användare:** Välj ett av följande värden:

     - **Alla** (standard)
     - **Specifika användare/grupper**
     - **Bara jag**

   - **Distributionsmetod:** Välj ett av följande värden:

     - **Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.
     - **Tillgängligt:** Användare kan installera tillägget **på Startsidan** Få administratör \>  \> **hanterade tillägg.**
     - **Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.

   Klicka på Distribuera när du är **klar.**

8. På sidan **Distribuera rapport nätfiske** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats. Klicka på Nästa när du har läst **informationen.**

9. Granska **informationen på sidan Presentera** tillägg som visas och klicka sedan på **Stäng.**

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Lär dig hur du använder tillägget Rapport nätfiske

Personer som har tilldelats tillägget ser följande ikoner:

- Ikonen ser ut så här i Outlook:

  ![Ikon för tillägget Rapport om nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- Ikonen ser ut så här i Outlook på webben:

  ![Ikonen för tillägget Nätfiske i Outlook på webben](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Granska eller redigera inställningar för tillägget Rapport nätfiske

1. I administrationscentret för Microsoft 365 går  du till sidan Inställningar för tillägg. Om tilläggssidan inte visas går du till länken Inställningar integrerade appar tillägg högst upp på sidan Integrerade \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  appar. 

2. Leta upp och **välj tillägget Rapport** nätfiske.

3. I den **utfällblad** för Redigera rapport nätfiske som visas, granskar och redigerar inställningar efter behov för din organisation. Klicka på **Spara** när du är klar.

## <a name="view-and-review-reported-messages"></a>Visa och granska rapporterade meddelanden

Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:

- Använd administrationsportalen för inskickade material. Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)

- Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden. Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
