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
description: Läs om hur du granskar och hanterar hot som upptäcks av Microsoft Defender Antivirus på dina Windows 10-enheter.
ms.openlocfilehash: 15e99fb75e4a3ac1af842ca7d0b900e02cbc6bd4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912792"
---
# <a name="review-detected-threats-and-take-action"></a>Granska identifierade hot och vidta åtgärder

När en skadlig fil eller programvara hittas blockerar Microsoft Defender Antivirus den och förhindrar att den körs. Och med moln levererat skydd aktiverat läggs nyligen identifierade hot till i antivirus- och antimalwaremotorn så att även dina andra enheter och användare skyddas.

Microsoft Defender Antivirus identifierar och skyddar mot följande typer av hot:

- Virus, skadlig kod och webbaserade hot på enheter
- Försök till nätfiske
- Datastöldförsök

Som IT-proffs/administratör kan du visa information om identifiering av hot på [Windows 10-enheter](/mem/intune/enrollment/device-enrollment) som är registrerade i Intune i administrationscentret för Microsoft 365. Du ser sammanfattningsinformation som:

- Hur många enheter behöver antivirusskydd
- Hur många enheter uppfyller inte säkerhetsprinciperna
- Hur många hot som är aktiva, minimerade eller lösta för närvarande

Du kan visa specifik information om identifiering av hot och enheter på flera olika sätt:

- Sidan **Aktiva enheter** i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret för Microsoft 365.</a> Se [Hantera identifieringar av hot på sidan Aktiva enheter i](#manage-threat-detections-on-the-active-devices-page) den här artikeln.
- Sidan **Aktiva hot i** administrationscentret för Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365.</a> Se [Hantera identifieringar av hot på sidan Aktiva hot i](#manage-threat-detections-on-the-active-threats-page) den här artikeln.
- Antivirussidan i <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Microsoft Endpoint Manager</a>.  Se [Hantera identifieringar av hot i Microsoft Endpoint Manager i](#manage-threat-detections-in-microsoft-endpoint-manager) den här artikeln.

Mer information finns i [Hot som upptäckts av Microsoft Defender Antivirus.](threats-detected-defender-av.md)

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Hantera identifieringar av hot på **sidan Aktiva** enheter

Följande procedur gäller för kunder som har Microsoft 365 Business Premium.

1. Gå till administrationscentret för Microsoft 365 och <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> logga in.

2. På navigeringssidan väljer du **Enheter**  >  **aktiva enheter**. Du ser en lista över aktiva enheter och information, till exempel status för skydd, skyddstatus för antivirus (AV) och antalet aktiva hot som upptäckts.

3. Välj en enhet om du vill visa mer information om enheten och tillgängliga åtgärder. En utfällig fönsterskärm öppnas med rekommendationer och tillgängliga åtgärder, till exempel Uppdateringsprincip **,** Uppdatera **antivirusprogram,** Kör snabbsökning, Kör **fullständig** sökning med mera.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Hantera identifieringar av hot på **sidan Aktiva** hot

Följande procedur gäller för kunder som har Microsoft 365 Business Premium. [Windows 10-enheter måste vara](./secure-win-10-pcs.md) skyddade [och registrerade i Intune.](/mem/intune/enrollment/windows-enrollment-methods)

> [!NOTE]
> Sidan **Microsoft Defender Antivirus** och aktiva hot **distribueras** i faser, så du kanske inte har direkt åtkomst till dem.

1. Gå till administrationscentret för Microsoft 365 och <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> logga in.

2. Välj Visa aktiva hot på Microsoft **Defender** **Antivirus-kortet.** (Du kan också välja Hälsa i **navigeringsfönstret**  >  **Hot & antivirus**.)

3. På sidan **Aktiva hot väljer** du ett upptäckt hot för att lära dig mer om det. En utfälling öppnas med information om hoten, inklusive vilka enheter som påverkas.

4. Välj en enhet på den utfäll plats där du vill visa tillgängliga åtgärder, till exempel Uppdateringsprincip, Uppdatera **antivirus,** **Kör snabbsökning** och mycket mer.

## <a name="actions-you-can-take"></a>Åtgärder som du kan utföra

När du visar information om specifika hot eller enheter ser du rekommendationer och en eller flera åtgärder som du kan vidta. I följande tabell beskrivs åtgärder som kan visas.<br><br>

| Åtgärd | Beskrivning |
|--|--|
| Konfigurera skydd | Dina principer för skydd mot hot måste konfigureras. Klicka på länken för att gå till sidan för principkonfigurationen.<br><br>Behöver du hjälp? Se [Hantera enhetssäkerhet med slutpunktssäkerhetsprinciper i Microsoft Intune.](/mem/intune/protect/endpoint-security-policy) |
| Uppdateringsprincip | Dina principer för antivirus- och realtidsskydd måste uppdateras eller konfigureras. Klicka på länken för att gå till sidan principkonfiguration.<br><br>Behöver du hjälp? Se [Hantera enhetssäkerhet med slutpunktssäkerhetsprinciper i Microsoft Intune.](/mem/intune/protect/endpoint-security-policy) |
| Kör snabbsökning | Startar en snabb antivirussökning på enheten med fokus på vanliga platser där skadlig programvara kan registreras, t.ex. registernycklar och kända startmappar i Windows. |
| Kör fullständig sökning | Startar en fullständig antivirussökning på enheten med fokus på vanliga platser där skadlig programvara kan registreras, och inklusive alla filer och mappar på enheten. Resultatet skickas till [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Uppdatera antivirus | Kräver att enheten får [säkerhetsintelligensuppdateringar](https://go.microsoft.com/fwlink/?linkid=2149926) för skydd mot skadlig programvara. |
| Starta om enheten | Tvingar en Windows 10-enhet att starta om inom fem minuter.<br><br>**VIKTIGT!** Enhetens ägare eller användaren meddelas inte automatiskt om omstarten och kan förlora osparat arbete. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Hantera identifieringar av hot i Microsoft Endpoint Manager

Du kan använda Microsoft Endpoint Manager för att hantera identifiering av hot. Windows 10-enheter måste [vara registrerade i Intune (en del](/mem/intune/enrollment/windows-enrollment-methods) av Microsoft Endpoint Manager).

1. Gå till administrationscentret för Microsoft Endpoint Manager vid <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> och logga in.

2. Välj Slutpunktssäkerhet i **navigeringsfönstret.**

3. Under **Hantera** väljer du **Antivirus.** Du ser flera flikar, till exempel Sammanfattning , Slutpunkter med **fel i Windows 10** och **Windows 10 upptäckte skadlig programvara.**

4. Granska informationen på de tillgängliga flikarna och vidta sedan de åtgärder som behövs.

Anta till exempel att enheter listas på fliken skadlig programvara i **Windows 10.** När du väljer en enhet finns vissa åtgärder tillgängliga, till exempel Starta om **,** **Snabbsökning,** **Fullständig** sökning, **Synkronisera** eller **Uppdatera signaturer**. Välj en åtgärd för enheten.

I följande tabell beskrivs de åtgärder som kan visas i Microsoft Endpoint Manager.<br><br>

| Åtgärd | Beskrivning |
|--|--|
| Starta om | Tvingar en Windows 10-enhet att starta om inom fem minuter.<br><br>**VIKTIGT!** Enhetens ägare eller användaren meddelas inte automatiskt om omstarten och kan förlora osparat arbete. |
| Snabbsökning | Startar en snabb antivirussökning på enheten med fokus på vanliga platser där skadlig programvara kan registreras, t.ex. registernycklar och kända startmappar i Windows. Resultatet skickas till [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Fullständig sökning | Startar en fullständig antivirussökning på enheten med fokus på vanliga platser där skadlig programvara kan registreras, och inklusive alla filer och mappar på enheten. Resultatet skickas till [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Synkronisera | Kräver att en enhet checkas in med Intune (en del av Microsoft Endpoint Manager). När enheten checkar in får enheten alla väntande åtgärder eller principer tilldelade till enheten. |
| Uppdatera signaturer | Kräver att enheten får [säkerhetsintelligensuppdateringar](https://go.microsoft.com/fwlink/?linkid=2149926) för skydd mot skadlig programvara. |

> [!TIP]
> Mer information finns i [Fjärråtgärder för enheter](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Så här skickar du in en fil för analys av skadlig programvara

Om du har en fil som du tror har missats eller felaktigt klassificerats som skadlig programvara kan du skicka filen till Microsoft för analys av skadlig programvara. Användare och IT-administratörer kan skicka en fil för analys. Besök [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .