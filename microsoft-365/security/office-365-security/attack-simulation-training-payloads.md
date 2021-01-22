---
title: Skapa ett nyttolast för att simulera attacker
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig hur man skapar anpassade nyttolaster för att simulera attacker i Microsoft Defender för Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929196"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Skapa en anpassad nyttolast för att träna på attacksimulering

Microsoft tillhandahåller en robust katalog för nyttolaster för olika tekniker för social teknik som kan paras ihop med din utbildnings attacksimulering. Men det kan vara bra att skapa anpassade nyttolaster som fungerar bättre för din organisation. I den här artikeln beskrivs hur du skapar en nyttolast i utbildningen Attack-simulering i Microsoft Defender för Office 365.

Du kan skapa en nyttolast genom att klicka på Skapa en nyttolast på antingen den dedikerade fliken Nyttolaster eller i [guiden för att skapa simulering.](attack-simulation-training.md#selecting-a-payload) [  ](https://security.microsoft.com/attacksimulator?viewid=payload) 

I det första steget i guiden väljer du en nyttolasttyp. **För närvarande är endast e-post tillgänglig.**

Välj sedan en associerad teknik. Mer information om olika tekniker finns [i Välja en social engineering-teknik.](attack-simulation-training.md#selecting-a-social-engineering-technique)

Namnge din nyttolast i nästa steg. Du kan också ge den en beskrivning.

## <a name="configure-payload"></a>Konfigurera nyttolast

Nu är det dags att skapa din nyttolast. Ange avsändarens namn, e-postadress och ämne i avsnittet Med **avsändarinformation.** Välj en nätfiske-URL i den angivna listan. Den här URL-adressen bäddas senare in i meddelandets brödtext.

> [!TIP]
> Du kan välja ett internt e-postmeddelande för payloadens avsändare, så att nyttolasten visas som kommer från en annan anställd på företaget. Detta ökar känsligheten för nyttolasten och utbildar anställda om risken för interna hot.

En RTF-redigerare finns tillgänglig för att skapa din nyttolast. Du kan också importera ett e-postmeddelande som du har skapat i förväg. När du skapar brödtexten i e-postmeddelandet kan du dra nytta av de **dynamiska taggarna** för att anpassa e-postmeddelandet efter dina mål. Klicka **på nätfiskelänk** för att lägga till den tidigare markerade nätfiske-URL:en i meddelandets brödtext.

![Nätfiskelänk och dynamiska taggar markerade när nyttolast skapades för Microsoft Defender för Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Spara tid genom att växla alternativet att ersätta **alla länkar i e-postmeddelandet med nätfiskelänken.**

När du är klar med att skapa nyttolasten som du vill klickar du på **Nästa.**

## <a name="adding-indicators"></a>Lägga till indikatorer

Indikatorer hjälper anställda att gå igenom attackberäkningen och förstå ledtråden de kan leta efter i framtida attacker. Börja med att klicka på **Lägg till-indikator.**

Välj en indikator som du vill använda i listrutan. Den här listan är listad för att innehålla de vanligaste ledtrådarna som visas i nätfiskemeddelanden. När det är markerat kontrollerar du att indikatorns placering är inställd på Från brödtexten i **e-postmeddelandet** och klickar **på Markera text.** Markera den del av nyttolasten där indikatorn visas och klicka på **Markera.**

![Markerad text i meddelandets brödtext som ska läggas till i en indikator i attacksimuleringsutbildning](../../media/attack-sim-preview-select-text.png)

Lägg till en anpassad beskrivning för att beskriva indikatorn och klicka i förhandsgranskningsrutan för att se en förhandsgranskning av indikatorn. Klicka på Lägg till när du **är klar.** Upprepa dessa steg tills du har tagit upp alla indikatorer i din nyttolast.

## <a name="review-payload"></a>Granska nyttolast

Du är klar med att skapa din nyttolast. Nu är det dags att granska informationen och se en förhandsgranskning av din nyttolast. Förhandsgranskningen innehåller alla indikatorer som du har skapat. I det här steget kan du redigera varje del av nyttolasten. När du är nöjd kan **du skicka** in din nyttolast.

> [!IMPORTANT]
> Payloads that you've created will have **Tenant** as their source. När du väljer nyttolaster ska du se till att du inte filtrerar bort **klientorganisationen.**

## <a name="related-links"></a>Relaterade länkar

[Kom igång med Attack simuleringsträning](attack-simulation-training-get-started.md)

[Skapa en simulering av nätfiskeattack](attack-simulation-training.md)

[Få insikter genom att träna på attacksimulering](attack-simulation-training-insights.md)
