---
title: Använda känslighetsetiketter i Office-appar
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Information för IT-administratörer om hur du hanterar känslighetsetiketter i Office-appar för dator, mobila enheter och webben.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3da3d971a1ef55d343ac1b61e6457981022c4c92
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770391"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Använda känslighetsetiketter i Office-appar

>*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

När du har [publicerat](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) känslighetsetiketter från Microsoft 365 Efterlevnadscenter eller motsvarande etiketteringscenter kommer de att visas i Office-appar för användare för att klassificera och skydda data när den skapas eller redigeras.

Använd informationen i den här artikeln för att hjälpa dig att hantera känslighetsetiketter i Office-appar. Identifiera exempelvis de lägsta versioner av appar som du behöver för att stödja inbyggd etikettering och förstå interaktionen med Azure Information Protection enhetliga etiketteringsklient och kompatibilitet med andra program och tjänster.

## <a name="labeling-client-for-desktop-apps"></a>Etiketteringsklient för datorprogram

Om du vill använda känslighetsetiketter som är inbyggda i Office datorprogram för Windows och Mac måste du använda en prenumerationsversion av Office. Den här etiketteringsklienten stöder inte fristående versioner av Office, till exempel Office 2016 eller Office 2019.

Om du vill använda känslighetsetiketter med dessa fristående versioner av Office på Windows-datorer installerar du [Azure Information Protection enhetlig etiketteringsklient](/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Stöd för funktioner för känslighetsetiketter i program

Följande tabeller innehåller för varje funktion den Office-version du behöver för att stödja känslighetsetiketter med hjälp av inbyggd etikettering. Eller om etikettfunktionerna är offentliga förhandsversioner eller under granskning för en kommande version. Använd [översikt för Microsoft 365](https://aka.ms/MIPC/Roadmap) för mer information om kommande versioner.

Nya versioner av Office-program blir tillgängliga vid olika tidpunkter för olika uppdateringskanaler. Mer information, inklusive hur du konfigurerar uppdateringskanalen så att du kan testa en ny etiketteringsfunktion som du är intresserad av finns i [Översikt över uppdateringskanaler för Microsoft 365-applikationer](/DeployOffice/overview-update-channels). Nya funktioner som är privata förhandsversioner tas inte med i tabellen men du kan eventuellt ansluta dig till dessa förhandsversioner genom att ansluta organisationen till det privata [förhandsversionsprogrammet för Microsoft Information Protection](https://aka.ms/mip-preview).

> [!NOTE]
> Namnen på uppdateringskanalerna för Office-apparna har nyligen ändrats. Till exempel är Månatlig kanal nu Aktuell kanal och Office Insider är nu Beta-kanal. Mer information finns i [Ändringar för uppdateringskanaler för Microsoft 365-applikationer](/deployoffice/update-channels-changes).

Office för iOS och Office för Android: Känslighetsetiketter är inbyggda i [Office-appen](https://www.microsoft.com/sv-SE/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

Ytterligare funktioner är tillgängliga när du installerar Azure Information Protection enhetlig etiketteringsklient som endast kan köras på Windows-datorer. Mer information finns i [Jämför etiketteringsklienter för Windows-datorer](/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Funtioner för känslighetsetikett i Word, Excel och PowerPoint

Siffrorna som visas är den lägsta Office-programversion som krävs för varje funktion.

|Funktion                                                                                                        |Windows |Mac |iOS    |Android      |Webb                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Använda, ändra eller ta bort etiketter manuellt](https://support.microsoft.com/sv-SE/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Välj till](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Använda har standardetikett](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Välj till](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Kräva en justering för att ändra en etikett](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Välj till](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Ange hjälplänk till en anpassad hjälpsida](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Välj till](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Markera innehållet](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Välj till](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Dynamiska markeringar med variabler](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | Under granskning |
|[Tilldela behörigheter nu](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Ja – Välj till](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Låt användare tilldela behörigheter: <br /> – Fråga användare](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | Under granskning   | Under granskning         | Under granskning                                                        |
|[Granska etikettrelaterad användaraktivitet](data-classification-activity-explorer.md)                      | 2011+ | 16.43+ | 2.46+ | Lansering: 16.0.13628+ | Ja <sup>\*</sup>                                                        |
|[Kräva att användare använder en etikett för sin e-post och dokument](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+             | Lansering: 16.45+         | Lansering: 2.47+ | 16.0.13628+ | [Ja – Välj till](sensitivity-labels-sharepoint-onedrive-files.md)                                            
|[Använda en känslighetsetikett för innehåll automatiskt](apply-sensitivity-label-automatically.md)                    | 2009+                                  | Lansering: 16.44+ | Under granskning | Under granskning | [Ja – Välj till](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Stöd för samtidig redigering och spara automatiskt](sensitivity-labels-coauthoring.md) för etiketterade och krypterade dokument | Förhandsversion: [Aktuell kanal (förhandsversion)](https://office.com/insider) | Förhandsversion: [Aktuell kanal (förhandsversion)](https://office.com/insider) | Under granskning | Under granskning | [Ja – Välj till](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Fotnot:**

<sup>\*</sup> För närvarande innehåller inte justeringstext för att ta bort en etikett eller sänka klassificeringsnivån

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funktioner för känslighetsetiketter i Outlook

Siffrorna som visas är den lägsta Office-programversion som krävs för varje funktion.

|Funktion                                                                                                        |Outlook för Windows |Outlook för Mac |Outlook för iOS |Outlook för Android |Outlook på webben |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Använda, ändra eller ta bort etiketter manuellt](https://support.microsoft.com/sv-SE/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Använda har standardetikett](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Kräva en justering för att ändra en etikett](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Ange hjälplänk till en anpassad hjälpsida](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Markera innehållet](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Dynamiska markeringar med variabler](#dynamic-markings-with-variables)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Tilldela behörigheter nu](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Låt användare tilldela behörigheter: <br /> – Vidarebefordra inte](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Ja               |
|[Låt användare tilldela behörigheter: <br /> – endast kryptering](encryption-sensitivity-labels.md#let-users-assign-permissions)  |2011+ | 16.48+ <sup>\*</sup> | 4.2112.0+  | 4.2112.0+ | Ja |
|[Kräva att användare använder en etikett för sin e-post och dokument](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+                        | 16.43+ <sup>\*</sup>                    | 4.2111+            | 4.2111+                | Ja                |
|[Granska etikettrelaterad användaraktivitet](data-classification-activity-explorer.md) | 2011+ | Under granskning | Under granskning           | Under granskning               | Under granskning |
|[Använda en känslighetsetikett för innehåll automatiskt](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+ <sup>\*</sup>                    | Under granskning           | Under granskning               | Ja |
|[Olika inställningar för standardetikett och obligatorisk etikettering](#outlook-specific-options-for-default-label-and-mandatory-labeling)                    | 2105+                      | 16.43.1108+ <sup>\*</sup>                   | 4.2111+           | 4.2111+               | Ja |
|

**Fotnoter:**

<sup>\*</sup> Kräver [nya Outlook för Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office inbyggda etiketteringsklient och andra etiketteringslösningar

Den inbyggda etiketteringsklienten för Office laddar ned känslighetsetiketter och principinställningar för känslighetsetiketter från följande administrationscenter:

- Microsoft 365 Efterlevnadscenter
- Säkerhets- och efterlevnadscenter för Office 365 (äldre adminportal)

Om du vill använda den inbyggda etiketteringsklienten för Office måste du ha en eller flera [etikettprinciper publicerade](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) till användare från något av administratörscenter i listan och en [version av Office som stöds](#support-for-sensitivity-label-capabilities-in-apps).

Om båda dessa villkor uppfylls, men du måste inaktivera den inbyggda ettiketteringsklienten för Office, använder du följande grupprincipinställning:

1. Gå till **Användarkonfiguration/Administrativa mallar/Microsoft Office 2016/Säkerhetsinställningar**.

2. Ställ **Använd funktionen Känslighet i Office om du vill använda och visa känslighetsetiketter** till **0**. 
 
Använd denna inställning med hjälp av Grupprincip eller genom att använda [principtjänst för Office-moln](/DeployOffice/overview-office-cloud-policy-service). Inställningen börjar gälla när Office-programmen startas om.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office inbyggda ettiketteringsklient och Azure Information Protection-klienten

Om användarna har [Azure Information Protection-klienten installerad](/azure/information-protection/rms-client/aip-clientv2), inaktiveras den inbyggda etiketteringsklienten som standard i Office-apparna. 

Om du vill använda inbyggd etikettering istället för Azure Information Protection-klienten för Office-appar rekommenderar vi att du använder grupprincipinställningen **Lista över hanterade tillägg** enligt informationen i [Inga tillägg läses in på grund av grupprincipinställningar för Office 2013- och Office 2016-program](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off).

I Microsoft Word 2016, Excel 2016, PowerPoint 2016 och Outlook 2016 anger du följande programmatisk identifierare (ProgID) för Azure Information Protection-klienten och ställer in alternativet till **0: Tillägget är alltid inaktiverat (blockerat)**

|Program  |ProgID  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 


Använd denna inställning med hjälp av Grupprincip eller genom att använda [principtjänst för Office-moln](/DeployOffice/overview-office-cloud-policy-service).

> [!NOTE]
> Om du använder grupprincipinställningen **Använd funktionen Känslighet i Office för att använda och visa känslighetsetiketter** och ange denna till **1**, kan det finnas vissa situationer där Azure Information Protection-klienten fortfarande kan läsas in i Office-appar. Genom att blockera tillägget från inläsning i varje app förhindras detta.

Du kan även interaktivt inaktivera eller ta bort Office-tillägget **Microsoft Azure Information Protection** från Word, Excel, PowerPoint och Outlook. Den här metoden är lämplig för en enda dator och ad hoc-testning. Instruktioner finns i [Visa, hantera och installera tillägg i Office-program](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d). 

Oavsett vilken metod du väljer börjar ändringarna att gälla när Office-apparna startas om. Genom att inaktivera eller ta bort det här Office-tillägget förblir Azure Information Protection-klienten installerad på datorn så att du kan fortsätta att märka filer utanför Office-programmen. Till exempel med hjälp av Utforskaren eller PowerShell.

Mer information om vilka funktioner som stöds av Azure Information Protection-klienterna och den inbyggda etiketteringsklienten för Office finns i [Välj din Windows-lösning för etikettering](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution) i Azure Information Protection-dokumentationen.

## <a name="office-file-types-supported"></a>Office-filtyper som stöds

Office-program som har inbyggd etikettering för Word-, Excel- och PowerPoint-filer har stöd för Open XML-format (till exempel .docx och .xlsx), men inte Microsoft Office 97-2003-format (t.ex. .doc och .xls), Open Document Format (till exempel .odt och .ods) eller andra format. När det inte finns stöd för en filtyp för inbyggd etikettering är knappen **Känslighet** inte tillgänglig i Office-appen.

Azure Information Protection enhetliga etiketteringsklient har stöd för både Open XML-formatet och Microsoft Office 97-2003-format. Mer information finns i [Filtyper som stöds av det Azure Information Protection enhetliga etiketteringsklient](/azure/information-protection/rms-client/clientv2-admin-guide-file-types) från klientens administratörsguide.

Kontrollerar dokumentationen för andra etiketteringslösningar för vilka filtyper som stöds.

## <a name="protection-templates-and-sensitivity-labels"></a>Skyddsmallar och känslighetsetiketter

Administratörsdefinierade [skyddsmallar](/azure/information-protection/configure-policy-templates), som de du definierar för Meddelandekryptering i Office 365, visas inte i Office-appar när du använder inbyggd etikettering. Den här förenklade upplevelsen återspeglar att det inte finns något behov av att välja en skyddsmall, eftersom samma inställningar ingår i känslighetsetiketter som har kryptering aktiverad.

Om du behöver konvertera befintliga skyddsmallar till etiketter använder du Microsoft Azure-portalen och följande instruktioner: [Så här konverterar du mallar till etiketter](/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>IRM-alternativ (Information Rights Management) och känslighetsetiketter

Känslighetsetiketter som du konfigurerar för att tillämpa kryptering tar bort komplexiteten från användarna för att ange sina egna krypteringsinställningar. I många Office-program kan de här enskilda krypteringsinställningarna ändå konfigureras manuellt av användarna med hjälp av IRM-alternativ (Information Rights Management). Till exempel för Windows-appar:

- För ett dokument: **Arkiv** > **Info** > **Skydda dokument** > **Begränsa åtkomst**
- för ett e-postmeddelande: Gå till fliken **Alternativ** > **Kryptera** 
  
När användare först etiketterar ett dokument eller ett e-postmeddelande kan de åsidosätta dina inställningar för etikettkonfiguration med sina egna krypteringsinställningar. Till exempel:

- En användare använder etiketten **Konfidentiell \ Alla anställda** för ett dokument och den här etiketten har konfigurerats för att tillämpa krypteringsinställningar för alla användare i organisationen. Den här användaren konfigurerar sedan IRM-inställningarna manuellt för att begränsa åtkomsten för användare utanför organisationen. Slutresultatet är ett dokument med etiketten **Konfidentiellt \ Alla anställda** och krypterad, men användarna i organisationen kan inte öppna det som förväntat.

- En användare tillämpar etiketten **Konfidentiellt \ Endast mottagare** på ett e-postmeddelande och det här e-postmeddelandet har konfigurerats för att tillämpa krypteringsinställningen **Vidarebefordra inte**. I Outlook-appen väljer den här användaren manuellt IRM-inställningen för endast kryptering. Resultatet blir att e-postmeddelandet förblir krypterat men att det kan vidarebefordras av mottagarna, trots att det har etiketten **Konfidentiellt/Endast mottagare**.
    
    Som ett undantag för Outlook på webben är alternativen från menyn **Kryptera** inte tillgängliga för en användare att välja när den valda etiketten tillämpar kryptering.

- En användare använder etiketten **Allmänt** för ett dokument och den här etiketten har inte konfigurerats för att tillämpa kryptering. Den här användaren konfigurerar sedan IRM-inställningarna manuellt för att begränsa åtkomsten till dokumentet. Slutresultatet är ett dokument som har etiketten **Allmänt** men som också tillämpar kryptering så att vissa användare inte kan öppna det som förväntat.

Om dokumentet eller e-postmeddelandet redan är etiketterat kan en användare utföra någon av dessa åtgärder om innehållet inte redan är krypterat eller om de har [användningsrättighet](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Exportera eller Fullständig kontroll. 

För en mer konsekvent etikett med meningsfull rapportering kan du ge användarna lämpliga etiketter och vägledningar så att de bara kan använda etiketter för att skydda dokument och e-postmeddelanden. Till exempel:

- För undantagsfall där användare måste tilldela sina egna behörigheter tillhandahåller du etiketter som [låter användarna tilldela sin egna behörigheter](encryption-sensitivity-labels.md#let-users-assign-permissions). 

- I stället för att användare manuellt tar bort kryptering efter att ha valt en etikett som använder kryptering, kan du erbjuda ett underetikettsalternativ när användarna behöver en etikett med samma klassificering, men ingen kryptering. Till exempel:
    - **Konfidentiellt \ Alla anställda**
    - **Konfidentiellt \ Alla (ingen kryptering)**

- Du kan inaktivera IRM-inställningar för att hindra användare från att markera dem:
    - Outlook för Windows: 
        - Registernycklar (DWORD:00000001) *DisableDNF* och *DisableEO* från HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DRM
        - Kontrollera att grupprincipinställningen för **Konfigurera alternativet för standardkryptering för knappen Kryptera** inte är konfigurerad
    - Outlook för Mac: 
        - Nycklar *DisableEncryptOnly* och *DisableDoNotForward* säkerhetsinställningar som dokumenteras i [Ange inställningar för Outlook för Mac](/DeployOffice/mac/preferences-outlook)
    - Outlook på webben: 
        - Parametrar *SimplifiedClientAccessDoNotForwardDisabled* och *SimplifiedClientAccessEncryptOnlyDisabled* dokumenteras för [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)
    - Outlook för iOS och Android: De här apparna stöder inte användare som använder kryptering utan etiketter, så det finns inget att inaktivera.

> [!NOTE]
> Om användare tar bort kryptering manuellt från ett etiketterat dokument som lagras i SharePoint eller OneDrive och du har [aktiverat känslighetsetiketter för Office-filer i SharePoint och OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), återställs etikettkrypteringen automatiskt nästa gång dokumentet används eller laddas ned. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Tillämpa känslighetsetiketter på filer, e-postmeddelanden och bilagor

Användare kan bara använda en etikett i taget för varje dokument eller e-postmeddelande.

När du etiketterar ett e-postmeddelande som innehåller bifogade filer, ärver de bifogade filerna bara etiketten om den etikett som du använder för e-postmeddelandet tillämpar kryptering och den bifogade filen är ett Office-dokument som inte redan är krypterat. Eftersom den ärvda etiketten tillämpar kryptering, krypteras den bifogade filen.

En bifogad fil ärver inte etiketterna från e-postmeddelandet när etiketten som används i e-postmeddelandet inte använder kryptering eller den bifogade filen redan är krypterad.

Exempel på arv av etiketter där etiketten **Konfidentiell** använder kryptering och etiketten **Allmänt** inte använder kryptering:

- En användare skapar ett nytt e-postmeddelande och använder etiketten **Konfidentiell** på det här meddelandet. Sedan lägger de till ett Word-dokument som inte är etiketterat eller krypterat. Till följd av arvet har dokumentet fått etiketten **Konfidentiellt** och nu används kryptering från den etiketten.

- En användare skapar ett nytt e-postmeddelande och använder etiketten **Konfidentiell** på det här meddelandet. Sedan lägger de till ett Word-dokument med etiketten **Allmänt** och den här filen är inte krypterad. Till följd av arvet har dokumentet fått etiketten **Konfidentiellt** igen och nu används kryptering från den etiketten.

## <a name="sensitivity-label-compatibility"></a>Kompatibilitet med känslighetsetiketter

**Med RMS-använda appar**: Om du öppnar ett etiketterat och krypterat dokument eller e-postmeddelande i ett [RMS-använd applikation](/azure/information-protection/requirements-applications#rms-enlightened-applications) som inte stöder känslighetsetiketter, upprätthåller appen fortfarande kryptering och rättighetshantering.

**Med Azure Information Protection-klienten**: Du kan visa och ändra känslighetsetiketter som du använder för dokument och e-postmeddelanden med Office inbyggda etiketteringsklient med hjälp av Azure Information Protection-klienten och tvärtom.

**I andra versioner av Office**: Alla behöriga användare kan öppna etiketterande dokument och e-postmeddelanden i andra versioner av Office. Du kan dock bara visa eller ändra etiketten i Office-versioner som stöds eller med hjälp av Azure Information Protection-klienten. Versioner av Office-appen som stöds visas i [tidigare avsnitt](#support-for-sensitivity-label-capabilities-in-apps).

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Stöd för SharePoint- och OneDrive-filer som skyddas av känslighetsetiketter

Om du vill använda den inbyggda etiketteringsklienten i Office med Office på webben för dokument i SharePoint eller OneDrive ska du kontrollera att du har [aktiverat känslighetsetiketter för Office-filer i SharePoint och OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="support-for-external-users-and-labeled-content"></a>Stöd för externa användare och etiketterar innehåll

När du etiketterar ett dokument eller ett e-postmeddelande lagras etiketten som metadata som innehåller klientorganisationen och en etikett-GUID. När ett etiketterat dokument eller e-postmeddelande öppnas i ett Office-program med stöd för känslighetsetiketter, läses dessa metadata och om användaren tillhör samma klientorganisation visas etiketten i appen. För inbyggd etikettering för Word, PowerPoint och Excel visas etikettnamnet i statusfältet. 

Det innebär att om du delar dokument med en annan organisation som använder andra etikettnamn kan varje organisation använda och se sin egen etikett tillämpas på dokumentet. Följande element från en tillämpad etikett kan dock visas för användare utanför organisationen:

- Innehållsmarkeringar. När en etikett tillämpar ett sidhuvud, en sidfot eller en vattenstämpel läggs dessa till direkt i innehållet och förblir synliga tills någon ändrar eller tar bort dem.

- Namn och beskrivning av den underliggande skyddsmallen från en etikett som använder kryptering. Den här informationen visas i ett meddelandefält högst upp i dokumentet för att ange information om vem som har behörighet att öppna dokumentet och deras användningsrättigheter för dokumentet.

### <a name="sharing-encrypted-documents-with-external-users"></a>Dela krypterade dokument med externa användare

Förutom att begränsa åtkomsten till användare i din egen organisation kan du utöka åtkomsten till alla andra användare som har ett konto i Azure Active Directory. Om din organisation använder villkorsstyrda principer kan du emellertid se [nästa avsnitt](#conditional-access-policies) för ytterligare överväganden.

Alla Office-appar och [RMS-använda program](/azure/information-protection/requirements-applications#rms-enlightened-applications) kan öppna krypterade dokument när användaren har autentiserats. 

Om externa användare inte har ett konto i Azure Active Directory kan de autentisera med hjälp av gästkonton i din klientorganisation. Dessa gästkonton kan också användas för att komma åt delade dokument i SharePoint eller OneDrive när du har [aktiverat känslighetsetiketter för Office-filer i SharePoint och OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):

- Ett alternativ är att skapa dessa gästkonton själv. Du kan ange vilken e-postadresser som helst som de här användarna redan använder. Till exempel deras Gmail-adress.
    
    Fördelen med det här alternativet är att du kan begränsa åtkomsten och behörigheten för vissa användare genom att ange deras e-postadress i krypteringsinställningarna. Nackdelen är att administrationsomkostnaderna för att skapa och samordna konton med etikettkonfigurationen.

- Ett annat alternativ är att [SharePoint- och OneDrive-integrering med Azure AD B2B (förhandsversion)](/sharepoint/sharepoint-azureb2b-integration-preview) så att gästkonton skapas automatiskt när användarna delar länkar.
    
    Fördelen med det här alternativet är minimala administrationsomkostnader eftersom kontona skapas automatiskt och enklare etikettkonfiguration. I det här scenariot måste du välja krypteringsalternativet [Lägg till autentiserade användare](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) eftersom du inte känner till e-postadresserna i förväg. Nackdelen är att den här inställningen inte tillåter att du begränsar åtkomst- och användningsbehörigheter för specifika användare.

Externa användare kan också använda ett Microsoft-konto för att öppna krypterade dokument när de använder Windows och Microsoft 365-applikationer ([tidigare Office 365-appar](/deployoffice/name-change)) eller den fristående versionen av Office 2019. Nyare stöd för andra plattformar har Microsoft-konton också stöd för att öppna krypterade dokument i macOS (Microsoft 365-applikationer, version 16.42+), Android (version 16.0.13029+) och iOS (version 2.42+). En användare i organisationen delar till exempel ett krypterat dokument med en användare utanför organisationen och krypteringsinställningarna anger en Gmail-adress för den externa användaren. Den externa användaren kan skapa ett eget Microsoft-konto som använder deras Gmail-adress. När de har loggat in med det här kontot kan de sedan öppna dokumentet och redigera det, enligt de användningsbegränsningar som anges för dem. En genomgång av det här scenariot finns i [du öppnar och redigera det skyddade dokumentet](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> E-postadressen för Microsoft-kontot måste matcha den e-postadress som angetts för att begränsa åtkomsten till krypteringsinställningarna.

När en användare med ett Microsoft-konto öppnar ett krypterat dokument på det här sättet skapas automatiskt ett gästkonto för klientorganisationen om ett gästkonto med samma namn inte redan finns. När gästkontot finns kan det sedan användas för att öppna dokument i SharePoint och OneDrive genom att använda Office på webben, förutom att öppna krypterade dokument från skrivbords- och mobilapparna för Office-program som stöds.

Det automatiska gästkontot skapas dock inte direkt i det här scenariot på grund av replikeringsfördröjning. Om du anger personliga e-postadresser som en del av inställningarna för etikettkryptering rekommenderar vi att du skapar motsvarande gästkonton i Azure Active Directory. Meddela sedan användarna att de måste använda det här kontot för att öppna ett krypterat dokument från din organisation.

> [!TIP]
> Eftersom du inte kan vara säker på att externa användare kommer att använda en Office-klientapp som stöds är att dela länkar från SharePoint och OneDrive när du har skapat gästkonton (för specifika användare) eller när du använder [SharePoint- och OneDrive-integrering med Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) (för alla autentiserade användare) en mer tillförlitlig metod för att stödja säkert samarbete med externa användare.

### <a name="conditional-access-policies"></a>Principer för villkorsstyrd åtkomst

Om din organisation har implementerat [Azure Active Directory-principer för villkorsstyrd åtkomst](/azure/active-directory/conditional-access/overview) bör du kontrollera konfigurationen av dessa principer. Om principerna inkluderar **Microsoft Azure Information Protection** och principen utökas till externa användare måste de externa användarna ha ett gästkonto i klientorganisationen även om de har ett Azure AD-konto i sin egen klientorganisation.

Utan det här gästkontot kan de inte öppna det krypterade dokumentet och ser ett felmeddelande. Meddelandetexten kanske informerar dem om att användarens konto måste läggas till som en extern användare i klientorganisationen, med de felaktiga instruktionerna för det här scenariot för att **Logga ut och logga in igen med ett annat Azure Active Directory-användarkonto**.

Om du inte kan skapa och konfigurera gästkonton i klientorganisationen för externa användare som behöver öppna dokument som är krypterade av dina etiketter, måste du antingen ta bort Azure Information Protection från villkorsstyrda åtkomstprinciper eller exkludera externa användare från principerna.

Mer information om villkorlig åtkomst och Azure Information Protection, krypteringstjänsten som används av känslighetsetiketter, finns i vanliga frågor. [Jag ser att Azure Information Protection är listat som en tillgänglig molnapp för villkorsstyrd åtkomst – hur fungerar det?](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>När Office-program använder innehållsmarkering och kryptering

Office-program tillämpar innehållsmarkering och kryptering med en känslighetsetikett på olika sätt, beroende på vilken app du använder.

| Program | Innehållsmarkering | Kryptering |
| --- | --- | --- |
| Word, Excel, PowerPoint på alla plattformar | Omedelbart | Omedelbart |
| Outlook för PC och Mac | När Exchange Online har skickat e-postmeddelandet | Omedelbart |
| Outlook på webben, iOS och Android | När Exchange Online har skickat e-postmeddelandet | När Exchange Online har skickat e-postmeddelandet |
|

Lösningar som använder känslighetsetiketter på filer utanför Office-program gör det genom att använda etikettering av metadata i filen. I det här scenariot infogas inte innehållsmarkering från etikettens konfiguration i filen men kryptering används. 

När dessa filer öppnas i en Office-app på datorn tillämpas innehållsmarkeringarna automatiskt av Azure Information Protection enhetliga etiketteringsklient när filen först sparas. Innehållsmarkeringar används inte automatiskt när du använder inbyggd etikettering för dator-, mobil- eller webbprogram.

Scenarier som omfattar att använda en känslighetsetikett utanför Office-appar är:

- Skannern, Utforskaren och PowerShell från Azure Information Protection enhetliga etiketteringsklient 

- Autoetiketteringsprinciper för SharePoint och OneDrive

- Exportera etiketterad och krypterad data från Power BI

- Microsoft Cloud App Security

För de här scenarierna kan en användare med hjälp av deras Office-program använda inbyggd etikettering för att ange etikettens innehållsmarkeringar genom att tillfälligt ta bort eller ersätta den aktuella etiketten och sedan återanvända den ursprungliga etiketten.

### <a name="dynamic-markings-with-variables"></a>Dynamiska markeringar med variabler

> [!IMPORTANT]
> För närvarande har inte alla appar på alla plattformar stöd för dynamiska innehållsmarkeringar som du kan ange för sidhuvuden, sidfötter och vattenstämplar. För appar som inte stöder den här funktionen används markeringarna som den ursprungliga texten som angetts i etikettkonfigurationen i stället för att matcha variablerna.
> 
> Azure Information Protection enhetliga etiketteringsklient har stöd för dynamiska markeringar. För inbyggd etikettering i Office finns det tabeller i avsnittet [funktioner](#support-for-sensitivity-label-capabilities-in-apps) här sidan för de minimiversioner som stöds.

När du konfigurerar en känslighetsetikett för innehållsmarkeringar kan du använda följande variabler i textsträngen för sidhuvudet, sidfoten eller vattenstämpeln:

| Variabel | Beskrivning | Exempel på när etikett används |
| -------- | ----------- | ------- |
| `${Item.Label}` | Etikettvisningsnamn på den etikett som används | **Allmänt**|
| `${Item.Name}` | Filnamn eller e-postämne för det innehåll som ska etiketteras | **Sales.docx** |
| `${Item.Location}` | Sökväg och filnamn för det dokument som ska etiketteras eller e-postämnet för ett e-postmeddelande som ska etiketteras | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Visningsnamn på användaren som använder etiketten | **Richard Simone** |
| `${User.PrincipalName}` | Azure AD-användarens huvudnamn (UPN) för användaren som använder etiketten | **rsimone\@contoso.com** |
| `${Event.DateTime}` | Datum och tid när innehållet är etiketterat, i den lokala tidszon för användaren som använder etiketten | **2020-08-10 13:30** |

> [!NOTE]
> Syntax för dessa variabler är skiftlägeskänslig.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Ange olika visuella markeringar för Word, Excel, PowerPoint och Outlook

Som ytterligare en variabel kan du konfigurera visuell markering per Office-programtyp med hjälp av åtgärdssats “If.App” i textsträngen och identifiera programtypen med hjälp av värdena **Word**, **Excel**, **PowerPoint** eller **Outlook**. Du kan också korta ned de här värdena, vilket är nödvändigt om du vill ange fler än en i samma If.App åtgärdssats.

Använd följande syntax:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Precis som andra dynamiska visuella markeringar är syntaxen skiftlägeskänslig, vilket innefattar förkortningar för varje programtyp (WEPO).

Exempel:

- **Ange endast rubriktext för Word-dokument:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Endast i Word-dokumentrubriker tillämpas etiketten "Det här Word-dokumentet är känsligt" på rubriktexten. Ingen rubriktext tillämpas på andra Office-program.

- **Ange sidfotstext för Word, Excel och Outlook och annan sidfotstext för PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    I Word, Excel och Outlook tillämpas etiketten "Det här innehållet är konfidentiellt" på fotnotstexten. I PowerPoint tillämpas etiketten "Den här presentationen är konfidentiell" på fotnotstexten.

- **Ange specifik vattenstämpeltext för Word och PowerPoint och sedan vattenstämpeltext för Word, Excel och PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    I Word och PowerPoint tillämpas etiketten "Det här innehållet är konfidentiellt" på vattenstämpeltexten. I Excel tillämpas etiketten "Konfidentiellt" på vattenstämpeltexten. I Outlook tillämpas inte etiketten till vattenstämpeltext eftersom det inte finns stöd för vattenstämplar som visuella markeringar för Outlook.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Kräva att användare använder en etikett för sin e-post och dokument

> [!IMPORTANT]
> 
> [Azure Information Protection enhetliga etiketteringsklient](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) stöder konfiguration som även kallas obligatorisk etikettering. För inbyggd etikettering i Office finns det tabeller i avsnittet [funktioner](#support-for-sensitivity-label-capabilities-in-apps) här sidan för de minimiversioner som stöds.
>
> Om du vill använda obligatorisk etikettering för dokument men inte e-postmeddelanden följer du anvisningarna i nästa avsnitt som förklarar hur du konfigurerar Outlook-specifika alternativ.

När principinställningen **Kräv att användare ska använda en etikett för sin e-post och dokument** är markerat måste användare som tilldelas principen markera och använda en känslighetsetikett under följande scenarier:

- För Azure Information Protection enhetliga etiketteringsklient:
    - För dokument (Word, Excel och PowerPoint): När ett dokument som inte är etiketterad sparas eller användare stänger dokumentet.
    - För e-postmeddelanden (Outlook): När användare skickar ett meddelande utan etikett.

- För inbyggd etikettering i Office-program:
    - För dokument (Word, Excel och PowerPoint): När ett dokument som inte är etiketterat öppnas eller sparas.
    - För e-postmeddelanden (Outlook): När användare skickar ett e-postmeddelande utan etikett.

Mer information om inbyggd etikettering:

- När användare uppmanas att lägga till en känslighetsetikett eftersom de öppnar ett dokument som inte är etiketterat kan de lägga till en etikett eller välja att öppna dokumentet i skrivskyddat läge.

- När den obligatoriska etiketten används kan användarna inte ta bort känslighetsetiketter från dokument, men de kan ändra en befintlig etikett.

Information om när du använder den här inställningen finns i informationen om [principinställningar](sensitivity-labels.md#what-label-policies-can-do).

> [!NOTE]
> Om du använder standardinställningen för etikettprinciper för dokument och e-postmeddelanden utöver obligatorisk etikettering: 
>
> Standardetiketten har alltid prioritet framför obligatorisk etikettering. För dokument tillämpar Azure Information Protection enhetliga etiketteringsklienten standardetiketten för alla dokument som inte är etiketterade, medan den inbyggda etiketteringen använder standardetiketten för nya dokument och inte för befintliga dokument som inte är etiketterade. Den här skillnaden i beteende innebär att när du använder obligatorisk etikettering med inställning för standardetiketter uppmanas användarna att använda en känslighetsetikett oftare när de använder inbyggd etikettering än när de använder Azure Information Protection enhetliga etiketteringsklienten.

## <a name="outlook-specific-options-for-default-label-and-mandatory-labeling"></a>Outlook-specifika alternativ för standardetikett och obligatorisk etikettering

Identifiera de minimiversioner av Outlook som stöder de här funktionerna för inbyggd etikettering med hjälp av [funktionstabellen för Outlook](#sensitivity-label-capabilities-in-outlook) på den här sidan samt rad **Olika inställningar för standardetikett och obligatorisk etikettering**. Alla versioner av Azure Information Protection enhetlig etiketteringsklient stöder de här Outlook-specifika alternativen.

När Outlook-appen har stöd för en standardetikettinställning som skiljer sig från standardetikettinställningen för dokument gör du så här:

- I guiden för etikettprinciper på sidan **Ange en standardetikett för e-postmeddelanden** kan du ange valfri känslighetsetikett som ska användas för alla omärkta e-postmeddelanden eller ingen standardetikett. Den här inställningen är oberoende av **Använd den här etiketten som standard på dokument**-inställningen på den föregående sidan **Principinställningar för dokument** i guiden.

När Outlook-appen inte stöder en standardetikettinställning som skiljer sig från standardetikettinställningen för dokument: I Outlook används alltid det värde du anger för **Använd den här etiketten som standard för dokument** på sidan **Principinställningar för dokument** i guiden för etikettprinciper.

När Outlook-appen har stöd för att inaktivera obligatorisk etikettering gör du så här:

- I guiden för etikettprinciper på sidan **Principinställningar** väljer du **Kräv att användare tillämpar en etikett på sin e-post eller sina dokument**. Välj sedan **Nästa** > **Nästa** och avmarkera kryssrutan **Kräv att användare tillämpar en etikett på sina e-postmeddelanden**. Låt kryssrutan vara markerad om du vill använda obligatorisk etikett för e-post och dokument.

När Outlook-appen inte har stöd för att inaktivera obligatorisk etikettering: Om du väljer **Kräv att användare tillämpar en etikett på sin e-post eller sina dokument** som en principinställning, uppmanas användarna alltid att välja en etikett för omärkta e-postmeddelanden.

> [!NOTE]
> Om du har konfigurerat de avancerade PowerShell-inställningarna **OutlookDefaultLabel** och **DisableMandatoryInOutlook** med cmdlet:erna [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) eller [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy):
> 
> De valda värdena för de här PowerShell-inställningarna återspeglas i guiden för etikettprinciper och fungerar automatiskt för Outlook-program som har stöd för de här inställningarna. Andra avancerade PowerShell-inställningar stöds fortfarande endast av Azure Information Protection enhetlig etiketteringsklient.

## <a name="end-user-documentation"></a>Dokumentation för slutanvändare

- [Använda känslighetsetiketter för filer och e-postmeddelanden i Office](https://support.microsoft.com/sv-SE/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Kända problem med känslighetsetiketter i Office](https://support.microsoft.com/sv-SE/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Tillämpa känslighetsetiketter automatiskt eller rekommendera känslighetsetiketter för filer och e-postmeddelanden i Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Kända problem med att automatiskt använda eller rekommendera känslighetsetiketter](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)
