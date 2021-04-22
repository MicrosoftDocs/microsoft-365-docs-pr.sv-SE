---
title: Undersöka en IP-adress som associeras med en avisering
description: Använd undersökningsalternativen för att undersöka möjlig kommunikation mellan enheter och externa IP-adresser.
keywords: undersöker, undersöker, IP-adress, avisering, Microsoft Defender för slutpunkt, extern IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: cb95deb890b52f0f5fde26a3a193181713b8ae5f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933835"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Undersöka en IP-adress som är kopplad till en Microsoft Defender för Slutpunktsavisering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Undersök eventuell kommunikation mellan dina enheter och IP-adresser (External Internet Protocol).

Identifiera alla enheter i organisationen som kommunicerat med en misstänkt eller känd skadlig IP-adress, till exempel kommando- och kontrollservrar (C2), för att fastställa möjlig omfattning för intrång, associerade filer och smittade enheter.

Du hittar information i följande avsnitt i IP-adressvyn:

- IP globalt
- Spegelvända DNS-namn
- Aviseringar relaterade till denna IP
- IP i organisation
- Endeprenad

## <a name="ip-worldwide-and-reverse-dns-names"></a>IP Worldwide and Reverse DNS names

I avsnittet för IP-adressinformation visas attribut för IP-adressen, till exempel dess ASN och de omvända DNS-namnen.

## <a name="alerts-related-to-this-ip"></a>Aviseringar relaterade till denna IP

Aviseringar **relaterade till den här IP-adressen** innehåller en lista med aviseringar som associeras med IP-adressen.

## <a name="ip-in-organization"></a>IP i organisation

I **avsnittet IP i** organisationen finns information om hur IP-adressen i organisationen utser.

## <a name="prevalence"></a>Endeprenad

I **avsnittet Föregående** visas hur många enheter som har anslutit till den här IP-adressen och när IP-adressen sågs för första och sista gången. Du kan filtrera resultatet av det här avsnittet efter tidsperiod. standardtiden är 30 dagar.

## <a name="most-recent-observed-devices-with-ip"></a>Senaste observerade enheter med IP

De **senaste observerade enheterna med** IP-avsnitt ger en kronologisk vy över händelser och tillhörande aviseringar som observerats på IP-adressen.

**Undersök en extern IP:**

1. Välj **IP** i **sökfältets** nedrullningsbar meny.
2. Ange IP-adressen i **sökfältet.**
3. Klicka på sökikonen eller tryck på **Retur.**

Information om IP-adressen visas, bland annat: registreringsinformation (om tillgänglig), omvända IP-adresser (t.ex. domäner), från enheter i organisationen som kommunicerar med denna IP-adress (under valbar tidsperiod) och vilka enheter i organisationen som har observerats kommunicerar med den här IP-adressen.

> [!NOTE]
> Sökresultat returneras endast för IP-adresser som observerats under kommunikation med enheter i organisationen.

Använd sökfiltren för att definiera sökvillkoren. Du kan också använda sökrutan för tidslinjen för att filtrera de resultat som visas på alla enheter i organisationen som observerats kommunicerar med IP-adressen, filen som är kopplad till kommunikationen och det senaste observerade datumet.

Om du klickar på något av enhetsnamnen visas enhetens vy, där du kan fortsätta undersöka rapporterade aviseringar, beteenden och händelser.

## <a name="related-topics"></a>Relaterade ämnen

- [Visa och ordna kön Microsoft Defender för slutpunktsaviseringar](alerts-queue.md)
- [Hantera Microsoft Defender för slutpunktsaviseringar](manage-alerts.md)
- [Undersöka Microsoft Defender för slutpunktsaviseringar](investigate-alerts.md)
- [Undersöka en fil som är kopplad till en Microsoft Defender för slutpunktsavisering](investigate-files.md)
- [Undersöka enheter i listan Microsoft Defender för slutpunktsenheter](investigate-machines.md)
- [Undersöka en domän som är kopplad till en Microsoft Defender för slutpunktsavisering](investigate-domain.md)
- [Undersöka ett användarkonto i Microsoft Defender för Endpoint](investigate-user.md)
