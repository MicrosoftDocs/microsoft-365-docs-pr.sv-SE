---
title: Hantera undantagsaviseringar
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Använd arbetsflödet för kommunikation i Advanced eDiscovery för att spåra status för aviseringar om juridiska meddelanden och vid behov uppdatera och skicka dem igen.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2020
ms.locfileid: "52161505"
---
# <a name="manage-hold-notifications"></a>Hantera undantagsaviseringar

När du har initierat arbetsflödet för aviseringar om juridiskt håll kan du använda kommunikationsarbetsflödet i Advanced eDiscovery för att spåra status för kommunikationen. Fliken Kommunikation innehåller en lista över alla meddelanden i ditt Advanced eDiscovery ärende. Du kan se information, t.ex. antalet biblioteksare som har tilldelats eller har bekräftat meddelandet.

## <a name="monitor-acknowledgments"></a>Övervaka bekräftelser

När du väljer en kommunikation på **fliken Kommunikation** kan du visa en lista över de bibliotek som har bekräftat ett meddelande om väntande samtal. 

1. Gå till **eDiscovery-> Advanced eDiscovery i efterlevnadscentret.**

2. Markera ett ärende och klicka sedan på **fliken** Kommunikation.

3. Välj en kommunikation för att visa den **utfällningssida som visar den** utfällningssida som är utfälld för trådlöst objekt.

En lista med vårdnadshavare som är associerade med den valda kommunikationen visas på den utfällade kommunikationssidan. Den här sidan visar också insikter och om hur många bekräftelser som har tagits emot och hur många som är utestående. Sidan visar också vilka företag som har skickat en bekräftelse på att de har fått meddelandet om att de har blivit inhållna.

## <a name="re-send-a-hold-notice"></a>Skicka om en avis om att vänta

Ibland tappar biblioteken bort e-postmeddelanden i det dagliga arbetet. För långvariga rättstvister kan en vårdnadshavare kontakta dig eller andra och begära att du skickar ett meddelande igen. När du hanterar arbetsflödet för meddelanden om juridiska meddelanden om väntande meddelanden kan du behöva skicka om ett meddelande för att få tillbaka det "överst i en användares postlåda".

Så här skickar du ett meddelande om att en kalender på nytt ska skickas till en vårdnadshavare:

1. I Advanced eDiscovery du ett ärende och klickar sedan på **fliken** Kommunikationer.

2. Välj en kommunikation för att visa den **utfällningssida som visar den** utfällningssida som är utfälld för trådlöst objekt.

3. Klicka **på > meddelande om att skicka om väntande.**

4. På den **utfällbara** sidan Med meddelande om att skicka om plats väljer du de som ska skicka meddelandet igen och anger en valfri orsak.

5. Klicka **på Skicka om du** vill skicka meddelandet till de valda biblioteksarna.

Om en vårdnadshavare inte har bekräftat att meddelandet om väntande har startats påminnelsen och eskaleringsarbetsflödet om. Om en vårdnadshavare har bekräftat att han/hon har rätt till meddelandet om kvartrering får han/hon en kopia av den ursprungliga fri vilja ta emot en kopia av den ursprungliga fri vilja ta del av den.

> [!NOTE]
> Du kan bara skicka om en avisering om juridiskt håll för att bli biblioteksenare som har tilldelats till meddelandet. 

## <a name="update-preservation-requirements"></a>Uppdatera bevarandekrav
  
I sådana fall kan det hända att företag måste bevara ytterligare eller mindre data än vad som har beskrivits tidigare. I eDiscovery-termer måste du utfärda meddelandet om väntande meddelanden på nytt med uppdaterat innehåll.

Så här uppdaterar du innehållet i det ursprungliga meddelandet om väntande:

1. I Advanced eDiscovery du ett ärende och klickar sedan på **fliken** Kommunikationer.

2. Välj det meddelande om väntande som du vill uppdatera och klicka **på** Redigera på den **utfällningsfäll sida för** uppläsningskommunikation som du vill uppdatera.

3. I guiden **Redigera** kommunikation klickar du **på Definiera portalinnehåll** i den vänstra fönsterrutan i guiden och uppdaterar innehållet i meddelandet.

4. Klicka på **Spara**.

Meddelandet om om utfärdning skickas till alla de licensierare som tilldelats meddelandet om juridiskt kvarhålls. Om påminnelsen eller eskaleringsmeddelandet är aktiverat startar arbetsflödena för dessa typer av meddelanden om.

## <a name="update-legal-hold-notifications-and-settings"></a>Uppdatera meddelanden och inställningar för juridiskt håll

När du uppdaterar innehållet eller inställningarna i meddelandet Utfärdning, utgivning, nyutgåva, påminnelse eller eskalering tillämpas ändringarna på all framtida kommunikation som genereras av arbetsflödet.

## <a name="more-information"></a>Mer information

- [Lägga till dokumentägare i ett ärende](add-custodians-to-case.md)

- [Skapa ett meddelande om juridiskt väntande](create-hold-notification.md)

- [Bekräfta en undantagsavisering](acknowledge-hold-notification.md)
