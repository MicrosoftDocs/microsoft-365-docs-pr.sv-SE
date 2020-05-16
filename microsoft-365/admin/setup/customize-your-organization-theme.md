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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: 'Lär dig att ändra standardtemat i Microsoft 365 och anpassa det så att det matchar företagets logotyp eller färg. '
ms.openlocfilehash: 3674c26be50d622364a4dc077a85eaa974d71fcd
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262335"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>Anpassa Microsoft 365-temat för din organisation

Läs om hur du anpassar ditt tema i administrationscentret för Microsoft 365. Som administratör för din Microsoft 365 för företag-prenumeration kan du ändra standardtemat som visas i det övre navigeringsfältet för alla i organisationen. Du kan lägga till företagets logotyp och ändra färgerna så att de matchar resten av ditt varumärke. Du kan till och med lägga till en mållänk som användarna kan navigera till när de väljer din logotyp. Här kan du se standardtemat och det anpassade temat i Microsoft 365.
  
![Standardt Microsoft 365-tema och anpassat Microsoft 365-tema](../../media/e2cbc922-b424-4683-8c5c-fdbcbd0ce844.png)
  
## <a name="customize-your-theme-in-the-admin-center"></a>Anpassa ditt tema i administrationscentret

1. Gå till inställningars organisationsprofilen i **administrationscentret** \> **Org Settings**och välj sedan fliken **Organisationsprofil.**

2. Välj **Anpassade teman**på fliken **Organisationsprofil** .

3. På panelen **Tullteman** ändrar du de temaelement du vill ha för din organisation:
    
    - **Använd en anpassad logotypbild:** Välj om du vill använda en bild från en WEBBADRESS eller ladda upp en bild. Om du använder en URL ska du se till att webbadressen använder HTTPS och är 200 x 30 pixlar av alla format av valfri storlek. Du kan ladda upp en logotyp under 10 KB som är 200 x 30 pixlar i JPG-, PNG-, GIF- eller SVG-format.

      > [!NOTE]
      > Om logotypen ska visas i SharePoint-mobilappen använder du bara SVG-bilder. Bilder som laddas upp i något annat format visas inte i appen. Logotyper kan inte klickas i SharePoint Mobile-appen.

    - **Gör logotypen klickbar:** Du kan använda din logotyp i navigeringsfältet som en länk till alla företagsresurser. Du kan ange webbadressen för logotypen här, med början http:// eller https://. Det här är valfritt.

    - **Välj bakgrundsbild:** Välj bilden och ladda upp din egen JPG, PNG eller GIF med en upplösning på 1366 x 50 pixlar, inte större än 15 KB. Bakgrundsbilden visas i det övre navigeringsfältet på varje sida.

      > [!NOTE]
      > Bilder som innehåller text visas kanske inte som förväntat. Fördefinierade element som visas på vänster och höger sida i navigeringsfältet kan variera mellan de olika tjänsterna och texten kan döljas bakom elementen. Navigeringsfältets dynamik gör så att vi i nuläget inte kan ge vägledning för utfyllnad för som ger en enhetlig upplevelse. 

    - **Navigeringsfältsfärg:** Välj en färg som ska användas för navigeringsfältets bakgrund. Det visas längst upp på varje sida.

    - **Text and ikoner**: Välj en färg som ska användas för text och ikoner i det övre navigeringsfältet.

    - **Accentfärg:** Välj en färg som ska användas för knappen hovringningsfärg och sidaccenter för navigeringsfältet, till exempel knappar och text i vissa program.

     - **Förhindra att användare åsidosätter temat:** Vänd på den här växlingsknappen för att förhindra att användarna väljer sitt eget tema från vårt temaval. Detta hindrar inte användare från att kunna ställa in ett tema med hög kontrast.

    - **Visa användarnamnet**: Välj om du vill visa en användares fullständiga namn vid startpunkten för kontohanteraren längst upp till höger på sidan när användaren är inloggad. Som standard ser användarna sitt foto eller sina initialer om ett foto inte har laddats upp.
    
4. Välj **Spara ändringar**.
    
Du ser ditt nya tema i administrationscentret direkt och efter en kort fördröjning visas det i hela Microsoft 365, inklusive sidor i Outlook, SharePoint, [SharePoint-mobilappen för iOS](https://support.office.com/article/SharePoint-mobile-app-for-iOS-339402ce-16bb-4c97-9475-0c5375ccef7a)och [SharePoint-mobilapp för Android](https://support.office.com/article/SharePoint-mobile-app-for-Android-d875654b-fb0a-4dbe-a17a-a676cf936284). Ett exempel på var du kan anpassa temaändringar från administrationscentret finns i följande bild.

![m365-admin-tenant-tema-konceptuell](../../media/m365-admin-tenant-theme-conceptual.png)

Du kan ta bort den anpassade ikonen eller de anpassade färgerna när som helst. Gå bara tillbaka till temasidan och välj **Ta bort anpassad teman**.
  
## <a name="best-practices"></a>Metodtips

När du väljer en **logotypbild**rekommenderar vi att du använder en SVG-filtyp, så att din logotyp får ett högupplöst utseende på alla skärmar och på alla zoomnivåer.

När du väljer anpassade färger väljer du en **bakgrundsfärg i navigeringsfältet** som har ett högt kontrastförhållande med den **logotypbild** som du har valt. Välj också en **text- och ikonerfärg** med ett högt kontrastförhållande till **bakgrundsfärgen i navigeringsfältet** för att säkerställa att all text och alla ikoner är väl synliga.

Välj en **accentfärg** som syns bra mot en vit eller ljus bakgrund när du väljer anpassade färger. **Accentfärgen** används som färg på vissa länkar och knappar som visas mot en vit eller ljus bakgrund. **Accentfärgen** används till exempel för att färglägga element i en användares inkorg och på deras Office.com portalsida. 
  
Det rekommenderade kontrastförhållandet för text, ikon eller knappfärg och bakgrundsfärg är 4,5:1.

Här är ett enkelt flödesschema som hjälper dig att snabbt konfigurera med ett visuellt tilltalande anpassat Microsoft 365-tema för din organisation:
  - Jag skulle vilja använda en färgstark version av vår logotyp.
    - Vi rekommenderar följande inställningar:
      - **Logotypbild**: Organisationens färgstarka logotyp.
      - **Navigeringsfält färg:** En neutral färg. Vi rekommenderar #FAF9F7 för en ljus färg och #252423 för en mörk färg.
      - **Text och ikonfärg**: En färg som **kontrasterar färgen i navigeringsfältet**. Vi rekommenderar #FAF9F7 för en ljus färg och #252423 för en mörk färg.
      - **Accent färg:** En mörk märkesfärg. Med vissa program måste den här färgen vara synlig på en ljus bakgrund.
  - Jag skulle vilja använda en neutral version av vår logotyp och representera färg i navigeringsfältet.
    - Vi rekommenderar följande inställningar:
      - **Logotypbild**: Organisationens neutrala logotyp.
      - **Navigeringsfält färg:** En varumärkesfärg som kontrasterar mot din logotyp.
      - **Text och ikonfärg:** Välj en färg som kontrasterar mot den märkesfärg du valde för **navigeringsfältets färg.** Vi rekommenderar #252423 för en mörk färg och #FAF9F7 för en ljus färg.
      - **Accent färg:** En mörk märkesfärg. Med vissa program måste den här färgen vara synlig på en ljus bakgrund.
  
## <a name="related-articles"></a>Relaterade artiklar

[Lägga till anpassade paneler på sidan Mina program och startprogram](../manage/customize-the-app-launcher.md)
  
  
