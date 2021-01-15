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
description: Lär dig hur Microsoft Defender Antivirus skyddar dina Windows-enheter från program varu hot, till exempel virus, skadlig program vara och spionprogram.
ms.openlocfilehash: 1653aef6967cdf76e6e19acda158fb29758280a8
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870905"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Hot som upptäcks av Microsoft Defender Antivirus

Microsoft Defender Antivirus skyddar dina Windows-enheter från program varu hot, till exempel virus, skadlig program vara och spionprogram.

- Virus sprider sig normalt genom att koppla sin kod till andra filer på din enhet eller ditt nätverk och kan göra att infekterade program inte fungerar som de ska.
- Skadlig program vara inkluderar skadliga filer, program och kod som kan orsaka skada och störa normal användning av enheter. Dessutom kan skadlig program vara tillåta obehörig åtkomst, använda system resurser, stjäla lösen ord och konto information, låsa ut dig från datorn och be om utpressning och mer.
- Spionprogram samlar in data, till exempel Webbs öknings aktivitet, och skickar data till fjärrservrar.
 
För att skydda hotet kan Microsoft Defender Antivirus använda flera olika sätt. Dessa metoder inkluderar molnbaserade skydd, real tids skydd och dedikerade skydds uppdateringar.

- Molnbaserade skydd ger snabb identifiering och blockering av nya och framväxande hot.
- Genomsökning alltid använder fil-och process beteende övervakning och andra tekniker (kallas även för *real tids skydd*).
- Dedikerade skydds uppdateringar baseras på dator inlärning, mänsklig och automatiserad data analys, och djupgående hot motstånds forskningen. 

Om du vill veta mer om skadlig program vara och Microsoft Defender Antivirus kan du läsa följande artiklar: 

- [Förstå skadlig program vara & andra hot](/windows/security/threat-protection/intelligence/understanding-malware)
- [Så här identifieras skadlig kod och potentiellt oönskade program](/windows/security/threat-protection/intelligence/criteria)
- [Nästa generations skydd i Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Vad händer när en lösning som inte tillhör Microsoft Antivirus används? 

Microsoft Defender Antivirus är en del av operativ systemet och är aktiverat på enheter med Windows 10. Om du använder en lösning som inte kommer från Microsoft och du inte använder [Microsoft Defender för slut punkten](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)hamnar Microsoft Defender Antivirus automatiskt i inaktiverat läge.  

I inaktiverat läge kan användarna och kunderna ändå använda Microsoft Defender Antivirus för schemalagda eller på begäran för att identifiera hot. men Microsoft Defender Antivirus kommer inte längre:

- används som standard antivirus program.
- Sök efter hot i filer.
- åtgärda eller lös, hot.

Om du avinstallerar en lösning för antivirus program som inte kommer från Microsoft öppnas Microsoft Defender Antivirus automatiskt för att skydda dina Windows-enheter mot hot.

> [!TIP]
> - Om du använder Microsoft 365 kan du använda Microsoft Defender Antivirus som din primära antivirus lösning. Integreringen kan ge bättre skydd. Se [bättre tillsammans: Microsoft Defender Antivirus och Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Se till att Microsoft Defender Antivirus är uppdaterat, även om du använder en lösning som inte tillhör Microsoft Antivirus.

## <a name="what-to-expect-when-threats-are-detected"></a>Vad du kan förvänta dig när hot identifieras

När hot identifieras av Microsoft Defender Antivirus händer följande:

- Användare får [aviseringar i Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- Identifieringar visas i Windows- [säkerhetsprogrammet](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) på sidan **skydds historik** .  
- Om du har [skyddat dina Windows 10-enheter](secure-win-10-pcs.md) och [registrerat dem i Intune](/mem/intune/enrollment/windows-enrollment-methods), och din organisation har 800 eller färre registrerade enheter visas hot identifieringar och insikter i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrations centret för Microsoft 365</a> på sidan **hot och Antivirus** , som du kommer åt från **Microsoft Defender Antivirus** -kortet på **Start** sidan (eller från navigerings fönstret genom att välja **hälso skydd**  >  **& antivirus program**).

    Om organisationen har fler än 800 enheter registrerade i Intune uppmanas du att Visa hot identifieringar och insikter från [Microsoft slut punkts hanteraren](/mem/endpoint-manager-overview) i stället för från sidan **hot och Antivirus** .
 
    > [!NOTE]
    > **Microsoft Defender Antivirus** -kortet och **Antivirus** sidan är distribuerade i faser, så du kanske inte har omedelbar åtkomst till dem.

I de flesta fall behöver användarna inte vidta några ytterligare åtgärder. När en skadlig fil eller ett program identifieras på en enhet, blockerar Microsoft Defender Antivirus den och förhindrar att den körs. Dessutom kan nyligen upptäckta hot läggas till i Antivirus-och antimalware-motorn så att andra enheter och användare skyddas.  

Om en åtgärd krävs, till exempel för att godkänna borttagningen av en skadlig fil, kommer de att se det i meddelandet som tas emot. Om du vill veta mer om åtgärder som Microsoft Defender Antivirus tar på en användares räkning eller vilka åtgärder användarna kan behöva vidta kan du läsa mer i [skydds historiken](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Information om hur du hanterar Threat-identifieringar som IT-tekniker och-administratörer finns i [Granska upptäckta hot och vidta åtgärder](review-threats-take-action.md).

Om du vill veta mer om olika hot kan du gå till <a href="https://www.microsoft.com/wdsi/threats" target="_blank">webbplatsen Microsoft Security Intelligence Threats</a>, där du kan utföra följande åtgärder: 

- Visa aktuell information om de vanligaste hoten.
- Visa de senaste hoten för ett visst område.
- Sök i Threat Encyclopedia efter information om ett specifikt hot.

## <a name="related-content"></a>Relaterat innehåll

[Skydda Windows 10-enheter](secure-windows-10-devices.md) (artikel) \
[Utvärdera Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artikel) \
[Så aktiverar du antivirus skydd i real tid och Cloud-levererat](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (artikel) \
[Hur du aktiverar och använder Microsoft Defender Antivirus från Windows-säkerhetsprogrammet](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (artikeln) \
[Aktivera Microsoft Defender Antivirus med grup princip](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artikel) \
[Så här uppdaterar du dina antivirus definitioner](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artikel) \
Så [här skickar du skadlig program vara och icke-malware till Microsoft för analys](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artikel)