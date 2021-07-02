---
title: Användning Microsoft OneDrive Learning verktygskompatibilitet
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Skapa och betygs gradera uppgifter, skapa och hantera kursinnehåll och samarbeta i filer i realtid med den nya appen Microsoft OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257074"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Integrera Microsoft OneDrive LTI med Canvas

Att Microsoft OneDrive en LTI med Canvas är en process i två steg. Med det första steget Microsoft OneDrive funktionen i Canvas, och med det andra steget Microsoft OneDrive LTI tillgängligt i Canvas-kurser.

## <a name="recommended-browser-settings"></a>Rekommenderade webbläsarinställningar

- Cookies ska aktiveras för Microsoft OneDrive.
- Popup-fönster ska inte blockeras för Microsoft OneDrive.

> [!NOTE]
> - Cookies är inte aktiverade som standard i Chrome-webbläsaren inkognitoläge och måste aktiveras.
> - Microsoft OneDrive LTI fungerar i privat läge i Microsoft Edge webbläsare. Kontrollera att du inte har blockerat cookies (som är aktiverade som standard).

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>Aktivera Microsoft OneDrive LTI i Canvas

> [!IMPORTANT]
> Den person som utför den här integrationen bör vara administratör för Canvas och administratör för Microsoft 365 klientorganisationen.

1. Logga in Microsoft OneDrive <a href="https://onedrivelti.microsoft.com/admin" target="_blank">LTI-registreringsportalen</a>
1. Välj knappen **Administratörsmedgivande** och godkänn behörigheterna.
1. Välj knappen **Skapa ny LTI-klient.** På sidan LTI Registration väljer du **Canvas** i listrutan och anger bas-URL-adressen för Canvas-instansen.

> [!NOTE]
> Om din Canvas-instans till exempel https://contoso.test.instructure.com är ]( https://contoso.test.instructure.com) ska den fullständiga webbadressen anges.

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Administrationssidan för LTI-klientorganisationen med ett listreringsfält för att välja LTI-konsumentplattformen och ett textfält för URL.":::

4. Kopiera JSON genom att välja **knappen** Kopiera (en ikon till höger som visar två sidor ovanpå varandra). Detta används för att generera nyckeln i Canvas.

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="En bild som visar knappen Kopiera som kopierar den JSON-text som visas och gör den tillgänglig för nyckelgenerering i Canvas.":::

5. Logga in på Canvas-instansen som administratör och välj **Utvecklarnycklar** på menyn till vänster på sidan. Skapa en utvecklarnyckel i listrutan genom att välja **LTI-nyckel** i listrutan uppe till höger på sidan.

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="En skärmbild som visar det vänstra navigeringsfältet med Utvecklarnycklar markerat och LTI-tangentposten markerad i en listmeny till höger på sidan.":::

6. På sidan Configure i listrutan **Method** väljer du Klistra in **JSON** som metod och klistrar in den JSON-text du kopierade i steg 5 i textfältet som visas.
7. Spara nyckeln så blir den tillgänglig i Canvas i läget **Av.** Aktivera nyckeln **och** kopiera den nyckel som anges i kolumnen **Information** som ska användas i nästa steg.

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Arbetsytesidan med nyckeln i läget Off. Den måste vara aktiverad och nyckeln måste kopieras från informationskolumnen på den här sidan.":::

8. Gå tillbaka till Microsoft OneDrive för LTI-registrering och klistra in nyckeln i **fältet Canvas klient-ID.** Välj **Nästa** när du är klar.

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Registreringssidan för LTI-klientorganisation, som visar JSON-texten och textrutan som nyckeln ska kopieras till.":::

9. Granska och spara ändringarna. Ett meddelande visas om att registreringen har lyckats.
10. Du kan också granska din registreringsinformation genom att välja knappen Visa **LTI-innehavare** på startsidan.

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>Aktivera Microsoft OneDrive LTI i Canvas-kurser

En Canvas-administratör kan aktivera funktionen Microsoft OneDrive LTI för alla kurser. Om Microsoft OneDrive LTI krävs i en särskild kurs (och inte i alla kurser), måste kursläraren följa samma steg i kursinställningarna.

1. Logga in som administratör och gå till **avsnittet Inställningar** administratör.
2. Gå till **avsnittet Appar** och välj knappen Visa **appkonfigurationer.**
3. Välj knappen **Lägg till** app.
4. I **listrutan Konfigurationstyp** väljer du **alternativet Efter klient-ID.**
5. Klistra in värdet för utvecklarnyckeln som genererades tidigare i fältet **Klient-ID** och välj **knappen** Skicka.

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Sidan Lägg till app, med alternativet Efter klient-ID under listrutan Konfigurationstyp.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Samarbetsfunktioner Inställningar för Microsoft OneDrive LTI i Canvas-kurser

> [!NOTE]
> För att samarbete ska fungera för lärare och elever bör du inte aktivera inställningen för samarbete. Kontrollera att inställningen inte är aktiverad genom att följa stegen nedan.

1. Logga in som administratör och gå till avsnittet **Inställningar** administratör.
1. Gå **till avsnittet Funktionsalternativ** och gå sedan till **avsnittet** Kurs.
1. Ange att **funktionen Verktyg för externt** samarbete inte ska aktiveras.

> [!NOTE]
> Samarbete kan tilldelas enskilda elever och grupper av elever. Tilldelning till enskilda elever fungerar som standard. Följ de här stegen för att kunna tilldela samarbete till en grupp elever:

1. Logga in som administratör och gå till **avsnittet Utvecklarnycklar.**
1. Leta reda på nyckeln med värdet 17000000000710 och ställ in den på **På**.
