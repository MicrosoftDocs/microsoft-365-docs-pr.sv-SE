---
title: Aktivera rapportmeddelandet eller tilläggen för nätfiske
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
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
description: Läs om hur du aktiverar tilläggen Rapportmeddelande eller Rapport nätfiske för Outlook och Outlook på webben, för enskilda användare eller för hela organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 25c4f7d67fd4fa876544a17df0f4bc1abfd7b3e7
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782939"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a>Aktivera rapportmeddelandet eller tilläggen för nätfiske

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Om du är administratör i en Microsoft 365 organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för inskickade inskickade material i Säkerhets- & efterlevnadscenter. Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)

Med tilläggen Rapportmeddelande och Rapport om nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva meddelanden (bra e-postmeddelanden som markerats som dåliga) eller falska negativa (felaktig e-post tillåts) till Microsoft och dess dotterbolag för analys. 

Microsoft använder dessa inskickade material för att göra e-postskyddstekniken mer effektiv. Anta till exempel att personer rapporterar många meddelanden med hjälp av tillägget Rapport om nätfiske. Den här informationen visas i säkerhetspanelen och andra rapporter. Din organisations säkerhetsgrupp kan använda den här informationen som en indikation på att principer mot nätfiske kan behöva uppdateras. 

Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske. Om du vill att användarna ska rapportera både skräppost och nätfiske distribuerar du tillägget Rapportmeddelande i organisationen. Mer information finns i Aktivera tillägget Rapportmeddelande. 

Via tillägget Rapportmeddelande kan du rapportera både skräppost och nätfiske. Administratörer kan aktivera tillägget Rapportmeddelande för organisationen och enskilda användare kan installera det själva. 

Tillägget Rapport nätfiske ger möjlighet att endast rapportera nätfiskemeddelanden. Administratörer kan aktivera tillägget Rapport nätfiske för organisationen, och enskilda användare kan installera det själva. 

Om du är enskild användare kan du aktivera båda tilläggen själv.

Om du är global administratör eller Exchange Online-administratör och Exchange har konfigurerats att använda OAuth-autentisering kan du aktivera tilläggen Rapportmeddelande och Rapportera nätfiske för organisationen. Båda tilläggen är nu tillgängliga via [centraliserad distribution.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Både tillägget Rapportmeddelande och tillägget Rapportfiske fungerar med de flesta Microsoft 365 prenumerationer och följande produkter:

  - Outlook på webben
  - Outlook 2013 SP1 eller senare
  - Outlook 2016 för Mac
  - Outlook ingår i Microsoft 365 för företag
  - Outlook för iOS och Android

- Båda tilläggen är inte tillgängliga för delade postlådor eller postlådor i lokala Exchange organisationer.

- Din befintliga webbläsare bör fungera med tilläggen Rapportmeddelande och Rapportera nätfiske. Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.

- För organisationsinstallationer måste organisationen konfigureras för att använda OAuth-autentisering. Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Administratörer måste vara medlemmar i rollgruppen Globala administratörer. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

- Mer information om hur du rapporterar ett meddelande med hjälp av funktionen Rapportmeddelande finns i Rapportera falska positiva och falska [negativa resultat i Outlook](report-false-positives-and-false-negatives.md).

## <a name="get-the-report-message-add-in"></a>Hämta tillägget Rapportmeddelande

### <a name="get-the-add-in-for-yourself"></a>Skaffa tillägget åt dig själv

1. Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapportmeddelande. Gå direkt till tillägget Rapportmeddelande genom att gå till <https://appsource.microsoft.com/product/office/wa104381180> .

2. Klicka **på HÄMTA NU.**

   ![Rapportmeddelande – skaffa det nu](../../media/ReportMessageGETITNOW.png)

3. I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**

4. Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).

När tillägget har installerats och aktiverats visas följande ikoner:

- I Outlook ser ikonen ut så här:

  > [!div class="mx-imgBorder"]
  > ![Ikonen för tillägget Rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)

- I Outlook på webben ser ikonen ut så här:

  > [!div class="mx-imgBorder"]
  > ![Outlook på webbikonen Rapportmeddelande](../../media/owa-report-message-icon.png)

### <a name="get-the-add-in-for-your-organization"></a>Hämta tillägget för din organisation

> [!NOTE]
> Det kan ta upp till 12 timmar innan tillägget visas i organisationen.

1. I Microsoft 365 administrationscentret går du till sidan **Inställningar** tillägg \>  på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Om du inte ser  tilläggssidan går du till **länken Inställningar** Tillägg för integrerade appar högst upp på sidan \>  \>  **Integrerade** appar.

2. Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa.**

   ![Sidan Tjänster och tillägg i Microsoft 365 administrationscenter](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. I den **utfällbaserade menyn** Distribuera ett nytt tillägg som visas granskar du informationen och klickar sedan på **Nästa.**

4. Klicka på Välj från **Store på nästa sida.**

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. På sidan **Välj tillägg som visas** klickar du i rutan **Sök,** skriver **Rapportmeddelande** och klickar sedan på **sökikonen** ![ ](../../media/search-icon.png) . Leta rätt på Rapportmeddelande i **resultatlistan och klicka** sedan på Lägg **till**.

   ![Välj sökresultat för tillägg](../../media/NewAddInScreen3.png)

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

   ![Konfigurera tilläggssida](../../media/configure-add-in.png)

   När du är klar klickar du på **Distribuera.**

8. På **sidan Distribuera rapportmeddelande** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats. När du har läst informationen klickar du på **Nästa.**

   ![Sidan Distribuera rapportmeddelande](../../media/deploy-report-message-page.png)

9. På **sidan Presentera tillägg som** visas granskar du informationen och klickar sedan på **Stäng.**

   ![Sidan Presentera tillägg](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Granska eller redigera inställningar för tillägget Rapportmeddelande

1. I Microsoft 365 administrationscentret går du till sidan **Inställningar** tillägg \>  på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Om du inte ser  tilläggssidan går du till **länken Inställningar** Tillägg för integrerade appar högst upp på sidan \>  \>  **Integrerade** appar.

   ![Tjänster och Add-Ins i det nya Microsoft 365 Administrationscenter](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Leta upp och **välj tillägget** Rapportmeddelande.

3. I den **utfällna** menyn Redigera rapportmeddelande som visas granskar och redigerar du lämpliga inställningar för din organisation. Klicka på **Spara** när du är klar.

   ![Inställningar för tillägget Rapportmeddelande](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a>Hämta tillägget Rapport om nätfiske

### <a name="get-the-add-in-for-yourself"></a>Skaffa tillägget åt dig själv

1. Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapport nätfiske.

2. Klicka **på HÄMTA NU.**

3. I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**

4. Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).

När tillägget har installerats och aktiverats visas följande ikoner:

- I Outlook ser ikonen ut så här:

  ![Ikonen för tillägget Nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- I Outlook på webben ser ikonen ut så här:

  > [!div class="mx-imgBorder"]
  > ![Outlook på webbrapportens ikon för nätfiske](../../media/OWA-ReportPhishing.png)

### <a name="get-the-add-in-for-your-organization"></a>Hämta tillägget för din organisation

> [!NOTE]
> Det kan ta upp till 12 timmar innan tillägget visas i organisationen.

1. I Microsoft 365 administrationscentret går du till sidan **Inställningar** tillägg \>  på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Om du inte ser  tilläggssidan går du till **länken Inställningar** Tillägg för integrerade appar högst upp på sidan \>  \>  **Integrerade** appar.

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

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Granska eller redigera inställningar för tillägget Rapport nätfiske

1. I Microsoft 365 administrationscentret går du till sidan **Inställningar** tillägg \>  på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Om du inte ser  tilläggssidan går du till **länken Inställningar** Tillägg för integrerade appar högst upp på sidan \>  \>  **Integrerade** appar.

2. Leta upp och **välj tillägget** Rapport nätfiske.

3. I den **utfällna** menyn Redigera rapport nätfiske som visas, granskar och redigerar du inställningarna efter behov för din organisation. Klicka på **Spara** när du är klar.
