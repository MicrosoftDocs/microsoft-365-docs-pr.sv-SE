---
title: Anpassa temat för din organisation
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: 'Lär dig hur du ändrar standardtemat för Microsoft 365 och anpassar det så att det matchar ditt företags logotyp eller färg. '
ms.openlocfilehash: 9d17ac800fb0fe38627fcb7842ed5555d2ac28ae
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926888"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>Anpassa Microsoft 365-temat för din organisation

Som administratör för Microsoft 365 för företag-prenumerationen kan du ändra standardtemat som visas i det övre navigeringsfältet för alla i organisationen:

- Lägg till företagets logotyp.
- Ändra färgerna så att de matchar resten av ditt varumärke.
- Lägg till en mållänk som användare går när de väljer din logotyp.
  
## <a name="customize-your-theme-in-the-admin-center"></a>Anpassa temat i administrationscentret

1. Gå till sidan Inställningar för organisationens **inställningar** \> **i** administrationscentret och välj sedan **fliken Organisationsprofil.**

2. Välj **Anpassade teman på** fliken **Organisationsprofil.**

3. Ändra **temaelementen som** du vill använda för din organisation på panelen tullteman:

    - **Använd en anpassad logotypbild:** Välj om du vill använda en bild från en URL eller ladda upp en bild. Om du använder en URL kontrollerar du att URL-adressen använder HTTPS och att bilden är 200 x 30 bildpunkter i alla format av alla storlekar. Du kan ladda upp en logotyp under 10 kB som är 200 x 30 bildpunkter i JPG-, PNG-, GIF- eller SVG-format.

      > [!NOTE]
      > För att logotypen ska visas i SharePoint-mobilappen ska du bara använda SVG-bilder. Bilder som laddats upp i något annat format visas inte i appen. Logotyper går inte att klicka på i SharePoint Mobile-appen.

    - **Gör logotypen klickbar:** Du kan använda din logotyp i navigeringsfältet som en länk till en företagsresurs. Här kan du ange URL-adressen för logotypen, som börjar http:// eller https://. Det här är valfritt.

    - **Välj bakgrundsbild:** Markera bilden och ladda upp en egen JPG-, PNG- eller GIF-fil med en upplösning på 1366 x 50 bildpunkter och inte större än 15 KB. Bakgrundsbilden visas i det övre navigeringsfältet på varje sida.

      > [!NOTE]
      > Bilder som innehåller text kanske inte visas som förväntat. Inbyggda element som visas på höger och vänster sida i navigeringsfältet kan variera mellan olika tjänster och texten kan döljas vid dessa element.

    - **Navigeringsfältsfärg:** Välj en färg som ska användas som bakgrund i navigeringsfältet. Navigeringsfältet visas högst upp på varje sida.

    - **Text and ikoner**: Välj en färg som ska användas för text och ikoner i det övre navigeringsfältet.

    - **Accentfärg:** Välj en färg som du vill använda för hovringsfärgen i navigeringsfältet och sidaccent som knappar och text i vissa program.

    - **Hindra användare från att åsidosätta teman:** Vänd den här växlingsknappen för att hindra användare från att välja ett eget tema från vårt temaval. Det hindrar inte användare från att ange ett högkontrasttema.

    - **Visa användarnamnet:** Välj om du vill visa en användares fullständiga namn vid startpunkten för kontohanteraren längst upp till höger på sidan när användaren är inloggad. Standardinställningen är att användare ser sitt foto eller sina initialer, om inget foto har laddats upp.

4. Välj **Spara ändringar**.

Du kan se det nya temat i administrationscentret direkt. Efter en kort fördröjning kan du se den i hela Microsoft 365, inklusive på sidor i Outlook, SharePoint, [SharePoint-mobilappen](https://support.microsoft.com/office/339402ce-16bb-4c97-9475-0c5375ccef7a)för iOS och [SharePoint-mobilappen](https://support.microsoft.com/office/d875654b-fb0a-4dbe-a17a-a676cf936284)för Android.

Du kan ta bort den anpassade ikonen eller de anpassade färgerna när som helst. Gå bara tillbaka till temasidan och välj **Ta bort anpassade teman.**
  
## <a name="best-practices"></a>Metodtips

- **Logotypbild:** Använd en SVG-filtyp så att logotypen visas med hög upplösning på alla skärmar och på alla zoomnivåer.

- **Anpassade färger:** Välj en **bakgrundsfärg i navigeringslisten** med ett högkontrastförhållande med **den logotypbild** som du valde. Välj en **färg för text och** ikoner  med hög kontrast till bakgrundsfärgen i navigeringslisten så att all text och alla ikoner syns tydligt.

- **Accentfärg:** Välj en färg som syns bra mot en vit eller ljus bakgrund. Accentfärgen används för att färglägga vissa länkar och knappar som visas på en vit eller ljus bakgrund. Accentfärgen används till exempel för att färglägga element i en användares inkorg och på deras Office.com portalsida.
  
- **Kontrastförhållande:** Det rekommenderade kontrastförhållandet mellan text, ikon eller knappfärg och bakgrundsfärg är 4,5:1.
  
## <a name="related-articles"></a>Relaterade artiklar

[Lägga till anpassade paneler på sidan Mina program och startprogram](../manage/customize-the-app-launcher.md)