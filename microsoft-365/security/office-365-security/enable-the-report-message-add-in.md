---
title: Aktivera tillägget Rapportmeddelande
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Lär dig hur du aktiverar tillägget Report Message för Outlook och Outlook på webben, för enskilda användare eller hela organisationen.
ms.openlocfilehash: c160e928c9a46dd4dc360c5e61d70ca401430378
ms.sourcegitcommit: a86787b62cec95a392ff2b933f5dc44334ceb7e9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2020
ms.locfileid: "43061755"
---
# <a name="enable-the-report-message-add-in-in-office-365"></a>Aktivera tillägget Rapportmeddelande i Office 365

> [!NOTE]
> Om du är administratör i en Office 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inlämningar i Office 365 Security & Compliance Center. Mer information finns i [Använda administratörsöverföring för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft](admin-submission.md).

Tillägget Report Message för Outlook och Outlook på webben (tidigare känt som Outlook Web App) gör det möjligt för människor att enkelt rapportera falska positiva (bra e-post markerad som dålig) eller falska negativ (dålig e-post tillåten) till Microsoft och dess dotterbolag för analys. Microsoft använder dessa inlämningar för att förbättra effektiviteten i e-postskyddstekniker.

Anta till exempel att andra rapporterar många meddelanden som nätfiske. Den här informationen visas i [säkerhetsinstrumentpanelen](security-dashboard.md) och andra rapporter. Organisationens säkerhetsteam kan använda den här informationen som en indikation på att anti-phishing-principer kan behöva uppdateras. Om personer rapporterar många meddelanden som har flaggats som skräppost som Inte skräppost med tillägget Rapportera meddelande kan organisationens säkerhetsteam behöva justera [principer mot skräppost.](configure-your-spam-filter-policies.md)

Om din organisation använder [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) eller [Plan 2](office-365-ti.md)ger tillägget Rapportmeddelande dessutom organisationens säkerhetsteam användbar information som de kan använda för att granska och uppdatera säkerhetsprinciper.

Administratörer kan aktivera tillägget Rapportmeddelande för organisationen och enskilda användare kan installera det själva.

Om du är en enskild användare kan du [aktivera tillägget Rapportmeddelande själv](#get-the-report-message-add-in-for-yourself).

Om du är global Office 365-administratör eller Exchange [Online-administratör](#get-and-enable-the-report-message-add-in-for-your-organization)och Exchange är konfigurerat för att använda OAuth-autentisering kan du aktivera tillägget Rapportmeddelande för din organisation . Tillägget Rapportmeddelande är nu tillgängligt via [centraliserad distribution](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Tillägget Rapportmeddelande fungerar med de flesta Office 365-prenumerationer och följande produkter:

  - Outlook på webben
  - Outlook 2013 SP1 eller senare
  - Outlook 2016 för Mac
  - Outlook ingår i Office 365 ProPlus

- Tillägget Rapportmeddelande är inte tillgängligt för:

  - Postlådor i lokala Exchange-organisationer
  - GCC-, GCC HIGH- eller DoD-prenumerationer

- Din befintliga webbläsare bör fungera med tillägget Rapportmeddelande. Men om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.

- För organisationsinstallationer måste organisationen konfigureras för att använda OAuth-autentisering. Mer information finns [i Avgöra om centraliserad distribution av tillägg fungerar för din organisation](../../admin/manage/centralized-deployment-of-add-ins.md).

- Administratörer måste vara medlemmar i rollgruppen Globala administratörer. Mer information finns [i Behörigheter i Säkerhets- & Compliance Center för Office 365.](permissions-in-the-security-and-compliance-center.md)

## <a name="get-the-report-message-add-in-for-yourself"></a>Hämta tillägget Rapportmeddelande själv

1. Gå till Microsoft AppSource och <https://appsource.microsoft.com/marketplace/apps> sök efter tillägget Rapportmeddelande. Gå direkt till tillägget Rapportmeddelande och <https://appsource.microsoft.com/product/office/wa104381180>gå till .

2. Klicka på **Hämta den nu.**

   ![Rapportera meddelande - Hämta det nu](../../media/ReportMessageGETITNOW.png)

3. Granska användarvillkoren och sekretesspolicyn i dialogrutan som visas och klicka sedan på **Fortsätt**.

4. Logga in på Office 365 med ditt arbets- eller skolkonto (för företagsbruk) eller ditt Microsoft-konto (för personligt bruk).

När tillägget har installerats och aktiverats visas följande ikoner:

- I Outlook ser ikonen ut så här:

  ![Rapportmeddelandetillägg för Outlook](../../media/OutlookReportMessageIcon.png)

- I Outlook på webben ser ikonen ut så här:

  ![Outlook på ikonen För webbrapportmeddelande](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Mer information om hur du använder tillägget finns i [Använda tillägget Rapportmeddelande](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Hämta och aktivera tillägget Rapportmeddelande för din organisation

> [!NOTE]
> Det kan ta upp till 12 timmar innan tillägget visas i organisationen.

1. Gå till sidan **Tjänster & tillägg i administrationscentret** för Microsoft 365 och <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>klicka sedan på Distribuera **tillägg**.

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Granska informationen i utfällningen **Distribuera ett nytt tillägg** som visas och klicka sedan på **Nästa**.

3. Klicka på Välj **på**nästa sida .

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

4. På sidan **Välj tillägg** som visas klickar du i rutan **Sök,** anger **Rapportmeddelande**och klickar sedan på **Sök** ![efter ikon](../../media/search-icon.png). Leta reda på **Rapportmeddelande i** resultatlistan och klicka sedan på **Lägg till**.

   ![Välj sökresultat för tillägg](../../media/NewAddInScreen3.png)

5. Granska licensierings- och sekretessinformationen i dialogrutan som visas och klicka sedan på **Fortsätt**.

6. Konfigurera följande inställningar på sidan **Konfigurera tillägg** som visas:

   - **Tilldelade användare**: Välj ett av följande värden:

     - **Alla** (standard)
     - **Specifika användare/grupper**
     - **Bara jag**

   - **Distributionsmetod**: Välj ett av följande värden:

     - **Fast (standard)**: Tillägget distribueras automatiskt till de angivna användarna och de kan inte ta bort det.
     - **Tillgänglig:** Användare kan installera tillägget at **Home** \> **Get-tillägg som administreras.** \> **Admin-managed**
     - **Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.

   ![Konfigurera tilläggssida](../../media/configure-add-in.png)

   När du är klar klickar du på **Distribuera**.

7. På sidan **Distribuera rapportmeddelande** som visas visas visas en lägesrapport följt av en bekräftelse på att tillägget har distribuerats. När du har läst informationen klickar du på **Nästa**.

   ![Sidan Distribuera rapportmeddelande](../../media/deploy-report-message-page.png)

8. På sidan **Meddela tillägg** som visas granskar du informationen och klickar sedan på **Stäng**.

   ![Meddela tilläggssida](../../media/announce-add-in-page.png)

### <a name="learn-how-to-use-the-report-message-add-in"></a>Läs om hur du använder tillägget Rapportmeddelande

Personer som har tillägget tilldelats för dem ser följande ikoner:

- I Outlook ser ikonen ut så här:

  ![Ikonen För rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)

- I Outlook på webben ser ikonen ut så här:

  ![Outlook i ikonen För webbrapportmeddelande](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

När du meddelar användarna om tillägget Rapportmeddelande ska du inkludera en länk till [Använda tillägget Rapportmeddelande](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

### <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Granska eller redigera inställningar för tillägget Rapportmeddelande

1. Gå till sidan **Tjänster & tillägg på** sidan Tjänster & på <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.

   ![Sidan Tjänster och tillägg i det nya administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Sök efter och välj tillägget **Rapportmeddelande.**

3. Granska och redigera inställningar som är lämpliga för din organisation i det utfällbara meddelandet **Redigera rapportmeddelande** som visas. Klicka på **Spara** när du är klar.

   ![Inställningar för tillägget Rapportmeddelande](../../media/EditReportMessageAddIn.png)
