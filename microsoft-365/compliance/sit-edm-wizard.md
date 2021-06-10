---
title: Använd Exact Data Match-schemat och guiden för typ av känslig information
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Läs mer om att använda Exact Data Match-schemat och guiden för typ av känslig information.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9d6f870239b963ee7483b9f08e93e40b10f4f0b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878010"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>Använd Exact Data Match-schemat och guiden för typ av känslig information

[Att skapa en anpassad typ av känslig information med EDM-baserad (Exact Data Match) klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) innefattar flera steg.  Du kan använda den här guiden till att skapa schema- och SIT-mönsterfiler (rule package) för att förenkla processen.

> [!NOTE]
> Exact Data Match-schemat och guiden för typ av känslig information är endast tillgänglig för World Wide- och GCC-molnen.

Guiden kan användas i stället för:

- [Definiera schemat för databasen med känslig information](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [Konfigurera ett mönster (regelpaket)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

steg i [del 1: Konfigurera EDM-baserad klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).

## <a name="pre-requisites"></a>Förutsättningar

1. Bekanta dig med stegen för att skapa en anpassad typ av känslig information med EDM:s [arbetsflöde i korthet](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).

2. Utför stegen i Spara [känsliga data i .csv- eller .tsv-format.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format)

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>Använda Exact Data Match-schemat och mönsterguiden för typ av känslig information

1. I Microsoft 365 Efterlevnadscenter för klientorganisationen går du till **Dataklassificering** > **Exakta datamatchningar**.

2. Välj **Skapa EDM-schema** för att öppna schemaguidens utfällbara konfiguration.

![Utfällbar konfigurationsguide för att skapa ett EDM-schema](../media/edm-schema-wizard-1.png)

3. Fyll i **Namn** och **Beskrivning**.

4. Välj **Ignorera avgränsare och skiljetecken för alla schemafält om** du vill ha det beteendet. Mer information om hur du konfigurerar EDM för att ignorera fall eller avgränsare finns i Skapa en anpassad typ av känslig information med [EDM-baserad klassificering (Exact Data Match).](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

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

13. Välj **Skapa mönster** om du vill skapa ytterligare mönster för din typ av EDM-känslig information.

14. Välj **Nästa** och fyll i ett **Namn** och en **Beskrivning för administratörer**.

15. Granska och välj **Skicka**.

Du kan ta bort eller redigera mönstret för den känsliga informationstypen genom att markera det som visar redigerings- och borttagningskontrollerna.

> [!IMPORTANT]
> Om du vill ta bort ett schema som redan är associerat med en EDM-känslig informationstyp, måste du först ta bort den EDM-känsliga informationstypen. Sedan kan du ta bort schemat.

## <a name="post-creation-steps"></a>Steg efter skapande

När du har använt den här guiden för att skapa dina filer för EDM-schemat och mönstret (regelpaket), måste du fortfarande utföra stegen i [Del 2: Hasha och ladda upp känsliga data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) innan du kan använda den anpassade EDM-känsliga informationstypen.

När du har verifierat att tabellen med känslig information har överförts korrekt kan du testa att den fungerar som den ska.

1. Öppna **klassificeringscenter**  >  **för dataklassificering**  >  **av känsliga informationstyper.**
2. Välj din EDM SIT i listan och välj sedan **Testa** i det utfällbara fönstret. 
3. Upload ett objekt som innehåller data som du vill identifiera, till exempel skapa ett objekt som innehåller en del av informationen i tabellen över känslig information. Om du har använt funktionen för konfigurerbar matchning i schemat för att definiera ignorerade avgränsare ska du se till att objektet innehåller exempel med och utan de avgränsare.
4. När filen har laddats upp och sökts igenom kontrollerar du om det finns matchningar för din EDM SIT.
5. Om funktionen **Test** i SIT upptäcker en matchning kontrollerar du att den inte trimmar den eller extraherar den felaktigt. Genom att exempelvis bara extrahera en understräng av hela strängen ska den identifiera eller bara hämta det första ordet i en sträng med flera ord, eller inkludera extra symboler eller tecken i extrahering. Se [Reguljära uttryck – snabbreferens för](/dotnet/standard/base-types/regular-expression-language-quick-reference) referensen till reguljära uttryck. 

### <a name="troubleshooting"></a>Felsökning

Om du inte hittar några matchningar kan du prova följande:
- Kontrollera att känsliga data har laddats upp på rätt sätt med de kommandon som beskrivs i vägledning av känsliga data med hjälp av [EDM-verktyget.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- Kontrollera att de exempel som du har angett i objektet finns i tabellen för känslig information och att ignorerade avgränsare är korrekta.
- **Testa** den SIT du använde när du konfigurerade det primära elementet i vart och ett av dina mönster. Detta bekräftar att SIT kan matcha exemplen i objektet. 
  -  Om det SIT du valde för ett primärt element i EDM-typen inte hittar en matchning i objektet eller hittar färre matchningar än du väntat dig, kontrollerar du att det har stöd för avgränsare som finns i innehållet. Se till att ta med de ignorerade avgränsare som definierats i schemat. 
  -  Om funktionen **Test** inte hittar något innehåll alls kontrollerar du om den SIT du valde innehåller krav för ytterligare nyckelord eller andra valideringar. Information om inbyggda SIT:er finns i [Definitioner av](sensitive-information-type-entity-definitions.md) entitetsdefinitioner för typer av känslig information och kontrollera vilka minimikraven är för att matcha varje typ.
