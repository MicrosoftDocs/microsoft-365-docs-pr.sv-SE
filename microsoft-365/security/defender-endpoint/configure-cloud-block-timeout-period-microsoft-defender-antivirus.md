---
title: Konfigurera Microsoft Defender Antivirus tidsperiod för blockering av molntjänster
description: Du kan konfigurera hur länge Microsoft Defender Antivirus att blockera en fil från att köras medan du väntar på ett molnbestämande.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, moln, timeout, blockering, punkt, sekunder
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789093"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Konfigurera tidsgräns för blockering i molnet

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

När Microsoft Defender Antivirus hittar en misstänkt fil kan den förhindra att filen körs när den frågar [Microsoft Defender Antivirus molntjänsten.](cloud-protection-microsoft-defender-antivirus.md)

Standardtiden då filen [blockeras är](configure-block-at-first-sight-microsoft-defender-antivirus.md) 10 sekunder. Om du är säkerhetsadministratör kan du ange mer tid att vänta innan filen får köras. Om du utökar tidsgränsperioden för molnblockering får du tillräckligt med tid för att få ett ordentligt beslut Microsoft Defender Antivirus molntjänsten.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Krav för att använda den utökade timeout för molnblockering

[Blocket vid första synen](configure-block-at-first-sight-microsoft-defender-antivirus.md) och förutsättningarna måste vara aktiverade innan du kan ange en längre tidsgräns.

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>Ange den utökade tidsgränsperioden med hjälp av Microsoft Endpoint Manager

Du kan ange tidsgränssperioden för molnblockering med en [slutpunktssäkerhetsprincip i Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).

1. Gå till Endpoint Manager ( ) [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) och logga in.

2. Välj **Slutpunktssäkerhet** och välj **sedan** Antivirus under **Hantera**.

3. Välj (eller skapa) en antivirusprincip.

4. Expandera **Molnskydd i** avsnittet **Konfigurationsinställningar.** Ange sedan mer tid i sekunder från 1 sekund till 50 sekunder i rutan Utökad **timeout** för Defender Cloud i sekunder. Det du anger läggs till i standardinställningarna på 10 sekunder.

5. (Det här steget är valfritt) Gör eventuella andra ändringar i din antivirusprincip. (Behöver du hjälp? Se [Inställningar för Microsoft Defender Antivirus princip i Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)

6. Välj **Nästa** och slutför konfigurationen av principen.

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>Ange den utökade tidsgränsperioden med grupprincip

Du kan använda grupprinciper för att ange en utökad tidsgräns för molnkontroller.

1. Öppna konsolen Grupprinciphantering på datorn för [grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera.**

3. Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering och** välj sedan **Administrativa mallar**.

3. Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **MpEngine**.

4. Dubbelklicka på Konfigurera **utökad molnkontroll och** kontrollera att alternativet är aktiverat. 

   Ange extra tid för att förhindra att filen körs medan du väntar på att molnen ska fastställas i molnet. Ange den extra tiden i sekunder från 1 sekund till 50 sekunder. Det du anger läggs till i standardinställningarna på 10 sekunder.

5. Välj **OK**.

 