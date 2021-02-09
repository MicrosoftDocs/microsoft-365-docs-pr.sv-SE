---
title: Skydda mot hot
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan läsa mer om skydd mot hot i Microsoft 365 och konfigurera hur de ska använda det för din organisation.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb2866fd3e60c021ae89ffabe7149f4b415d63bc
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150718"
---
# <a name="protect-against-threats"></a>Skydda mot hot

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Här är en snabbstartsguide som delar upp konfigurationen av Defender för Office 365. Om du inte har börjat använda skyddsfunktioner för hot i Office 365 förr eller är osäker på var du ska börja, eller om du lär dig bäst genom att göra det, kan du använda den här vägledningen som en checklista och en utgångspunkt.

> [!IMPORTANT]
> **De rekommenderade initiala inställningarna** ingår för varje typ av princip, men det finns många alternativ och du kan justera inställningarna så att de uppfyller organisationens behov. Det tar ungefär 30 minuter för principer eller ändringar att fungera genom datacentret.

## <a name="requirements"></a>Krav

### <a name="subscriptions"></a>Prenumerationer

Skyddsfunktioner för hot ingår *i* alla Microsoft- eller Office 365-prenumerationer. Men vissa prenumerationer har avancerade funktioner. I tabellen nedan visas de skyddsfunktioner som ingår i den här artikeln tillsammans med de lägsta prenumerationskraven.

> [!TIP]
> Lägg märke till att stegen, förutom anvisningarna för att aktivera *granskning,* startar skydd mot skadlig programvara, skydd mot nätfiske och skräppost, som markeras som en del av Office 365 Exchange Online Protection **(EOP).** Det kan verka konstigt i en Defender för Office 365-artikel tills du kommer ihåg att (Defender för **Office 365)** innehåller, och bygger på, EOP.

****

|Skyddstyp|Prenumerationskrav|
|---|---|
|Granskningsloggning (i rapporteringssyfte)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Skydd mot skadlig kod|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) **(EOP)**|
|Skydd mot nätfiske|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Skydd mot skräppost|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatisk rensning utan timme (för e-post)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Skydd mot skadliga URL:er och filer i e-post och Office-dokument (säkra länkar och säkra bifogade filer)|[Microsoft Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Aktivera säkra bifogade filer för SharePoint-, OneDrive- och Microsoft Teams-arbetsbelastningar|[Defender för Office 365 ](atp-for-spo-odb-and-teams.md)|
|Avancerat skydd mot nätfiske|[Defender förr Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Roller och behörigheter

Om du vill konfigurera Defender för Office 365-principer måste du ha tilldelats en lämplig roll i [Säkerhets- & Efterlevnadscenter.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) I tabellen nedan ser du vilka roller som kan utföra de här åtgärderna.

****

|Roll eller rollgrupp|Här kan du lära dig mer|
|---|---|
|global administratör|[Om administratörsroller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Säkerhetsadministratör|[Administratörens rollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Organisationshantering i Exchange Online|[Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> och <p> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Mer information finns i [Behörigheter i Säkerhets- & Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Innan du börjar aktiverar du granskningsloggning för rapportering och undersökning

Starta granskningsloggningen tidigt. Du måste ha granskning på **för** vissa av stegen som följer. Granskningsloggning är tillgänglig i prenumerationer som innehåller [Exchange Online.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) För att kunna visa data i skyddsrapporter, till exempel instrumentpanelen för [säkerhet,](security-dashboard.md)e-postsäkerhetsrapporter och [Utforskaren,](threat-explorer.md)måste granskningsloggning vara *på.* [](view-email-security-reports.md) Mer information finns i Aktivera [eller inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Del 1 – Skydd mot skadlig programvara

[Skydd mot skadlig programvara är](anti-malware-protection.md) tillgängligt i prenumerationer som innehåller [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Välj [Skydd mot skadlig programvara &](https://protection.office.com) **Säkerhets-** \> **och** \> efterlevnadscenter.

2. Dubbelklicka på **standardprincipen** och välj **inställningar.**

3. Ange följande inställningar:

    - Behåll **standardinställningen Nej** i avsnittet Svar för identifiering av skadlig **kod.**

    - Välj På **i avsnittet Vanliga typer av** bifogade **filer.**

4. Klicka på **Spara**.

Mer information om policyalternativ för skadlig programvara finns i [Konfigurera principer för skadlig programvara.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection"></a>Del 2 – Skydd mot nätfiske

[Skydd mot nätfiske är](anti-phishing-protection.md) tillgängligt i prenumerationer som innehåller [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Avancerat skydd mot nätfiske finns i [Defender för Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

Här beskrivs hur du konfigurerar en princip mot nätfiske i Microsoft Defender för Office 365. Stegen liknar varandra när du konfigurerar en princip mot nätfiske i EOP.

1. I [Säkerhets- & Center väljer](https://protection.office.com)du ATP för  \> **hothanteringspolicy** \> **mot nätfiske.**

2. Klicka **på Standardprincip.**

3. Klicka på **Redigera i** avsnittet **Personifiering** och ange sedan följande inställningar:

   - Aktivera **skydd på fliken Lägg till** användare för att *skydda.* Sedan kan du lägga till användare, till exempel organisationens styrelsemedlemmar, din VD, ekonomichef och andra högre chefer. (Du kan skriva en enskild e-postadress eller klicka för att visa en lista.)

   - På fliken **Lägg till domäner för att** skydda aktiverar du Inkludera automatiskt de domäner jag **äger.** Om du har egna domäner kan du lägga till dem nu.

   - Välj Sätt **meddelandet** i karantän för  **både den personifierade** användaren och de imiterade **domänalternativen på fliken** Åtgärder. Aktivera även säkerhetstips för personifiering.

   - Kontrollera att **postlådeinformation** är aktiverat på fliken Postlådeinformation och aktivera postlådebaserat personifieringsskydd. I listan **Om e-post skickas med en imiterad** användare väljer du **Sätt meddelandet i karantän.**

   - På fliken **Lägg till betrodda avsändare och** domäner anger du de betrodda avsändare eller domäner som du vill lägga till.

   - **Spara** på **fliken Granska dina** inställningar när du har granskat inställningarna.

4. Klicka på **Redigera i** avsnittet **Förfalskning** och ange sedan följande inställningar:

   - Kontrollera **att skydd** mot förfalskning är aktiverat på fliken Inställningar för förfalskning.

   - Välj **Sätt meddelandet** i karantän **på fliken Åtgärder.**

   - **Spara** på **fliken Granska dina** inställningar när du har granskat ändringarna. (Avbryt om du inte har gjort **några** ändringar.)

5. Stäng sidan med standardprincipinställningar.

Mer information om alternativen för nätfiskeprinciper finns i Konfigurera principer mot nätfiske i [Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection"></a>Del 3 – Skydd mot skräppost

[Skydd mot skräppost är tillgängligt](anti-spam-protection.md) i prenumerationer som innehåller [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Välj [Skydd mot skräppost i & Säkerhets-](https://protection.office.com)  \> **och efterlevnadscenter.** \> 

2. Aktivera **Anpassade** inställningar på fliken Anpassad.

3. Expandera **standardprincipen för skräppostfilter,** klicka på **Redigera** princip och ange sedan följande inställningar:

   - I avsnittet **Skräppost- och massåtgärder** anger du tröskelvärdet till 5 eller 6.

   - Gå till **avsnittet Tillåt,** granska (och/eller redigera) dina tillåtna avsändare och domäner.

4. Klicka på **Spara**.

Mer information om policyalternativen för skydd mot skräppost finns i [Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Del 4 – Skydd mot skadliga URL:er och filer (säkra länkar och säkra bifogade filer i Defender för Office 365)

Tids för klick-skydd mot skadliga URL:er och filer är tillgängligt i prenumerationer som [inkluderar Microsoft Defender för Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Den konfigureras via principer [för säkra bifogade](atp-safe-attachments.md) filer och [säkra](atp-safe-links.md) länkar.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Principer för säkra bifogade filer i Microsoft Defender för Office 365

Skapa minst [en princip för](atp-safe-attachments.md)säkra länkar om du vill konfigurera säkra bifogade filer.

1. I [Säkerhets- & Center väljer](https://protection.office.com)du ATP **för** hothanteringspolicy , säkra \>  \> **bifogade** filer och klickar sedan på **Skapa.**

2. I den **nya principguiden för säkra** bifogade filer som visas konfigurerar du följande inställningar:

   - Skriv **i rutan** Namn `Block malware` och klicka sedan på **Nästa.**

   - Konfigurera **följande** inställningar på sidan Inställningar:
     - Välj Blockera **i avsnittet Säkra bifogade filer som inte** är kända för skadlig **programvara.**
     - Markera alternativet **Aktivera** omdirigering i avsnittet **Omdirigering av bifogad fil.** Ange e-postadressen till organisationens säkerhetsadministratör eller operatör, som ska granska identifierade filer.

     Klicka på **Nästa**.

3. Klicka på Lägg till ett **villkor** på sidan Används på, välj Används **om:** Mottagarens domän är, klicka på Lägg **till,** välj din domän eller domäner, klicka på Lägg **till,** klicka på Klar och klicka sedan på  **Nästa.**

4. Granska inställningarna och klicka sedan på **Slutför.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Principer för säkra länkar i Microsoft Defender för Office 365

Konfigurera säkra [länkar, granska](atp-safe-links.md)och redigera dina globala inställningar för säkra länkar och skapa minst en princip för säkra länkar.

1. I [Säkerhets- & Säkerhets-](https://protection.office.com)  och efterlevnadscenter väljer du ATP – säkra länkar för hothanteringspolicy, klickar på Globala inställningar och \>  \> konfigurerar sedan följande inställningar: 

   - Kontrollera **Att Använd säkra länkar i: Office 365-program** är aktiverat: Slå ![ ](../../media/scc-toggle-on.png) på.
   - **Spåra inte när användare klickar på Säkra länkar**: Inaktivera den här inställningen om du vill spåra användarklick: ![ ](../../media/scc-toggle-off.png) Inaktivera.
   - **Låt inte användare klicka sig fram genom säkra länkar till den ursprungliga** URL:en: Kontrollera att den här inställningen är ![ aktiverad: ](../../media/scc-toggle-on.png) Aktivera.

   Klicka på **Spara** när du är klar.

2. Tillbaka på huvudsidan för Säkra länkar klickar du på **Skapa.**

3. Konfigurera **följande inställningar i guiden Skapa** säkra länkar som visas:

   - Skriv **ett namn** i rutan Namn, till `Safe Links` exempel, och klicka sedan på **Nästa.**

   - Konfigurera **följande** inställningar på sidan Inställningar:
     - **Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden:** Välj **På.**
     - **Välj åtgärden för okända eller potentiellt skadliga URL-adresser i Microsoft Teams:** **Välj På.**
     - **Använda säkra länkar i e-postmeddelanden som skickas inom organisationen**
     - **Vänta tills URL-skanningen har slutförts innan meddelandet levereras**
     - **Använda säkra länkar i e-postmeddelanden som skickas inom organisationen**
     - **Tillåt inte att användare klickar till den ursprungliga URL:en**

     Klicka på **Nästa**

4. Klicka på Lägg till ett **villkor** på sidan Används för, välj Används **om:** Mottagarens domän är, klicka på Lägg **till,** välj din domän eller domäner, klicka på Lägg **till,** klicka på Klar och klicka sedan på  **Nästa.**

5. Granska inställningarna och klicka sedan på **Slutför.**

Mer information finns i [Ställ in policyer för säkra länkar](set-up-atp-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Del 5 – Verifiera säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams är aktiverat

Arbetsbelastningar som SharePoint, OneDrive och Teams är byggda för samarbete. Med hjälp av Defender för Office 365 kan du blockera och identifiera filer som identifieras som skadliga på gruppwebbplatser och dokumentbibliotek. Du kan läsa mer om hur det fungerar [här.](atp-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> **Innan du börjar kontrollerar du att granskningsloggning redan är aktiverad för Microsoft 365-miljön.** Det görs vanligtvis av någon som har tilldelats rollen Granskningsloggar i Exchange Online. Mer information finns i Aktivera [eller inaktivera granskningsloggsökning!](../../compliance/turn-audit-log-search-on-or-off.md)

1. I [Säkerhets- & Center väljer](https://protection.office.com)  du ATP för hanteringspolicy för säkra bifogade filer och klickar \>  \> sedan på **Globala inställningar.**

2. Kontrollera att växlingsknappen Aktivera Defender för **Office 365 för SharePoint, OneDrive** och Microsoft Teams är till höger: Aktivera och klicka sedan ![ på ](../../media/scc-toggle-on.png) **Spara.**

3. Granska (och vid behov, redigera) organisationens principer för [säkra bifogade](set-up-atp-safe-attachments-policies.md) filer och principer för [säkra länkar.](set-up-atp-safe-links-policies.md)

4. (Rekommenderas) Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med _parametern DisallowInfectedFileDownload_ inställd `$true` på.

   - `$true` blockerar alla åtgärder (utom Ta bort) för identifierade filer. Användare kan inte öppna, flytta, kopiera eller dela identifierade filer.
   - `$false` blockerar alla åtgärder utom Ta bort och Ladda ned. Personer kan välja att acceptera risken och ladda ned en upptäckt fil.

   > [!TIP]
   > Mer information om hur du använder PowerShell med Microsoft 365 finns i [Hantera Microsoft 365 med PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)

5. Tillåt upp till 30 minuter för dina ändringar att spridas till alla Microsoft 365-datacenter.

### <a name="now-set-up-alerts-for-detected-files"></a>Konfigurera nu aviseringar för identifierade filer

Om du vill få ett meddelande när en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams har identifierats som skadlig kan du konfigurera en avisering.

1. Välj Aviseringar [hantera aviseringar & Säkerhets-](https://protection.office.com)och  \> **efterlevnadscenter.**

2. Välj **Ny aviseringsprincip.**

3. Ange ett namn för aviseringen. Du kan till exempel skriva Skadliga filer i bibliotek.

4. Skriv en beskrivning för aviseringen. Du kan till exempel skriva Meddela administratörer när skadliga filer upptäcks i SharePoint Online, OneDrive eller Microsoft Teams.

5. I avsnittet **Skicka den här aviseringen när...** anger du:

   a. Välj Identifierade **skadlig** programvara i filen i **listan Aktiviteter.**

   b. Lämna **fältet Användare** tomt.

6. I avsnittet **Skicka den här aviseringen till...** väljer du en eller flera globala administratörer, säkerhetsadministratörer eller säkerhetsläsare som ska få ett meddelande när en skadlig fil identifieras.

7. **Spara.**

Mer information om aviseringar finns i [Skapa aktivitetsaviseringar i Säkerhets- & Efterlevnadscenter.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> När du är klar med konfigureringen kan du använda de här länkarna för att starta undersökningar om arbetsbelastningen:
>
>- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
>- [Använda Säkerhets- & för att hantera filer i karantän](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Vad kan jag göra när en skadlig fil hittas i SharePoint Online, OneDrive eller Microsoft Teams?](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Del 6 – Ytterligare inställningar att konfigurera

Förutom att konfigurera skydd mot skadlig programvara, skadliga URL:er och filer, nätfiske och skräppost rekommenderar vi att du konfigurerar automatisk rensning utan timme.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Automatisk rensning utan timme för e-post i EOP

[ZAP (Zero-hour auto purge)](zero-hour-auto-purge.md) är tillgängligt i prenumerationer som inkluderar [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Det här skyddet är aktiverat som standard. Följande villkor måste dock vara uppfyllda för att skyddet ska gälla:

- Skräppoståtgärder är inställda på **att flytta meddelanden till mappen Skräppost** i principer för [skräppostskydd.](anti-spam-protection.md)

- Användarna har kvar sina [standardinställningar för skräppost](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)och har inte inaktiverat skräppostskyddet.

Mer information finns i Automatisk rensning [på nolltimmar – skydd mot skräppost och skadlig programvara.](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>Uppgifter efter installationen och nästa steg

När du har konfigurerat funktionerna för skydd mot hot bör du övervaka hur funktionerna fungerar! Granska och ändra dina principer så att de gör vad du behöver för dem. Titta också efter nya funktioner och tjänstuppdateringar som kan tillför något extra.

****

|Vad kan jag göra?|Resurser för att få mer information|
|---|---|
|Se hur skyddsfunktioner för hot fungerar för din organisation genom att visa rapporter|[Säkerhetsinstrumentpanel](security-dashboard.md) <p> [E-postsäkerhetsrapporter](view-email-security-reports.md) <p> [Rapporter för Microsoft Defender för Office 365](view-reports-for-atp.md) <p> [Hotutforskaren](threat-explorer.md)|
|Regelbundet granska och revidera dina principer för skydd mot hot efter behov|[Secure Score](../mtp/microsoft-secure-score.md) <p> [Smarta rapporter och insikter](reports-and-insights-in-security-and-compliance.md) <p> [Funktioner för undersökning av hot och hot i Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Håll utkik efter nya funktioner och tjänstuppdateringar|[Alternativ för standard och riktad version](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365) <p> [Meddelandecentral](https://docs.microsoft.com/microsoft-365/admin/manage/message-center) <p> [Översikt över Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Tjänstbeskrivningar](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Läs mer om rekommenderade standard- och strikt säkerhetskonfigurationer för EOP och Defender för Office 365|[Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md)|
