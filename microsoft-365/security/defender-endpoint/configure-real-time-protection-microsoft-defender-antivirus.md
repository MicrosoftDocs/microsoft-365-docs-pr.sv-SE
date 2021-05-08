---
title: Aktivera och Microsoft Defender Antivirus funktioner för skydd
description: Aktivera och Microsoft Defender Antivirus funktioner för realtidsskydd som övervakning av beteende, heuristics och maskininlärning
keywords: antivirus, realtidsskydd, rtp, maskininlärning, beteendeövervakning, heuristics
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1e39e42b79a2a767473c4473434da249a0d07228
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275138"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>Aktivera och konfigurera alltid aktiverat skydd från Microsoft Defender Antivirus i grupprinciper

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Ständigt skydd består av realtidsskydd, övervakning av beteende och heuristics för att identifiera skadlig programvara baserat på kända misstänkta och skadliga aktiviteter.

Dessa aktiviteter omfattar händelser, till exempel processer som gör ovanliga ändringar i befintliga filer, ändrar eller skapar automatiska registernycklar för start och startplatser (kallas även utökningspunkter för automatisk start eller ASEPs) och andra ändringar av filsystemet eller filstrukturen.

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>Aktivera och konfigurera alltid skydd i Grupprincip

Du kan använda **redigeraren för lokala grupprinciper** för att Microsoft Defender Antivirus inställningar för alltid-skydd.

Så här aktiverar och konfigurerar du alltid skydd:

1. Öppna **redigeraren för lokala grupprinciper**. Gör så här:  

    1. I sökrutan Windows 10 Aktivitetsfältet skriver du **gpedit**.
    
    1. Under **Bästa matchning klickar** du på Redigera grupprincip **för** att starta **redigeraren för lokala grupprinciper.**
    
       ![SÖKRESULTAT i GPEdit-aktivitetsfältet](images/gpedit-search.png)

2. I den vänstra rutan i **redigeraren för** lokala grupprinciper expanderar du trädet till Administrativa mallar för   >    >  **datorkonfiguration Windows komponenter**  >  **Microsoft Defender Antivirus**. 

3. Konfigurera Microsoft Defender Antivirus principinställningar för program mot skadlig programvara. Gör så här:  

    1. I **Microsoft Defender Antivirus** till höger dubbelklickar du på principinställningen enligt tabellen nedan:

       | Inställning | Beskrivning | Standardinställning |
       |-----------------------------|------------------------|-------------------------------|
       | Tillåt att program mot skadlig kod startas med normal prioritet | Du kan sänka prioriteten för Microsoft Defender Antivirus motor, vilket kan vara användbart i lätta distributioner där du vill ha så smidig startprocessen som möjligt. Det kan påverka skyddet för slutpunkten. | Aktiverad
       | Tillåt att program mot skadlig programvara alltid körs | Om skyddsuppdateringar har inaktiverats kan du ange att Microsoft Defender Antivirus fortfarande ska köras. Då sänks skyddet på slutpunkten. | Inaktiverad |
    
    1. Konfigurera inställningen efter behov och klicka på **OK.**
    
    1. Upprepa föregående steg för varje inställning i tabellen.

4. Konfigurera Microsoft Defender Antivirus principinställningar för realtidsskydd. Gör så här:

    1. I **Microsoft Defender Antivirus** informationsrutan dubbelklickar du **på Realtidsskydd**. Eller klicka på **Realtidsskydd Microsoft Defender Antivirus** i det vänstra **trädet.**
    
    1. I **informationsfönstret Realtidsskydd** till höger dubbelklickar du på principinställningen enligt tabellen nedan:  

       | Inställning | Beskrivning | Standardinställning |
       |-----------------------------|------------------------|-------------------------------|
       | Aktivera beteendeövervakning | Av-motorn övervakar filprocesser, fil- och registerändringar och andra händelser på slutpunkterna för misstänkt och känd skadlig aktivitet. | Aktiverad |
       | Genomsöka alla nedladdade filer och bifogade filer | Nedladdade filer och bifogade filer genomsöks automatiskt. Det här fungerar utöver det nya Windows Defender SmartScreen-filtret, som söker igenom filer före och under nedladdningen. | Aktiverad |
       | Övervaka fil- och programaktivitet på datorn | The Microsoft Defender Antivirus engine makes note of any file changes (file writes, such as moves, copies, or modifications) and general program activity (programs that are opened or running and that cause other programs to run). | Aktiverad |
       | Aktivera aviseringar om rådata för volymskrivning | Information om rådata i volym skriver analyseras genom övervakning av beteendet. | Aktiverad |
       | Aktivera processsökning när realtidsskydd är aktiverat | Du kan aktivera funktionen Microsoft Defender Antivirus genomsöker körningsprocesser efter misstänkta ändringar eller beteenden. Det här är användbart om du tillfälligt har inaktiverat realtidsskyddet och vill söka igenom processer som startades när det inaktiverades automatiskt. | Aktiverad |
       | Definiera den maximala storleken på nedladdade filer och bifogade filer som ska genomsökas | Du kan definiera storleken i kilobyte. | Aktiverad |
       | Konfigurera åsidosättning av lokal inställning för att aktivera beteendeuppföljning | Konfigurera en lokal åsidosättning för konfiguration av beteendeövervakning. Den här inställningen kan endast anges av Grupprincip. Om du aktiverar den här inställningen prioriteras den lokala inställningen framför Grupprincip. Om du inaktiverar eller inte konfigurerar den här inställningen kommer grupprincipen att ha företräde framför den lokala inställningen.| Aktiverad |
       | Konfigurera åsidosättning av lokal inställning för genomsökning av alla nedladdade filer och bifogade filer | Konfigurera en lokal åsidosättning för konfiguration av genomsökning för alla nedladdade filer och bifogade filer. Den här inställningen kan endast anges av Grupprincip. Om du aktiverar den här inställningen prioriteras den lokala inställningen framför Grupprincip. Om du inaktiverar eller inte konfigurerar den här inställningen kommer grupprincipen att ha företräde framför den lokala inställningen.| Aktiverad |
       | Konfigurera en lokal åsidosättning för övervakning av fil- och programaktivitet på datorn | Konfigurera en lokal åsidosättning för konfiguration av övervakning för fil- och programaktivitet på datorn. Den här inställningen kan endast anges av Grupprincip. Om du aktiverar den här inställningen prioriteras den lokala inställningen framför Grupprincip. Om du inaktiverar eller inte konfigurerar den här inställningen kommer grupprincipen att ha företräde framför den lokala inställningen.| Aktiverad |
       | Konfigurera åsidosättning av lokal inställning för att aktivera realtidsskydd | Konfigurera en lokal åsidosättning för konfigurationen för att aktivera realtidsskydd. Den här inställningen kan endast anges av Grupprincip. Om du aktiverar den här inställningen prioriteras den lokala inställningen framför Grupprincip. Om du inaktiverar eller inte konfigurerar den här inställningen kommer grupprincipen att ha företräde framför den lokala inställningen.| Aktiverad |
       | Konfigurera åsidosättning av lokal inställning för övervakning av inkommande och utgående filaktivitet | Konfigurera en lokal åsidosättning för konfiguration av övervakning för inkommande och utgående filaktivitet. Den här inställningen kan endast anges av Grupprincip. Om du aktiverar den här inställningen prioriteras den lokala inställningen framför Grupprincip. Om du inaktiverar eller inte konfigurerar den här inställningen kommer grupprincipen att ha företräde framför den lokala inställningen. | Aktiverad |
       | Konfigurera övervakning för inkommande och utgående fil och programaktivitet | Ange om övervakning ska ske i inkommande, utgående, båda eller endera riktningen. Detta är relevant för Windows-serverinstallationer där du har definierat specifika servrar eller serverroller som ser stora mängder filändringar bara i en riktning och du vill förbättra nätverksprestandan. Helt uppdaterade slutpunkter (och servrar) på ett nätverk kommer att få liten prestandaeffekter oavsett hur många ändringar filen har gjort eller i vilken riktning de har gjorts. | Aktiverad (båda anvisningarna) |

    1. Konfigurera inställningen efter behov och klicka på **OK.**
    
    1. Upprepa föregående steg för varje inställning i tabellen.

5. Konfigurera inställningen Microsoft Defender Antivirus genomsökningsprincip. Gör så här:  

    1. Från fönstret **Microsoft Defender Antivirus** till vänster klickar du på **Sök**.
    
       ![Microsoft Defender Antivirus Skanningsalternativ](images/gpedit-windows-defender-antivirus-scan.png)

    1. I fönstret **Genomsökningsinformation** till höger dubbelklickar du på principinställningen enligt tabellen nedan:

       | Inställning | Beskrivning | Standardinställning |
       |-----------------------------|------------------------|-------------------------------|    
       | Aktivera heuristisk | Heuristiskt skydd inaktiverar eller blockerar misstänkt aktivitet direkt innan Microsoft Defender Antivirus visas en fråga om att identifiera aktiviteten. | Aktiverad |

    1. Konfigurera inställningen efter behov och klicka på **OK.**
    
6. Stäng **redigeraren för lokala grupprinciper**.


## <a name="disable-real-time-protection-in-group-policy"></a>Inaktivera realtidsskydd i Grupprincip

> [!WARNING]
> Om du inaktiverar realtidsskydd minskar du avsevärt skyddet för slutpunkterna och rekommenderas inte.

Den huvudsakliga realtidsskyddet är aktiverat som standard, men du kan inaktivera det med hjälp av **redigeraren för lokala grupprinciper.**

Så här inaktiverar du realtidsskydd i Grupprincip:

1. Öppna **redigeraren för lokala grupprinciper**.

   1. I sökrutan Windows 10 Aktivitetsfältet skriver du **gpedit**.
   
   1. Under **Bästa matchning klickar** du på Redigera grupprincip **för** att starta **redigeraren för lokala grupprinciper.**

2.  I det vänstra fönstret i **redigeraren** för lokala grupprinciper expanderar du trädet till Administrativa mallar för datorkonfiguration Windows komponenter  >    >    >  **Microsoft Defender Antivirus**  >  **Realtidsskydd**.

3. I **informationsfönstret Realtidsskydd** till höger dubbelklickar du på **Inaktivera realtidsskydd.**

   ![Inaktivera realtidsskydd](images/gpedit-turn-off-real-time-protection.png)

4. I **inställningsfönstret Inaktivera realtidsskydd** ställer du in alternativet på **Aktiverad**.

   ![Inaktivera realtidsskydd aktiverat](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. Klicka på **OK**.

6. Stäng **redigeraren för lokala grupprinciper**.

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera skydd för beteende, heuristisk och realtid](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)