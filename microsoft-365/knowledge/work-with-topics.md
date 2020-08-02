---
title: 'Arbeta med ämnen i ämnescentret(Förhandsgranska) '
description: Så här arbetar du med ämnen i ämnescentret.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: 3519b8a1ddcaae09779ae8761ac368e3bd84294f
ms.sourcegitcommit: 91c82a79962387205c4dd4dd8d61322b79fed55f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46539893"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a>Arbeta med ämnen i ämnescentret (förhandsgranska)

> [!Note] 
> Innehållet i den här artikeln är för Project Cortex Private Preview. [Läs mer om Project Cortex](https://aka.ms/projectcortex).


I ämnescentret kan en kunskapshanterare granska ämnen som har brutits och upptäckts på de SharePoint-källplatser som du har angett och antingen bekräfta eller avvisa dem. En kunskapshanterare kan också skapa och publicera nya ämnessidor om en inte hittades i ämnesidentifieringen eller redigera befintliga om de behöver uppdateras.

## <a name="requirements"></a>Krav

För att kunna arbeta i ämnescentret måste du ha de behörigheter som krävs. Administratören kan lägga till dig under [inställningarna för kunskapshantering](set-up-knowledge-network.md)eller nya användare kan [läggas till efteråt](give-user-permissions-to-the-topic-center.md).

Användare av ämnescenter kan få två uppsättningar behörigheter:

- Skapa och redigera ämnen: Skapa nya ämnen eller uppdatera ämnesinnehåll som beskrivning, dokument och associerade personer
- Hantera ämnen: Använd instrumentpanelen för ämneshantering för att granska ämnen i hela organisationen. Användare kan utföra åtgärder som att bekräfta och avvisa ämnen


## <a name="review-unconfirmed-topics"></a>Granska obekräftade ämnen

På startsidan för ämnescentret visas avsnitt som upptäcktes på de angivna SharePoint-källplatserna på fliken **Obekräftade.** En användare med behörighet att hantera ämnen kan granska obekräftade ämnen och välja att bekräfta eller avvisa dem.


Så här granskar du ett obekräftat ämne:

1. Öppna ämnessidan på fliken **Obekräftade.**</br>

2. På ämnessidan går du igenom ämnessidan och väljer **Redigera** om du behöver göra några ändringar på sidan.
3. För det valda avsnittet på knowledgecenter-startsidan kan du:</br>
    a. Markera kryssrutan för att bekräfta att du vill behålla ämnet.</br>
    b. Markera **krysset** om du vill avvisa ämnet.</br>

    Bekräftade ämnen tas bort från listan **Obekräftade** och visas nu på fliken **Bekräftad.**</br>

    Avvisade ämnen tas bort från listan **Obekräftade** och visas nu på fliken **Avvisad eller Utesluten.**</br>
    
   
## <a name="create-a-new-topic"></a>Skapa ett nytt ämne

En användare med behörighet att skapa eller redigera ämne kan skapa ett nytt ämne om det behövs. Du kan behöva göra detta om ämnet inte upptäcktes genom upptäckt eller om AI-tekniken inte hittade tillräckligt med bevis för att etablera det som ett ämne.

Så här skapar du ett nytt ämne:
1. På ämnescentrets sida väljer du **Ny**och väljer sedan **Ämnessida**.</br>

    ![Nytt ämne](../media/content-understanding/k-new-topic.png) </br>

2. På den nya ämnessidan kan du fylla i informationen om den nya ämnesmallen:</br>
    a. Skriv namnet på det nya avsnittet i avsnittet **Namn på** det nya avsnittet.</br>
    b. I avsnittet **Alternativa namn** skriver du namn eller akronymer som också används för att referera till ämnet.</br>
    c. I avsnittet **Kort beskrivning** skriver du en beskrivning av ämnet en eller två meningen. Den här texten används för det associerade ämneskortet.</br>
    d. I avsnittet **Personer** skriver du namnen på ämnesexperter för ämnet.</br>
    e. I avsnittet **Filer och sidor** väljer du Lägg **till** och sedan på nästa sida kan du välja associerade OneDrive-filer eller SharePoint Online-sidor.</br>
    f. Välj **Lägg till**i avsnittet **Platser** . Markera de platser som är associerade till ämnet i fönstret **Platser** som visas.</br>

    ![Ny ämnessida](../media/content-understanding/k-new-topic-page.png) </br>
3. Om du behöver lägga till andra komponenter på sidan, till exempel text, bilder, webbdelar, länkar, etc., väljer du arbetsytan i mitten av sidan för att hitta och lägga till dem.
    ![Lägga till objekt på sidan](../media/content-understanding/static-icon.png) </br> 

4. När du är klar väljer du **Publicera** för att publicera ämnessidan. Publicerade ämnessidor visas på fliken **Sidor.**

> [!Note] 
> Den nya ämnessidan består av webbdelar som är *kunskapsnätverksmedvetna*. Detta innebär att när AI samlar in mer information om ämnet, kommer informationen i dessa webbdelar att uppdateras med förslag för att göra sidan mer användbar för användarna.


## <a name="edit-an-existing-topic-page"></a>Redigera en befintlig ämnessida

Befintliga ämnessidor finns på sidan **Sidor.** 

1. Välj **Sidor**på sidan Ämnescenter .</br>
2. På sidan **Sidor** visas en lista över ämnessidor. Använd rutan Sök för att hitta den ämnessida som du vill uppdatera. Klicka på namnet på den ämnessida som du vill redigera.</br>
3. På ämnessidan väljer du **Redigera**. </br>
4. Gör de ändringar du behöver på sidan. Detta inkluderar uppdateringar av följande fält:</br>
    a. Alternativa namn</br>
    b. Beskrivning</br>
    c. Kontakter</br>
    d. Filer och sidor</br>
    e. Platser</br>
    f. Du kan också lägga till statiska objekt på sidan – till exempel text, bilder eller länk – genom att välja canvasikonen.</br>

5. Välj **Publicera om** du vill spara ändringarna.

## <a name="see-also"></a>Se även



  






