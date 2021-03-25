---
title: Skapa en nyttolast för utbildning av attackattacker
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
description: Administratörer kan lära sig att skapa anpassade nyttolaster för utbildning av attackattacker i Microsoft Defender för Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207050"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Skapa en anpassad nyttolast för att träna på attacksimulering

Microsoft erbjuder en robust katalog över nyttolaster för olika tekniker för social teknik som kan paras ihop med din attack simuleringsutbildning. Men det kan vara bra att skapa anpassade nyttolaster som fungerar bättre för din organisation. I den här artikeln beskrivs hur du skapar en nyttolast i utbildning om attack simulering i Microsoft Defender för Office 365.

Du kan skapa en nyttolast genom att klicka på Skapa en nyttolast på antingen den dedikerade fliken Nyttolaster eller i [guiden för att skapa simulering.](attack-simulation-training.md#selecting-a-payload) [  ](https://security.microsoft.com/attacksimulator?viewid=payload) 

Det första steget i guiden är att välja en nyttolasttyp. **För närvarande är endast e-post tillgänglig.**

Välj sedan en associerad teknik. Mer information om tekniker finns under [Välja en social engineering-teknik.](attack-simulation-training.md#selecting-a-social-engineering-technique)

I nästa steg ska du namnge din nyttolast. Du kan också ge den en beskrivning.

## <a name="configure-payload"></a>Konfigurera nyttolast

Nu är det dags att skapa din nyttolast. Ange avsändarens namn, e-postadress och ämne i avsnittet **Avsändarinformation.** Välj en nätfiske-URL i den angivna listan. Den här URL-adressen bäddas senare in i meddelandets brödtext.

> [!TIP]
> Du kan välja ett internt e-postmeddelande för nyttolastens avsändare, vilket gör att nyttolasten visas som kommer från en annan anställd på företaget. Detta ökar känsligheten för nyttolasten och utbildar anställda om risken för interna hot.

Det finns en RTF-redigerare som kan skapa din nyttolast. Du kan också importera ett e-postmeddelande som du har skapat i förväg. När du skapar brödtexten i e-postmeddelandet kan du använda de dynamiska **taggarna för** att anpassa e-postmeddelandet efter dina mål. Klicka **på Nätfiskelänk** för att lägga till den tidigare markerade nätfiske-URL:en i meddelandets brödtext.

![Nätfiskelänk och dynamiska taggar markerade i skapa nyttolast för Microsoft Defender för Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Spara tid genom att aktivera alternativet att ersätta **alla länkar i e-postmeddelandet med nätfiskelänken**.

När du är klar med att skapa nyttolasten som du vill klickar du på **Nästa**.

## <a name="adding-indicators"></a>Lägga till indikatorer

Indikatorer hjälper anställda att gå genom attack simuleringen förstå ledtråden de kan leta efter i framtida attacker. Börja med att klicka på **Lägg till indikator**.

Välj en indikator som du vill använda i listrutan. Listan används för att visa de vanligaste ledtrådarna i nätfiskemeddelanden. När du är markerad kontrollerar du att indikatorns placering är inställd på Från **brödtexten i e-postmeddelandet** och klickar på **Markera text**. Markera den del av nyttolasten där indikatorn visas och klicka på **Välj**.

![Markerad text i meddelandets brödtext som ska läggas till i en indikator i simuleringsutbildning för attack](../../media/attack-sim-preview-select-text.png)

Lägg till en anpassad beskrivning för att beskriva indikatorn och klicka i förhandsgranskningsrutan för indikatorn så visas en förhandsgranskning av indikatorn. Klicka på Lägg till när du **är klar.** Upprepa dessa steg tills du har tagit upp alla indikatorer i din nyttolast.

## <a name="review-payload"></a>Granska nyttolast

Du är klar med att skapa din nyttolast. Nu är det dags att granska informationen och se en förhandsgranskning av din nyttolast. Förhandsgranskningen innehåller alla indikatorer som du har skapat. Du kan redigera varje del av nyttolasten från det här steget. När den är nöjd kan **du skicka** in din nyttolast.

> [!IMPORTANT]
> Payloads that you've created will have **Tenant** as their source. Se till att du inte filtrerar ut klientorganisationen när du väljer **nyttolaster.**

## <a name="related-links"></a>Relaterade länkar

[Kom igång med Attack simuleringsträning](attack-simulation-training-get-started.md)

[Skapa en simulering av nätfiskeattacker](attack-simulation-training.md)

[Få insikter genom att träna på attacksimulering](attack-simulation-training-insights.md)
