---
title: Konfigurera funktioner för automatisk undersökning och svar i Microsoft 365 Defender
description: Konfigurera automatisk undersökning och svar med självbetjäning i Microsoft 365 Defender
search.appverid: MET150
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 685c23f4e8daac4f00e0bbd90dcaca9a80703559
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696520"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Konfigurera funktioner för automatisk undersökning och svar i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender innehåller kraftfulla [automatiska undersöknings- och svarsfunktioner](m365d-autoir.md) som kan spara mycket tid och arbete från ditt säkerhetsteam. Med [självbetjäning](m365d-autoir.md#how-automated-investigation-and-self-healing-works)imiterar de här funktionerna de steg en säkerhetsanalytiker skulle vidta för att undersöka och reagera på hot, bara snabbare och med större skalningsmöjligheter.

I den här artikeln beskrivs hur du konfigurerar automatisk undersökning och svar i Microsoft 365 Defender med följande steg:

1. [Granska förutsättningarna](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Granska eller ändra automationsnivån för enhetsgrupper](#review-or-change-the-automation-level-for-device-groups).
3. [Granska dina principer för säkerhet och aviseringar i Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Kontrollera att Microsoft 365 Defender är aktiverat](#make-sure-microsoft-365-defender-is-turned-on).

När du är konfigurerad kan du sedan [visa och hantera åtgärder i Åtgärdscenter.](m365d-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Krav för automatiserad undersökning och svar i Microsoft 365 Defender

<br>

****

|Krav|Information|
|---|---|
|Prenumerationskrav|En av dessa prenumerationer: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E3 med Microsoft 365 E5 Security tillägg</li><li>Microsoft 365 A3 med Microsoft 365 tillägg för A5-säkerhet</li><li>Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5</li></ul> <p> Se [Microsoft 365 Defender-licenskrav](./prerequisites.md#licensing-requirements).|
|Nätverkskrav|<ul><li>[Microsoft Defender för identitet](/azure-advanced-threat-protection/what-is-atp) aktiverad</li><li>[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) konfigurerad</li><li>[Microsoft Defender för identitetsintegrering](/cloud-app-security/mdi-integration)</li></ul>|
|Windows maskinkrav|<ul><li>Windows 10, version 1709 eller senare installerade (se [Windows 10 versionsinformation](/windows/release-information/))</li><li>Följande skyddstjänster för hot har konfigurerats:<ul><li>[Microsoft Defender för Endpoint](../defender-endpoint/configure-endpoints.md)</li><li>[Microsoft Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|Skydd för e-postinnehåll och Office filer|[Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) konfigurerad|
|Behörigheter|Om du vill konfigurera funktioner för automatisk undersökning och svar måste du ha rollen Global administratör eller Säkerhetsadministratör tilldelad i antingen Azure Active Directory () eller <https://portal.azure.com> i Microsoft 365-administrationscentret ( <https://admin.microsoft.com> ). <p> Information om hur du får de behörigheter som krävs för att arbeta med automatiska undersöknings- och svarsfunktioner, till exempel att granska, godkänna eller avvisa väntande åtgärder, finns i Obligatoriska behörigheter för aktiviteter [i Åtgärdscenter.](m365d-action-center.md#required-permissions-for-action-center-tasks)|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Granska eller ändra automationsnivån för enhetsgrupper

Om automatiserade undersökningar körs och om åtgärder vidtas automatiskt eller bara vid godkännande för dina enheter är beroende av vissa inställningar, till exempel organisationens enhetsgruppsprinciper. Granska den konfigurerade automationsnivån för enhetens gruppprinciper.

1. Gå till Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) och logga in.
2. Gå till **Inställningar**  >  **Grupper med** behörigheter på  >  **enheter**.
3. Granska principer för din enhetsgrupp. Titta särskilt på **kolumnen Åtgärdsnivå.** Vi rekommenderar att **du använder Fullständigt – åtgärda hot automatiskt.**  Du kan behöva skapa eller redigera enhetsgrupper för att få den automatisering du vill ha. Om du behöver hjälp med den här uppgiften kan du läsa följande artiklar:
   - [Hur hot åtgärdas](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Skapa och hantera enhetsgrupper](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Granska säkerhetsprinciperna och aviseringsprinciperna i Office 365

Microsoft tillhandahåller inbyggda [aviseringsprinciper som](../../compliance/alert-policies.md) hjälper till att identifiera vissa risker. Dessa risker omfattar Exchange administratörsbehörighet, missbruk av skadlig programvara, potentiella externa och interna hot och risker för informationsstyrning. Vissa aviseringar kan utlösa [automatisk undersökning och svar i Office 365](../office-365-security/office-365-air.md). Se till att [Defender för Office 365](../office-365-security/defender-for-office-365.md) är korrekt konfigurerade.

Även om vissa varningar och säkerhetsprinciper kan utlösa automatiska undersökningar, vidtas inga åtgärder *automatiskt för e-post och innehåll.* I stället väntar alla åtgärder för e-post- och e-postinnehåll på godkännande från säkerhetsåtgärdsteamet i [Åtgärdscenter.](m365d-action-center.md)

Säkerhetsinställningarna i Office 365 skydda e-post och innehåll. Om du vill visa eller ändra dessa inställningar följer du [vägledning i Skydda mot hot.](../office-365-security/protect-against-threats.md)

1. I säkerhetscentret Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) går du till **Principer & Principer för** hot mot \> **regler.**
2. Kontrollera att alla följande principer har konfigurerats. Mer information om hur du får hjälp och [rekommendationer finns i Skydda mot hot.](/microsoft-365/security/office-365-security/protect-against-threats)
   - [Skydd mot skadlig programvara)](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [Skydd mot nätfiske)](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [Säkra bifogade filer](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Säkra länkar](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Skräppostskydd](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)
3. Se till [att Microsoft Defender Office 365 för SharePoint, OneDrive och Microsoft Teams](../office-365-security/protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on) är aktiverat.
4. Se till [att automatisk rensning med nolltimmar för e-postskydd](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) är i kraft.
5. (Det här steget är valfritt.) Granska dina [Office 365 principer för](../../compliance/alert-policies.md) avisering i Microsoft 365 kompatibilitetscenter [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) (). Flera standardaviseringsprinciper finns i kategorin Hothantering. Vissa av dessa varningar kan utlösa automatisk undersökning och svar. Mer information finns i [Standardaviseringsprinciper](../../compliance/alert-policies.md#default-alert-policies).

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Se till Microsoft 365 Defender är aktiverat

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP på":::

1. Logga in på Microsoft 365 säkerhetscenter ( [https://security.microsoft.com](https://security.microsoft.com) ).
2. I navigeringsfönstret letar du efter **Incidenter**, **Åtgärdscenter** och **Letar**, som visas i bilden ovan.
   - Om Du ser **Incidenter**, **Åtgärdscenter** **och** Microsoft 365 är Defender aktiverat. Läs avsnittet [Granska eller ändra automatiseringsnivån för enhetsgrupper i](#review-or-change-the-automation-level-for-device-groups) den här artikeln.
   - Om du inte *ser* **Incidenter,** **Åtgärdscenter** eller Microsoft 365 kanske Defender inte är aktiverat. I det här fallet [går du till Åtgärdscenter](m365d-action-center.md)).
3. Välj Defender i **Inställningar**  >  **Microsoft 365**. Kontrollera att Microsoft 365 Defender är aktiverat.

> [!TIP]
> Behöver du hjälp? Se [Aktivera Microsoft 365 Defender](m365d-enable.md).

## <a name="next-steps"></a>Nästa steg

- [Åtgärdsåtgärder i Microsoft 365 Defender](m365d-remediation-actions.md)
- [Besök åtgärden centret](m365d-action-center.md)
