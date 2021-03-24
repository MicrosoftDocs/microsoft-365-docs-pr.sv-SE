---
title: Informationsskydd i Windows – översikt
ms.reviewer: ''
description: Läs om hur informationsskydd fungerar i Windows för att identifiera och skydda känslig information
keywords: information, skydd, dlp, data, förlust, skydd, skydda
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6d8f76786d4ee0bb96221d765bc1c3de0523c391
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073857"
---
# <a name="information-protection-in-windows-overview"></a>Informationsskydd i Windows – översikt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

Informationsskydd är en integrerad del av Microsoft 365 Enterprise Suite, vilket ger intelligent skydd för att skydda känsliga data samtidigt som produktivitet på arbetsplatsen möjliggörs.


>[!TIP]
> Läs vårt blogginlägg om hur Microsoft Defender ATP integreras med Microsoft Information Protection för att upptäcka, skydda och [övervaka känsliga data på Windows-enheter.](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)

Defender för Endpoint tillämpar följande metoder för att identifiera, klassificera och skydda data:

- **Dataidentifiering** – Identifiera känsliga data på Windows-enheter på risk
- **Dataklassificering** – Klassificera data automatiskt utifrån vanliga Microsoft Information Protection-policyer (MIP) som hanteras i Office 365 Security & Compliance Center. Med automatisk klassificering kan du skydda känsliga data även om slutanvändaren inte har klassificerat dem manuellt.


## <a name="data-discovery-and-data-classification"></a>Dataidentifiering och dataklassificering

Defender för Slutpunkt identifierar automatiskt filer med känslighetsetiketter och filer som innehåller typer av känslig information.

Känslighetsetiketter klassificerar och hjälper till att skydda känsligt innehåll.

Typer av känslig information i DLP-implementering (Data Loss Prevention) i Office 365 faller under två kategorier:

- Standard
- Anpassad

Standardtyper för känslig information är t.ex. bankkontonummer, personnummer och nationella IT-nummer. Mer information finns i Vilken [typ av känslig information letar efter](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for).

Anpassade typer är sådana som du definierar och som har utformats för att skydda olika typer av känslig information (till exempel anställnings-ID eller projektnummer). Mer information finns i Skapa [en anpassad typ av känslig information.](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type)

När en fil skapas eller redigeras på en Windows-enhet söker Defender för slutpunkt igenom innehållet för att utvärdera om det innehåller känslig information.

Aktivera Azure Information Protection-integreringen så att när en fil som innehåller känslig information upptäcks av Defender för Endpoint, även om etiketter eller informationstyper, vidarebefordras den automatiskt till Azure Information Protection från enheten.

![Bild på inställningssidan med Azure Information Protection](images/atp-settings-aip.png)

De rapporterade signalerna kan visas på Azure Information Protection – Instrumentpanelen för dataidentifiering.

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure Information Protection – Instrumentpanel för dataidentifiering

Den här instrumentpanelen visar en sammanfattad identifieringsinformation av data som upptäcks av både Defender för Endpoint och Azure Information Protection. Data från Defender för slutpunkt markeras med Platstyp – Slutpunkt.

![Bild av Azure Information Protection – Dataidentifiering](images/azure-data-discovery.png)

Lägg märke till kolumnen Enhetsrisk till höger. Den här enhetsrisken härleds direkt från Defender för Endpoint, vilket anger risknivån för säkerhetsenheten där filen identifierats, baserat på de aktiva säkerhetshot som upptäckts av Defender för Endpoint.

Klicka på en enhet för att visa en lista med filer som observerats på enheten med deras känslighetsetiketter och informationstyper.

>[!NOTE]
>Det kan ta ungefär 15–20 minuter innan identifieringen av Azure Information Protection Dashboard återspeglar identifierade filer.

## <a name="log-analytics"></a>Logganalys

Dataidentifiering baserat på Defender för slutpunkt är också tillgängligt i [Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview), där du kan utföra komplexa frågor över rådata.

Mer information om Azure Information Protection-analyser finns i [Central rapportering för Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/reports-aip)

Öppna Azure Log Analytics i Azure Portal och öppna ett frågeverktyg (standard eller klassisk).

Om du vill visa Defender för slutpunktsdata utför du en fråga som innehåller:

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

**Krav:**

- Kunder måste ha en prenumeration på Azure Information Protection.
- Aktivera Azure Information Protection-integrering i Microsoft Defender Säkerhetscenter:
    - Gå till **Inställningar** i Microsoft Defender Säkerhetscenter, klicka på **Avancerade inställningar** under **Allmänt**.



