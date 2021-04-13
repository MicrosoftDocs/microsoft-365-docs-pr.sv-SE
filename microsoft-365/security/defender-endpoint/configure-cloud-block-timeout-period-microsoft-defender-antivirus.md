---
title: Konfigurera timeout-perioden för blockering av moln i Microsoft Defender Antivirus
description: Du kan konfigurera hur länge microsoft Defender Antivirus blockerar en fil från att köras medan du väntar på att molnen ska fastställas i molnet.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, moln, tidsgräns, blockering, punkt, sekunder
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691066"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Konfigurera tidsgränsen för molnblockering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

När Microsoft Defender Antivirus hittar en misstänkt fil kan den förhindra att filen körs när den frågar [microsoft Defender Antivirus-molntjänsten.](cloud-protection-microsoft-defender-antivirus.md)

Standardtiden då filen [blockeras är](configure-block-at-first-sight-microsoft-defender-antivirus.md) 10 sekunder. Du kan ange ytterligare en tid att vänta innan filen får köras. På så sätt får du tillräckligt med tid för att få ett ordentligt avgörande från molntjänsten Microsoft Defender Antivirus.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Krav för att använda den utökade timeout för molnblockering

[Blocket vid första synen](configure-block-at-first-sight-microsoft-defender-antivirus.md) och förutsättningarna måste vara aktiverade innan du kan ange en längre tidsgräns.

## <a name="specify-the-extended-timeout-period"></a>Ange den utökade tidsgränsperioden

Du kan använda grupprinciper för att ange en utökad tidsgräns för molnkontroller.

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.

3. Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus > MpEngine**

4. Dubbelklicka på Konfigurera **utökad molnkontroll och** kontrollera att alternativet är aktiverat. Ange ytterligare tid för att förhindra att filen körs medan du väntar på ett molnbestämande. Du kan ange den ytterligare tiden i sekunder från 1 sekund till 50 sekunder. Den här gången läggs till i standardinställningen på 10 sekunder.

5. Klicka på **OK**.

## <a name="related-topics"></a>Relaterade ämnen

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Använd nästa generations antivirusprogram genom moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md)
- [Konfigurera blocket vid första synen](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Aktivera moln levererat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)