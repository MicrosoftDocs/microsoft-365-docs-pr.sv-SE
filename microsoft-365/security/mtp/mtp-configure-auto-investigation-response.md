---
title: Konfigurera automatiserade undersökningar och svars funktioner i Microsoft 365 Defender
description: Konfigurera automatisk undersökning och svar med själv återställning i Microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: 5ba17c414b6f6470d2e9af14d1f484b435cb4f51
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846502"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Konfigurera automatiserade undersökningar och svars funktioner i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 Defender innehåller kraftfulla [automatiserade undersökningar och svars funktioner](mtp-autoir.md) som kan spara säkerhets arbets gruppen i stort sett tid och arbete. Med själv lagning kan de här funktionerna efterlikna de steg som en säkerhetsanalytiker vidtar för att undersöka och reagera på hot, bara snabbare och med större kapacitet att bygga ut. I den här artikeln beskrivs hur du konfigurerar automatisk undersökning och svar i Microsoft 365 Defender.

Följ de här stegen om du vill konfigurera automatiserade undersökningar och svars funktioner:

1. [Granska kraven](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Granska eller ändra automatiserings nivån för enhets grupper](#review-or-change-the-automation-level-for-device-groups).
3. [Granska säkerhets-och aviserings principer i Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Kontrol lera att Microsoft 365 Defender är aktiverat](#make-sure-microsoft-365-defender-is-turned-on).

Efter att du har ställt in allt kan du [Granska de pågående och slutförda åtgärderna i åtgärds centret](#review-pending-and-completed-actions-in-the-action-center). 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Förutsättningar för automatisk undersökning och svar i Microsoft 365 Defender

|Krav |Information |
|--|--|
|Abonnemangs krav |En av abonnemangen: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5-säkerhet<br/>-Microsoft 365 A5-säkerhet<br/>-Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>Se [licensierings kraven för Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Nätverks krav |- [Microsoft Defender för identitet](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) är aktiverat<br/>- [Säkerhets inställningar för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)<br/>- [Microsoft Cloud App-säkerhet integrerad med Microsoft Defender för identitet](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|System krav för Windows |-Windows 10, version 1709 eller senare installerad (se [Windows 10](https://docs.microsoft.com/windows/release-information/)-versions information) med följande skydds tjänster konfigurerade:<br/>- [Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Skydd för e-postinnehåll och Office-filer |[Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) konfigurerat |
|Behörigheter |-För att kunna konfigurera automatiserade undersökningar och svars funktioner måste du ha rollen global administratör eller säkerhets administratör tilldelad i antingen Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) eller i Microsoft 365 Admin Center ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>-För att få de behörigheter som krävs för att arbeta med automatiserade funktioner för undersökning och svar, till exempel granskning, godkännande eller avvisning av väntande åtgärder, se [nödvändiga behörigheter för åtgärds Center uppgifter](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Granska eller ändra automatiserings nivån för enhets grupper

Om automatiska utredningar körs och om reparations åtgärder vidtas automatiskt eller bara vid godkännande av dina enheter beror på vissa inställningar, till exempel organisationens enhets grup principer. Granska den automatiserings nivå som är inställd för dina enhets grup principer.

1. Gå till Microsoft Defender säkerhets Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) och logga in.

2. Gå till **Inställningar** för  >  **behörighets**  >  **enheter**. 

3. Granska din enhets grup principer. Titta i så fall på åtgärds **nivå** kolumnen. Vi rekommenderar att du använder **fullständig åtgärd automatiskt**.  Du kan behöva skapa eller redigera dina enhets grupper för att få den automatiserings nivå du vill ha. Om du vill ha hjälp med den här uppgiften kan du läsa följande artiklar:

   - [Så här åtgärdar du hot](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   
   - [Skapa och hantera enhets grupper](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Granska säkerhets-och aviserings principer i Office 365

Microsoft tillhandahåller inbyggda [aviserings principer](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) som hjälper dig att identifiera vissa risker. Dessa risker inkluderar behörigheter för Exchange-administratörer missbruk, skadlig program vara, potentiella externa och interna hot samt informations styrnings risker. Vissa larm kan utlösa [Automatisk undersökning och svar i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Kontrol lera att [Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) -funktionerna är korrekt konfigurerade.

Även om vissa larm och säkerhets principer kan utlösa automatiska utredningar vidtas inga reparations åtgärder automatiskt för e-post och innehåll. I stället väntar alla reparations åtgärder för e-post-och e-postinnehåll godkännande av din säkerhets åtgärds team i [Åtgärds centret](mtp-action-center.md).

Säkerhets inställningar i Office 365 hjälper till att skydda e-post och innehåll. Om du vill visa eller ändra de här inställningarna följer du anvisningarna för att [skydda mot hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

1. [https://security.microsoft.com/](https://security.microsoft.com/)Gå till **principer** för  >  **hotets skydd** i Microsoft 365 säkerhets Center ().

2. Kontrol lera att alla följande principer är konfigurerade. För att få hjälp och rekommendationer, se [skydda mot hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

   - [Skydd mot skadlig program vara (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Anti-nätfiske i Defender för Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Säkra bifogade filer (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Säkra länkar (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Anti-spam (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. Kontrol lera att [Microsoft Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) är aktiverat.

5. Kontrol lera att [Rensa automatiskt för e-](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) postskydd är aktivt. 

8. (Det här är valfritt.) Granska [aviserings principerna för Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) i Microsoft 365 Compliance Center ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Flera standard aviserings principer är i kategorin Threat Management. Vissa av dessa aviseringar kan utlösa automatisk undersökning och svar. Mer information finns i avsnittet [standard larm principer](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies).
 
## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Kontrol lera att Microsoft 365 Defender är aktiverat

1. Gå till Microsoft 365 säkerhets Center ( [https://security.microsoft.com](https://security.microsoft.com) ) och logga in.

2. Leta efter **händelser** , **Åtgärds Center** och **jakt** i navigerings fönstret, som visas i följande bild:

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP den":::

   - Om du ser **händelser** , **Åtgärds Center** och **jakt** är Microsoft 365 Defender aktiverat. Gå vidare till nästa procedur, [Granska eller ändra automatiserings nivån för enhets grupper](#review-or-change-the-automation-level-for-device-groups).

   - Om du inte *ser* **problem** , **Åtgärds center** eller **jakt** kanske Microsoft 365 Defender inte är aktiverat. I det här fallet fortsätter du till nästa steg.

3. I navigerings fönstret väljer du **Inställningar**  >  **Microsoft 365 Defender**. Kontrol lera att Microsoft 365 Defender är aktiverat. 

   Behöver du hjälp? Se [aktivera Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Granska väntande och slutförda åtgärder i åtgärds centret

När du har konfigurerat en automatisk undersökning och ett svar i Microsoft 365 Defender är nästa steg att besöka åtgärds centret ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ). Där kan du granska och godkänna väntande åtgärder och se åtgärds åtgärder som vidtogs automatiskt. 

[Gå till åtgärds Center](mtp-action-center.md).
