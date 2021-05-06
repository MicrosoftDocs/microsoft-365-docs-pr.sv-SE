---
title: Använda eDiscovery-exportverktyget i Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Du måste aktivera ClickOnce för att kunna använda den senaste versionen av Microsoft Edge för att ladda ned sökresultat från Innehållssökning och eDiscovery i säkerhets- och efterlevnadscentret.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "52161605"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Använda eDiscovery-exportverktyget i Microsoft Edge

På grund av de senaste ändringarna av den senaste Microsoft Edge är ClickOnce inte längre aktiverat som standard. Om du vill fortsätta att använda verktyget för eDiscovery-export för att ladda ned innehållssökning eller eDiscovery-sökresultat måste du antingen använda [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) eller aktivera ClickOnce stöd i den senaste versionen Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Aktivera ClickOnce i Microsoft Edge

1. I Microsoft Edge går du till **edge://flags/#edge-click-once**.

2. Om det befintliga värdet är **Inställt på Standard** **eller** Inaktiverat i listrutan ändrar du det till **Aktiverad.**

   ![Välj Aktiverad i listrutan](../media/ClickOnceimage1.png)

3. Rulla ned till slutet av webbläsarfönstret och klicka på Starta om **för att** starta om Edge.

   ![Klicka på Starta om](../media/ClickOnceimage2.png)

**Obs!** Organisationer kan använda grupprinciper för att inaktivera ClickOnce support. Om du vill kontrollera om det finns en organisationspolicy för ClickOnce support går du till **edge://policy**. Följande skärmbild visar att ClickOnce är aktiverat i hela organisationen. Om värdet för den här principen **är falskt** måste du kontakta en administratör i organisationen.

![Lista över Edge organisationspolicyer](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Installera och köra eDiscovery-exportverktyget

1. Klicka **på Ladda** ned resultat på den utfällsbara sidan för en export i Innehållssökning eller ett eDiscovery-ärende.

   ![Klicka på Ladda ned resultat på den utfällsbara sidan för att ladda ned sökresultat](../media/ClickOnceExport1.png)

2. Du uppmanas att bekräfta att du vill starta verktyget genom att klicka på **Öppna.**

   ![Klicka på Öppna för att starta eDiscovery-exportverktyget](../media/ClickOnceimage4.png)

   Om verktyget för eDiscovery-export inte är installerat visas en säkerhetsvarning där 

   ![Klicka på Installera för att installera eDiscovery-exportverktyget](../media/ClickOnceimage5.png)

3. Klicka på **Installera**. När det har installerats startas exportverktyget automatiskt.

Mer information finns i följande avsnitt:

- [Exportera resultat för innehållssökning](export-search-results.md)

- [Så här aktiverar du experimentflaggor i Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
