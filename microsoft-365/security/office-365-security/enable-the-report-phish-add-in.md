---
title: Aktivera tillägget Rapportfras
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
description: Läs om hur du aktiverar tillägget Rapport nätfiske för Outlook Outlook på webben, för enskilda användare eller hela organisationen.
ms.openlocfilehash: 44fa55a82462de336982d3af2e3996c14699fd7c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625395"
---
# <a name="enable-the-report-phishing-add-in"></a>Aktivera tillägget för att rapportera nätfiske

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Om du är administratör i en Microsoft 365 organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för inskickade inskickade material i Säkerhets- & efterlevnadscenter. Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)

Med tilläggen Rapportmeddelande och Rapport om nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva meddelanden (bra e-postmeddelanden som markerats som dåliga) eller falska negativa (felaktig e-post tillåts) till Microsoft och dess dotterbolag för analys.

Microsoft använder dessa inskickade material för att göra e-postskyddstekniken mer effektiv. Anta till exempel att personer rapporterar många meddelanden med hjälp av tillägget Rapport om nätfiske. Den här informationen visas i [säkerhetspanelen](security-dashboard.md) och andra rapporter. Din organisations säkerhetsgrupp kan använda den här informationen som en indikation på att principer mot nätfiske kan behöva uppdateras.

Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske. Om du vill att användarna ska rapportera både skräppost och nätfiske distribuerar du tillägget Rapportmeddelande i organisationen. Mer information finns [i Aktivera tillägget Rapportmeddelande.](enable-the-report-message-add-in.md)

Tillägget Rapport nätfiske ger möjlighet att endast rapportera nätfiskemeddelanden. Administratörer kan aktivera tillägget Rapport nätfiske för organisationen, och enskilda användare kan installera det själva.

Om du är enskild användare kan du [aktivera tillägget Rapport nätfiske för dig själv.](#get-the-report-phishing-add-in-for-yourself)

Om du är global administratör eller [Exchange Online-administratör](#get-and-enable-the-report-phishing-add-in-for-your-organization)och Exchange är konfigurerat att använda OAuth-autentisering kan du aktivera tillägget Rapport nätfiske för din organisation. Rapporten nätfiske-Add-In är nu tillgänglig via [centraliserad distribution.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Tillägget Rapport nätfiske fungerar med de flesta Microsoft 365 prenumerationer och följande produkter:

  - Outlook på webben
  - Outlook 2013 SP1 eller senare
  - Outlook 2016 för Mac eller senare
  - Outlook ingår i Microsoft 365 för företag
  - Outlook för iOS och Android

- Tillägget Rapport nätfiske är inte tillgängligt för delade postlådor eller postlådor i lokala Exchange organisationer.

- Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i Principer [för användarinskick.](user-submission.md)

- Din befintliga webbläsare bör fungera med tillägget Rapport nätfiske. Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.

- För organisationsinstallationer måste organisationen konfigureras för att använda OAuth-autentisering. Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Administratörer måste vara medlemmar i rollgruppen Globala administratörer. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-phishing-add-in-for-yourself"></a>Skaffa tillägget Rapport om nätfiske åt dig själv

1. Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapport nätfiske.

2. Klicka **på HÄMTA NU.**

3. I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**

4. Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).

När tillägget har installerats och aktiverats visas följande ikoner:

- I Outlook ser ikonen ut så här:

  ![Ikonen för tillägget Nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- I Outlook på webben ser ikonen ut så här:

  ![Outlook på webbrapportens ikon för nätfiske](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>Hämta och aktivera tillägget Rapport om nätfiske för din organisation

> [!NOTE]
> Det kan ta upp till 12 timmar innan tillägget visas i organisationen.

1. I administrationscentret för Microsoft 365 går du till sidan **Inställningar-tillägg** på . Om tilläggssidan inte visas går du till länken tillägg för \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **Inställningar-integrerade**  appar högst upp på sidan Integrerade appar.

2. Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa.**

   ![Sidan Tjänster och tillägg i Microsoft 365 administrationscenter](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. I den **utfällbaserade menyn** Distribuera ett nytt tillägg som visas granskar du informationen och klickar sedan på **Nästa.**

4. Klicka på Välj från **Store på nästa sida.**

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. På sidan **Välj tillägg som visas** klickar  du i rutan Sök, anger **Rapportfiske** och klickar sedan på **sökikonen** ![ ](../../media/search-icon.png) . Leta rätt på Rapport nätfiske i **listan med resultat och** klicka sedan på Lägg **till**.

6. I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**

7. Konfigurera **följande inställningar på sidan** Konfigurera tillägget som visas:

   - **Tilldelade användare:** Välj ett av följande värden:

     - **Alla** (standard)
     - **Specifika användare/grupper**
     - **Bara jag**

   - **Distributionsmetod:** Välj något av följande värden:

     - **Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.
     - **Tillgängligt:** Användarna kan installera tillägget på **Fliken** Hämta \> **tillägg som hanteras** av \> **administratören.**
     - **Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.

   När du är klar klickar du på **Distribuera.**

8. På sidan **Distribuera nätfiske** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats. När du har läst informationen klickar du på **Nästa.**

9. På **sidan Presentera tillägg som** visas granskar du informationen och klickar sedan på **Stäng.**

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Lär dig hur du använder tillägget Rapport om nätfiske

Personer som har tilldelats tillägget ser följande ikoner:

- I Outlook ser ikonen ut så här:

  ![Ikonen för tillägget Nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- I Outlook på webben ser ikonen ut så här:

  ![Outlook på ikonen för tillägget Nätfiske](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Granska eller redigera inställningar för tillägget Rapport nätfiske

1. I administrationscentret för Microsoft 365 går du till sidan **Inställningar-tillägg** på . Om tilläggssidan inte visas går du till länken tillägg för \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **Inställningar-integrerade**  appar högst upp på sidan Integrerade appar.

2. Leta upp och **välj tillägget** Rapport nätfiske.

3. I den **utfällna** menyn Redigera rapport nätfiske som visas, granskar och redigerar du inställningarna efter behov för din organisation. Klicka på **Spara** när du är klar.

## <a name="view-and-review-reported-messages"></a>Visa och granska rapporterade meddelanden

Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:

- Använd portalen för administrationsinskick. Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)

- Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden. Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)
