---
title: Granska identifierade hot och vidta åtgärder
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Lär dig hur du granskar och hanterar hot som upptäckts av Microsoft Defender Antivirus på Windows 10-enheter.
ms.openlocfilehash: 41465cb81850415a7b490b6af7f0ec66c724ca68
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588523"
---
# <a name="review-detected-threats-and-take-action"></a>Granska identifierade hot och vidta åtgärder

När en skadlig fil eller program vara identifieras blockerar Microsoft Defender Antivirus den och förhindrar att den körs. Och med moln skydd aktiverat kan nyligen upptäckta hot läggas till i Antivirus-och antimalware-motorn så att dina andra enheter och användare skyddas.

Microsoft Defender Antivirus identifierar och skyddar mot följande typer av hot:

- Virus, skadlig program vara och webbaserade hot på enheter
- Nät fiske försök
- Data stöld försök

Som IT-ansvarig kan du Visa information om hot identifieringar på [Windows 10-enheter som är registrerade i Intune](/mem/intune/enrollment/device-enrollment) i administrations centret för Microsoft 365. Översikts information visas, till exempel:

- Hur många enheter behöver Antivirus skydd
- Hur många enheter är inte kompatibla med säkerhets principer
- Hur många hot som för närvarande är aktiva, lösta eller stängda

Det finns flera alternativ för att visa specifik information om hot identifiering och enheter:

- Sidan **aktiva enheter** i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrations centret för Microsoft 365</a>. Se [Hantera hot identifieringar på sidan aktiva enheter](#manage-threat-detections-on-the-active-devices-page) i den här artikeln.
- Sidan **aktiva hot** i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrations centret för Microsoft 365</a>. Se [Hantera hot identifieringar på sidan aktiva hot](#manage-threat-detections-on-the-active-threats-page) .
- **Antivirus** -sidan i <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Microsoft slut punkts hanteraren</a>. Se [Hantera hot identifieringar i Microsoft slut punkts hanteraren](#manage-threat-detections-in-microsoft-endpoint-manager) i den här artikeln.

Mer information finns i [hot som upptäckts av Microsoft Defender Antivirus](threats-detected-defender-av.md).

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Hantera hot identifieringar på sidan **aktiva enheter**

Följande procedur gäller för kunder som har Microsoft 365 Business Premium.

1. Gå till administrations centret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> och logga in.

2. Välj **enheter**  >  **aktiva enheter** på navigerings sidan. Du kommer att se en lista över aktiva enheter och information, till exempel skydds status, antivirus status och antalet aktiva hot som upptäckts.

3. Välj en enhet för att visa mer information om den enheten och tillgängliga åtgärder. En utfällning öppnas med rekommendationer och tillgängliga åtgärder, till exempel **uppdaterings policy**, **uppdatering av antivirus program**, **snabb sökning**, **Kör fullständig sökning** och mycket mer.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Hantera hot identifieringar på sidan **aktiva hot**

Följande procedur gäller för kunder som har Microsoft 365 Business Premium. [Windows 10-enheter måste vara säkra och vara](/microsoft-365/business/secure-win-10-pcs) [registrerade i Intune](/mem/intune/enrollment/windows-enrollment-methods).

> [!NOTE]
> **Microsoft Defender Antivirus** -kortet och **aktiva hot** -sidan distribueras i faser, så du kanske inte har omedelbar åtkomst till dem.

1. Gå till administrations centret för Microsoft 365 på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> och logga in.

2. På **Microsoft Defender Antivirus** -kortet väljer du **Visa aktiva hot**. (Alternativt kan du i navigerings fönstret välja **hälsa**  >  **Hot & Antivirus**.)

3. På sidan **aktiva hot** väljer du ett identifierat hot för att få veta mer om det. En utfällbara öppning öppnas med information om det hotet, inklusive vilka enheter som påverkas.

4. Välj en enhet som du vill visa tillgängliga åtgärder på, till exempel **uppdaterings policy**, **uppdatera antivirus**, **Kör snabb sökning** och mycket mer.

## <a name="actions-you-can-take"></a>Åtgärder du kan vidta

När du visar information om specifika hot eller enheter får du rekommendationer och en eller flera åtgärder du kan vidta. I följande tabell beskrivs de åtgärder som kan visas.<br><br>

| Fattning | Beskrivning |
|--|--|
| Konfigurera skydd | Dina skydds principer måste konfigureras. Välj länken för att gå till sidan princip konfiguration.<br><br>Behöver du hjälp? Se [Hantera enhets säkerhet med säkerhets principer för slut punkter i Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Uppdatera policy | Dina antivirus-och real tids skydds principer måste uppdateras eller konfigureras. Välj länken för att gå till sidan princip konfiguration.<br><br>Behöver du hjälp? Se [Hantera enhets säkerhet med säkerhets principer för slut punkter i Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Kör snabb sökning | Startar en snabb Antivirus sökning på enheten och fokuserar på vanliga platser där skadlig kod kan vara registrerad, till exempel register nycklar och kända Windows-startmappar. |
| Kör fullständig genomsökning | Startar en fullständig Antivirus sökning på enheten och fokuserar på vanliga platser där skadlig kod kan registreras och inklusive alla filer och mappar på enheten. Resultat skickas till [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Uppdatera antivirus | Kräver att enheten hämtar [säkerhets information](https://go.microsoft.com/fwlink/?linkid=2149926) för skydd mot skadlig program vara. |
| Starta om enheten | Tvingar en Windows 10-enhet att starta om inom fem minuter.<br><br>**Viktigt:** Enhetens ägare eller användare meddelas inte automatiskt och kan förlora arbete som inte har sparats. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Hantera hot identifieringar i Microsoft slut punkts hanteraren

Du kan använda Microsoft slut punkts hanteraren för att hantera hot identifieringar. Windows 10-enheter måste vara [registrerade i Intune](/mem/intune/enrollment/windows-enrollment-methods) (ingår i Microsoft Endpoint Manager).

1. Gå till administrations centret för Microsoft Endpoint Manager på <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> och logga in.

2. I navigerings fönstret väljer du **Endpoint Security**.

3. Under **Hantera** väljer du **Antivirus**. Du kommer att se flera flikar, till exempel **Sammanfattning**, **slut punkter för Windows 10**-slutanvändare och **Windows 10 upptäckte skadlig kod**.

4. Granska informationen på flikarna tillgängliga och vidta nödvändiga åtgärder.

Antag till exempel att enheter visas på fliken **skadlig program vara** . När du väljer en enhet har du vissa åtgärder tillgängliga, till exempel **starta om**, **snabb sökning**, **fullständig skanning**, **synkronisering** eller uppdatering av **signaturer**. Välj en åtgärd för den enheten.

I följande tabell beskrivs de åtgärder du kan se i Microsoft slut punkts hanteraren.<br><br>

| Fattning | Beskrivning |
|--|--|
| Sedan | Tvingar en Windows 10-enhet att starta om inom fem minuter.<br><br>**Viktigt:** Enhetens ägare eller användare meddelas inte automatiskt och kan förlora arbete som inte har sparats. |
| Snabb sökning | Startar en snabb Antivirus sökning på enheten och fokuserar på vanliga platser där skadlig kod kan vara registrerad, till exempel register nycklar och kända Windows-startmappar. Resultat skickas till [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Fullständig genomsökning | Startar en fullständig Antivirus sökning på enheten och fokuserar på vanliga platser där skadlig kod kan registreras och inklusive alla filer och mappar på enheten. Resultat skickas till [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Bakgrundssynkronisering | Kräver en enhet att checka in med Intune (ingår i Microsoft Endpoint Manager). När enheten checkar in får enheten eventuella väntande åtgärder eller principer som tilldelats enheten. |
| Uppdatera signaturer | Kräver att enheten hämtar [säkerhets information](https://go.microsoft.com/fwlink/?linkid=2149926) för skydd mot skadlig program vara. |

> [!TIP]
> Mer information finns i [fjärråtgärder för enheter](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Skicka en fil för analys av skadlig program vara

Om du har en fil som du tror har missats eller felaktigt klassificerats som skadlig program vara, kan du skicka filen till Microsoft för analys av skadlig program vara. Användare och IT-administratörer kan skicka en fil för analys. Besök [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .
