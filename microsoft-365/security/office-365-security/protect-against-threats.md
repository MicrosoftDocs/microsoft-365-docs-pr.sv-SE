---
title: Skydda mot hot
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om hotets skydd i Microsoft 365 och konfigurera hur det ska användas för din organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8f1cecbb3141b4751778212025e5aad582707e12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826831"
---
# <a name="protect-against-threats"></a>Skydda mot hot

Microsoft 365 innehåller flera olika skydds funktioner. Här är en snabb start guide som du kan använda som check lista för att kontrol lera att dina skydds funktioner är inställda för din organisation. Om du är nybörjare i Office 365, eller om du inte är säker på var du ska börja, kan du använda följande vägledning som utgångs punkt.

> [!IMPORTANT]
> **Initiala rekommenderade inställningar är tillgängliga för alla typer av principer, men du kan också ändra dina inställningar för att uppfylla specifika organisationens behov**. Tillåt cirka 30 minuter för dina principer eller ändringar för att fungera på ett annat sätt via ditt data Center.

## <a name="requirements"></a>Krav

### <a name="subscriptions"></a>Prenumerationer

Hot Protection-funktioner ingår i alla Microsoft 365-abonnemang; Vissa abonnemang innehåller dessutom mer avancerade funktioner. I följande tabell finns de skydds funktioner som ingår i den här artikeln tillsammans med de minsta abonnemangs kraven.

****

|Skydds typ|Abonnemangs behov|
|---|---|
|Skydd mot skadlig kod|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)|
|Skydda från skadliga URL-adresser och filer i e-post-och Office-dokument|[Office 365 Avancerat skydd](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)|
|Skydd mot nätfiske|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Avancerat skydd mot nätfiske|[Skaffa Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Skydd mot skräppost|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatisk rensning av Tom timme (för e-post)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Gransknings loggning (används för rapporterings ändamål)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>Roller och behörigheter

Du måste ha en lämplig roll för att konfigurera principer i [säkerhets & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Följande tabell innehåller några exempel:

****

|Roll eller rollgrupp|Var kan jag läsa mer?|
|---|---|
|global administratör|[Om administratörsroller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Säkerhets administratör|[Administratörens rollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Organisations hantering i Exchange Online|[Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>och<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Mer information finns i [behörigheter i säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md).

## <a name="part-1---anti-malware-protection"></a>Del 1 – skydd mot skadlig program vara

[Skydd mot skadlig program](anti-malware-protection.md) vara finns i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. Välj skydd mot **Threat management**skadligt Management policy i [Center för säkerhet & efterlevnad](https://protection.office.com)  >  **Policy**  >  **Anti-malware**.

2. Dubbelklicka på **standard** principen och välj sedan **Inställningar**.

3. Ange följande inställningar:

    - Behåll standardinställningen i avsnittet för **identifiering av skadlig program** **vara.**

    - I **filter avsnittet gemensamma bilagor** väljer du **på**.

4. Klicka på **Spara**.

Mer information om alternativ för principer mot skadlig program vara finns i [Konfigurera principer för skadlig program vara](configure-anti-malware-policies.md).

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Del 2 – skydda skadlig URL och filer

Skydd mot skadlig URL-adress och filer är tillgängligt i prenumerationer som inkluderar [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) och som har kon figurer ATS med principer för säkra [bifogade filer](atp-safe-attachments.md) och [ATP-länkar](atp-safe-links.md) .

### <a name="atp-safe-attachments-policies"></a>Principer för säkra bifogade filer via ATP

För att konfigurera [säkerhet för säkerhets](atp-safe-attachments.md)skull för ATP måste du definiera minst en policy för säker användning av ATP.

1. Välj **Threat Management**policy [Security & Compliance Center](https://protection.office.com)  >  **Policy**  >  **Safe Attachments**i säkerhets & Compliance Center.

2. Välj alternativet **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.

3. Klicka på plus tecknet () i avsnittet **skydda e-postbilagor** **+** .

4. Ange följande inställningar:

   - Skriv i rutan **namn** `Block malware` .

   - I avsnittet svar väljer du **blockera**.

   - I avsnittet **omdirigera bilaga** väljer du alternativet **Aktivera omdirigering**och anger sedan e-postadressen för organisationens säkerhets administratör eller operatör som ska granska upptäckta filer.

   - I avsnittet **används för** väljer **du mottagaren**. Välj sedan din domän, Välj **Lägg till**och klicka sedan på **OK**.

5. Klicka på **Spara**.

6. (**Rekommenderat steg**) Som global administratör eller SharePoint Online-administratör kör cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern **DisallowInfectedFileDownload** inställd på  *True* för din Microsoft 365-miljö. (Detta förhindrar att personer öppnar, flyttar, kopierar eller delar filer som identifieras som skadliga.)

Mer information finns i [Konfigurera office 365-principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md) och [aktivera Office 365 ATP för SharePoint-, OneDrive-och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Principer för säkraste säkerhets länkar

Om du vill ställa in [säkerhets Länkar för ATP](atp-safe-links.md)kan du läsa och redigera standard principen och lägga till en princip för specifika användare.

1. Välj **Threat Management**policy säkerhets länkar i [säkerhets& efterlevnad](https://protection.office.com)  >  **Policy**  >  **ATP Safe Links**.

2. Dubbelklicka på **standard** policyn.

3. I avsnittet **Använd säkra länkar i** väljer du alternativet **Microsoft 365-appar för Enterprise, Office för iOS och Android**och klickar sedan på **Spara**.

4. Klicka på plus tecknet () i avsnittet **principer som gäller för specifika mottagare** **+** .

5. Ange följande inställningar:

   - Skriv ett namn i rutan **namn** , till exempel `Safe Links` .

   - I avsnittet **Välj åtgärd väljer du** **på**.

   - Välj de här alternativen:

     - **Använda säkra bifogade filer för att skanna nedladdnings Bart innehåll**

     - **Använda säkra länkar till e-postmeddelanden som skickas inom organisationen**

     - **Tillåt inte att användare klickar genom säkra länkar till ursprunglig URL**

   - I avsnittet **används för** väljer **du mottagaren**. Välj sedan din domän, Välj **Lägg till**och klicka sedan på **OK**.

6. Klicka på **Spara**.

Mer information finns i [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md)(Konfigurera Office 365 ATP-principer för säkra länkar).

## <a name="part-3---anti-phishing-protection"></a>Del 3-skydd mot nätfiske

[Anti-nätfiske]

[Skydd mot nätfiske](anti-phishing-protection.md) är tillgängligt i abonnemang med [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Avancerat skydd mot nätfiske är tillgängligt i [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Här beskrivs hur du konfigurerar en policy för ATP-anti-nätfiske. De här stegen är liknande för att konfigurera en anti-nätfiske-princip (utan ATP).

1. Välj **Threat Management**policy [Security & Compliance Center](https://protection.office.com)  >  **Policy**  >  **ATP-nätfiske**i säkerhets & Compliance Center.

2. Klicka på **standard policy**.

3. Klicka på **Redigera**i avsnittet **personifiering** och ange sedan följande inställningar:

   - På fliken **Lägg till användare på skydda** aktiverar du skydd. Lägg sedan till användare, till exempel organisationens styrelse medlemmar, VD, ekonomi och andra chefs ledare. (Du kan skriva en enskild e-postadress eller klicka på för att visa en lista.)

   - På fliken **Lägg till domäner på skydda** aktiverar **du automatiskt de domäner jag äger**. Om du har anpassade domäner kan du även lägga till dem.

   - På fliken **åtgärder** väljer du **Quarantine meddelandet** för både den **personifierade användaren** och de **personifierade domän** alternativen. Aktivera dessutom säkerhets tips.

   - På fliken **Mailbox Intelligence** kontrollerar du att post låda-intelligens är aktiverat. Aktivera dessutom post låda baserat skydd mot postsamtal. I listan **om e-post som skickas av en personifierad användare** väljer **du sätt i karantän meddelandet**.

   - På fliken **Lägg till betrodda avsändare och domäner** anger du betrodda avsändare eller domäner som du vill lägga till.

   - Klicka på **Spara**på fliken **Granska inställningar** när du har granskat dina inställningar.

4. Klicka på **Redigera**i avsnittet **Spoof** och ange sedan följande inställningar:

   - Kontrol lera att skyddet mot förfalskning är aktiverat på fliken **Inställningar för falska filter** .

   - Välj **Quarantine The meddelande**på fliken **Actions** .

   - Klicka på **Spara**på fliken **Granska inställningar** när du har granskat dina inställningar. (Om du inte har gjort några ändringar klickar du på **Avbryt**.)

5. Stäng sidan standardinställningar för princip inställningar.

Mer information om dina alternativ för skydd mot nätfiske finns i avsnittet [Konfigurera AntiPhishing-principer för ATP](configure-atp-anti-phishing-policies.md).

## <a name="part-4---anti-spam-protection"></a>Del 4-skydd mot skräp post

[Skydd mot skräp post](anti-spam-protection.md) finns i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. I [säkerhets & Compliance Center](https://protection.office.com)väljer du **hot Management**  >  **policy**  >  **anti-spam**.

2. På fliken **anpassad** aktiverar du **anpassade inställningar** .

3. Expandera **standard filter princip för skräp post**, klicka på **Redigera princip**och ange sedan följande inställningar:

   - I avsnittet **skräp post och Mass åtgärder** anger du tröskelvärdet till 5 eller 6.

   - I avsnittet **tillåta listor** granskar du (och om det behövs, redigera) tillåtna avsändare och domäner.

4. Klicka på **Spara**.

Mer information om alternativen för att förhindra skräp post finns i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).

## <a name="part-5---additional-settings-to-configure"></a>Del 5 – ytterligare inställningar att konfigurera

Förutom att konfigurera skydd från skadlig program vara, skadliga URL-adresser och filer, nätfiske och skräp post rekommenderar vi att du konfigurerar inställningarna för automatisk rensning och gransknings loggning för en tom timme.

### <a name="zero-hour-auto-purge-for-email"></a>Automatisk rensning av Tom timme för e-post

[Automatisk rensning för noll-timme](zero-hour-auto-purge.md) är tillgängligt i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Detta skydd är aktiverat som standard. men följande villkor måste uppfyllas för att skydd ska vara aktivt:

- Spam åtgärder är inställda på att **flytta meddelanden till mappen skräp post** i [principer för skräp post](anti-spam-protection.md).

- Användare har förbehållit sina standardinställningar för [skräp](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)post och har inte avaktiverat skydd mot skräp post.

Mer information finns i [nollställning av automatiskt skydd mot skräp post och skadlig program vara](zero-hour-auto-purge.md).

### <a name="audit-logging-for-reporting-and-investigation"></a>Gransknings loggning för rapportering och undersökning

Gransknings loggning är tillgängligt i abonnemang som innehåller [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). För att kunna visa data i Threat Protection-rapporter, till exempel [säkerhets instrument panelen](security-dashboard.md)och [Utforskaren](threat-explorer.md) [, måste](view-email-security-reports.md)gransknings loggning vara aktiverat för din organisation. Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Uppgifter efter installationen

När du har konfigurerat dina hot Protection-funktioner bör du kontrol lera hur de funktionerna fungerar, granska och revidera dina principer och titta efter nya funktioner och tjänst uppdateringar.

****

|Vad kan jag göra?|Resurser för att få mer information|
|---|---|
|Se hur hot Protection-funktioner fungerar för din organisation genom att visa rapporter|[Säkerhets instrument panel](security-dashboard.md)<br/>[Säkerhets rapporter för e-post](view-email-security-reports.md)<br/>[Rapporter för Office 365 ATP](view-reports-for-atp.md)<br/>[Hotutforskaren](threat-explorer.md)|
|Regelbundet granska och omarbeta dina skydds principer om det behövs|[Säkra Poäng](../mtp/microsoft-secure-score.md)<br/>[Smarta rapporter och insikter](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 hot-och svars funktioner](keep-users-safe-with-office-365-ti.md)|
|Titta efter nya funktioner och tjänste uppdateringar|[Standard-och riktade versions alternativ](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Meddelandecentral](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365-översikt](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Tjänst beskrivningar](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
