---
title: Konfigurera aviseringsmeddelanden i Microsoft Defender för Slutpunkt
description: Du kan använda Microsoft Defender för Endpoint för att konfigurera inställningar för e-postaviseringar för säkerhetsvarningar, baserat på allvarlighetsgrad och andra villkor.
keywords: e-postaviseringar, konfigurera aviseringsmeddelanden, Microsoft Defender för slutpunkt, Microsoft Defender för slutpunktsaviseringar, windows 10 Enterprise, windows 10 education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d423c5051634334f9dbb19b236446cdb579aef69
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327041"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>Konfigurera aviseringsmeddelanden i Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

Du kan konfigurera Defender för Endpoint så att e-postaviseringar skickas till vissa mottagare för nya aviseringar. Med den här funktionen kan du identifiera en grupp personer som omedelbart informeras och kan agera på aviseringar utifrån deras allvarlighetsgrad.

> [!NOTE]
> Endast användare med behörigheten Hantera säkerhetsinställningar kan konfigurera e-postaviseringar. Om du har valt att använda grundläggande behörighetshantering kan användare med roller som säkerhetsadministratör eller global administratör konfigurera e-postaviseringar.

Du kan ange allvarlighetsnivåer för aviseringar som utlöser aviseringar. Du kan också lägga till eller ta bort mottagare av e-postaviseringen. Nya mottagare får ett meddelande om aviseringar som utlöses när de läggs till. Mer information om aviseringar finns i [Visa och ordna kön Aviseringar.](alerts-queue.md)

Om du använder rollbaserad åtkomstkontroll (RBAC) får mottagarna endast meddelanden baserat på enhetsgrupper som har konfigurerats i aviseringsregeln.
Användare med rätt behörighet kan bara skapa, redigera eller ta bort meddelanden som är begränsade till enhetens grupphanteringsomfång.
Endast användare som tilldelats rollen Global administratör kan hantera meddelanderegler som är konfigurerade för alla enhetsgrupper.

E-postmeddelandet innehåller grundläggande information om aviseringen och en länk till portalen där du kan undersöka frågan ytterligare.

## <a name="create-rules-for-alert-notifications"></a>Skapa regler för aviseringar
Du kan skapa regler som bestämmer enheter och allvarlighetsgrad för aviseringar för att skicka e-postaviseringar till och aviseringsmottagarna.


1. Välj E-postaviseringar **Inställningar**  >  **navigeringsfönstret.**

2. Klicka **på Lägg till objekt.**

3. Ange allmän information:
    - **Regelnamn** – ange ett namn på meddelanderegeln.
    - **Ta med organisationsnamn** – Ange kundens namn som visas i e-postmeddelandet.
    - **Inkludera klientspecifik portallänk – Lägger** till en länk med klientorganisations-ID:t för att tillåta åtkomst till en viss klientorganisation.
    - **Ta med enhetsinformation** – Innehåller enhetens namn i e-postaviseringstexten.

        > [!NOTE]
        > Den här informationen kan bearbetas av mottagarens e-postservrar som inte finns på den geografiska plats som du har valt för Defender för slutpunktsdata.

    - **Enheter** – Välj om du vill meddela mottagare för aviseringar på alla enheter (endast rollen Global administratör) eller för valda enhetsgrupper. Mer information finns i Skapa [och hantera enhetsgrupper](machine-groups.md).
    - **Aviserings allvarlighetsgrad** – välj en allvarlighetsnivå för aviseringen.

4. Klicka på **Nästa**.

5. Ange mottagarens e-postadress och klicka sedan på **Lägg till mottagare.** Du kan lägga till flera e-postadresser.

6. Kontrollera att e-postmottagarna kan få e-postaviseringar genom att **välja Skicka testmeddelande**.

7. Klicka **på Spara meddelanderegel.**

## <a name="edit-a-notification-rule"></a>Redigera en aviseringsregel

1. Välj den aviseringsregel som du vill redigera.

2. Uppdatera informationen på fliken Allmänt och Mottagare.

3. Klicka **på Spara meddelanderegel.**

## <a name="delete-notification-rule"></a>Ta bort meddelanderegel

1. Välj den meddelanderegel som du vill ta bort.

2. Klicka på **Ta bort**.

## <a name="troubleshoot-email-notifications-for-alerts"></a>Felsöka e-postaviseringar för aviseringar

Det här avsnittet innehåller en lista över olika problem som kan uppstå när du använder e-postaviseringar för aviseringar.

**Problem:** Avsedd mottagare rapporterar att de inte får aviseringarna.

**Lösning:** Kontrollera att meddelandena inte blockeras av e-postfilter:

1. Kontrollera att Defender för slutpunktens e-postaviseringar inte skickas till mappen Skräppost. Markera dem som Inte skräppost.
2. Kontrollera att din e-postsäkerhetsprodukt inte blockerar e-postaviseringarna från Defender för Endpoint.
3. Kontrollera dina e-postprogramsregler som kanske fångar och flyttar din Defender för slutpunkts-e-postaviseringar.

## <a name="related-topics"></a>Relaterade ämnen

- [Uppdatera inställningar för datalagring](data-retention-settings.md)
- [Konfigurera avancerade funktioner](advanced-features.md)
- [Konfigurera e-postaviseringar om sårbarheter i Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
