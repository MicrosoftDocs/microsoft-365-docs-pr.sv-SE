---
title: Anpassa Office 365-temat för din organisation
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
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
description: 'Lär dig att ändra standardtemat i Office 365 och anpassa det så att det matchar företagets logotyp eller färg. '
ms.openlocfilehash: c553e5254246bd81d435b4ebc2be2e975dd80a9d
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826338"
---
# <a name="customize-the-office-365-theme-for-your-organization"></a>Anpassa Office 365-temat för din organisation

Läs om hur du anpassar temat i administrationscentret för Microsoft 365. Som administratör för Office 365 för företag-prenumerationen kan du ändra standardtemat som visas i det övre navigationsfältet och som alla i organisationen ser. Du kan lägga till företagets logotyp och ändra färgerna så att de matchar resten av ditt varumärke. Du kan till och med lägga till en mållänk som användarna kan navigera till när de väljer din logotyp. Här kan du se resultatet av standardtemat och det anpassade temat i Office 365.
  
![Default Office 365 theme and Custom Office 365 theme](../../media/e2cbc922-b424-4683-8c5c-fdbcbd0ce844.png)
  
## <a name="customize-your-theme-in-the-admin-center"></a>Anpassa temat i administrationscentret

1. I administrationscentret går du till \> **inställningsinställningarna**och väljer sedan fliken **Organisationsprofil.** **Settings**

2. Välj **Anpassade teman**på fliken **Organisationsprofil.**

3. Ändra de temaelement du vill använda för din organisation på panelen **Tullteman:**
    
    - **Använd en anpassad logotypbild:** Välj om du vill använda en bild från en WEBBADRESS eller ladda upp en bild. Om du använder en URL, se till att webbadressen använder HTTPS och är 200 x 30 pixlar av alla format av valfri storlek. Du kan ladda upp en logotyp under 10 KK som är 200 x 30 pixlar i JPG-, PNG-, GIF- eller SVG-format.

      > [!NOTE]
      > Om logotypen ska visas i SharePoint-mobilappen använder du bara SVG-bilder. Bilder som laddas upp i något annat format visas inte i appen. Logotyper kan inte klickas i SharePoint Mobile-appen.

    - **Gör logotypen klickbar:** Du kan använda logotypen i navigeringsfältet som en länk till alla företagsresurser. Du kan ange webbadressen för logotypen här, med början http:// eller https://. Det här är valfritt.

    - **Välj bakgrundsbild:** Välj bilden och ladda upp din egen JPG, PNG eller GIF med en upplösning på 1366 x 50 pixlar, inte större än 15 kB. Bakgrundsbilden visas i det övre navigeringsfältet på varje sida.

      > [!NOTE]
      > Bilder som innehåller text visas kanske inte som förväntat. Fördefinierade element som visas på vänster och höger sida i navigeringsfältet kan variera mellan de olika tjänsterna och texten kan döljas bakom elementen. Navigeringsfältets dynamik gör så att vi i nuläget inte kan ge vägledning för utfyllnad för som ger en enhetlig upplevelse. 

    - **Navigeringsfältfärg:** Välj en färg som ska användas för navigeringsfältets bakgrund. Det visas längst upp på varje sida.

    - **Text and ikoner**: Välj en färg som ska användas för text och ikoner i det övre navigeringsfältet.

    - **Accentfärg:** Välj en färg som ska användas för att hovra färg och sidaccenter med navigeringsfältet som knappar och text i vissa program.

     - **Förhindra att användare åsidosätter temat**: Vänd den här växlingsknappen för att förhindra att användarna väljer sitt eget tema från vårt temaval. Detta hindrar inte användare från att kunna ställa in ett tema med hög kontrast.

    - **Visa användarnamnet**: Välj om du vill visa en användares fullständiga namn vid startpunkten till kontohanteraren längst upp till höger på sidan när användaren är inloggad. Som standard ser användarna sitt foto eller sina initialer om ett foto inte har laddats upp.
    
4. Välj **Spara ändringar**.
    
Du ser det nya temat i administrationscentret direkt och efter en kort fördröjning ser du det i hela Office 365, inklusive sidor i Outlook, SharePoint, [SharePoint-mobilapp för iOS](https://support.office.com/en-us/article/SharePoint-mobile-app-for-iOS-339402ce-16bb-4c97-9475-0c5375ccef7a)och [SharePoint-mobilapp för Android](https://support.office.com/en-us/article/SharePoint-mobile-app-for-Android-d875654b-fb0a-4dbe-a17a-a676cf936284). Se följande bild för ett exempel på var du ett anpassat temaändringar från administrationscentret.

![m365-admin-tenant-tema-konceptuella](../../media/m365-admin-tenant-theme-conceptual.png)

Du kan ta bort den anpassade ikonen eller de anpassade färgerna när som helst. Gå bara tillbaka till temasidan och välj **Ta bort anpassade teman**.
  
## <a name="best-practices"></a>Metodtips

När du väljer en **logotypbild**rekommenderar vi att du använder en SVG-filtyp, där så är möjligt, så att din logotyp får ett högupplöst utseende på alla skärmar och på alla zoomnivåer.

När du väljer anpassade färger väljer du en bakgrundsfärg i **Nav-fältet** som har ett högt kontrastförhållande med **logotypbilden** som du valde. Välj också en färg för **text och ikoner** med ett högt kontrastförhållande till **Nav-stångens bakgrundsfärg** för att säkerställa att all text och alla ikoner är väl synliga.

Välj en **accentfärg** som syns bra mot en vit eller ljus bakgrund när du väljer anpassade färger. **Accentfärgen** används som färg på vissa länkar och knappar som visas mot en vit eller ljus bakgrund. **Accent-färgen** används till exempel för att färga element i en användares inkorg och på deras Office.com portalsida. 
  
Det rekommenderade kontrastförhållandet för text, ikon eller knappfärg och bakgrundsfärg är 4,5:1.

Här är ett enkelt flödesschema som hjälper dig att snabbt konfigurera med ett visuellt tilltalande anpassat Office 365-tema för din organisation:
  - Jag skulle vilja använda en färgstark version av vår logotyp.
    - Vi rekommenderar följande inställningar:
      - **Logotypbild:** Organisationens färgglada logotyp.
      - **Navigeringsfält färg:** en neutral färg. Vi rekommenderar #FAF9F7 för en ljus färg och #252423 för en mörk färg.
      - **Text- och ikonfärg:** En färg som kontrasterar färg i **navigeringsfältet**. Vi rekommenderar #FAF9F7 för en ljus färg och #252423 för en mörk färg.
      - **Accent färg:** en mörk varumärke färg. Med vissa program måste den här färgen vara synlig på en ljusbakgrund.
  - Jag skulle vilja använda en neutral version av vår logotyp och representera färg i navigeringsfältet.
    - Vi rekommenderar följande inställningar:
      - **Logotypbild**: Organisationens neutrala logotyp.
      - **Navigeringsfältfärg:** En varumärkesfärg som kontrasterar mot din logotyp.
      - **Text- och ikonfärg:** Välj en färg som kontrasterar mot den varumärkesfärg du valde för **navigeringsfältets färg.** Vi rekommenderar #252423 för en mörk färg och #FAF9F7 för en ljus färg.
      - **Accent färg:** en mörk varumärke färg. Med vissa program måste den här färgen vara synlig på en ljusbakgrund.
  
## <a name="related-articles"></a>Relaterade artiklar

[Lägga till anpassade paneler på sidan Mina program och startprogram](../manage/customize-the-app-launcher.md)
  
  

