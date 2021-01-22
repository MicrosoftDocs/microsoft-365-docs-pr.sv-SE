---
title: Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender
description: Konfigurera automatisk undersökning och svar med self-microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 123b3b5f8514e9b3914b98178191d60e78280991
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930324"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 Defender innehåller kraftfulla [funktioner för](mtp-autoir.md) automatisk undersökning och svar som kan spara mycket tid och arbete för ditt säkerhetsteam. Med självbild kan dessa funktioner efterlikna de steg en säkerhetsanalytiker skulle vidta för att undersöka och reagera på hot, bara snabbare och med fler skalningsmöjligheter. I den här artikeln beskrivs hur du konfigurerar automatisk undersökning och svar i Microsoft 365 Defender.

Om du vill konfigurera automatisk undersökning och svarsfunktioner gör du så här:

1. [Granska förutsättningarna.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Granska eller ändra automatiseringsnivån för enhetsgrupper.](#review-or-change-the-automation-level-for-device-groups)
3. [Granska principer för säkerhet och aviseringar i Office 365.](#review-your-security-and-alert-policies-in-office-365)
4. [Kontrollera att Microsoft 365 Defender är aktiverat.](#make-sure-microsoft-365-defender-is-turned-on)

När du är klar går du sedan igenom [väntande och slutförda åtgärder i Åtgärdscenter.](#review-pending-and-completed-actions-in-the-action-center)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Förutsättningar för automatiserad undersökning och svar i Microsoft 365 Defender

|Krav |Information |
|--|--|
|Prenumerationskrav |En av prenumerationerna: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E5– säkerhet</li><li>Microsoft 365 A5 – säkerhet</li><li>Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5</li></ul><p> Se [licenskraven för Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)|
|Nätverkskrav |<ul><li>[Microsoft Defender för identitet aktiverat](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)</li><li>[Microsoft Cloud App-säkerhet](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) konfigurerad</li><li>[Microsoft Defender för identitetsintegrering](https://docs.microsoft.com/cloud-app-security/mdi-integration)</li></ul>|
|Maskinkrav för Windows |Windows 10, version 1709 eller senare installerat (se versionsinformationen för [Windows 10)](https://docs.microsoft.com/windows/release-information/)med följande skyddstjänster konfigurerade:<ul><li>[Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</li><li>[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul>|
|Skydd för e-postinnehåll och Office-filer |[Konfigurerade Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|Behörigheter |<ul><li>Om du vill konfigurera automatisk undersökning och svarsfunktioner måste du ha rollen Global administratör eller säkerhetsadministratör tilldelad i antingen Azure Active Directory () eller i administrationscentret för [https://portal.azure.com](https://portal.azure.com) Microsoft 365 [https://admin.microsoft.com](https://admin.microsoft.com) ().</li><p><li>Information om hur du får de behörigheter som krävs för att arbeta med automatiserad undersökning och svarsfunktioner, till exempel att granska, godkänna eller avvisa väntande åtgärder, finns i Behörigheterna som krävs för uppgifter i [Åtgärdscenter.](mtp-action-center.md#required-permissions-for-action-center-tasks)</li></ul>|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Granska eller ändra automatiseringsnivån för enhetsgrupper

Om automatiserade undersökningar körs och om åtgärder vidtas automatiskt eller bara vid godkännande för dina enheter beror på vissa inställningar, till exempel företagets enhetsgruppsprinciper. Granska automationsnivåuppsättningen för enhetens gruppprinciper.

1. Gå till Microsoft Defender Säkerhetscenter [https://securitycenter.windows.com](https://securitycenter.windows.com) () och logga in.

2. Gå till **Grupper för**  >  **inställningarsbehörigheter** för  >  **enheter.**

3. Granska principer för din enhetsgrupp. Titta särskilt på **kolumnen åtgärdsnivå.** Vi rekommenderar att **du använder Fullständigt – åtgärda hot automatiskt.**  Du kan behöva skapa eller redigera enhetsgrupper för att få den automatiseringsnivå du vill ha. Om du behöver hjälp med den här uppgiften kan du läsa följande artiklar:

   - [Hur hot åtgärdas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Skapa och hantera enhetsgrupper](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Granska principer för säkerhet och aviseringar i Office 365

Microsoft tillhandahåller inbyggda [aviseringsprinciper som](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) hjälper dig att identifiera vissa risker. Dessa risker omfattar missbruk av behörigheter från Exchange-administratörer, skadlig programvara, potentiella externa och interna hot och informationsstyrningsrisker. Vissa aviseringar kan utlösa [automatisk undersökning och svar i Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Kontrollera att funktionerna [i Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) är korrekt konfigurerade.

Även om vissa varningar och säkerhetsprinciper kan utlösa automatiska undersökningar vidtas inga åtgärder automatiskt för e-post och innehåll. I stället väntar alla åtgärder för e-post- och e-postinnehåll på godkännande från teamet för säkerhetsåtgärder i [Åtgärdscenter.](mtp-action-center.md)

Säkerhetsinställningar i Office 365 hjälper till att skydda e-post och innehåll. Om du vill visa eller ändra de här inställningarna följer du [vägsvägledning i Skydda mot hot.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

1. Gå till Skydd mot hot i Microsoft 365 [https://security.microsoft.com/](https://security.microsoft.com/)   >  **Säkerhetscenter**( ).

2. Kontrollera att alla följande principer är konfigurerade. Mer information om hur du får hjälp och [rekommendationer finns i Skydda mot hot.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

   - [Skydd mot skadlig programvara (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Skydd mot nätfiske i Defender för Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Säkra bifogade filer (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Säkra länkar (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Skräppostskydd (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection)

3. Kontrollera att [Microsoft Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) är aktiverat.

4. Kontrollera att [automatisk rensning utan timme för e-postskydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) är i kraft.

5. (Det här är valfritt.) Granska [aviseringsprinciperna för Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) i Efterlevnadscenter för Microsoft 365 [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) (). Flera standardprinciper för aviseringar finns i kategorin Hothantering. Vissa av dessa varningar kan utlösa automatisk undersökning och svar. Mer information finns i [Standardaviseringsprinciper.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Kontrollera att Microsoft 365 Defender är aktiverat

1. Gå till Microsoft 365 säkerhetscenter ( [https://security.microsoft.com](https://security.microsoft.com) ) och logga in.

2. Leta efter Incidenter, **Åtgärdscenter** **och** Sök i navigeringsfönstret, enligt följande bild:

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP på":::

   - Om du ser **Incidenter,** **Åtgärdscenter** **och Jagning** är Microsoft 365 Defender aktiverat. Läs proceduren, [granska eller ändra automatiseringsnivån för enhetsgrupper](#review-or-change-the-automation-level-for-device-groups) (i den här artikeln).

   - Om du inte *ser* **Incidenter,** **Åtgärdscenter** eller **Jagning** kanske Microsoft 365 Defender inte är aktiverat. I det här fallet går du vidare till nästa steg[(Granska väntande och slutförda åtgärder](#review-pending-and-completed-actions-in-the-action-center)i den här artikeln).

3. Välj Inställningar Microsoft   >  **365 Defender i navigeringsfönstret.** Kontrollera att Microsoft 365 Defender är aktiverat.

   Behöver du hjälp? Se [Aktivera Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Granska väntande och slutförda åtgärder i Åtgärdscenter

När du har konfigurerat automatisk undersökning och svar i Microsoft 365 Defender är nästa steg att gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) (). Där kan du granska och godkänna väntande åtgärder och se åtgärder som har vidtagits automatiskt eller manuellt.

[Besök Åtgärdscenter.](mtp-action-center.md)
