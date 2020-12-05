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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: 'Lär dig hur du ändrar standard temat i Microsoft 365 och anpassa det så att det stämmer överens med företagets logo typ eller färg. '
ms.openlocfilehash: 7392ea43c32635a9852b0fbceed80475d99c9d64
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580691"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>Anpassa Microsoft 365-temat för din organisation

Som administratör för Microsoft 365 för företag-prenumerationen kan du ändra standard temat som visas i det övre navigerings fältet för alla i organisationen:

- Lägg till företagets logo typ.
- Ändra färgerna så att de stämmer överens med resten av varumärket.
- Lägg till mål länka användare när de väljer din logo typ.
  
## <a name="customize-your-theme-in-the-admin-center"></a>Anpassa ditt tema i administrations centret

1. I administrations centret går du till sidan **Inställningar** \> **organisations inställningar** och väljer sedan fliken **organisations profil** .

2. Välj **anpassade teman** på fliken **organisations profil** .

3. På panelen **tull teman** ändrar du de tema element du vill använda för organisationen:

    - **Använda en egen logo typ bild**: Välj om du vill använda en bild från en URL-adress eller ladda upp en bild. Om du använder en URL-adress kontrollerar du att URL-adressen använder HTTPS och att bilden är 200 x 30 bild punkter i valfri storlek. Du kan ladda upp en logo typ under 10 KB som är 200 x 30 pixlar i JPG-, PNG-, GIF-eller SVG-format.

      > [!NOTE]
      > Använd endast SVG-bilder för att logo typen ska visas i SharePoint-mobilappen. Bilder som laddas upp i andra format visas inte i programmet. Logo typer går inte att klicka på i SharePoint-mobilappen.

    - **Gör logo typen lätt att klicka på**: du kan använda logo typen i navigerings fältet som en länk till en företags resurs. Du kan ange URL-adressen för logo typen här, från http://eller https://. Det här är valfritt.

    - **Välj bakgrunds bild**: Markera bilden och ladda upp din egen jpg, PNG eller GIF med en upplösning på 1366 x 50 pixlar, inte större än 15 KB. Bakgrundsbilden visas i det övre navigeringsfältet på varje sida.

      > [!NOTE]
      > Bilder som innehåller text kanske inte visas som förväntat. De inbyggda elementen som visas till höger och vänster sida i navigerings fältet kan variera mellan olika tjänster och texten kanske inte är dold.

    - **Navigerings fälts färg**: Välj en färg som ska användas för bakgrunden i navigerings fältet. Navigerings fältet visas högst upp på varje sida.

    - **Text and ikoner**: Välj en färg som ska användas för text och ikoner i det övre navigeringsfältet.

    - **Accentfärg**: Välj en färg som ska användas i navigerings fältets hov rings färg och sidor som knappar och text i vissa program.

    - **Hindra användare från att åsidosätta tema**: växla den här växlings knappen för att förhindra att användare väljer ett eget tema från vår tema markering. Detta förhindrar inte att användare kan ange ett tema med hög kontrast.

    - **Visa användar namn**: Välj om du vill visa en användares fullständiga namn vid start punkten till konto hanteraren längst upp till höger på sidan när användaren är inloggad. Som standard ser användarna deras bild eller deras initialer om inget foto har laddats upp.

4. Välj **Spara ändringar**.

Du kan se det nya temat i administrations centret direkt. Efter en kort fördröjning kan du se den i Microsoft 365, inklusive på sidor i Outlook, SharePoint, [SharePoint-mobilapp för iOS](https://support.microsoft.com/office/339402ce-16bb-4c97-9475-0c5375ccef7a)och SharePoint- [mobilapp för Android](https://support.microsoft.com/office/d875654b-fb0a-4dbe-a17a-a676cf936284).

Du kan ta bort den anpassade ikonen eller de anpassade färgerna när som helst. Gå tillbaka till sidan tema och välj **ta bort anpassade**.
  
## <a name="best-practices"></a>Metodtips

- **Logo** typ: Använd en SVG-filtyp så att din logo typ visas med hög upplösning på alla skärmar och på alla zoomnings nivåer.

- **Anpassade färger**: Välj en **bakgrunds färg för navigerings fältet** med ett högt kontrast förhållande med **logo typ bilden** du valde. Välj färg för **text och ikoner** med hög kontrast förhållande till **navigerings fältets bakgrunds färg** så att all text och alla ikoner syns tydligt.

- **Accentfärg**: Välj en som visas på en vit eller ljus bakgrund. Accentfärg används för att färglägga länkar och knappar som visas på en vit eller ljus bakgrund. Accentfärg används till exempel för att färglägga element i en användares inkorg och på deras Office.com-portal.
  
- **Kontrast förhållande**: det rekommenderade kontrast förhållandet mellan text, ikon eller knapp färg och bakgrunds färg är 4,5:1.
  
## <a name="related-articles"></a>Relaterade artiklar

[Lägga till anpassade paneler på sidan Mina program och startprogram](../manage/customize-the-app-launcher.md)