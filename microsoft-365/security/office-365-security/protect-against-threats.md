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
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Administratörer kan läsa om hotets skydd i Microsoft 365 och konfigurera hur det ska användas för din organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6ac5b67d589db57d449ba61f07668b10b32706d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845726"
---
# <a name="protect-against-threats"></a>Skydda mot hot

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Här är en snabb start guide som bryter konfigurationen av Defender för Office 365 till delar. Om du är nybörjare i Office 365 och inte vet var du ska börja, eller om du får det genom *att göra* , kan du använda den här vägledningen som en check lista och en utgångs punkt.

> [!IMPORTANT]
> **Initiala rekommenderade inställningar är tillgängliga för alla typer av principer, men du kan också ändra dina inställningar för att uppfylla specifika organisationens behov**. Tillåt cirka 30 minuter för dina principer eller ändringar för att fungera på ett annat sätt via ditt data Center.

## <a name="requirements"></a>Krav

### <a name="subscriptions"></a>Prenumerationer

Hot Protection-funktioner är inkluderade i *alla* Microsoft-eller Office 365-abonnemang; Vissa abonnemang har emellertid avancerade funktioner. I tabellen nedan visas de skydds funktioner som ingår i den här artikeln tillsammans med de minsta abonnemangs kraven.

> [!TIP]
> Observera att, utöver anvisningarna för att aktivera granskning, *att börja mot* skadlig program vara, nätfiske och anti-spam, som är markerade som en del av Office 365 Exchange Online Protection ( **EOP** ). Det kan verka konstigt i en artikel i Defender för Office 365 tills du kommer ihåg ( **Defender för Office 365** ) innehåller och skapar EOP.

****

|Skydds typ|Abonnemangs behov|
|---|---|
|Gransknings loggning (för rapporterings ändamål)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Skydd mot skadlig kod|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) ( **EOP** )|
|Skydd mot nätfiske|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Skydd mot skräppost|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatisk rensning av Tom timme (för e-post)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Skydda från skadliga URL-adresser och filer i e-post och Office-dokument (säkra länkar och säkra bifogade filer)|[Microsoft Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Aktivera ATP för arbets belastning för SharePoint, OneDrive och Microsoft Teams|[Defender för Office 365 ](atp-for-spo-odb-and-teams.md)|
|Avancerat skydd mot nätfiske|[Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Roller och behörigheter

För att konfigurera Defender för Office 365-principer måste du ha en lämplig roll i [säkerhets & efterlevnad](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Ta en titt på tabellen nedan för roller som kan utföra de här åtgärderna.

****

|Roll eller rollgrupp|Var kan jag läsa mer?|
|---|---|
|global administratör|[Om administratörsroller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Säkerhets administratör|[Administratörens rollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Organisations hantering i Exchange Online|[Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>och<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Mer information finns i [behörigheter i säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md).

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Innan du börjar aktiverar du gransknings loggning för rapportering och undersökning

Starta din gransknings loggning tidigt. Du behöver **Granska för vissa** av stegen som följer. Gransknings loggning är tillgängligt i abonnemang som innehåller [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Gransknings loggning måste vara *aktiverat* för att du ska kunna visa data i Threat Protection [email security reports](view-email-security-reports.md)-rapporter, till exempel [säkerhets instrument panelen](security-dashboard.md)och [Utforskaren](threat-explorer.md). Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="part-1---anti-malware-protection"></a>Del 1 – skydd mot skadlig program vara

[Skydd mot skadlig program](anti-malware-protection.md) vara finns i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. Välj skydd mot **Threat management** skadligt Management policy i [Center för säkerhet & efterlevnad](https://protection.office.com)  >  **Policy**  >  **Anti-malware**.

2. Dubbelklicka på **standard** principen och välj sedan **Inställningar**.

3. Ange följande inställningar:

    - Behåll standardinställningen i avsnittet för **identifiering av skadlig program** **vara.**

    - I **filter avsnittet gemensamma bilagor** väljer du **på**.

4. Klicka på **Spara**.

Mer information om alternativ för principer mot skadlig program vara finns i [Konfigurera principer för skadlig program vara](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection"></a>Del 2 – skydd mot nätfiske

[Skydd mot nätfiske](anti-phishing-protection.md) är tillgängligt i abonnemang med [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Avancerat skydd mot nätfiske är tillgängligt i [Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

I följande procedur beskrivs hur du konfigurerar en anti-nätfiske-princip i Microsoft Defender för Office 365. De här stegen är liknande för att konfigurera en skydds policy för en EOP.

1. Välj **Threat Management** policy [Security & Compliance Center](https://protection.office.com)  >  **Policy**  >  **ATP-nätfiske** i säkerhets & Compliance Center.

2. Klicka på **standard policy**.

3. Klicka på **Redigera** i avsnittet **personifiering** och ange sedan följande inställningar:

   - På fliken **Lägg till användare på skydda** *aktiverar du* skydd. Lägg sedan till användare, till exempel organisationens styrelse medlemmar, VD, ekonomi och andra chefs ledare. (Du kan skriva en enskild e-postadress eller klicka på för att visa en lista.)

   - På fliken **Lägg till domäner på skydda** aktiverar **du automatiskt de domäner jag äger**. Om du har anpassade domäner kan du lägga till dem nu.

   - På fliken **åtgärder** väljer du **Quarantine meddelandet** för både den **personifierade användaren** och de **personifierade domän** alternativen. Aktivera också säkerhets tips.

   - På fliken **Mailbox** Intelligence kontrollerar du att post låda-intelligens är aktiverat och aktiverar postbaserad skydd mot postlådan. I listan **om e-post som skickas av en personifierad användare** väljer **du sätt i karantän meddelandet**.

   - På fliken **Lägg till betrodda avsändare och domäner** anger du betrodda avsändare eller domäner som du vill lägga till.

   - **Spara** på fliken **Granska inställningar** när du har granskat dina inställningar.

4. Klicka på **Redigera** i avsnittet **Spoof** och ange sedan följande inställningar:

   - Kontrol lera att skyddet mot förfalskning är aktiverat på fliken **Inställningar för falska filter** .

   - Välj **Quarantine The meddelande** på fliken **Actions** .

   - **Spara** på fliken **Granska inställningar** när du har granskat dina ändringar. (Om du inte har gjort några ändringar **avbryter** du.)

5. Stäng sidan standardinställningar för princip inställningar.

Om du vill veta mer om alternativen för att skydda dina nätfiske-principer läser du [Konfigurera policyer för nätfiske i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection"></a>Del 3-skydd mot skräp post

[Skydd mot skräp post](anti-spam-protection.md) finns i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. I [säkerhets & Compliance Center](https://protection.office.com)väljer du **hot Management**  >  **policy**  >  **anti-spam**.

2. Aktivera anpassade inställningar på fliken **anpassad** .

3. Expandera **standard filter princip för skräp post** , klicka på **Redigera princip** och ange sedan följande inställningar:

   - I avsnittet **skräp post och Mass åtgärder** anger du tröskelvärdet till 5 eller 6.

   - Granska (och/eller redigera) dina tillåtna avsändare och domäner i avsnittet **tillåta listor** .

4. Klicka på **Spara**.

Mer information om alternativen för att förhindra skräp post finns i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Del 4 – skydda skadlig URL-adress och filer (säkra länkar och säkra bifogade filer i Defender för Office 365)

Skydd mot skadlig URL-adress och filer är tillgängligt i abonnemang som innehåller [Microsoft Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Den är inställd genom principer för [säker bifogad fil](atp-safe-attachments.md) och [Safe Links](atp-safe-links.md) .

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Principer för säkra bifogade filer i Microsoft Defender för Office 365

Om du vill konfigurera [säkra bilagor](atp-safe-attachments.md)måste du skapa minst en princip för säkra länkar.

1. I [säkerhets & Compliance Center](https://protection.office.com)väljer du **hot Management**  >  **policy** säkerhets meddelanden om säkerhet  >  , **ATP** och klickar sedan på **skapa**.

2. Konfigurera följande inställningar i guiden **ny princip för säkra bifogade filer** som visas:

   - Skriv i rutan **namn** `Block malware` och klicka sedan på **Nästa**.

   - Konfigurera följande inställningar på sidan **Inställningar** :
     - Välj **blockera** i avsnittet **säkra bifogade filer** .
     - I avsnittet **omdirigera bilaga** väljer du alternativet **Aktivera omdirigering**. Ange e-postadressen för organisationens säkerhets administratör eller-ansvarig, som ska granska upptäckta filer.

     Klicka på **Nästa**.

3. På sidan **används för klickar du** på **Lägg till ett villkor** , **väljer tillämpas om: mottagar domänen är** , klickar du på **Lägg till** , väljer din domän eller dina domäner **, klickar på Lägg till och** **klickar sedan** på **Nästa**.

4. Granska inställningarna och klicka sedan på **Slutför**.

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Principer för säkra länkar i Microsoft Defender för Office 365

Om du vill konfigurera [säkra länkar](atp-safe-links.md)kan du läsa och redigera dina globala inställningar för säkra länkar och skapa minst en princip för säkra länkar.

1. I [säkerhets & Compliance Center](https://protection.office.com)väljer du **Threat Management**  >  **policy**  >  **Safe Links** och klickar på **globala inställningar** och konfigurerar sedan följande inställningar:

   - Verifiera **Använd säkra länkar i: Office 365-program** är aktiverat: ![ slå på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .
   - **Spåra inte när användare klickar på säkra länkar** : inaktivera den här inställningen för att spåra användare: Stäng ![ av ](../../media/scc-toggle-off.png) .
   - **Tillåt inte att användare klickar via säkra länkar till ursprunglig URL** : kontrol lera att den här inställningen är aktive rad: ![ slå på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   Klicka på **Spara** när du är klar.

2. Klicka på **skapa** på sidan huvud säkra länkar.

3. Konfigurera följande inställningar i **princip guiden skapa säkra länkar** som visas:

   - Skriv ett namn i rutan **namn** , till exempel `Safe Links` och klicka sedan på **Nästa**.

   - Konfigurera följande inställningar på sidan **Inställningar** :
     - **Välj åtgärd för okända URL-adresser i meddelanden** : Välj **på**.
     - **Välj åtgärd för okända eller potentiellt skadliga webb adresser i Microsoft Teams** : Välj **på**.
     - **Använda säkra länkar till e-postmeddelanden som skickas inom organisationen**
     - **Vänta på att URL-genomsökningen ska slutföras innan du levererar meddelandet**
     - **Använda säkra länkar till e-postmeddelanden som skickas inom organisationen**
     - **Tillåt inte att användare klickar genom till ursprunglig URL**

     Klicka på **Nästa**

4. På sidan **används för klickar du** på **Lägg till ett villkor** , **väljer tillämpas om: mottagar domänen är** , klickar du på **Lägg till** , väljer din domän eller dina domäner **, klickar på Lägg till och** **klickar sedan** på **Nästa**.

5. Granska inställningarna och klicka sedan på **Slutför**.

Mer information finns i [Ställ in policyer för säkra länkar](set-up-atp-safe-links-policies.md).

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Del 5 – kontrol lera ATP för SharePoint, OneDrive och Microsoft Teams

Arbets belastningar som SharePoint, OneDrive och Teams är byggda för samarbete. Med Defender för Office 365 får du hjälp med blockering och identifiering av filer som identifieras som skadliga på grupp webbplatser och dokument bibliotek. Du kan läsa mer om hur det fungerar [här](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams).

> [!IMPORTANT]
> **Innan du påbörjar den här proceduren bör du kontrol lera att gransknings loggning redan är aktiverat för din Microsoft 365-miljö**. Det gör du vanligt vis av någon som har rollen gransknings loggar som tilldelats i Exchange Online. Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md)!

1. I [säkerhets & Compliance Center](https://protection.office.com)väljer du **hot Management**  >  **policy**  >  **säkerhets** **Inställningar** för fler spar ande bilagor

2. Kontrol lera att växla mellan **ATP för SharePoint, OneDrive och Microsoft Teams** är till höger: ![ slå på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) och klicka sedan på **Spara**.

3. Granska (och, om tillämpligt, redigera) organisationens principer för [säkert bifogade filer](set-up-atp-safe-attachments-policies.md) och [säkra länkar](set-up-atp-safe-links-policies.md).

4. Lämpligt Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern _DisallowInfectedFileDownload_ inställd på `$true` .

   - `$true` blockerar alla åtgärder (förutom borttagning) för identifierade filer. Personer kan inte öppna, flytta, kopiera eller dela identifierade filer.
   - `$false` alla åtgärder förutom Delete och nedladdning blockeras. Andra kan välja att acceptera risken och hämta en identifierad fil.

   > [!TIP]
   > Mer information om hur du använder PowerShell med Microsoft 365 finns i [Hantera Microsoft 365 med PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).

5. Tillåt upp till 30 minuter för att ändringarna ska spridas till alla Microsoft 365-datacenter.

### <a name="now-set-up-alerts-for-detected-files"></a>Konfigurera aviseringar för identifierade filer

Om du vill få aviseringar när en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams har identifierats som skadlig kan du ställa in en avisering.

1. I fönstret [säkerhets & efterlevnad](https://protection.office.com)väljer du **aviseringar** \> **Hantera aviseringar**.

2. Välj **ny aviserings princip**.

3. Ange ett namn för aviseringen. Du kan till exempel skriva in skadliga filer i bibliotek.

4. Ange en beskrivning av aviseringen. Du kan till exempel skriva meddelanden administratörer när skadliga filer upptäcks i SharePoint Online, OneDrive eller Microsoft Teams.

5. I avsnittet **Skicka aviseringen när...** anger du:

   a. Välj **upptäckt skadlig kod i filen** i listan **aktiviteter** .

   b. Lämna fältet **användare** tomma.

6. I avsnittet **Skicka aviseringen till... väljer du** en eller flera globala administratörer, säkerhets administratörer eller säkerhets läsare som ska få avisering när en skadlig fil identifieras.

7. **Spara**.

Om du vill veta mer om aviseringar läser [du skapa aktivitets aviseringar i avsnittet säkerhets & efterlevnad](../../compliance/create-activity-alerts.md).

> [!NOTE]
> När du är klar med konfigurationen kan du använda de här länkarna för att starta arbets belastnings undersökningar:
>
>- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
>- [Använda säkerhets & Compliance Center för att hantera filer i karantän](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Vad kan jag göra? när en skadlig fil hittas i SharePoint Online, OneDrive eller Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Del 6 – ytterligare inställningar att konfigurera

Förutom att konfigurera skydd från skadlig program vara, skadliga URL-adresser och filer, nätfiske och skräp post rekommenderar vi att du konfigurerar automatisk rensning av en tom timme.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Automatisk rensning av Tom timme för e-post i EOP

[Automatisk rensning för noll-timme](zero-hour-auto-purge.md) är tillgängligt i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Detta skydd är aktiverat som standard. men följande villkor måste uppfyllas för att skydd ska vara aktivt:

- Spam åtgärder är inställda på att **flytta meddelanden till mappen skräp post** i [principer för skräp post](anti-spam-protection.md).

- Användare har förbehållit sina standardinställningar för [skräp](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)post och har inte avaktiverat skydd mot skräp post.

Mer information finns i [nollställning av automatiskt skydd mot skräp post och skadlig program vara](zero-hour-auto-purge.md).

## <a name="post-setup-tasks-and-next-steps"></a>Åtgärder efter installationen och nästa steg

När du har konfigurerat hotets skydds funktioner ser du till att övervaka hur funktionerna fungerar! Granska och omarbeta dina principer så att de gör det du behöver dem. Titta också efter nya funktioner och tjänst uppdateringar som kan lägga till ett värde.

****

|Vad kan jag göra?|Resurser för att få mer information|
|---|---|
|Se hur hot Protection-funktioner fungerar för din organisation genom att visa rapporter|[Säkerhets instrument panel](security-dashboard.md)<br/>[Säkerhets rapporter för e-post](view-email-security-reports.md)<br/>[Rapporter för Microsoft Defender för Office 365](view-reports-for-atp.md)<br/>[Hotutforskaren](threat-explorer.md)|
|Regelbundet granska och omarbeta dina skydds principer om det behövs|[Säkra Poäng](../mtp/microsoft-secure-score.md)<br/>[Smarta rapporter och insikter](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 hot-och svars funktioner](keep-users-safe-with-office-365-ti.md)|
|Titta efter nya funktioner och tjänste uppdateringar|[Standard-och riktade versions alternativ](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Meddelandecentral](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Översikt över Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Tjänst beskrivningar](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Lär dig mer om rekommenderade standard-och strikta säkerhetskonfigurationer för EOP och Defender för Office 365|[Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md)|
