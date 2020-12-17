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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du skapar och hanterar känslighets etiketter.
ms.openlocfilehash: ff3f7eb5ffddf797e254fac0ed8fc87d96940455
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703217"
---
# <a name="protect-documents-with-sensitivity-labels"></a>Skydda dokument med känslighets etiketter

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

Med känslighets etiketter kan du klassificera och skydda innehåll som är känsligt för ditt företag.

## <a name="try-it"></a>Prova!

1. I [Admin Center](https://admin.microsoft.com)väljer du administrations centret för **efterlevnad** .
1. Välj **klassificering** och sedan **känslighets etiketter**.
1. Välj **skapa en etikett** och klicka på **Ja** när varningen visas.
1. Ange **etikett namn**, **knapp Beskrivning** och **Beskrivning**. Välj **Nästa**.
1. Aktivera **kryptering**. Välj när du vill tilldela behörigheter, oavsett om du vill att användarnas åtkomst till innehållet ska upphöra och om du vill tillåta offlineåtkomst.
1. **Välj tilldela behörigheter** och Lägg sedan **till dessa e-postadresser eller domäner**.
1. Ange en e-postadress eller ett domän namn (till exempel Contoso.org).  Välj **Lägg till** och upprepa för varje e-postadress eller domän som du vill lägga till.
1. Välj **Välj behörigheter från förinställt eller anpassat**.
1. Använd den nedrullningsbara List rutan för att välja förinställda behörigheter, till exempel **granskare** eller **visnings program**, eller Välj **anpassade** behörigheter. Om du väljer **Custom** väljer du behörigheter i listan. Välj **Spara**, **Spara** och sedan **Nästa**.
1. Aktivera **innehålls markering** och välj de markeringar du vill använda.
1. Välj **Anpassa text** för varje markering som du väljer. Ange den text du vill ska visas i dokumentet och ange alternativ för teckensnitt och layout. Välj **Spara** och upprepa sedan alla eventuella markeringar. Välj **Nästa**.
1. Du kan också aktivera **förhindrande av data förlust för Bryt punkter**. Välj **Nästa**.
1. Du kan också aktivera **automärkning**. Lägg till ett villkor. Under **identifiera innehåll som innehåller** väljer du **till exempel Lägg till ett villkor**. Ange villkoret Om du till exempel vill lägga till ett villkor som talar om att Passport, social säkerhet eller annan känslig information identifieras, läggs etiketten till. Välj **Nästa**.
1. Granska inställningarna och välj **skapa**. Din etikett har skapats. Upprepa den här proceduren för eventuella ytterligare etiketter.
1. Etiketter visas som standard i Office-program i den här ordningen: **konfidentiellt**, **internt** och **offentligt**. Om du vill ändra ordningen väljer du **fler åtgärder** (ellips) för varje etikett och flyttar sedan etiketten uppåt eller nedåt. Behörigheter visas normalt från lägsta till högsta nivå.
1. Om du vill lägga till en under etikett i en etikett väljer du **fler åtgärder** och sedan **Lägg till under nivå**.
1. När du är klar väljer du **publicera etiketter**, **väljer etiketter för publicering** och sedan **Lägg till**. Markera de etiketter som du vill publicera och välj sedan **Lägg till**, **klar** och sedan **Nästa**.
1. Den nya etikett policyn används som standard för alla. Om du vill begränsa vem principen tillämpas på väljer du **Välj användare eller grupper** och sedan **Lägg till**. Välj vem du vill att principen ska gälla för och välj sedan **Lägg till**, **klar** och sedan **Nästa**.
1. Om du vill ha en standard etikett för dokument och e-post väljer du den etikett som du vill använda i list rutan. Granska återstående inställningar, justera efter behov och välj sedan **Nästa**.
1. Ange ett **namn** och en **Beskrivning** för policyn. Välj **Nästa**.
1. Granska dina inställningar och välj sedan **publicera**.

För att dina etiketter ska fungera måste varje användare ladda ned Azure information Protection Unified-märknings klienten. Sök på webben efter **AzinfoProtection_UL.exe** och ladda ner det från Microsoft Download Center och kör det på användarnas datorer.

Nästa gång du öppnar en Office-app som Word visas känslighets etiketterna som har skapats. Om du vill ändra eller använda en etikett väljer du känslighet och väljer en etikett.

