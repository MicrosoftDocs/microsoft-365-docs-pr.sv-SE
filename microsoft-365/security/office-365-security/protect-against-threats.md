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
description: Administratörer kan läsa om hotets skydd i Microsoft 365 och konfigurera hur det ska användas för din organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b96ba1735f94e80450fa4f604fc45dc60b80d12
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417128"
---
# <a name="protect-against-threats"></a>Skydda mot hot

Här är en snabb start guide som bryter ned konfigurationen av avancerat skydd mot segment. Om du är nybörjare i Office 365 och inte vet var du ska börja, eller om du får det genom *att göra*, kan du använda den här vägledningen som en check lista och en utgångs punkt.

> [!IMPORTANT]
> **Initiala rekommenderade inställningar är tillgängliga för alla typer av principer, men du kan också ändra dina inställningar för att uppfylla specifika organisationens behov**. Tillåt cirka 30 minuter för dina principer eller ändringar för att fungera på ett annat sätt via ditt data Center.

## <a name="requirements"></a>Krav

### <a name="subscriptions"></a>Prenumerationer

Hot Protection-funktioner är inkluderade i *alla* Microsoft-eller Office 365-abonnemang; Vissa abonnemang har emellertid avancerade funktioner. I tabellen nedan visas de skydds funktioner som ingår i den här artikeln tillsammans med de minsta abonnemangs kraven.

> [!TIP]
> Observera att, utöver anvisningarna för att aktivera granskning, *att börja mot* skadlig program vara, nätfiske och anti-spam, som är markerade som en del av Office 365 Exchange Online Protection (**EOP**). Detta kan verka så udda ut i en artikel för avancerat skydd, tills du får ett avancerat skydd (**ATP**) och bygger på EOP.

****

|Skydds typ|Abonnemangs behov|
|---|---|
|Gransknings loggning (för rapporterings ändamål)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Skydd mot skadlig kod|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Skydd mot nätfiske|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Skydd mot skräppost|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatisk rensning av Tom timme (för e-post)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Skydda från skadliga URL-adresser och filer i e-post och Office-dokument (säkra länkar och säkra bifogade filer)|[Office 365 Avancerat skydd](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)|
|Aktivera ATP för arbets belastning för SharePoint, OneDrive och Microsoft Teams| [LOVA](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)|
|Avancerat skydd mot nätfiske|[LOVA](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Roller och behörigheter

För att kunna konfigurera ATP-principer måste du ha tilldelats en lämplig roll i [säkerhets & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Ta en titt på tabellen nedan för roller som kan utföra de här åtgärderna.

****

|Roll eller rollgrupp|Var kan jag läsa mer?|
|---|---|
|global administratör|[Om administratörsroller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Säkerhets administratör|[Administratörens rollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Organisations hantering i Exchange Online|[Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>och<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Mer information finns i [behörigheter i säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md).

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Innan du börjar aktiverar du gransknings loggning för rapportering och undersökning

Starta din gransknings loggning tidigt. Du behöver **Granska för vissa** av stegen som följer. Gransknings loggning är tillgängligt i abonnemang som innehåller [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Gransknings loggning måste vara *aktiverat*för att du ska kunna visa data i Threat Protection [email security reports](view-email-security-reports.md)-rapporter, till exempel [säkerhets instrument panelen](security-dashboard.md)och [Utforskaren](threat-explorer.md). Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="part-1---anti-malware-protection"></a>Del 1 – skydd mot skadlig program vara

[Skydd mot skadlig program](anti-malware-protection.md) vara finns i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. Välj skydd mot **Threat management**skadligt Management policy i [Center för säkerhet & efterlevnad](https://protection.office.com)  >  **Policy**  >  **Anti-malware**.

2. Dubbelklicka på **standard** principen och välj sedan **Inställningar**.

3. Ange följande inställningar:

    - Behåll standardinställningen i avsnittet för **identifiering av skadlig program** **vara.**

    - I **filter avsnittet gemensamma bilagor** väljer du **på**.

4. Klicka på **Spara**.

Mer information om alternativ för principer mot skadlig program vara finns i [Konfigurera principer för skadlig program vara](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection"></a>Del 2 – skydd mot nätfiske

[Anti-nätfiske]

[Skydd mot nätfiske](anti-phishing-protection.md) är tillgängligt i abonnemang med [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Avancerat skydd mot nätfiske är tillgängligt i [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Här beskrivs hur du konfigurerar en policy för ATP-anti-nätfiske. De här stegen är liknande för att konfigurera en anti-nätfiske-princip (utan ATP).

1. Välj **Threat Management**policy [Security & Compliance Center](https://protection.office.com)  >  **Policy**  >  **ATP-nätfiske**i säkerhets & Compliance Center.

2. Klicka på **standard policy**.

3. Klicka på **Redigera**i avsnittet **personifiering** och ange sedan följande inställningar:

   - På fliken **Lägg till användare på skydda** *aktiverar du* skydd. Lägg sedan till användare, till exempel organisationens styrelse medlemmar, VD, ekonomi och andra chefs ledare. (Du kan skriva en enskild e-postadress eller klicka på för att visa en lista.)

   - På fliken **Lägg till domäner på skydda** aktiverar **du automatiskt de domäner jag äger**. Om du har anpassade domäner kan du lägga till dem nu.

   - På fliken **åtgärder** väljer du **Quarantine meddelandet** för både den **personifierade användaren** och de **personifierade domän** alternativen. Aktivera också säkerhets tips.

   - På fliken **Mailbox** Intelligence kontrollerar du att post låda-intelligens är aktiverat och aktiverar postbaserad skydd mot postlådan. I listan **om e-post som skickas av en personifierad användare** väljer **du sätt i karantän meddelandet**.

   - På fliken **Lägg till betrodda avsändare och domäner** anger du betrodda avsändare eller domäner som du vill lägga till.

   - **Spara** på fliken **Granska inställningar** när du har granskat dina inställningar.

4. Klicka på **Redigera**i avsnittet **Spoof** och ange sedan följande inställningar:

   - Kontrol lera att skyddet mot förfalskning är aktiverat på fliken **Inställningar för falska filter** .

   - Välj **Quarantine The meddelande**på fliken **Actions** .

   - **Spara** på fliken **Granska inställningar** när du har granskat dina ändringar. (Om du inte har gjort några ändringar **avbryter**du.)

5. Stäng sidan standardinställningar för princip inställningar.

Mer information om dina alternativ för skydd mot nätfiske finns i avsnittet [Konfigurera AntiPhishing-principer för ATP](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection"></a>Del 3-skydd mot skräp post

[Skydd mot skräp post](anti-spam-protection.md) finns i abonnemang som innehåller [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. I [säkerhets & Compliance Center](https://protection.office.com)väljer du **hot Management**  >  **policy**  >  **anti-spam**.

2. Aktivera anpassade inställningar på fliken **anpassad** .

3. Expandera **standard filter princip för skräp post**, klicka på **Redigera princip**och ange sedan följande inställningar:

   - I avsnittet **skräp post och Mass åtgärder** anger du tröskelvärdet till 5 eller 6.

   - Granska (och/eller redigera) dina tillåtna avsändare och domäner i avsnittet **tillåta listor** .

4. Klicka på **Spara**.

Mer information om alternativen för att förhindra skräp post finns i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments"></a>Del 4 – skydda skadlig URL och filer (säkra länkar och säkra bifogade filer)

Skydd mot skadlig URL-adress och filer är tillgängligt i abonnemang som inkluderar [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP). Det är inställt med principer för säkra [bilagor via ATP](atp-safe-attachments.md) och [Safe Links för ATP](atp-safe-links.md) .

### <a name="atp-safe-attachments-policies"></a>Principer för säkra bifogade filer via ATP

För att konfigurera [säkerhet för säkerhets](atp-safe-attachments.md)skull för ATP måste du definiera minst en policy för säker användning av ATP.

1. Välj **Threat Management**policy [Security & Compliance Center](https://protection.office.com)  >  **Policy**  >  **Safe Attachments**i säkerhets & Compliance Center.

2. Välj alternativet **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.

3. Klicka på plus tecknet () i avsnittet **skydda e-postbilagor** **+** .

4. Ange följande inställningar:

   - Skriv i rutan **namn** `Block malware` .

   - I avsnittet svar väljer du **blockera**.

   - I avsnittet **omdirigera bilaga** väljer du alternativet **Aktivera omdirigering**. Ange e-postadressen för organisationens säkerhets administratör eller-ansvarig, som ska granska upptäckta filer.

   - I avsnittet **används för** väljer **du mottagaren**. Välj sedan din domän, Välj **Lägg till**och sedan **OK**.

5. **Spara**.

6. (**Rekommenderat steg**) Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern **DisallowInfectedFileDownload** inställd på  *True* för din Microsoft 365-miljö. (Detta förhindrar att personer öppnar, flyttar, kopierar eller delar filer som identifieras som skadliga.)

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

   - I avsnittet **används för** väljer **du mottagaren**. Välj sedan din domän, Välj **Lägg till**och sedan **OK**.

6. **Spara**.

Mer information finns i [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md)(Konfigurera Office 365 ATP-principer för säkra länkar).

## <a name="part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads"></a>Del 5 – aktivera ATP för arbets belastning för SharePoint, OneDrive och Microsoft Teams

Arbets belastningar som SharePoint, OneDrive och Teams är byggda för samarbete. Genom att använda ATP kan du blockera och upptäcka filer som identifieras som skadliga på grupp webbplatser och dokument bibliotek. Du kan läsa mer om hur det fungerar [här](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide).

> [!IMPORTANT]
> **Innan du påbörjar den här proceduren bör du kontrol lera att gransknings loggning redan är aktiverat för din Microsoft 365-miljö**. Det gör du vanligt vis av någon som har rollen gransknings loggar som tilldelats i Exchange Online. Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md)!

1. Gå till <https://protection.office.com> och logga in med ditt arbets-eller skol konto.

2. I det vänstra navigerings **fältet under säkerhets**& Compliance Center väljer du **policy** \> **Safe Attachments**.

   ![Välj Threat Management policy i Center för säkerhet & efterlevnad \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. Välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.

   ![Aktivera avancerat skydd för SharePoint Online, OneDrive för företag och Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. **Spara**.

5. Granska (och, om tillämpligt, redigera) organisationens principer för [säkert bifogade filer](set-up-atp-safe-attachments-policies.md) och [säkra länkar](set-up-atp-safe-links-policies.md).

6. Lämpligt Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern _DisallowInfectedFileDownload_ angiven till *True*.

   - Om du anger parametern till *True* blockeras alla åtgärder (förutom borttagning) för identifierade filer. Personer kan inte öppna, flytta, kopiera eller dela identifierade filer.

   - Om du anger parametern till *falskt* blockeras alla åtgärder förutom Delete och nedladdning. Andra kan välja att acceptera risken och hämta en identifierad fil.
   > [!TIP] Mer information om hur du använder PowerShell med Microsoft 365 finns i [Hantera Microsoft 365 med PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).

7. Tillåt upp till 30 minuter för att ändringarna ska spridas till alla Microsoft 365-datacenter.


#### <a name="now-set-up-alerts-for-detected-files"></a>Konfigurera aviseringar för identifierade filer

Om du vill få aviseringar när en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams har identifierats som skadlig kan du ställa in en avisering.

1. I fönstret [säkerhets & efterlevnad](https://protection.office.com)väljer du **aviseringar** \> **Hantera aviseringar**.

2. Välj **ny aviserings princip**.

3. Ange ett namn för aviseringen. Du kan till exempel skriva in skadliga filer i bibliotek.

4. Ange en beskrivning av aviseringen. Du kan till exempel skriva meddelanden administratörer när skadliga filer upptäcks i SharePoint Online, OneDrive eller Microsoft Teams.

5. I avsnittet **Skicka aviseringen när...** anger du:

   a. Välj **upptäckt skadlig kod i filen**i listan **aktiviteter** .

   b. Lämna fältet **användare** tomma.

6. I avsnittet **Skicka aviseringen till... väljer du** en eller flera globala administratörer, säkerhets administratörer eller säkerhets läsare som ska få avisering när en skadlig fil identifieras.

7. **Spara**.

Om du vill veta mer om aviseringar läser [du skapa aktivitets aviseringar i avsnittet säkerhets & efterlevnad](../../compliance/create-activity-alerts.md).

> [!NOTE]
> När du är klar med konfigurationen kan du använda de här länkarna för att starta arbets belastnings undersökningar:
>- [Visa information om skadliga filer som identifieras i SharePoint, OneDrive eller Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
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
|Se hur hot Protection-funktioner fungerar för din organisation genom att visa rapporter|[Säkerhets instrument panel](security-dashboard.md)<br/>[Säkerhets rapporter för e-post](view-email-security-reports.md)<br/>[Rapporter för Office 365 ATP](view-reports-for-atp.md)<br/>[Hotutforskaren](threat-explorer.md)|
|Regelbundet granska och omarbeta dina skydds principer om det behövs|[Säkra Poäng](../mtp/microsoft-secure-score.md)<br/>[Smarta rapporter och insikter](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 hot-och svars funktioner](keep-users-safe-with-office-365-ti.md)|
|Titta efter nya funktioner och tjänste uppdateringar|[Standard-och riktade versions alternativ](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Meddelandecentral](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365-översikt](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Tjänst beskrivningar](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Lär dig mer om rekommenderade standard-och strikta säkerhetskonfigurationer för EOP och ATP | [Rekommenderade inställningar för EOP och Office 365 säkerhet för ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) |
