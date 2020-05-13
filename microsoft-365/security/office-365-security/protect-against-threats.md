---
title: Skydda mot hot
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig mer om hotskydd i Microsoft 365 och konfigurera hur du använder det för din organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3ed243d36866e9ebadf00a0247dd4545113788e8
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206610"
---
# <a name="protect-against-threats"></a>Skydda mot hot

Microsoft 365 innehåller en mängd olika hotskyddsfunktioner. Här är en snabbstartsguide som du kan använda som checklista för att se till att dina hotskyddsfunktioner är konfigurerade för din organisation. Om du inte har använt hotskyddsfunktionerna i Office 365 tidigare, eller om du bara inte är säker på var du ska börja, använder du följande vägledning som utgångspunkt.

> [!IMPORTANT]
> **De första rekommenderade inställningarna ingår för varje typ av princip, men många alternativ är tillgängliga och du kan justera inställningarna så att de uppfyller organisationens behov**. Tillåt cirka 30 minuter för dina principer eller ändringar att arbeta sig igenom ditt datacenter.

## <a name="requirements"></a>Krav

### <a name="subscriptions"></a>Prenumerationer

Hotskyddsfunktioner ingår i alla Microsoft 365-prenumerationer. Vissa prenumerationer innehåller dock mer avancerade funktioner. I följande tabell visas de skyddsfunktioner som ingår i den här artikeln tillsammans med minimikraven för prenumeration.<br/>

|||
|---|---|
|**Typ av skydd**|**Abonnemangskrav**|
|Skydd mot skadlig kod|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)|
|Skydd mot skadliga webbadresser och filer i e-post- och Office-dokument|[Office 365 Avancerat skydd mot hot](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)|
|Skydd mot nätfiske|[EOP (på andra sätt)](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|Avancerat skydd mot nätfiske|[Skaffa Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Skydd mot skräppost|[EOP (på andra sätt)](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|Nolltimmars automatisk rensning (för e-post)|[EOP (på andra sätt)](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|Granskningsloggning (detta används för rapportering)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>Roller och behörigheter

Du måste tilldelas en lämplig roll för att konfigurera principer i [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Följande tabell innehåller några exempel:

|Roll eller rollgrupp|Här kan du läsa mer|
|---------|---------|
|global administratör|[Om administratörsroller i Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Säkerhetsadministratör|[Administratörens rollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Hantering av Exchange Online-organisation|[Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>Och<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|

Mer information finns [i Behörigheter i &amp; Säkerhetsefterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

## <a name="part-1---anti-malware-protection"></a>Del 1 - Skydd mot skadlig kod

[Skydd mot skadlig kod](anti-malware-protection.md) är tillgängligt i prenumerationer som inkluderar [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).

1. I [Security & Compliance Center](https://protection.office.com)väljer du **Policy**  >  **Policy**  >  **anti-malware mot hothantering.**

2. Dubbelklicka på **standardprincipen** och välj sedan **inställningar**.

3. Ange följande inställningar:

    - Behåll **Malware Detection Response** standardinställningen **nr.**

    - I avsnittet **Filter för vanliga typer av bifogade filer** väljer du **På**.

4. Klicka på **Spara**.

Mer information om policyalternativ mot skadlig kod finns i [Konfigurera policyer mot skadlig kod](configure-anti-malware-policies.md).

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Del 2 - Skydd mot skadliga webbadresser och filer

Tidsberedskapsskydd mot skadliga webbadresser och filer är tillgängligt i prenumerationer som innehåller [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) och konfigureras via [ATP-principer för säkra bilagor](atp-safe-attachments.md) och [ATP-principer](atp-safe-links.md) för säkra länkar.

### <a name="atp-safe-attachments-policies"></a>ATP-principer för säkra bilagor

Om du vill ställa in [ATP-säkra bilagor](atp-safe-attachments.md)måste du definiera minst en ATP-princip för säkra bilagor.

1. I [Security & Compliance Center](https://protection.office.com)väljer du ATP-säkra atp-betrodda bilagor **för hothanteringsprincip.**  >  **Policy**  >  **ATP safe attachments**

2. Välj alternativet **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.

3. Klicka på plustecknet ( i avsnittet **Skydda e-postbilagor).** **+**

4. Ange följande inställningar:

   - Skriv i rutan **Namn** `Block malware` .

   - I svarsavsnittet väljer du **Blockera**.

   - I avsnittet **Omdirigera bifogad fil** väljer du alternativet **Aktivera omdirigering**och anger sedan e-postadressen för organisationens säkerhetsadministratör eller operatör som ska granska identifierade filer.

   - I avsnittet **Tillämpad** på väljer du **Den mottagande domänen är**. Välj sedan din domän, välj **Lägg till**och klicka sedan på **OK**.

5. Klicka på **Spara**.

6. **(Rekommenderat ytterligare steg)** Som global administratör eller SharePoint **[Online-administratör kör cmdlet set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern **DisallowInfectedFileDownload** inställd på *true* för din Microsoft 365-miljö. (Detta förhindrar att personer öppnar, flyttar, kopierar eller delar filer som identifieras som skadliga.)

Mer information finns i Konfigurera principer för [betrodda anslutningspunkter för Office 365 ATP](set-up-atp-safe-attachments-policies.md) och [Aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>ATP-principer för säkra länkar

Om du vill konfigurera [atp-säkra länkar](atp-safe-links.md)granskar och redigerar du standardprincipen och lägger till en princip för specifika användare.

1. I [Security & Compliance Center](https://protection.office.com)väljer du ATP Safe Links **för hothanteringsprincip.**  >  **Policy**  >  **ATP Safe Links**

2. Dubbelklicka **Default** på standardprincipen.

3. I avsnittet **Använd säkra länkar i** väljer du alternativet Microsoft **365 Apps för företag, Office för iOS och Android**och klickar sedan på **Spara**.

4. Klicka **på** plustecknet ( **+** ).

5. Ange följande inställningar:

   - Skriv ett namn i rutan **Namn,** till exempel `Safe Links` .

   - Välj **På**i avsnittet **Välj åtgärd** .

   - Välj de här alternativen:

     - **Använd säkra bilagor för att skanna nedladdningsbart innehåll**

     - **Använda säkra länkar till e-postmeddelanden som skickas inom organisationen**

     - **Låt inte användare klicka igenom säkra länkar till den ursprungliga webbadressen**

   - I avsnittet **Tillämpad** på väljer du **Den mottagande domänen är**. Välj sedan din domän, välj **Lägg till**och klicka sedan på **OK**.

6. Klicka på **Spara**.

Mer information finns i [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md)(Konfigurera Office 365 ATP-principer för säkra länkar).

## <a name="part-3---anti-phishing-protection"></a>Del 3 - Skydd mot nätfiske

[Anti-phishing]

[Skydd mot nätfiske](anti-phishing-protection.md) är tillgängligt i prenumerationer som inkluderar [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description). Avancerat skydd mot nätfiske finns i [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

I följande procedur beskrivs hur du konfigurerar en ATP-princip mot nätfiske. Stegen är liknande för att konfigurera en anti-phishing-policy (utan ATP).

1. I [Security & Compliance Center](https://protection.office.com)väljer du **Threat management**  >  **Policy**  >  **ATP-principen mot hothantering.**

2. Klicka på **Standardprincip**.

3. Klicka på **Redigera**i avsnittet **Personifiering** och ange sedan följande inställningar:

   - Aktivera skyddet på fliken **Lägg till användare för att skydda.** Lägg sedan till användare, till exempel organisationens styrelseledamöter, din VD, EKONOMI och ANDRA ledande befattningshavare. (Du kan skriva en enskild e-postadress eller klicka för att visa en lista.)

   - På fliken **Lägg till domäner för att skydda** aktiverar du Automatiskt de **domäner jag äger**. Om du har anpassade domäner, lägg till dessa också.

   - På fliken **Åtgärder** väljer du **Karantän för både** den **personifierade användaren** och de **personifierade domänalternativen.** Dessutom aktiverar du säkerhetstips för personifiering.

   - Kontrollera att postlådeinformation är aktiverat på fliken **Postlådeinformation.** Dessutom aktiverar du informationsbaserat personifieringsskydd för postlådan. Välj **Karantän meddelandet** **i om e-postmeddelandet skickas av en personifierad användarlista** .

   - På fliken **Lägg till betrodda avsändare och domäner** anger du alla betrodda avsändare eller domäner som du vill lägga till.

   - Klicka på **Spara**när du har granskat inställningarna på fliken **Granska dina inställningar** .

4. Klicka på **Redigera**i avsnittet **Spoof** och ange sedan följande inställningar:

   - Kontrollera att förfalskningsskydd är aktiverat på fliken **Spoofing** filter settings.

   - Välj Karantän meddelandet **på**fliken **Åtgärder** .

   - Klicka på **Spara**när du har granskat inställningarna på fliken **Granska dina inställningar** . (Om du inte har gjort några ändringar klickar du på **Avbryt**.)

5. Stäng sidan standardinställningsinställningar.

Mer information om dina policyalternativ mot nätfiske finns i [Konfigurera ATP-principer för nätfiske](configure-atp-anti-phishing-policies.md).

## <a name="part-4---anti-spam-protection"></a>Del 4 - Skydd mot skräppost

[Skydd mot skräppost](anti-spam-protection.md) är tillgängligt i prenumerationer som inkluderar [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).

1. I [Security & Compliance Center](https://protection.office.com)väljer du **Anti-spam för hothanteringspolicy**  >  **Policy**  >  **Anti-spam**.

2. Aktivera **Anpassade inställningar** på fliken **Anpassad.**

3. Expandera **standardprincip för skräppostfilter,** klicka på **Redigera princip**och ange sedan följande inställningar:

   - I avsnittet **Skräppost och massåtgärder** anger du tröskelvärdet till ett värde av 5 eller 6.

   - Granska (och vid behov redigera) tillåtna avsändare och domäner i avsnittet **Tillåt listor.**

4. Klicka på **Spara**.

Mer information om dina policyalternativ mot skräppost finns [i Konfigurera policyer mot skräppost i EOP](configure-your-spam-filter-policies.md).

## <a name="part-5---additional-settings-to-configure"></a>Del 5 - Ytterligare inställningar för att konfigurera

Förutom att konfigurera skydd mot skadlig kod, skadliga webbadresser och filer, nätfiske och skräppost rekommenderar vi att du konfigurerar inställningarna för automatisk rensning och granskning av nolltimmarstimmar.

### <a name="zero-hour-auto-purge-for-email"></a>Nolltimmars automatisk rensning för e-post

[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) är tillgängligt i prenumerationer som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description). Det här skyddet är aktiverat som standard. Följande villkor måste dock vara uppfyllda för att skyddet skall vara i kraft:

- Skräppoståtgärder är inställda på **Flytta meddelande till skräppostmapp** i [anti-spam-policyer](anti-spam-protection.md).

- Användare har behållit sina [standardinställningar för skräppost](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)och har inte inaktiverat skydd för skräppost.

Mer information finns i [Zero-hour auto purge - skydd mot skräppost och skadlig kod](zero-hour-auto-purge.md).

### <a name="audit-logging-for-reporting-and-investigation"></a>Revisionsloggning för rapportering och utredning

Granskningsloggning är tillgängligt i prenumerationer som inkluderar [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description). För att kunna visa data i rapporter om skydd mot hot, till exempel [säkerhetspanelen,](security-dashboard.md) [e-postsäkerhetsrapporter](view-email-security-reports.md)och [Utforskaren,](threat-explorer.md)måste granskningsloggning vara aktiverat för din organisation. Mer information finns i [Aktivera eller inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Uppgifter efter installationen

När du har konfigurerat hotskyddsfunktionerna ska du se till att övervaka hur dessa funktioner fungerar, granska och ändra dina principer efter behov och titta efter nya funktioner och tjänstuppdateringar.

|||
|---|---|
|**Vad du ska göra**|**Resurser för att få mer information**|
|Se hur hotskyddsfunktioner fungerar för din organisation genom att visa rapporter|[Instrumentpanel för säkerhet](security-dashboard.md)<br/>[Säkerhetsrapporter för e-post](view-email-security-reports.md)<br/>[Rapporter för OFFICE 365 ATP](view-reports-for-atp.md)<br/>[Hotutforskaren](threat-explorer.md)|
|Granska och revidera regelbundet dina policyer för hotskydd efter behov|[Secure Score](../mtp/microsoft-secure-score.md)<br/>[Smarta rapporter och insikter](reports-and-insights-in-security-and-compliance.md)<br/>[Funktioner för utredning och svar i Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Håll utkik efter nya funktioner och serviceuppdateringar|[Standard- och målutgivningsalternativ](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[Meddelandecentral](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[Översikt över Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Beskrivningar av tjänsten](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
