---
title: 'Kommer snart: Konfigurera SharePoint som en källa för utbildningsinnehåll för Microsoft Viva Learning (förhandsversion)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Lär dig hur du SharePoint som innehållskälla för utbildning för Microsoft Viva Learning (förhandsversion).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fc702f57b75b78ab523226ba7d8a8eb6505f2975
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244143"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a>Kommer snart: Konfigurera SharePoint som en källa för utbildningsinnehåll för Microsoft Viva Learning (förhandsversion)

> [!NOTE]
> Informationen i den här artikeln gäller en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk. 

Du kan konfigurera SharePoint som en källa för utbildningsinnehåll för att göra organisationens eget innehåll tillgängligt i Viva Learning (förhandsversion).

## <a name="overview"></a>Översikt

Kunskapsadministratören (eller global administratör) tillhandahåller en webbplats-URL till där utbildningstjänsten kan skapa en tom centraliserad plats – lagringsplatsen för innehåll i utbildningsappen – i form av en strukturerad SharePoint lista. Den här listan kan användas av din organisation för att hålla länkar till företagsbaserade SharePoint som innehåller utbildningsinnehåll. Administratörer ansvarar för att samla in och administrera en lista med URL:er för mappar. De här mapparna bör endast innehålla innehåll som kan göras tillgängligt i Viva Learning (förhandsversion).

Viva Learning (förhandsversion) har stöd för följande dokumenttyper:

- Word, PowerPoint, Excel PDF
- Ljud (.m4a)
- Video (.mov, .mp4, .avi)

Mer information finns i [SharePoint begränsningar](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498). 

## <a name="permissions"></a>Behörigheter

URL-adresser för dokumentbiblioteksmappar kan samlas in från SharePoint webbplats i organisationen. Viva Learning (förhandsversion) följer alla befintliga innehållsbehörigheter. Därför är endast innehåll där en användare har behörighet att komma åt sökbart och synligt i Viva Learning (förhandsversion). Allt innehåll i de här mapparna är sökbart, men endast innehåll som de enskilda anställda har behörighet till kan användas.

Borttagning av innehåll från organisationens lagringsplats stöds inte för närvarande.

Gör så här om du vill ta bort innehåll som inte fick visas av dig:

1.  Om du vill begränsa åtkomsten till dokumentbiblioteket **väljer du alternativet Visa** åtgärder och sedan Hantera **åtkomst.**
     
     ![Dokumentbibliotekssidan i SharePoint visar alternativet Visa åtgärder med Hantera åtkomst högtryckt.](../media/learning/learning-sharepoint-permissions2.png)

2.  Ta bort det ursprungliga dokumentet i dokumentbiblioteket.

Mer information finns i [Delning och behörigheter i den SharePoint moderna upplevelsen.](/sharepoint/modern-experience-sharing-permissions) 

## <a name="learning-service"></a>Utbildningstjänst

Tjänsten utbildning använder de angivna mapp-URL:erna för att hämta metadata från allt innehåll som lagras i de mapparna. Inom 24 timmar efter att mapp-URL:en har levererats på den centrala lagringsplatsen kan anställda söka efter och använda organisationens innehåll i Viva Learning (förhandsversion). Alla ändringar av innehåll, inklusive uppdaterade metadata och behörigheter, kommer också att tillämpas i utbildningstjänsten inom 24 timmar.

## <a name="configure-sharepoint-as-a-source"></a>Konfigurera SharePoint som en källa

Du måste vara global Microsoft 365, administratör SharePoint eller kunskapsadministratör för att kunna utföra de här uppgifterna.

Följ de SharePoint om du vill konfigurera SharePoint informationskällor för utbildningsinnehåll i för Viva Learning (förhandsversion):

1.  I det vänstra navigeringsfältet i Microsoft 365 administrationscenter går du **till Inställningar**  >  **Organisationsinställningar.**
 
2.  Välj  **Viva Learning (förhandsversion)** **på** fliken Tjänster på sidan Organisationsinställningar.

     ![Inställningar på sidan Microsoft 365 administrationscenter som visar Viva Learning.](../media/learning/learning-sharepoint-configure1.png)

3.  På panelen **Viva Learning (förhandsversion)** under SharePoint hittar du webbplats-URL:en till den SharePoint-webbplats där du vill att Viva Learning (förhandsversion) ska skapa en central lagringsplats.

     ![Utbildningspanelen i administrationscentret Microsoft 365 som visar SharePoint markerat.](../media/learning/learning-sharepoint-configure2.png)

4.  En SharePoint skapas automatiskt på den angivna SharePoint webbplatsen.

     ![Nyligen SharePoint lista SharePoint webbplatsen.](../media/learning/learning-sharepoint-configure3.png)

     I det vänstra navigeringsfältet på SharePoint väljer du **Lagringsplats för**  >  **utbildningsappens innehåll för webbplatsinnehåll.** 

     ![SharePoint över navigeringen för webbplatsinnehåll och lagringsplatsen för utbildningsappens innehåll.](../media/learning/learning-sharepoint-configure4.png) 

5. På sidan **Lagringsplats för innehåll i** utbildningsappar fyller du i SharePoint med WEBBADRESSer till mapparna med utbildningsinnehåll.

   1. Välj **Ny** för att visa **panelen Nytt** objekt. 

       ![Sidan Lagring för utbildningsinnehåll i SharePoint med alternativet Nytt.](../media/learning/learning-sharepoint-configure5.png)
 
   2. På panelen **Nytt objekt** går du till **fältet Rubrik** och lägger till ett valfri katalognamn. Lägg till **URL:en** till mappen utbildningsinnehåll i fältet Mapp-URL. Välj **Spara**.

       ![Panelen Nytt objekt i SharePoint med fälten Rubrik och Mapp-URL.](../media/learning/learning-sharepoint-configure6.png)

   3. Sidan **lagringsplats för innehåll i utbildningsappen** uppdateras med det nya utbildningsinnehållet.

       ![Sidan Lagringsplats för utbildningsinnehåll i SharePoint visar den uppdaterade informationen.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> För att ge bredare åtkomst till lagringsplatsen för innehåll i utbildningsappen kommer en länk till listan snart att finnas i gränssnittet för Viva Learning (förhandsversion) där användare kan begära åtkomst och få hjälp med att fylla på listan. Webbplatsägare och globala administratörer måste bevilja åtkomst till listan. Access är bara specifikt för listan och gäller inte för webbplatsen där listan lagras. Mer information finns i [Artikeln om att tillhandahålla organisationens innehåll](#provide-your-own-organizations-content) längre fram i den här artikeln.

### <a name="folder-url-document-library-curation"></a>Dokumentbiblioteks curation för mapp-URL

Standardmetadata (t.ex. ändringsdatum, skapat av, dokumentnamn, innehållstyp och organisationsnamn) hämtas automatiskt till Viva Learning (förhandsversion) av Microsoft Graph API.
 
För att förbättra den övergripande identifieringen och sökrelevansen för innehållet rekommenderar vi att du lägger till **en beskrivningskolumn.**

Så här lägger **du** till en beskrivningskolumn på dokumentbibliotekssidan:

1.  På sidan **Dokument** väljer du Lägg **till kolumn**.

2. Välj **alternativet Visa** åtgärder och välj sedan **Enskild rad med text.**

     ![Dokumentsidan i SharePoint visar alternativen Visa åtgärder med Enskild rad med text markerad.](../media/learning/learning-sharepoint-curation1.png)

3. Lägg **till ett beskrivande** namn för **kolumnen i fältet** Namn på panelen Skapa en kolumn. Välj **Spara**.

     ![Skapa en kolumnpanel i SharePoint visar Namn och andra fält.](../media/learning/learning-sharepoint-curation2.png)
 
4. Lägg **till anpassade** beskrivningar för **varje objekt** i kolumnen Beskrivning på sidan Dokument. Om ingen beskrivning anges kommer Viva Learning (förhandsversion) att tillhandahålla ett standardmeddelande som markerar innehållet som att det kommer från ditt SharePoint bibliotek. 

     ![Dokumentsidan i SharePoint beskrivningarna i kolumnen Beskrivning.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a>Tillhandahålla innehållet för din egen organisation

Kunskapsadministratörer kan komma åt organisationens lagringsplats för innehåll i utbildningsappen i SharePoint, där de kan hänvisa till dokumentbibliotek mellan olika organisationer. Innehåll i de här biblioteken visas sedan som utbildningsinnehåll i Viva Learning (förhandsversion).

1. I Viva Learning (förhandsversion) väljer **du Fler alternativ** (**...**) och väljer **sedan Inställningar**.

     ![SharePoint visar fler alternativ och alternativ Inställningar bibliotekssidan.](../media/learning/learning-sharepoint-library-1.png)
     
2. Under **Inställningar** väljer du **Behörigheter**.

     ![Inställningar alternativsidan i SharePoint med alternativen Behörigheter och Kontrollera åtkomst.](../media/learning/learning-sharepoint-library-2.png)

3. Välj **Kontrollera åtkomst** för att ansluta till organisationens centrala bibliotek.
     
