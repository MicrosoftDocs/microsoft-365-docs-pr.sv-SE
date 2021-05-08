---
title: Läs mer om typer av känslig information
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 7d23230ebe4321f355128d1f3268e967a35a0a89
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245654"
---
# <a name="learn-about-sensitive-information-types"></a>Läs mer om typer av känslig information

Att identifiera och klassificera känsliga objekt som din organisation kontrollerar är det första steget i [informationsskyddsgrenen.](./information-protection.md)  Microsoft 365 finns tre sätt att identifiera objekt så att de kan klassificeras:

- manuellt av användare
- automatiserad mönsterigenkänning, som typer av känslig information
- [maskininlärning](classifier-learn-about.md)

Känsliga informationstyper är mönsterbaserade klassificerare. De kan identifiera känslig information som personnummer, kreditkort eller bankkontonummer för att identifiera känsliga objekt i Definitioner av typer av [känslig information](sensitive-information-type-entity-definitions.md)

## <a name="sensitive-information-types-are-used-in"></a>Typer av känslig information används i

- [Principer för dataförlustskydd](dlp-learn-about-dlp.md) 
- [Känslighetsetiketter](sensitivity-labels.md)
- [Kvarhållningsetiketter](retention.md)
- [Insider-riskhantering](insider-risk-management.md)
- [Efterlevnad av kommunikation](communication-compliance.md)
- [Principer för automatiska policyer](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Grundläggande delar av en typ av känslig information

Alla typer av känslig information definieras av följande fält:

- namn: så här refereras typen av känslig information till
- beskrivning: beskriver vad typen av känslig information letar efter
- mönster: Ett mönster definierar vad en typ av känslig information identifierar. Den består av följande komponenter
    - Primärt element – huvudelementet som den typ av känslig information letar efter. Det kan vara ett **vanligt uttryck** med eller utan en kontrollsummaverifiering, **en** nyckelordslista, en **nyckelordsordlista** eller en **funktion**.
    - Stödelement – element som fungerar som stöd bevis som bidrar till att öka matchningens förtroende. Till exempel nyckelordet "SSN" i närheten av ett SSN-nummer. Det kan vara ett vanligt uttryck med eller utan en verifiering av kontrollsumma, nyckelordslista och nyckelordsordlista.
    - Konfidensnivå – Konfidensnivåer (hög, medium, låg) återspeglar hur mycket stöd bevis upptäcktes tillsammans med det primära elementet. Ju mer understödjande bevis ett objekt innehåller, desto högre förtroende för att ett matchat objekt innehåller den känsliga information du letar efter.
    - Närhet – antal tecken mellan primärt element och stödelement

![Diagram över bekräftande bevis och närhetsfönster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Lär dig mer om konfidensnivåer i den här videon


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>Exempel på typ av känslig information


## <a name="argentina-national-identity-dni-number"></a>Argentinas national identity (DNI) number

### <a name="format"></a>Format

Åtta siffror avgränsade med punkter

### <a name="pattern"></a>Mönster

Åtta siffror:
- två siffror
- en punkt
- tre siffror
- en punkt
- tre siffror

### <a name="checksum"></a>Kontrollsumma

Nej

### <a name="definition"></a>Definition

En DLP-princip har med medelhög säkerhet identifierat den här typen av känslig information om följande inifrån 300 tecken:
- Det reguljära uttrycket Regex_argentina_national_id hittar innehåll som matchar mönstret.
- Ett nyckelord från Keyword_argentina_national_id hittas.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Nyckelord

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity Number 
- Identitet 
- Identification National Identity Card 
- DNI 
- NIC National Registry of Persons 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>Mer om konfidensnivåer

I en definition av typen känslig information **återspeglar konfidensnivån** hur mycket stödbevis som identifieras utöver det primära elementet. Ju mer understödjande bevis ett objekt innehåller, desto högre förtroende för att ett matchat objekt innehåller den känsliga information du letar efter. Exempelvis innehåller matchningar med hög konfidensnivå fler stödbevis i nära närhet till det primära elementet, medan matchningar med låg konfidensnivå inte skulle innehålla några stödbevis i nära närhet. 

En hög konfidensnivå returnerar de minsta falska positiva talen men kan ge fler falska negativa resultat. Låga eller medelhöga konfidensnivåer returnerar fler falska positiva tal, men några till noll negativa tal.

- **låg konfidens:** Värdet 65, matchade objekt innehåller färre falska negativa men mest falska positiva värden. Med lågt förtroende returneras alla matchningar med låg, medel och hög konfidens.
- **medelförtroende:** Värdet 75, matchade objekt innehåller en genomsnittlig mängd falska positiva värden och falska negativa värden. Medelhög konfidens returnerar alla medelhöga och högförtroende matchningar.  
- **hög** konfidens: Värdet 85, matchade objekt innehåller färre falska positiva resultat men mest falska negativa. Hög konfidens returnerar bara matchningar med hög konfidens.  

Du bör använda mönster med hög konfidensnivå med låga tal, t.ex. fem till tio, och mönster med låg konfidensnivå med högre antal, t.ex. 20 eller fler.

> [!NOTE]
> Om du har befintliga principer eller anpassade typer av känslig information (SITs) som definierats med hjälp av nummerbaserade konfidensnivåer (som också är korrekta) mappas de automatiskt till de tre diskreta konfidensnivåerna. Med låg konfidens, medelhög konfidens och hög säkerhet i användargränssnittet för Säkerhets- och efterlevnadscenter.
> - Alla principer med minsta noggrannhet eller anpassade SIT-mönster med konfidensnivåer på mellan 76 och 100 mappas till högt förtroende. 
> - Alla principer med minsta precision eller anpassade SIT-mönster med konfidensnivåer mellan 66 och 75 mappas till medelhög konfidens.
> - Alla principer med minsta noggrannhet eller anpassade SIT-mönster med konfidensnivåer som är mindre än eller lika med 65 mappas till ett lågt förtroende. 

## <a name="creating-custom-sensitive-information-types"></a>Skapa anpassade typer av känslig information

Om du vill skapa anpassade typer av känslig information & Säkerhets- och efterlevnadscenter kan du välja mellan flera alternativ:

- **Använda användargränssnittet** Du kan konfigurera en anpassad typ av känslig information med hjälp av användargränssnittet & Säkerhets- och efterlevnadscenter. Med den här metoden kan du använda reguljära uttryck, nyckelord och ordlistor. Mer information finns i [Skapa en anpassad typ av känslig information.](create-a-custom-sensitive-information-type.md)

- **Använda EDM** Du kan konfigurera anpassade typer av känslig information med hjälp av exakt datamatchning (EDM)-baserad klassificering. Med den här metoden kan du skapa en dynamisk typ av känslig information med en säker databas som du kan uppdatera med jämna mellanrum. Mer [information finns i Skapa en anpassad typ av känslig information med exakt datamatchning baserad klassificering.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

- **Använda PowerShell** Du kan konfigurera anpassade typer av känslig information med PowerShell. Även om den här metoden är mer komplex än att använda gränssnittet har du fler konfigurationsalternativ. Se [Skapa en anpassad typ av känslig information i Security & Compliance Center PowerShell.](create-a-custom-sensitive-information-type-in-scc-powershell.md)



> [!NOTE]
> Förbättrade konfidensnivåer är tillgängliga för omedelbar användning inom dataförlustskydd för Microsoft 365-tjänster, Microsoft Information Protection för Microsoft 365-tjänster, kommunikationsefterlevnad, informationsstyrning och hantering av arkivhandlingar.

> Microsoft 365 Informationsskydd har nu stöd för teckenuppsättningsspråk för förhandsgranskning med dubbla byte för:
> - Kinesiska (förenklad)
> - Kinesiska (traditionell)
> - Korean
> - Japanese

>Det här stödet är tillgängligt för typer av känslig information. Mer information finns i Stöd för [informationsskydd](mip-dbcs-relnotes.md) för viktig information om teckenuppsättningar med dubbla byte (förhandsgranskning).

## <a name="for-further-information"></a>Om du vill ha mer information
- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)
- [Skapa en anpassad typ av känslig information](create-a-custom-sensitive-information-type.md)
- [Skapa en anpassad typ av känslig information i PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

Mer information om hur du använder känsliga informationstyper för att följa sekretessregler för data finns i Distribuera [informationsskydd](../solutions/information-protection-deploy.md) för bestämmelser om datasekretess med Microsoft 365 (aka.ms/m365dataprivacy).

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->