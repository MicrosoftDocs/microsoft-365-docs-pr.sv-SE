---
title: Bildtaggning i SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Läs mer om bildtaggning i SharePoint Syntex
ms.openlocfilehash: 0fba54db6a16a9a8571c7e1ced61b7620cf5113e
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975871"
---
# <a name="image-tagging-in-sharepoint-syntex"></a>Bildtaggning i SharePoint Syntex

(Kommer snart)

Med bildtaggning i SharePoint Syntex kan användare hitta bilder genom sökning genom att söka på bildtaggar och skapa arbetsflöden baserat på bildtaggar.. Som standard är grundläggande bildtaggning aktiverat för SharePoint och OneDrive. Bilder som laddas upp till endera platsen skannas automatiskt och lämpliga taggar används, om de är tillgängliga, från en lista på 37 grundläggande taggar. Användare kan hitta bilder via sök genom att söka på bildtaggarna.

När en användare laddar upp en bild körs taggningsprocessen automatiskt. Om en bild redigeras körs taggningsprocessen igen för att uppdatera taggarna.

Användare som har behörigheter till bildfilen kan visa och redigera taggarna i filens informationspanel eller i sidan för sökresultatet. När en användare har redigerat en bilds taggar, märker inte systemet automatiskt bilden, även om den redigeras.

Om du inaktiverar taggningen kommer bilderna inte längre att taggas automatiskt. Befintliga taggar tas inte bort.

> [!NOTE]
> Systemgenererade taggar kan ändras med uppdateringar av bilden eller vår tagg-teknik.


## <a name="configure-image-tagging"></a>Konfigurera bildtaggning

När du [konfigurera SharePoint Syntex](set-up-content-understanding.md) kan du konfigurera bildtaggning i Administrationscenter för Microsoft 365.  

Aktivera eller inaktivera bildtaggning

1. I Administrationscenter för Microsoft 365 klicka på **Inställningar**.

2. Under **Organisationskunskap** klickar du på **Automatisera innehållstolkning**.

3. Klicka på **Hantera**.

4. Klicka på **Bildtaggningsfliken**, klicka på **Redigera**.

5. Välj för att tillåta **Grundläggande taggning** eller avaktivera taggningen **Av**.

6. Klicka på **Spara**.

    ![Skärmbild på bildtaggningskontrollen](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
