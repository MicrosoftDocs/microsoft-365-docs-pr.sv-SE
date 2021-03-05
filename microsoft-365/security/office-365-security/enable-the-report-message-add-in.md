---
title: Aktivera tillägget för att rapportera meddelande
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Lär dig hur du aktiverar tillägget Rapportmeddelande för Outlook och Outlook på webben för enskilda användare eller hela organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5eed0fc8905020ea12d3fa6a51c5c8051205b0da
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453759"
---
# <a name="enable-the-report-message-add-in"></a>Aktivera tillägget för att rapportera meddelande

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter. Mer information finns i Använda [administrationsinskick för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)

Med tilläggen Rapportmeddelande och Rapport nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva meddelanden (bra e-postmeddelanden markerade som dåliga) eller falska negativa (felaktig e-post tillåts) till Microsoft och dess dotterbolag för analys.

Microsoft använder dessa inskickade e-postmeddelanden för att göra e-postskyddstekniken mer effektiv. Om personer till exempel rapporterar många meddelanden som flaggats som Skräppost med hjälp av tillägget Rapportmeddelande kan organisationens säkerhetsgrupp behöva justera principerna för [skräppostskydd.](configure-your-spam-filter-policies.md)

Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske. Om du vill att användarna endast ska rapportera nätfiskemeddelanden distribuerar du tillägget Rapport nätfiske i organisationen. Mer information finns i [Aktivera tillägget Rapport nätfiske.](enable-the-report-phish-add-in.md)

Med tillägget Rapportmeddelande kan du rapportera både skräppost och nätfiske. Administratörer kan aktivera tillägget Rapportmeddelande för organisationen och enskilda användare kan installera det själva.

Om du är en enskild användare kan [du aktivera tillägget Rapportmeddelande](#get-the-report-message-add-in-for-yourself)för dig själv.

Om du är global administratör eller Exchange [Online-administratör](#get-and-enable-the-report-message-add-in-for-your-organization)och Exchange är konfigurerat att använda OAuth-autentisering kan du aktivera tillägget Rapportmeddelande för organisationen. Rapportmeddelandets Add-In nu tillgänglig via [centraliserad distribution.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Tillägget Rapportmeddelande fungerar med de flesta Microsoft 365-prenumerationer och följande produkter:

  - Outlook på webben
  - Outlook 2013 SP1 eller senare
  - Outlook 2016 för Mac
  - Outlook ingår i Microsoft 365-appar för företag
  - Outlook-appen för iOS och Android

- Tillägget Rapportmeddelande är inte tillgängligt för delade postlådor eller postlådor i lokala Exchange-organisationer.

- Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i principer [för användarinskick.](user-submission.md)

- Din befintliga webbläsare bör fungera med tillägget Rapportmeddelande. Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova med en annan webbläsare.

- För organisationsinstallationer måste organisationen vara konfigurerad för att använda OAuth-autentisering. Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Administratörer måste vara medlemmar i rollgruppen globala administratörer. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-message-add-in-for-yourself"></a>Skaffa tillägget Rapportmeddelande åt dig själv

1. Gå till Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapportmeddelande. Gå direkt till tillägget Rapportmeddelande genom att gå <https://appsource.microsoft.com/product/office/wa104381180> till.

2. Klicka **på HÄMTA NU.**

   ![Rapportmeddelande – Skaffa nu](../../media/ReportMessageGETITNOW.png)

3. I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**

4. Logga in med ditt arbets- eller skolkonto (för företag) eller ditt Microsoft-konto (för personlig användning).

När tillägget är installerat och aktiverat visas följande ikoner:

- Ikonen ser ut så här i Outlook:

  ![Ikonen för tillägget Rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)

- Ikonen ser ut så här i Outlook på webben:

  ![Ikonen för tillägget Rapportmeddelande i Outlook på webben](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Mer information om hur du använder tillägget finns i Använda tillägget [Rapportmeddelande.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Skaffa och aktivera tillägget Rapportmeddelande för din organisation

> [!NOTE]
> Det kan ta upp till 12 timmar innan tillägget visas i organisationen.

1. I administrationscentret för Microsoft 365 går  du till sidan Inställningar för tillägg. Om tilläggssidan inte visas går du till länken Inställningar integrerade appar tillägg högst upp på sidan Integrerade \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  appar. 

2. Välj **Distribuera tillägg överst** på sidan och välj sedan **Nästa.**

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Granska informationen **i den utfällbaserade menyn** Distribuera ett nytt tillägg som visas och klicka sedan på **Nästa.**

4. Klicka på Välj från **Store på nästa sida.**

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. På sidan Välj **tillägg som visas** klickar  du i sökrutan, skriver rapportmeddelande och klickar sedan på  ![ sökikonen. ](../../media/search-icon.png) Leta rätt på Rapportmeddelande i **resultatlistan och klicka** sedan på **Lägg till.**

   ![Välj sökresultat för tillägg](../../media/NewAddInScreen3.png)

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

   ![Sidan Konfigurera tillägg](../../media/configure-add-in.png)

   Klicka på Distribuera när du är **klar.**

8. På sidan **Distribuera rapportmeddelande** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats. Klicka på Nästa när du har läst **informationen.**

   ![Sidan Distribuera rapportmeddelande](../../media/deploy-report-message-page.png)

9. Granska **informationen på sidan Presentera** tillägg som visas och klicka sedan på **Stäng.**

   ![Sidan Presentera tillägg](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Lär dig hur du använder tillägget Rapportmeddelande

Personer som har tilldelats tillägget ser följande ikoner:

- Ikonen ser ut så här i Outlook:

  ![Ikonen för tillägget Rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)

- Ikonen ser ut så här i Outlook på webben:

  ![Ikonen för tillägget Meddelande i Outlook på webben](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

När du meddelar användarna om tillägget Rapportmeddelande tar du med en länk [för att använda tillägget Rapportmeddelande.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Granska eller redigera inställningar för tillägget Rapportmeddelande

1. I administrationscentret för Microsoft 365 går  du till sidan Inställningar för tillägg. Om tilläggssidan inte visas går du till länken Inställningar integrerade appar tillägg högst upp på sidan Integrerade \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  appar. 

   ![Tjänster och Add-Ins i det nya administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Leta upp och **välj tillägget** Rapportmeddelande.

3. I den **utfällna** menyn Redigera rapportmeddelande som visas granskar och redigerar du inställningar efter behov för din organisation. Klicka på **Spara** när du är klar.

   ![Inställningar för tillägget Rapportmeddelande](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Visa och granska rapporterade meddelanden

Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:

- Använd administrationsportalen för inskickade material. Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)

- Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden. Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
