---
title: Använd Exact Data Match-schemat och guiden för typ av känslig information
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Läs mer om att använda Exact Data Match-schemat och guiden för typ av känslig information.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "52161642"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>Använd Exact Data Match-schemat och guiden för typ av känslig information

[Att skapa en anpassad typ av känslig information med EDM-baserad (Exact Data Match) klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) innefattar flera steg.  Du kan använda guiden till att skapa mönsterfiler för schemat och typen av känslig information (regelpaket) som förenklar processen.

> [!NOTE]
> Exact Data Match-schemat och guiden för typ av känslig information är endast tillgänglig för World Wide- och GCC-molnen.

Guiden kan användas i stället för:

- [Definiera schemat för databasen med känslig information](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [Konfigurera ett mönster (regelpaket)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

steg i [del 1: Konfigurera EDM-baserad klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).

## <a name="pre-requisites"></a>Förutsättningar

1. Bekanta dig med stegen för att skapa en anpassad typ av känslig information med EDM:s [arbetsflöde i korthet](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).

2. Utför stegen i avsnittet [Spara känsliga data i .csv-format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>Använda Exact Data Match-schemat och mönsterguiden för typ av känslig information

1. I Microsoft 365 Efterlevnadscenter för klientorganisationen går du till **Dataklassificering** > **Exakta datamatchningar**.

2. Välj **Skapa EDM-schema** för att öppna schemaguidens utfällbara konfiguration.

![Utfällbar konfigurationsguide för att skapa ett EDM-schema](../media/edm-schema-wizard-1.png)

3. Fyll i **Namn** och **Beskrivning**.

4. Välj **Ignorera avgränsare och skiljetecken för alla schemafält** om du vill ha den funktionen. Mer information om hur du konfigurerar att EDM ignorerar skiftlägen eller avgränsare finns i [Skapa en anpassad typ av känslig information med EDM-baserad (Exact Data Match) klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

5. Fyll i önskade värden i **schemafältet och #1** lägg till fler fält efter behov. 

> [!IMPORTANT]
> Minst ett men inte fler än fem av schemafälten måste anges som sökbara.

6. Välj Spara. Schemat finns nu i listan.

7. Välj **EDM-typer av känslig information** och **Skapa EDM-typ av känslig information** för att öppna konfigurationsguiden för känsliga informationstyper.

8. Välj **Välj ett befintligt EDM-schema** och välj det schema som du skapade i steg 2–6 i listan.

9. Välj **Nästa** och **Skapa mönster**.

10. Välj **Konfidensnivå** och **Primärt element**.  Mer information om hur du konfigurerar ett mönster finns i [Skapa en anpassad typ av känslig information i Microsoft 365 Efterlevnadscenter](create-a-custom-sensitive-information-type.md)

11.  Välj **Det primära elementets typ av känslig information** att associera det med. Se [Entitetsdefinitioner för typ av känslig information](sensitive-information-type-entity-definitions.md) för läsa mer om de tillgängliga typerna av känslig information.

12. Välj **Klar**.

13. Välj önskad **Konfidensnivå och teckennärhet**.  Detta blir standardvärdet för hela den EDM-känsliga informationstypen

13. Välj **Skapa mönster** om du vill skapa fler mönster för din EDM-känsliga informationstyp.

14. Välj **Nästa** och fyll i ett **Namn** och en **Beskrivning för administratörer**.

15. Granska och välj **Skicka**.

Du kan ta bort eller redigera mönstret för den känsliga informationstypen genom att markera det som visar redigerings- och borttagningskontrollerna.

> [!IMPORTANT]
> Om du vill ta bort ett schema som redan är associerat med en EDM-känslig informationstyp, måste du först ta bort den EDM-känsliga informationstypen. Sedan kan du ta bort schemat.

## <a name="post-steps"></a>Publicera steg

När du har använt den här guiden för att skapa dina filer för EDM-schemat och mönstret (regelpaket), måste du fortfarande utföra stegen i [Del 2: Hasha och ladda upp känsliga data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) innan du kan använda den anpassade EDM-känsliga informationstypen.