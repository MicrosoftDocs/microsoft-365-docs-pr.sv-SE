---
title: Aktivera tilläggsprogrammet rapportera Phish
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
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
description: Lär dig hur du aktiverar tillägget för rapport-nätfiske för Outlook och Outlook på webben, för enskilda användare eller hela organisationen.
ms.openlocfilehash: 2ea6a9bf9b00fc844aede6daeb9fc11f23c81e4a
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865288"
---
# <a name="enable-the-report-phishing-add-in"></a>Aktivera tillägget rapportera nät fiske

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för säkerhets & efterlevnad. Mer information finns i [använda administratörs överföring för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft](admin-submission.md).

Med tilläggen rapportera meddelande och rapportera nät fiske funktioner för Outlook och Outlook på webben (tidigare Outlook Web App) kan andra personer enkelt rapportera falsk identifiering (god e-post som är markerad som dålig) eller falsk negativ (dålig e-post) till Microsoft och dess dotter bolag för analys.

Microsoft använder dessa inlämningar för att förbättra effektiviteten hos e-postskydd. Antag till exempel att personer rapporterar många meddelanden med hjälp av tillägget för rapport nät. De här informations ytorna i [säkerhets instrument panelen](security-dashboard.md) och andra rapporter. Din organisations säkerhets team kan använda den här informationen som en indikation på att mot nätfiske-principer kan behöva uppdateras.

Du kan installera ett tilläggsprogram för rapport-eller rapport nät. Om du vill att användarna ska kunna rapportera både skräp post och nät fiske meddelanden kan du distribuera tillägget rapportera meddelanden i organisationen. Mer information finns i [aktivera tillägget rapportera meddelanden](enable-the-report-message-add-in.md).

Tillägget rapport nätfiske tillhandahåller alternativet att endast rapportera nät fiske meddelanden. Administratörer kan aktivera tillägget Rapportera nätfiske för organisationer och enskilda användare kan installera det själva.

Om du är en enskild användare kan du [aktivera tillägget rapportera nät fiske för dig själv](#get-the-report-phishing-add-in-for-yourself).

Om du är global administratör eller Exchange Online-administratör och Exchange är konfigurerat för att använda OAuth-autentisering kan du [aktivera tillägget Rapportera nätfiske för din organisation](#get-and-enable-the-report-phishing-add-in-for-your-organization). Nät fiske Add-In är nu tillgängligt via [centraliserad distribution](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Tillägget rapport nät fiske fungerar med de flesta Microsoft 365-abonnemang och följande produkter:

  - Outlook på webben
  - Outlook 2013 SP1 eller senare
  - Outlook 2016 för Mac
  - Outlook ingår i Microsoft 365-appar för företag

- Tillägget rapport nätfiske är inte tillgängligt för post lådor i lokala Exchange-organisationer.

- Du kan konfigurera vilka meddelanden som ska kopieras eller dirigeras om till en post låda som du anger. Mer information finns i [principer för användar profiler](user-submission.md).

- Din befintliga webbläsare bör fungera med tillägget rapportera nät fiske. Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.

- För organisatoriska installationer måste organisationen konfigureras för att använda OAuth-autentisering. Mer information finns i [avgöra om centraliserad distribution av tillägg fungerar för din organisation](../../admin/manage/centralized-deployment-of-add-ins.md).

- Administratörer måste vara medlemmar i roll gruppen globala administratörer. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-phishing-add-in-for-yourself"></a>Hämta tillägget rapport nät fiske för dig själv

1. Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och Sök efter tillägget för rapport nätfiske.

2. Klicka på **Skaffa det nu**.

3. Kontrol lera användnings villkoren och sekretess policyn i dialog rutan som visas och klicka sedan på **Fortsätt**.

4. Logga in med ditt arbets-eller skol konto (för företag) eller ditt Microsoft-konto (för personligt bruk).

När tillägget har installerats och Aktiver ATS ser du följande ikoner:

- Ikonen ser ut så här i Outlook:

  ![Ikonen rapportera tilläggsprogram för nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- I Outlook på webben ser ikonen ut så här:

  ![Ikonen nät fiske tillägg för Outlook på webb sidan](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>Hämta och aktivera tillägget Rapportera nätfiske för din organisation

> [!NOTE]
> Det kan ta upp till 12 timmar innan tillägget visas i din organisation.

1. I administrations centret för Microsoft 365 går du till sidan **Inställningar, integrerade appar & tillägg** på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> och klickar sedan på **distribuera tillägg**.

   ![Sidan tjänster och tillägg i administrations centret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. I **distribuera en ny** utfällbar tillägg som visas läser du informationen och klickar sedan på **Nästa**.

3. På nästa sida klickar du på **Välj från butiken**.

   ![Distribuera en ny tilläggs sida](../../media/NewAddInScreen2.png)

4. Klicka i **sökrutan på** sidan **Välj tillägg** som visas, ange **rapport nätfiske** och klicka sedan på ikonen **Sök** ![ sökning ](../../media/search-icon.png) . Sök efter **rapport nätfiske** i resultat listan och klicka sedan på **Lägg till**.

5. I dialog rutan som visas granskar du licensierings-och integritets informationen och klickar sedan på **Fortsätt**.

6. På sidan **Konfigurera tillägg** som visas konfigurerar du följande inställningar:

   - **Tilldelade användare**: Välj något av följande värden:

     - **Alla** (standard)
     - **Specifika användare/grupper**
     - **Bara jag**

   - **Distributions metod**: Välj något av följande värden:

     - **Åtgärdat (standard)**: tillägget distribueras automatiskt till de angivna användarna och de kan inte tas bort.
     - **Tillgängligt**: användarna kan installera **tillägget via** \> **Skaffa** tillägg som \> **hanteras av administratören**.
     - **Valfritt**: tillägget distribueras automatiskt till angivna användare, men de kan välja att ta bort det.

   När du är klar klickar du på **distribuera**.

7. I sidan **distribuera rapport nät fiske** som visas visas en status rapport följt av en bekräftelse på att tillägget distribuerades. När du har läst informationen klickar du på **Nästa**.

8. På sidan om meddelande **tillägget** som visas granskar du informationen och klickar sedan på **Stäng**.

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Lär dig hur du använder tillägget rapportera nät fiske

Personer som har tillägget tilldelat kommer att se följande ikoner:

- Ikonen ser ut så här i Outlook:

  ![Ikonen rapportera tilläggsprogram för nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- I Outlook på webben ser ikonen ut så här:

  ![Ikonen nät fiske tillägg för Outlook på webb sidan](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Granska eller redigera inställningar för tillägget rapportera nät fiske

1. Gå till sidan **tjänster & tillägg** i administrations centret för Microsoft 365 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .

2. Sök reda på och välj tillägget **rapportera nät fiske** .

3. I **Redigera rapport nät fiske** som visas, granskar och redigerar du inställningar för din organisation. Klicka på **Spara** när du är klar.

## <a name="view-and-review-reported-messages"></a>Visa och granska rapporterade meddelanden

Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:

- Använd portalen administrations underställda. Mer information finns i [Visa användar inlämningar till Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Skapa en regel för e-postflöde (kallas även transport regel) för att skicka kopior av rapporterade meddelanden. Anvisningar finns i [använda e-postflödes regler för att se vad användarna rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).