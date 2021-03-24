---
title: Hot som upptäcks av Microsoft Defender Antivirus
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Läs om hur Microsoft Defender Antivirus skyddar dina Windows-enheter mot programvaruhot, till exempel virus, skadlig programvara och spionprogram.
ms.openlocfilehash: 5fe55817018eeae49e6e41c95d93006b6f05ece0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052224"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Hot som upptäcks av Microsoft Defender Antivirus

Microsoft Defender Antivirus skyddar dina Windows-enheter mot programvaruhot, till exempel virus, skadlig programvara och spionprogram.

- Virus sprids vanligtvis genom att deras kod bifogas till andra filer på enheten eller i nätverket och kan leda till att smittade program fungerar felaktigt.
- Skadlig programvara omfattar skadliga filer, program och kod som kan orsaka skada och störa normal användning av enheter. Skadlig programvara kan också tillåta obehörig åtkomst, använda systemresurser, stjäla lösenord och kontoinformation, låsa ut dig från datorn och be om utpressningstrojan och mycket mer.
- Spionprogram samlar in data, till exempel webbaktivitet, och skickar data till fjärrservrar.
 
För att tillhandahålla skydd mot hot använder Microsoft Defender Antivirus flera metoder. De här metoderna omfattar moln levererat skydd, realtidsskydd och dedikerade skyddsuppdateringar.

- Moln levererat skydd bidrar till att tillhandahålla omedelbar identifiering och blockering av nya och nya hot.
- I "always-on"-skanning används övervakning av filer och processer och andra tekniker (även kallat *realtidsskydd).*
- Dedikerade skyddsuppdateringar baseras på maskininlärning, mänsklig och automatiserad analys av stora data samt ingående forskning om ändliga hot. 

Mer information om skadlig programvara och Microsoft Defender Antivirus finns i följande artiklar: 

- [Förstå skadlig programvara & andra hot](/windows/security/threat-protection/intelligence/understanding-malware)
- [Hur Microsoft identifierar skadlig programvara och potentiellt oönskade program](/windows/security/threat-protection/intelligence/criteria)
- [Nästa generations skydd i Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Vad händer när en antiviruslösning som inte är en Microsoft-lösning används? 

Microsoft Defender Antivirus är en del av operativsystemet och är aktiverat på enheter med Windows 10. Men om du använder en antiviruslösning som inte är en Microsoft-antiviruslösning och du inte använder [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)för slutpunkt så inaktiveras Microsoft Defender Antivirus automatiskt.  

I inaktiverat läge kan användare och kunder fortfarande använda Microsoft Defender Antivirus för schemalagda genomsökningar eller på begäran för att identifiera hot. Men Microsoft Defender Antivirus kommer inte längre att:

- kan användas som standardantivirusprogram.
- söker aktivt igenom filer efter hot.
- åtgärda eller lösa hot.

Om du avinstallerar antiviruslösningen som inte är en Microsoft-antiviruslösning förs Microsoft Defender Antivirus automatiskt in i aktivt läge för att skydda dina Windows-enheter mot hot.

> [!TIP]
> - Om du använder Microsoft 365 bör du överväga att använda Microsoft Defender Antivirus som din primära antiviruslösning. Integrering kan ge bättre skydd. Se [Bättre tillsammans: Microsoft Defender Antivirus och Office 365.](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)
> - Se till att hålla Microsoft Defender Antivirus uppdaterat, även om du använder en antiviruslösning som inte är en Microsoft-lösning.

## <a name="what-to-expect-when-threats-are-detected"></a>Vad du kan förvänta dig när hot upptäcks

När hot upptäcks av Microsoft Defender Antivirus inträffar följande:

- Användarna får [aviseringar i Windows.](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e) 
- Identifieringar visas i [Windows-säkerhetsappen](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) på sidan **Skyddshistorik.**  
- Om du har skyddat dina Windows [10-enheter](secure-win-10-pcs.md) och registrerat dem i [Intune](/mem/intune/enrollment/windows-enrollment-methods), och din organisation har 800 eller färre registrerade enheter, visas identifieringar av hot och information i administrationscentret för  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> på sidan Hot och **antivirusprogram,** som du kommer åt från **Microsoft Defender Antivirus-kortet** på startsidan (eller från navigeringsfönstret genom att välja Hälsohot  >  **& antivirus).**

    Om din organisation har fler än 800 enheter registrerade i Intune uppmanas du att visa identifieringar av hot och insikter från [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) i stället för från sidan Hot och **antivirusprogram.**
 
    > [!NOTE]
    > **Microsoft Defender Antivirus-kortet** och sidan Hot och **antivirusprogram distribueras** i faser, så du kanske inte har direkt åtkomst till dem.

I de flesta fall behöver användarna inte vidta någon ytterligare åtgärd. När en skadlig fil eller ett program hittas på en enhet blockerar Microsoft Defender Antivirus den och förhindrar att den körs. Dessutom läggs nya hot till i antivirus- och antimalwaremotorn så att även andra enheter och användare skyddas.  

Om det finns en åtgärd som användaren måste vidta, till exempel att godkänna borttagningen av en skadlig fil, ser de det i meddelandet som de får. Mer information om åtgärder som Microsoft Defender Antivirus vidtar för en användares räkning eller åtgärder som användare kan behöva vidta finns i [Skyddshistorik.](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708) Mer information om hur du hanterar identifieringar av hot som IT-personal/administratör finns i Granska [identifierade hot och vidta åtgärder.](review-threats-take-action.md)

Om du vill veta mer om olika hot kan du <a href="https://www.microsoft.com/wdsi/threats" target="_blank">besöka webbplatsen med Microsofts säkerhetsinformationshot,</a>där du kan utföra följande åtgärder: 

- Visa aktuell information om de viktigaste hoten.
- Visa de senaste hoten för en viss region.
- Sök på encyclopedia med hot om du vill ha information om ett specifikt hot.

## <a name="related-content"></a>Relaterat innehåll

[Skydda Windows 10-enheter](secure-windows-10-devices.md) (artikel)\
[Utvärdera Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artikel)\
[Så här aktiverar du antivirusskydd i realtid och moln levererat](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (artikel)\
[Så här aktiverar och använder du Microsoft Defender Antivirus från Windows-säkerhetsappen](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (artikel)\
[Så här aktiverar du Microsoft Defender Antivirus med hjälp av Grupprincip](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artikel)\
[Hur du uppdaterar dina antivirusdefinitioner](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artikel)\
[Skicka skadlig programvara och icke-skadlig programvara till Microsoft för analys](/microsoft-365/security/defender-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artikel)
