---
title: Hantera ämnen i ämnescentret i Microsoft Viva-ämnen
description: Så här hanterar du ämnen i Ämnescenter.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 4532f5685fdde7c89ca59e5c22e1ad8afdf2b112
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904040"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a>Hantera ämnen i ämnescentret i Microsoft Viva-ämnen

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


I ämnescentret viva ämnen kan en  knowledge manager visa sidan Hantera ämnen för att granska ämnen som har identifierats på de källplatser som angetts av din kunskapsadministratör.  

   ![Ämnescenter](../media/knowledge-management/topic-center.png) </br> 



Knowledge managers help to guide discovered topics through the various topic lifecycle stages:

- **Förslag:** Ett ämne har identifierats med AI och har tillräckligt med stödresurser, anslutningar och egenskaper.
- **Bekräftad**: Ett ämne som har föreslagits av AI valideras. Valideringen utförs genom att en knowledge manager bekräftar detta. Ett ämne kan också bekräftas om det finns två positiva nettoröster från slutanvändarna som tas emot via feedbackmekanismen på ämneskortet.
- **Publicerades**: Ett bekräftat ämne som har redigerats: manuell redigering har gjorts för att förbättra kvaliteten.
- **Tas** bort : Ett ämne avvisas av en kunskapshanterare och visas inte längre för tittare. Avsnittet kan vara i valgivet läge när det tas bort (förslag, bekräftar eller publiceras). När ett publicerat ämne tas bort måste sidan med den curated informationen tas bort manuellt via ämnescentrets sidbibliotek.

   ![Diagram för livscykel för ämnen](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> På sidan Hantera ämnen kan varje kunskapshanterare bara se ämnen där de har åtkomst till underliggande filer och sidor som är kopplade till ämnet. Den här behörighets trimningen visas i listan med ämnen på flikarna **Föreslagna,** **Bekräftade,** **Borttaget** **och Publicerade.** I avsnittet antal visas dock det totala antalet i organisationen, oavsett behörighet.

## <a name="requirements"></a>Krav

Om du vill hantera ämnen i ämnescentret måste du:
- Ha en Viva Topics-licens.

- Ha [**behörigheten Vem kan hantera**](./topic-experiences-user-permissions.md) ämnen. Knowledge admins can give users this permission in the Viva Topics topic permissions settings. 

Du kan inte visa sidan Hantera ämnen i ämnescentret om du inte har behörigheten Vem **kan hantera** ämnen.

I ämnescentret kan en knowledge manager granska ämnen som har identifierats på källplatserna du angett och bekräfta eller avvisa dem. En knowledge manager kan också skapa och publicera nya ämnessidor om en inte hittades i identifieringen av ämnen, eller redigera befintliga sidor om de behöver uppdateras.


## <a name="review-suggested-topics"></a>Granska föreslagna ämnen

På sidan Ämnescenter Hantera ämnen visas ämnen som identifierats på dina angivna platser för SharePoint-källor på **fliken Förslag.** Vid behov kan en kunskapshanterare granska ämnen som inte har bekräftats och välja att bekräfta eller avvisa dem.

   ![Föreslagna ämnen](../media/knowledge-management/quality-score.png) </br> 

Så här granskar du ett föreslaget ämne:

1. På sidan **Hantera ämnen** väljer du **fliken Förslag** och väljer ämnet för att öppna ämnessidan.</br>

2. På ämnessidan granskar du ämnessidan och väljer **Redigera** om du behöver göra ändringar på sidan. När du publicerar eventuella ändringar flyttas det här avsnittet till **fliken Publicerade.**

3. När du har granskat ämnet går du tillbaka till sidan Hantera ämnen. För det valda avsnittet kan du:

   - Välj bockmarkeringen för att bekräfta ämnet.
    
   - Markera **x om** du vill avvisa ämnet.

    Bekräftade ämnen tas bort från listan **Förslag** och visas nu i **den bekräftade** listan.

    Avvisade ämnen tas bort från listan **Förslag** och visas nu på fliken **Borttaget.**

   </br> 

### <a name="quality-score"></a>Kvalitetsresultat

Varje ämne som visas på sidan Föreslagna ämnen har tilldelats ett kvalitetsresultat. Kvalitetsresultatet är en reflektion av mängden information som medelvärdet ser för information om ämnet, med tanke på att varje användare kan se mer eller mindre information på grund av de behörigheter som de kan ha eller kanske inte har på informationen i ett ämne. 

Kvalitetsresultatet kan bidra till att ge insyn i de ämnen som innehåller mest information och kan vara användbart för att hitta ämnen som kan behöva redigeras manuellt. Ett ämne med lägre kvalitet kan till exempel vara ett resultat av att vissa användare inte har SharePoint-behörigheter till relevanta filer eller webbplatser som AI har inkluderat i ämnet. En deltagare kan sedan redigera ämnet så att det innehåller informationen (vid behov), som sedan kan visas för alla användare som kan visa ämnet.

### <a name="impressions"></a>Intryck

I kolumnen Intryck visas hur många gånger ett ämne har **visats** för slutanvändarna. Det omfattar vyer via ämnessvarskort i sökningar och genom viktiga ämnen. Den återspeglar inte genomklickning på dessa ämnen, men att ämnet har visats. Kolumnen **Intryck visas** för ämnen på flikarna **Föreslagna**, **Bekräftade,** **Publicerade** och **Borttagna** på sidan Hantera ämnen.

## <a name="confirmed-topics"></a>Bekräftade ämnen

På sidan Hantera ämnen visas ämnen som identifierats på dina angivna platser för SharePoint-källor och har bekräftats av en knowledge manager eller "crowdsourced" som bekräftas av ett nettot två eller fler personer (balansera negativa användarröster mot positiva användarröster) via systemet för kortfeedback på fliken **Bekräftad.** Om det behövs kan en användare med behörighet att hantera ämnen granska bekräftade ämnen och välja att avvisa dem.

Granska ett bekräftat ämne:

1. På fliken **Bekräftad** väljer du ämnet för att öppna ämnessidan.</br>

2. På ämnessidan granskar du ämnessidan och väljer **Redigera** om du behöver göra ändringar på sidan.

Observera att du fortfarande kan välja att avvisa ett bekräftat avsnitt. Det gör du genom att gå  till det valda avsnittet på fliken Bekräftad och välja **x** om du vill avvisa ämnet.

## <a name="published-topics"></a>Publicerade ämnen
Publicerade ämnen har redigerats så att specifik information alltid visas för dem som stöter på sidan. Här listas även manuellt skapade ämnen.

   ![Hantera ämnen](../media/knowledge-management/manage-topics-new.png) </br>
