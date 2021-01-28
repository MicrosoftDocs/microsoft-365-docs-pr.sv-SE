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
description: Lär dig hur du aktiverar rapport tillägget för Outlook och Outlook på webben, för enskilda användare eller hela organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1f8cffaa6346ec7f426da3c862014ed85a9a367
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029238"
---
# <a name="enable-the-report-message-add-in"></a>Aktivera tillägget för att rapportera meddelande

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för säkerhets & efterlevnad. Mer information finns i [använda administratörs överföring för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft](admin-submission.md).

Med tilläggen rapport meddelande och rapportera nät fiske funktioner för Outlook och Outlook på webben (tidigare Outlook Web App) kan andra personer enkelt rapportera falsk identifiering (god e-post som är markerad som dålig) eller falskt negativ (dålig e-post) till Microsoft och dess dotter bolag för analys.

Microsoft använder dessa inlämningar för att förbättra effektiviteten hos e-postskydd. Om du till exempel rapporterar många meddelanden som har flaggats som skräp post som icke-skräppost-objekt med hjälp av tillägget rapport, kan organisationens säkerhets Team behöva justera [principer för skräp post](configure-your-spam-filter-policies.md).

Du kan installera ett tilläggsprogram för rapport-eller rapport nät. Om du bara vill att användarna ska rapportera phishing-meddelanden kan du distribuera tillägget rapportera nät fiske i din organisation. Mer information finns i [aktivera tillägget rapportera nät fiske](enable-the-report-phish-add-in.md).

Med tillägget rapport meddelanden kan du rapportera både skräp post och nät fiske meddelanden. Administratörer kan aktivera tillägget rapportera till organisationen, och enskilda användare kan installera den själva.

Om du är en enskild användare kan du [Aktivera tilläggs tillägget för rapportering](#get-the-report-message-add-in-for-yourself).

Om du är global administratör eller Exchange Online-administratör och Exchange är konfigurerat för att använda OAuth-autentisering kan du [aktivera tillägget rapportera till din organisation](#get-and-enable-the-report-message-add-in-for-your-organization). Rapport meddelande Add-In är nu tillgängligt via [centraliserad distribution](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Tillägget rapportera meddelanden fungerar med de flesta Microsoft 365-abonnemang och följande produkter:

  - Outlook på webben
  - Outlook 2013 SP1 eller senare
  - Outlook 2016 för Mac
  - Outlook ingår i Microsoft 365-appar för företag

- Tillägget för rapport meddelanden är inte tillgängligt för post lådor i lokala Exchange-organisationer.

- Du kan konfigurera vilka meddelanden som ska kopieras eller dirigeras om till en post låda som du anger. Mer information finns i [principer för användar profiler](user-submission.md).

- Din befintliga webbläsare bör fungera med tilläggsprogrammet rapportera meddelande. Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.

- För organisatoriska installationer måste organisationen konfigureras för att använda OAuth-autentisering. Mer information finns i [avgöra om centraliserad distribution av tillägg fungerar för din organisation](../../admin/manage/centralized-deployment-of-add-ins.md).

- Administratörer måste vara medlemmar i roll gruppen globala administratörer. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-message-add-in-for-yourself"></a>Hämta tillägget för rapport meddelanden åt dig själv

1. Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och Sök efter rapport meddelande tillägget. Om du vill gå direkt till tillägget rapport, går du till <https://appsource.microsoft.com/product/office/wa104381180> .

2. Klicka på **Skaffa det nu**.

   ![Rapport meddelande – skaffa det nu](../../media/ReportMessageGETITNOW.png)

3. Kontrol lera användnings villkoren och sekretess policyn i dialog rutan som visas och klicka sedan på **Fortsätt**.

4. Logga in med ditt arbets-eller skol konto (för företag) eller ditt Microsoft-konto (för personligt bruk).

När tillägget har installerats och Aktiver ATS ser du följande ikoner:

- Ikonen ser ut så här i Outlook:

  ![Ikonen rapportera meddelande-tillägg för Outlook](../../media/OutlookReportMessageIcon.png)

- I Outlook på webben ser ikonen ut så här:

  ![Ikonen för att lägga till en Outlook-ikon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Information om hur du använder tillägget finns i [använda tillägget rapportera meddelanden](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Hämta och aktivera tillägget rapportera meddelande till din organisation

> [!NOTE]
> Det kan ta upp till 12 timmar innan tillägget visas i din organisation.

1. Gå till sidan **Inställningar** för tillägg i administrations centret för Microsoft 365, \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> om du inte kan se **tilläggs** sidan går du till länken **Inställningar** för \> **integrerade appar** \>  i den övre delen av sidan **integrerade program** .

2. Välj **distribuera tillägg** högst upp på sidan och välj sedan **Nästa**.

   ![Sidan tjänster och tillägg i administrations centret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. I **distribuera en ny** utfällbar tillägg som visas läser du informationen och klickar sedan på **Nästa**.

4. På nästa sida klickar du på **Välj från butiken**.

   ![Distribuera en ny tilläggs sida](../../media/NewAddInScreen2.png)

5. Klicka i **sökrutan på** sidan **Välj tillägg** som visas, ange **rapport meddelande** och klicka sedan på ikonen **Sök** sökning ![ ](../../media/search-icon.png) . Sök efter **rapport meddelande** i listan med resultat och klicka sedan på **Lägg till**.

   ![Välja Sök Resultat för tillägg](../../media/NewAddInScreen3.png)

6. I dialog rutan som visas granskar du licensierings-och integritets informationen och klickar sedan på **Fortsätt**.

7. På sidan **Konfigurera tillägg** som visas konfigurerar du följande inställningar:

   - **Tilldelade användare**: Välj något av följande värden:

     - **Alla** (standard)
     - **Specifika användare/grupper**
     - **Bara jag**

   - **Distributions metod**: Välj något av följande värden:

     - **Åtgärdat (standard)**: tillägget distribueras automatiskt till de angivna användarna och de kan inte tas bort.
     - **Tillgängligt**: användarna kan installera **tillägget via** \> **Skaffa** tillägg som \> **hanteras av administratören**.
     - **Valfritt**: tillägget distribueras automatiskt till angivna användare, men de kan välja att ta bort det.

   ![Konfigurera tilläggs Sidan](../../media/configure-add-in.png)

   När du är klar klickar du på **distribuera**.

8. På sidan **distribuera rapport meddelanden** som visas visas en status rapport följt av en bekräftelse på att tillägget distribuerades. När du har läst informationen klickar du på **Nästa**.

   ![Distribuera rapport meddelande sidan](../../media/deploy-report-message-page.png)

9. På sidan om meddelande **tillägget** som visas granskar du informationen och klickar sedan på **Stäng**.

   ![Sidan meddelande om tillägg](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Lär dig hur du använder tillägget rapport

Personer som har tillägget tilldelat kommer att se följande ikoner:

- Ikonen ser ut så här i Outlook:

  ![Ikonen rapportera meddelande-tillägg för Outlook](../../media/OutlookReportMessageIcon.png)

- I Outlook på webben ser ikonen ut så här:

  ![Ikonen för att lägga till en Outlook-ikon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

När du meddelar användare om tillägget för rapport meddelanden infogar du en länk där du kan [använda tillägget rapport](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Granska eller redigera inställningar för rapport tillägget

1. Gå till sidan **Inställningar** för tillägg i administrations centret för Microsoft 365, \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> om du inte kan se **tilläggs** sidan går du till länken **Inställningar** för \> **integrerade appar** \>  i den övre delen av sidan **integrerade program** .

   ![Tjänster och Add-Ins sida i det nya administrations centret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Hitta och välj tillägget **rapportera meddelanden** .

3. I **Redigera rapport** utfällning som visas granskar och redigerar du inställningar för din organisation. Klicka på **Spara** när du är klar.

   ![Inställningar för tillägget rapport meddelande](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Visa och granska rapporterade meddelanden

Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:

- Använd portalen administrations underställda. Mer information finns i [Visa användar inlämningar till Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Skapa en regel för e-postflöde (kallas även transport regel) för att skicka kopior av rapporterade meddelanden. Anvisningar finns i [använda e-postflödes regler för att se vad användarna rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
