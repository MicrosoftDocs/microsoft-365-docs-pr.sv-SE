---
title: Microsoft Defender för slutpunkt Flow anslutare
ms.reviewer: ''
description: Använd Microsoft Defender för Endpoint Flow-anslutning för att automatisera säkerhet och skapa ett flöde som utlöses när en ny avisering inträffar för klientorganisationen.
keywords: flöde, apis som stöds, api, Microsoft flow, fråga, automation
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a0718f8e3aba27e6fbfc92a4308278f4c629275f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843800"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (tidigare Microsoft Flow) och Azure-funktioner

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Att automatisera säkerhetsprocedurer är ett standardkrav för alla moderna säkerhetsoperationscenter. Brist på professionella cyberbrott tvingar SOC att arbeta på det mest effektiva sättet och automatisering är ett måste. Microsoft Power Automate har stöd för olika kopplingar som skapats exakt för det. Du kan skapa en end-to-end-procedurautomatisering inom några minuter.

Microsoft Defender API har en officiell Flow Connector med många funktioner.

![Bild av autentiseringsuppgifter för redigera1](images/api-flow-0.png)

> [!NOTE]
> Mer information om licenskrav för Premium Connectors finns i [Licensiering för premium-anslutningappar.](/power-automate/triggers-introduction#licensing-for-premium-connectors)


## <a name="usage-example"></a>Användningsexempel

I följande exempel visas hur du skapar en Flow som utlöses varje gång en ny avisering inträffar för din klientorganisation.

1. Logga in på [Microsoft Power Automate](https://flow.microsoft.com).

2. Gå till **My flows**  >  **New**  >  **Automated-from blank**.

    ![Bild av autentiseringsuppgifter för redigera2](images/api-flow-1.png)

3. Välj ett namn för din Flow, sök efter "Microsoft Defender ATP utlösare" som utlösare och välj sedan den nya aviseringsutlösaren.

    ![Bild av autentiseringsuppgifter för redigering3](images/api-flow-2.png)

Nu har du en Flow som utlöses varje gång en ny avisering inträffar.

![Bild av autentiseringsuppgifter för redigera4](images/api-flow-3.png)

Allt du behöver göra nu är att välja nästa steg.
Du kan till exempel isolera enheten om aviseringens allvarlighetsgrad är Hög och skicka ett e-postmeddelande om den.
Aviseringsutlösaren anger endast aviserings-ID och maskin-ID. Du kan använda kopplingen för att expandera dessa enheter.

### <a name="get-the-alert-entity-using-the-connector"></a>Hämta aviseringsentitet med hjälp av kopplingen

1. Välj **Microsoft Defender ATP** för det nya steget.

2. Välj **Aviseringar – Få API för enkel avisering.**

3. Ställ in **aviserings-ID** från det sista steget som **indata**.

    ![Bild av autentiseringsuppgifter för redigera5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Isolera enheten om aviseringens allvarlighetsgrad är hög

1. Lägg **till** villkor som ett nytt steg.

2. Kontrollera om allvarlighetsgraden för avisering **är lika med** Hög.

   Om ja lägger du till **åtgärden Microsoft Defender ATP – Isolera datorn** med maskin-ID:t och en kommentar.

    ![Bild av autentiseringsuppgifter för redigera6](images/api-flow-5.png)

3. Lägg till ett nytt steg för att skicka e-post om aviseringen och isoleringen. Det finns flera e-postanslutningar som är mycket enkla att använda, till exempel Outlook eller Gmail.

4. Spara flödet.

Du kan också skapa ett **schemalagt** flöde som kör Avancerad sökning och mycket mer!

## <a name="related-topic"></a>Relaterat ämne
- [Microsoft Defender för slutpunkts-API:er](apis-intro.md)
