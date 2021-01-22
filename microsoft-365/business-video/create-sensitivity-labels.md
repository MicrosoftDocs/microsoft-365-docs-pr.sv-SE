---
title: Skapa känslighetsetiketter
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du skapar och hanterar känslighetsetiketter.
ms.openlocfilehash: c8d528e7a742ca60345def415ce47b29b371c738
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927328"
---
# <a name="protect-documents-with-sensitivity-labels"></a>Skydda dokument med känslighetsetiketter

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

Med känslighetsetiketter kan du klassificera och skydda innehåll som är känsligt för ditt företag.

## <a name="try-it"></a>Prova!

1. Välj [administrationscentret för](https://admin.microsoft.com)efterlevnad **i** administrationscentret.
1. Välj **Klassificering** och sedan **Känslighetsetiketter.**
1. Välj **Skapa en etikett** och välj Ja när varningen **visas.**
1. Ange ett **etikettnamn,** **en knappbeskrivning** och **en beskrivning.** Välj **Nästa**.
1. Aktivera **kryptering.** Välj när du vill tilldela behörigheter, om du vill att användarnas åtkomst till innehållet ska upphöra och om du vill tillåta offlineåtkomst.
1. **Välj Tilldela behörigheter och** lägg sedan till **dessa e-postadresser eller domäner.**
1. Ange en e-postadress eller ett domännamn (till exempel Contoso.org).  Välj **Lägg till** och upprepa för varje e-postadress eller domän som du vill lägga till.
1. Välj **Välj behörigheter från förinställda eller anpassade.**
1. Använd listrutan för att välja förinställda behörigheter, till exempel **Granskare** eller **Läsare,** eller välj **Anpassade** behörigheter. Om du väljer **Anpassad** väljer du behörigheterna i listan. Välj **Spara,** **Spara** och sedan **Nästa.**
1. Aktivera **innehållsmarkering och** välj de markeringar du vill använda.
1. Välj Anpassa text för varje markering du **väljer.** Ange den text som du vill ska visas i dokumentet och ange teckensnitts- och layoutalternativ. Välj **Spara** och upprepa sedan för ytterligare markeringar. Välj **Nästa**.
1. Du kan också aktivera **dataförlustskydd för Slutpunkten.** Välj **Nästa**.
1. Du kan också aktivera **Automatisk märkning.** Lägg till ett villkor. Välj till exempel Lägg **till ett villkor under** Identifiera innehåll som **innehåller.** Ange villkoret. Lägg till exempel till ett villkor om pass, social säkerhet eller annan känslig information identifieras läggs etiketten till. Välj **Nästa**.
1. Granska inställningarna och välj **Skapa.** Din etikett har skapats. Upprepa proceduren för ytterligare etiketter som du vill använda.
1. Som standard visas etiketter i Office-program i följande ordning: **Konfidentiellt,** **Internt** och **Offentligt.** Om du vill ändra ordningen  väljer du Fler åtgärder (ellipsen) för varje etikett och flyttar sedan etiketten uppåt eller nedåt. Vanligtvis visas behörigheterna från den lägsta till den högsta nivån av behörigheter.
1. Om du vill lägga till en underetikett till en etikett väljer du Fler **åtgärder** och sedan **Lägg till undernivå.**
1. När du är klar väljer **du Publicera** **etiketter, Väljer etiketter att publicera** och sedan Lägg **till.** Markera de etiketter du vill publicera och välj sedan **Lägg till,** **Klar** och sedan **Nästa.**
1. Den nya etikettprincipen tillämpas som standard på alla. Om du vill begränsa vem principen tillämpas på väljer du **Välj användare eller grupper och** sedan Lägg **till.** Välj vem du vill att principen ska gälla för och välj sedan **Lägg till,** **Klar** och sedan **Nästa.**
1. Om du vill ha en standardetikett för dokument och e-post väljer du den etikett du vill använda i listrutan. Granska de återstående inställningarna, justera efter behov och välj **sedan Nästa.**
1. Ange ett **namn** och **en beskrivning** för principen. Välj **Nästa**.
1. Granska inställningarna och välj sedan **Publicera.**

För att etiketterna ska fungera måste varje användare ladda ned Azure Information Protection Unified Labeling Client. Sök på webben **efterAzinfoProtection_UL.exe** ladda sedan ned den från Microsoft Download Center och kör den på användarnas datorer.

Nästa gång du öppnar ett Office-program, till exempel Word, visas känslighetsetiketterna som har skapats. Om du vill ändra eller använda en etikett väljer du Känslighet och väljer en etikett.

