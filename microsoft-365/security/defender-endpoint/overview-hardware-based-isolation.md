---
title: Maskinvarubaserad avgränsning (Windows 10)
ms.reviewer: ''
description: Läs om hur maskinvarubaserad avgränsning i Windows 10 hjälper dig att bekämpa skadlig programvara.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b31db39e03ed23698e71c4b38fb0937d2ba59727
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069079"
---
# <a name="hardware-based-isolation-in-windows-10"></a>Maskinvarubaserad avgränsning i Windows 10

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Maskinvarubaserad avgränsning skyddar systemintegriteten i Windows 10 och är integrerad med Microsoft Defender för Slutpunkt. 

| Funktion | Beskrivning |
|------------|-------------|
| [Windows Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | Application Guard skyddar din enhet från avancerade attacker samtidigt som du håller dig produktiv. Med en unik maskinvarubaserad avgränsningsmetod är målet att isolera icke betrodda webbplatser och PDF-dokument i en lätt behållare som avgränsas från operativsystemet via den inbyggda Windows Hypervisor. Om ett icke betroddt webbplats- eller PDF-dokument visar sig vara skadligt finns det fortfarande kvar i Application Guard säkra behållare, så att den skyddade stationära datorn och attacken borta från dina företagsdata. |
| [Windows Defender System Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | System Guard skyddar och behåller integriteten för systemet när det startar och efter att det körs samt validerar systemintegritet genom att använda att göra detta.  |

