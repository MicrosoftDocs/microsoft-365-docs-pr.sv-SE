---
title: Bildtaggning i SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Läs mer om bildtaggning i SharePoint Syntex
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296237"
---
# <a name="image-tagging-in-sharepoint-syntex"></a>Bildtaggning i SharePoint Syntex

Som standard är grundläggande bildtaggning aktiverat för SharePoint och OneDrive. Bilder som laddas upp till endera platsen skannas automatiskt och lämpliga taggar används, om de är tillgängliga, från en lista på 37 grundläggande taggar. Användare kan hitta bilder via sök genom att söka på bildtaggarna.

När en användare laddar upp en bild körs taggningsprocessen automatiskt. Om en bild redigeras körs taggningsprocessen igen för att uppdatera taggarna.

Användare som har behörigheter till bildfilen kan visa och redigera taggarna i filens informationspanel eller i sidan för sökresultatet. När en användare redigerar en bilds taggar kommer systemet inte längre tagga automatiskt på den bilden, även om den har redigerats.

Om du inaktiverar taggningen kommer bilderna inte längre att taggas automatiskt. Befintliga taggar tas inte bort.

## <a name="configure-image-tagging"></a>Konfigurera bildtaggning

Du kan konfigurera bildtaggning i Administrationscenter för Microsoft 365.  

Aktivera eller inaktivera bildtaggning

1. I Administrationscenter för Microsoft 365 klicka på **Inställningar**.

2. Under **Organisationskunskap**klickar du på **Automatisera innehållstolkning**.

3. Klicka på **Hantera**.

4. Klicka på **Bildtaggningsfliken**, klicka på **Redigera**.

5. Välj för att tillåta **Grundläggande taggning** eller avaktivera taggningen **Av**.

6. Klicka på **Spara**.

    ![Skärmbild på bildtaggningskontrollen](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a>Se även

[Ställa in innehållstolkning](set-up-content-understanding.md)