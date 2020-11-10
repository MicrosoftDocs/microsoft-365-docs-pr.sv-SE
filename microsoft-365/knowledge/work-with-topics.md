---
title: 'Arbeta med ämnen i ämnes centret (för hands version) '
description: Så här arbetar du med ämnen i ämnes centret.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 464a926b99cceeb652756ad6d1456c5e17d2a925
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988744"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a>Arbeta med ämnen i ämnes centret (för hands version)

> [!Note] 
> Innehållet i den här artikeln gäller för projekt cortex privat för hands version. [Läs mer om Project Cortex](https://aka.ms/projectcortex).


I ämnes Center kan en kunskaps chef granska ämnen som har mined och upptäckts i de SharePoint source locations som du har angett, och du kan antingen bekräfta eller avvisa dem. En kunskaps chef kan också skapa och publicera nya avsnitts sidor om en sådan inte fanns i ämnes identifieringen eller redigera befintliga om de måste uppdateras.

## <a name="requirements"></a>Krav

För att kunna arbeta i ämnes centret måste du ha nödvändig behörighet. Din administratör kan lägga till dig under [Inställningar för kunskaps hantering](set-up-topic-experiences.md), eller så kan nya användare [läggas till senare](give-user-permissions-to-the-topic-center.md).

Användare av ämnes Center kan få två uppsättningar behörigheter:

- Skapa och redigera ämnen: skapa nya avsnitt eller uppdatera ämnets innehåll som beskrivning, dokument och associerade personer.

- Hantera ämnen: Använd instrument panelen för ämnes hantering för att granska ämnen i hela organisationen. Användare kan utföra åtgärder som att bekräfta och avvisa ämnen.


## <a name="review-suggested-topics"></a>Granska förslag till ämnen

På Start sidan för ämnes Center visas de avsnitt som upptäckts på dina angivna SharePoint source locations på fliken **föreslaget** . En användare med behörighet att hantera ämnen kan granska obekräftade ämnen och välja att bekräfta eller avvisa dem.


Så här granskar du ett föreslaget ämne:

1. Gå till fliken **föreslagen** och markera avsnittet för att öppna sidan ämne.</br>

2. På sidan ämne granskar du sidan ämne och väljer **Redigera** om du behöver göra några ändringar på sidan.

3. På Start sidan för kunskaps Center går du till det valda avsnittet:

    1. Markera kryss rutan för att bekräfta att du vill behålla avsnittet.
    
    1. Välj **x** om du vill avvisa avsnittet.

    Bekräftade ämnen kommer att tas bort från den **obekräftade** listan och kommer nu att visas på fliken **Bekräfta** .

    Avvisade ämnen tas bort från den **obekräftade** listan och visas nu på fliken **avvisad eller utesluten** .

## <a name="review-confirmed-topics"></a>Granska bekräftade ämnen

På Start sidan för ämnes Center, de avsnitt som upptäckts på dina angivna SharePoint-källor och har bekräftats av en kunskaps chef eller en crowdsourced som bekräftats av två eller fler personer via kort återkopplings funktionen visas en lista på fliken **bekräftad** . En användare med behörighet att hantera ämnen kan granska bekräftade ämnen och välja att avvisa dem.


Så här granskar du ett bekräftat ämne:

1. På fliken **bekräftat** markerar du avsnittet för att öppna sidan ämne.</br>

2. På sidan ämne granskar du sidan ämne och väljer **Redigera** om du behöver göra några ändringar på sidan.

3. Du kan avvisa det också

## <a name="review-published-topics"></a>Granska publicerade ämnen
Publicerade ämnen har redigerats så att viss information alltid visas för alla som stöter på sidan. Här visas manuellt avsnitt.

   
## <a name="create-a-new-topic"></a>Skapa ett nytt ämne

En användare med behörigheten Skapa eller redigera ämnen kan skapa ett nytt avsnitt om det behövs. Det kan hända att du måste göra det här om det inte upptäcks under identifiering eller om AI-tekniken inte hittade tillräckligt många belägg för att det ska bli ett ämne.

Så här skapar du ett nytt ämne:

1. På sidan avsnitt Center väljer du **nytt** och sedan **sidan ämne**.

    ![Nytt ämne](../media/content-understanding/k-new-topic.png)

2. På sidan ny ämne kan du fylla i informationen om den nya ämnes mal len:

    1. Skriv namnet på det nya avsnittet i avsnittet **namn i det här avsnittet** .
    
    1. I avsnittet **alternativa namn** skriver du namn eller akronymer som också används för att referera till ämnet.
    
    1. Skriv en eller två meningar för ämnet i avsnittet **kort beskrivning** . Den här texten används för det associerade ämnes kortet.
    
    1. Skriv namnen på ämnes experterna i avsnittet **personer** .
    
    1. I avsnittet **filer och sidor** väljer du **Lägg till** och på nästa sida kan du välja associerade OneDrive-filer eller SharePoint Online-sidor.
    
    1. I avsnittet **Sites** väljer du **Add**. I fönstret  **webbplatser** som visas väljer du de webbplatser som är kopplade till avsnittet.

    ![Sidan ny ämne](../media/content-understanding/k-new-topic-page.png)
    
3. Om du behöver lägga till andra komponenter på sidan, till exempel text, bilder, webb delar, länkar o.s.v., väljer du ikonen arbets yta mitt på sidan för att hitta och lägga till dem.

    ![Lägga till objekt på sidan](../media/content-understanding/static-icon.png)

4. När du är klar väljer du **publicera** för att publicera avsnitts sidan. Publicerade ämnes sidor visas på fliken **sidor** .

> [!Note] 
> Sidan ny ämne består av webb delar som är *medvetna om kunskaps nätverk*. Det innebär att när AI samlar in mer information om ämnet, uppdateras informationen i dessa webb delar med förslag för att göra sidan mer användbar för användarna.


## <a name="edit-an-existing-topic-page"></a>Redigera en befintlig ämnes sida

Befintliga sidor finns på sidan **sidor** . 

1. Välj **sidor** på sidan avsnitts Center.

2. På sidan **sidor** visas en lista med avsnitts sidor. Använd sökrutan för att hitta den sida du vill uppdatera. Klicka på namnet på den avsnitts sida som du vill redigera.

3. På sidan ämne väljer du **Redigera**.

4. Gör de ändringar du behöver på sidan. Detta inkluderar uppdateringar av följande fält:

    1. Alternativa namn
    1. Beskrivning
    1. Kontakter
    1. Filer och sidor
    1. Sidor
    1. Du kan också lägga till statiska objekt på sidan, till exempel text, bilder eller länkar – genom att välja ikonen för arbets ytan.

5. Välj **publicera** för att spara ändringarna.

<!--## See also-->


