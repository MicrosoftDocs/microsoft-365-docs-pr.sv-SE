---
title: Hantera ämnen i Ämnescenter i Microsoft Viva-ämnen
description: Så här hanterar du ämnen i Ämnescenter.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 45e8f26823998278f9a332d2ea1e362b77f2032b
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107200"
---
# <a name="manage-topics-in-the-topic-center"></a>Hantera ämnen i Ämnescenter 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


I Ämnescenter för Viva kan en  knowledge manager visa sidan Hantera ämnen för att granska ämnen som har identifierats på SharePoint-källplatserna enligt givna av din kunskapsadministratör.  

   ![Ämnescenter](../media/knowledge-management/topic-center.png) </br> 



Knowledge Managers help to guide discovered topics through the topic lifecycle in which topics are:

- Förslag: Ett ämne har identifierats av AI och har tillräckligt med stödresurser, anslutningar och egenskaper.
- Bekräftad: Ett ämne som har föreslagits av AI har validerats. Validering utförs genom bekräftelse från en kunskapshanterare. Dessutom kan ett ämne bekräftas om minst två användare ger positiv feedback via feedbackfrågan på ämneskortet.
- Publicerades: Ett bekräftat ämne som har gått ut: manuella redigeringar har gjorts för att förbättra kvaliteten.
- Borttaget: Ett ämne avvisas av en kunskapshanterare och visas inte längre för användare. Ämnet kan vara i val annat läge när det tas bort (förslag, bekräftar eller publiceras). När ett publicerat ämne tas bort måste sidan med den detaljerade informationen tas bort manuellt via ämnescentrets sidbibliotek.

   ![Livscykeldiagram för ämne](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> På sidan Hantera ämnen kan varje kunskapshanterare bara se ämnen där de har åtkomst till filer och sidor i ämnet. Det kommer att återspeglas i avsnitten som visas under flikarna Föreslagna, Bekräftade, Borttaget och Publicerade. I avsnittet antal visas dock det totala antalet i organisationen.

## <a name="requirements"></a>Krav

Om du vill hantera ämnen i ämnescentret måste du:
- Ha en Viva Topics-licens.

- Ha [**behörigheten Vem som kan hantera**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) ämnen. Knowledge admins can give users this permission in the Viva Topics topic permissions settings. 

Du kan inte visa sidan Hantera ämnen i Ämnescenter om du inte har behörigheten Vem **kan hantera** ämnen.

I ämnescentret kan en knowledge manager granska ämnen som har identifierats i de SharePoint-källplatser du angett och kan antingen bekräfta eller avvisa dem. En kunskapshanterare kan också skapa och publicera nya ämnessidor om det inte finns någon som finns med i identifieringen av ämnen, eller redigera befintliga sidor om de behöver uppdateras.


## <a name="review-suggested-topics"></a>Granska föreslagna ämnen

På sidan Ämnescenter Hantera ämnen visas ämnen som identifierats på dina angivna SharePoint-källplatser på **fliken Förslag.** Vid behov kan en kunskapshanterare granska ämnen som inte har bekräftats och välja att bekräfta eller avvisa dem.

   ![Föreslagna ämnen](../media/knowledge-management/quality-score.png) </br> 

Så här granskar du ett ämne som föreslås:

1. På sidan **Hantera ämnen** väljer du **fliken Förslag** och väljer sedan ämnet för att öppna ämnessidan.</br>

2. På ämnessidan granskar du ämnessidan och väljer **Redigera** om du behöver göra några ändringar på sidan. Om du publicerar några ändringar flyttas det här avsnittet till **fliken Publicerad.**

3. När du har granskat ämnet går du tillbaka till sidan Hantera ämnen. För det valda avsnittet kan du:

   - Markera bockmarkeringen för att bekräfta ämnet.
    
   - Markera **x om** du vill avvisa ämnet.

    Bekräftade ämnen tas bort från listan **förslag** och visas nu i **den bekräftade** listan.

    Avvisade ämnen tas bort från listan **förslag och** visas nu på fliken **Borttaget.**

   </br> 

### <a name="quality-score"></a>Kvalitetsresultat

Varje ämne som visas på sidan Föreslagna ämnen har <b>tilldelats ett</b> kvalitetsresultat. Kvalitetsresultatet är en reflektion av mängden information som en genomsnittlig användare ser för information om ämnet, med tanke på att varje användare kan se mer eller mindre information på grund av de behörigheter som de kanske inte har för information i ett ämne. 

Kvalitetsresultatet kan bidra till att ge insyn i de ämnen som innehåller mest information och kan vara användbart för att hitta ämnen som kan behöva redigeras manuellt.  Ett ämne med lägre kvalitet kan till exempel vara resultatet av att vissa användare inte har SharePoint-behörigheter till relevanta filer eller webbplatser som AI har tagit med i ämnet. En deltagare kan sedan redigera ämnet så att det innehåller information (vid behov), som sedan visas för alla användare som kan visa ämnet.

Kvalitetsresultatet kan variera mellan 1 och 100. Ett nyligen upptäckt ämne får ett kvalitetsresultat på 0 tills två eller fler användare har visat det. Varje användares kvalitetsresultat bestäms av ett antal faktorer, till exempel mängden innehåll som visas för en viss användare, som kontrolleras användarens behörigheter eftersom varje ämnessida har säkerhets trimning för AI-genererat innehåll. Kvalitetsresultatet som visas på fliken Föreslagna ämnen är ett genomsnitt för varje användares enskilda poäng.

### <a name="impressions"></a>Intryck

I kolumnen Intryck visas hur många gånger ett ämne har <b>visats</b> för slutanvändare. Det omfattar vyer via ämneskort i sökningar, genom viktiga ämnen och genom vyer i Ämnescenter. Det speglar inte genomklickning för dessa ämnen, men det ämnet har visats. Kolumnen Intryck visas för ämnen på flikarna Föreslagna, Bekräftade, Publicerade och Borttaget på sidan Hantera ämnen.


## <a name="confirmed-topics"></a>Bekräftade ämnen

På sidan Hantera ämnen visas ämnen som identifierats på dina angivna SharePoint-källplatser och har bekräftats av en knowledge manager eller "crowd-sourced" som bekräftats av två eller flera personer via feedbackmekanismen för kortet på fliken Bekräftad.  Om det behövs kan en användare med behörighet att hantera ämnen granska bekräftade ämnen och välja att avvisa dem.

Så här granskar du ett bekräftat ämne:

1. På fliken **Bekräftad** väljer du avsnittet för att öppna ämnessidan.</br>

2. På ämnessidan granskar du ämnessidan och väljer **Redigera** om du behöver göra några ändringar på sidan.

Observera att du fortfarande kan välja att avvisa ett bekräftat ämne.  Det gör du genom att gå till det valda avsnittet i listan Bekräftad och välja **x** om du vill avvisa ämnet.

## <a name="published-topics"></a>Publicerade ämnen
Publicerade ämnen har redigerats så att specifik information alltid visas för dem som stöter på sidan. Här listas även manuellt skapade ämnen.

   ![Hantera ämnen](../media/knowledge-management/manage-topics-new.png) </br> 




