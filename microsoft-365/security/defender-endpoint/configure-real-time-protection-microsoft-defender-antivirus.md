---
title: Aktivera och konfigurera skyddsfunktioner i Microsoft Defender Antivirus
description: Aktivera och konfigurera realtidsskyddsfunktioner i Microsoft Defender Antivirus, till exempel övervakning av beteende, heuristics och maskininlärning
keywords: antivirus, realtidsskydd, rtp, maskininlärning, beteendeövervakning, heuristics
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 807348fcbf3ad4ef9698b11b194d752d8038b4c9
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765113"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>Aktivera och konfigurera alltid-skydd för Microsoft Defender Antivirus i Grupprincip

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Ständigt skydd består av realtidsskydd, övervakning av beteende och heuristics för att identifiera skadlig programvara baserat på kända misstänkta och skadliga aktiviteter.

Dessa aktiviteter omfattar händelser, till exempel processer som gör ovanliga ändringar i befintliga filer, ändrar eller skapar automatiska registernycklar för start och startplatser (kallas även utökningspunkter för automatisk start eller ASEPs) och andra ändringar av filsystemet eller filstrukturen.

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>Aktivera och konfigurera alltid skydd i Grupprincip

Du kan använda **redigeraren för lokala grupprinciper** för att aktivera och konfigurera inställningar för alltid skydd i Microsoft Defender Antivirus.

Så här aktiverar och konfigurerar du alltid skydd:

1. Öppna **redigeraren för lokala grupprinciper**. Gör så här:  

    1. I sökrutan i Windows 10-aktivitetsfältet skriver **du gpedit**.
    
    1. Under **Bästa matchning klickar** du på Redigera grupprincip **för** att starta **redigeraren för lokala grupprinciper.**
    
       ![SÖKRESULTAT i GPEdit-aktivitetsfältet](images/gpedit-search.png)

2. I det vänstra fönstret i **redigeraren för lokala grupprinciper** expanderar du trädet **till** administrativa mallar för  >    >  **datorkonfiguration Windows-komponenter**  >  **Microsoft Defender Antivirus.** 

3. Konfigurera principinställningarna för tjänstprinciper för skydd mot skadlig programvara i Microsoft Defender Antivirus. Gör så här:  

    1. I **informationsfönstret för Microsoft Defender Antivirus** till höger dubbelklickar du på principinställningen enligt tabellen nedan:

       | Inställning | Beskrivning | Standardinställning |
       |-----------------------------|------------------------|-------------------------------|
       | Tillåt att program mot skadlig kod startas med normal prioritet | Du kan ge lägre prioritet för Microsoft Defender Antivirus-motorn, vilket kan vara användbart i enkel distribution där du vill ha så smidig startprocessen som möjligt. Det kan påverka skyddet för slutpunkten. | Aktiverad
       | Tillåt att program mot skadlig programvara alltid körs | Om skyddsuppdateringar har inaktiverats kan du ställa in att Microsoft Defender Antivirus fortfarande ska köras. Då sänks skyddet på slutpunkten. | Inaktiverad |
    
    1. Konfigurera inställningen efter behov och klicka på **OK.**
    
    1. Upprepa föregående steg för varje inställning i tabellen.

4. Konfigurera principinställningarna för realtidsskydd i Microsoft Defender Antivirus. Gör så här:

    1. I **informationsfönstret för Microsoft Defender Antivirus** dubbelklickar du på **Realtidsskydd.** Du kan också klicka **på Realtidsskydd** i trädträdet för Microsoft Defender Antivirus i **den vänstra rutan.**
    
    1. I **informationsfönstret Realtidsskydd** till höger dubbelklickar du på principinställningen enligt tabellen nedan:  

       | Inställning | Beskrivning | Standardinställning |
       |-----------------------------|------------------------|-------------------------------|
       | Aktivera beteendeövervakning | Av-motorn övervakar filprocesser, fil- och registerändringar och andra händelser på slutpunkterna för misstänkt och känd skadlig aktivitet. | Aktiverad |
       | Genomsöka alla nedladdade filer och bifogade filer | Nedladdade filer och bifogade filer genomsöks automatiskt. Det här fungerar utöver Windows Defender SmartScreen-filtret, som söker igenom filer före och under nedladdningen. | Aktiverad |
       | Övervaka fil- och programaktivitet på datorn | Microsoft Defender Antivirus-motorn notera alla filändringar (fil skriver, till exempel flyttningar, kopior eller ändringar) och allmän programaktivitet (program som öppnas eller körs och som gör att andra program kan köras). | Aktiverad |
       | Aktivera aviseringar om rådata för volymskrivning | Information om rådata i volym skriver analyseras genom övervakning av beteendet. | Aktiverad |
       | Aktivera processsökning när realtidsskydd är aktiverat | Du kan aktivera Antivirusmotorn i Microsoft Defender oberoende av varandra för att söka igenom processer som körs efter misstänkta ändringar eller beteenden. Det här är användbart om du tillfälligt har inaktiverat realtidsskyddet och vill söka igenom processer som startades när det inaktiverades automatiskt. | Aktiverad |
       | Definiera den maximala storleken på nedladdade filer och bifogade filer som ska genomsökas | Du kan definiera storleken i kilobyte. | Aktiverad |
       | Konfigurera åsidosättning av lokal inställning för att aktivera beteendeuppföljning | Konfigurera en lokal åsidosättning för konfiguration av beteendeövervakning. Den här inställningen kan endast anges av Grupprincip. Om du aktiverar den här inställningen prioriteras den lokala inställningen framför Grupprincip. Om du inaktiverar eller inte konfigurerar den här inställningen kommer grupprincipen att ha företräde framför den lokala inställningen.| Aktiverad |
       | Konfigurera åsidosättning av lokal inställning för genomsökning av alla nedladdade filer och bifogade filer | Konfigurera en lokal åsidosättning för konfiguration av genomsökning för alla nedladdade filer och bifogade filer. Den här inställningen kan endast anges av Grupprincip. Om du aktiverar den här inställningen prioriteras den lokala inställningen framför Grupprincip. Om du inaktiverar eller inte konfigurerar den här inställningen kommer grupprincipen att ha företräde framför den lokala inställningen.| Aktiverad |
       | Konfigurera en lokal åsidosättning för övervakning av fil- och programaktivitet på datorn | Konfigurera en lokal åsidosättning för konfiguration av övervakning för fil- och programaktivitet på datorn. Den här inställningen kan endast anges av Grupprincip. Om du aktiverar den här inställningen prioriteras den lokala inställningen framför Grupprincip. Om du inaktiverar eller inte konfigurerar den här inställningen kommer grupprincipen att ha företräde framför den lokala inställningen.| Aktiverad |
       | Konfigurera åsidosättning av lokal inställning för att aktivera realtidsskydd | Konfigurera en lokal åsidosättning för konfigurationen för att aktivera realtidsskydd. Den här inställningen kan endast anges av Grupprincip. Om du aktiverar den här inställningen prioriteras den lokala inställningen framför Grupprincip. Om du inaktiverar eller inte konfigurerar den här inställningen kommer grupprincipen att ha företräde framför den lokala inställningen.| Aktiverad |
       | Konfigurera åsidosättning av lokal inställning för övervakning av inkommande och utgående filaktivitet | Konfigurera en lokal åsidosättning för konfiguration av övervakning för inkommande och utgående filaktivitet. Den här inställningen kan endast anges av Grupprincip. Om du aktiverar den här inställningen prioriteras den lokala inställningen framför Grupprincip. Om du inaktiverar eller inte konfigurerar den här inställningen kommer grupprincipen att ha företräde framför den lokala inställningen. | Aktiverad |
       | Konfigurera övervakning för inkommande och utgående fil och programaktivitet | Ange om övervakning ska ske i inkommande, utgående, båda eller endera riktningen. Det här är relevant för Windows Server-installationer där du har definierat specifika servrar eller serverroller som ser stora mängder filändringar bara i en riktning och du vill förbättra nätverksprestandan. Helt uppdaterade slutpunkter (och servrar) på ett nätverk kommer att få liten prestandaeffekter oavsett hur många ändringar filen har gjort eller i vilken riktning de har gjorts. | Aktiverad (båda anvisningarna) |

    1. Konfigurera inställningen efter behov och klicka på **OK.**
    
    1. Upprepa föregående steg för varje inställning i tabellen.

5. Konfigurera inställningen för sökprincip för Microsoft Defender Antivirus. Gör så här:  

    1. I trädet **Microsoft Defender Antivirus** i den vänstra rutan klickar du på **Sök**.
    
       ![Alternativ för Microsoft Defender Antivirus Scan](images/gpedit-windows-defender-antivirus-scan.png)

    1. I fönstret **Genomsökningsinformation** till höger dubbelklickar du på principinställningen enligt tabellen nedan:

       | Inställning | Beskrivning | Standardinställning |
       |-----------------------------|------------------------|-------------------------------|    
       | Aktivera heuristisk | Heuristiskt skydd inaktiverar eller blockerar misstänkt aktivitet direkt innan Microsoft Defender Antivirus engine uppmanas att identifiera aktiviteten. | Aktiverad |

    1. Konfigurera inställningen efter behov och klicka på **OK.**
    
6. Stäng **redigeraren för lokala grupprinciper**.


## <a name="disable-real-time-protection-in-group-policy"></a>Inaktivera realtidsskydd i Grupprincip

> [!WARNING]
> Om du inaktiverar realtidsskydd minskar du avsevärt skyddet för slutpunkterna och rekommenderas inte.

Den huvudsakliga realtidsskyddet är aktiverat som standard, men du kan inaktivera det med hjälp av **redigeraren för lokala grupprinciper.**

Så här inaktiverar du realtidsskydd i Grupprincip:

1. Öppna **redigeraren för lokala grupprinciper**.

   1. I sökrutan i Windows 10-aktivitetsfältet skriver **du gpedit**.
   
   1. Under **Bästa matchning klickar** du på Redigera grupprincip **för** att starta **redigeraren för lokala grupprinciper.**

2.  I det vänstra fönstret i **redigeraren för** lokala grupprinciper expanderar du trädet till Administrativa mallar för datorkonfiguration   >    >  **Windows-komponenter**  >  **Microsoft Defender Antivirus**  >  **Realtidsskydd.**

3. I **informationsfönstret Realtidsskydd** till höger dubbelklickar du på **Inaktivera realtidsskydd.**

   ![Inaktivera realtidsskydd](images/gpedit-turn-off-real-time-protection.png)

4. I **inställningsfönstret Inaktivera realtidsskydd** ställer du in alternativet på **Aktiverad**.

   ![Inaktivera realtidsskydd aktiverat](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. Klicka på **OK**.

6. Stäng **redigeraren för lokala grupprinciper**.

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera behavioruellt, heuristiskt och realtidsskydd](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)