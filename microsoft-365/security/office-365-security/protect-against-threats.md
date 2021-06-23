---
title: Skydda mot hot i Microsoft Defender för Office 365, skadlig programvara, skydd mot nätfiske, skräppost, Valv-länkar, Valv-bilagor, zap (Zero-hour auto purge), MDO-säkerhetskonfiguration
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 06/22/2021
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan läsa mer om skydd mot hot i Microsoft 365 konfigurera hur de ska använda det för din organisation.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31ca7c27e3be20e20c16004490bd2ecd5ca4ae05
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083686"
---
# <a name="protect-against-threats"></a>Skydda mot hot

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Här är en snabbstartsguide som bryter konfigurationen av Defender för Office 365 delar. Om du inte har börjat använda skyddsfunktioner för hot i Office 365, är osäker på var du ska börja eller om du lär dig bäst genom att göra det kan du använda den här vägledningen som en checklista och en utgångspunkt.

> [!IMPORTANT]
> **Rekommenderade initiala inställningar ingår för** varje typ av princip, men det finns många alternativ och du kan justera inställningarna så att de uppfyller organisationens behov. Det kan ta ungefär 30 minuter innan principerna eller ändringarna fungerar via datacentret.
>
> Om du vill hoppa över manuell konfiguration av de flesta principer i Defender Office 365 kan du använda förinställda säkerhetsprinciper på nivå standard eller strikt. Mer information finns i [Förinställda säkerhetsprinciper i EOP och Microsoft Defender för Office 365.](preset-security-policies.md)

## <a name="requirements"></a>Krav

### <a name="subscriptions"></a>Prenumerationer

Skyddsfunktioner för hot ingår i *alla* Microsoft- eller Office 365 prenumerationer. Men vissa prenumerationer har avancerade funktioner. I tabellen nedan visas skyddsfunktioner som ingår i den här artikeln tillsammans med minimikraven för prenumeration.

> [!TIP]
> Lägg märke till att stegen,  utöver anvisningarna för att aktivera granskning, startar skydd mot skadlig programvara, nätfiske och skräppost, som markeras som en del av Office 365 Exchange Online Protection **(EOP).** Det här kan verka konstigt i en Defender Office 365 artikel, tills du kommer ihåg att ( Defender för **Office 365**) innehåller, och bygger på, EOP.

<br>

****

|Skyddstyp|Prenumerationskrav|
|---|---|
|Granskningsloggning (för rapporteringssyfte)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Skydd mot skadlig kod|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Skydd mot nätfiske|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Skydd mot skräppost|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Skydd mot skadliga URL:er och filer i e-Office och dokument (Valv och bifogade filer Valv)|[Microsoft Defender för Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Roller och behörigheter

Du måste vara tilldelad Office 365 för att kunna konfigurera Defender för Office 365-principer. I tabellen nedan ser du vilka roller som kan utföra de här åtgärderna.

<br>

****

|Roll eller rollgrupp|Här kan du lära dig mer|
|---|---|
|global administratör|[Om administratörsroller i Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Säkerhetsadministratör|[Administratörens rollbehörigheter i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online Organisationshantering|[Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo)|
|

Mer information finns i [Behörigheter i Microsoft 365 Defender portalen.](permissions-microsoft-365-security-center.md)

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Aktivera granskningsloggning för rapportering och undersökning

- Starta granskningsloggningen tidigt. Du måste granska vara PÅ **för** vissa av följande steg. Granskningsloggning är tillgänglig i prenumerationer som innehåller [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). För att du ska kunna [](view-email-security-reports.md)visa data i rapporter om skydd mot hot, e-postsäkerhetsrapporter [och Utforskaren](threat-explorer.md)måste granskningsloggningen vara *På.* Mer information finns i [Aktivera eller inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Del 1 – Skydd mot skadlig programvara i EOP

Mer information om rekommenderade inställningar för skydd mot skadlig programvara finns i Inställningar för [EOP-policy mot skadlig programvara.](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)

1. Öppna sidan **mot skadlig programvara** i Microsoft 365 Defender på <https://security.microsoft.com/antimalwarev2> .

2. På sidan **mot skadlig programvara** väljer du principen Standard **(standard) genom att** klicka på namnet.

3. Klicka på Redigera skyddsinställningar i den utfäll plats som öppnas med **principinformation** och konfigurera sedan följande inställningar:
   - **Avsnittet Skyddsinställningar:**
     - Välj **Aktivera filtret för vanliga bifogade filer om** du vill aktivera filtret för vanliga bifogade filer. Klicka **på Anpassa filtyper om** du vill lägga till fler filtyper.
     - **Aktivera automatisk rensning utan timme för skadlig programvara:** Kontrollera att den här inställningen är markerad. Mer information om ZAP för skadlig programvara finns i [Zap (Zero-hour auto purge) för skadlig programvara.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware)
   - **Meddelandeavsnitt:** Kontrollera att inga av meddelandeinställningarna är markerade.

   Klicka på **Spara** när du är klar.

4. Tillbaka på utfällda menyn principinformation klickar du **Stäng**.

Detaljerade instruktioner för konfigurering av principer för skadlig programvara finns i [Konfigurera principer för skydd mot skadlig programvara i EOP.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Del 2 – Skydd mot nätfiske i EOP och Defender för Office 365

[Skydd mot nätfiske är](anti-phishing-protection.md) tillgängligt i prenumerationer som innehåller [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Avancerat skydd mot nätfiske finns i [Defender för Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

Mer information om rekommenderade inställningar för principer för skydd mot nätfiske finns i Inställningar för [EOP-princip](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) mot nätfiske och Inställningar för skydd mot nätfiskeprincip i [Microsoft Defender för Office 365.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)

Här beskrivs hur du konfigurerar standardprincipen för skydd mot nätfiske. Inställningar som bara finns i Defender för Office 365 är tydligt markerade.

1. Öppna sidan **Mot nätfiske** i Microsoft 365 Defender i <https://security.microsoft.com/antiphishing> .

2. På sidan **Mot nätfiske** väljer du principen **Office365 AntiPhish Default (standard) genom** att klicka på namnet.

3. Konfigurera följande inställningar i den utfällade menyn med principinformation:
   - **Tröskelvärde för & skydd:** Klicka **på Redigera skyddsinställningar** och konfigurera följande inställningar i den utfällklara menyn som öppnas:
     - **Tröskelvärde för nätfiske:** <sup>\*</sup> Välj **2 – Aggressiv** (standard) eller **3 – Mer aggressiva** (strikt).
     - **Personifieringsavsnitt:** <sup>\*</sup> Konfigurera följande värden:
       - Välj **Aktivera** användare att skydda , klicka på länken Hantera **(nn)** avsändare som visas och lägg sedan till interna och externa avsändare som ska skyddas från personifiering, till exempel företagets styrelsemedlemmar, din VD, CFO och andra högre chefer.
       - Markera **Aktivera domäner att skydda** och konfigurera sedan följande inställningar som visas:
         - Välj **Inkludera domäner som jag äger** för att skydda interna avsändare i dina godkända domäner (visas genom att klicka på Visa mina **domäner**) från personifiering.
         - Om du vill skydda avsändare i andra domäner väljer du Inkludera egna domäner **,** klickar på länken Hantera **(nn)** anpassade domäner som visas och lägger sedan till andra domäner för att skydda mot personifiering.
     - Avsnittet Lägg till **betrodda** avsändare och domäner: Klicka på Hantera <sup>\*</sup> **(nn)** betrodda avsändare och domäner om du vill konfigurera undantag från avsändar- och avsändardomänen till personifieringsskydd om det behövs.
     - Inställningar för <sup>\*</sup> postlådeintelligens: Kontrollera att Aktivera postlådeintelligens och Aktivera intelligens **för personifieringsskydd** är markerade. 
     - **Förfalskningsavsnitt:** **Kontrollera att Aktivera förfalskningsinformation** har markerats.

     Klicka på **Spara** när du är klar.

   - **Avsnittet** Åtgärder: Klicka **på Redigera åtgärder** och konfigurera följande inställningar i den utfällfältet som öppnas:
     - **Avsnittet Meddelandeåtgärder:** Konfigurera följande inställningar:
       - **Om meddelandet identifieras som en imiterad användare:** <sup>\*</sup> Välj Sätt meddelandet i **karantän.**
       - **Om meddelandet identifieras som en imiterad domän:** <sup>\*</sup> Välj Sätt meddelandet i **karantän.**
       - **Om postlådeinformation** upptäcker en imiterad användare: Välj Flytta meddelandet till mottagarnas skräppostmappar (Standard) eller Sätt meddelandet <sup>\*</sup> i **karantän** (Strikt). 
       - **Om meddelandet identifieras som förfalskning** väljer du Flytta meddelandet till mottagarnas skräppostmappar **(Standard)** eller Sätt meddelandet **i** karantän (strikt).
     - **Säkerhetstips & indikatorer:** Konfigurera följande inställningar:
       - **Visa dialogrutan för säkerhetstips**: Välj (aktivera).
       - **Visa användares personifiering säkerhetstips:** <sup>\*</sup> Välj (aktivera).
       - **Visa domänens personifiering säkerhetstips** <sup>\*</sup> : Välj (aktivera).
       - **Visa användarpersonifiering ovanliga tecken säkerhetstips** <sup>\*</sup> : Välj (aktivera).
       - **Visa (?) för oauthenticerade avsändare för förfalskning:** Välj (aktivera).
       - **Visa "via"-taggen:** Välj (aktivera).

     Klicka på **Spara** när du är klar.

   <sup>\*</sup>Den här inställningen är endast tillgänglig i Defender för Office 365.

4. Klicka **på Spara** och sedan på **Stäng**

Detaljerade anvisningar för hur du konfigurerar principer för skydd mot nätfiske finns i Konfigurera principer för skydd mot nätfiske i [EOP](configure-anti-phishing-policies-eop.md) och Konfigurera principer för skydd mot nätfiske i [Microsoft Defender för Office 365.](configure-mdo-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection-in-eop"></a>Del 3 – Skydd mot skräppost i EOP

Mer information om rekommenderade inställningar för skydd mot skräppost finns i Inställningarna för [EOP-policy](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)mot skräppost.

1. Öppna sidan **Principer för skydd mot skräppost** i Microsoft 365 Defender på <https://security.microsoft.com/antispam> .

2. På sidan **Principer för skräppostskydd** markerar du principen **Anti-spam inbound policy (Default)** i listan genom att klicka på namnet.

3. Konfigurera följande inställningar i den utfällade menyn med principinformation:
   - **Tröskelvärde för massutskick & egenskaper för skräppost:** Klicka **på Redigera tröskelvärde för skräppost och egenskaper**. Konfigurera följande inställningar i den utfäll du vill använda:
     - **Tröskelvärde för massutskick:** Ställ in det här värdet på 5 (strikt) eller 6 (standard).
     - Lämna andra inställningar för standardvärdena **(Av** eller **Inget).**

     Klicka på **Spara** när du är klar.

   - **Avsnittet** Åtgärder: Klicka på **Redigera åtgärder.** Konfigurera följande inställningar i den utfäll du vill använda:
     - **Avsnittet Meddelandeåtgärder:**
       - **Skräppost:** Kontrollera **att Flytta meddelandet till mappen Skräppost är** markerat (Standard) eller välj Sätt meddelande i **karantän** (strikt).
       - **Skräppost med hög** konfidens: **Välj sätt meddelande i karantän.**
       - **Nätfiske:** Välj **Sätt meddelande i karantän.**
       - **Nätfiske med hög** konfidens: **Kontrollera att meddelanden i karantän** är markerat.
       - **Mass:** Kontrollera **att Flytta meddelandet till mappen Skräppost är** markerat (Standard) eller välj Sätt meddelande i **karantän** (strikt).
     - **Behåll skräppost i karantän i så här många** dagar: Verifiera värdet **30** dagar.
     - **Aktivera säkerhetstips för skräppost:** Kontrollera att den här inställningen är markerad (aktiverad).
     - **Aktivera ZAP (Zero-hour auto purge):** Kontrollera att den här inställningen är vald (aktiverad).
       - **Aktivera för nätfiskemeddelanden:** Kontrollera att den här inställningen är markerad (aktiverad). Mer information finns i [ZAP (Zero-hour auto purge) för nätfiske.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)
       - **Aktivera för skräppostmeddelanden:** Kontrollera att den här inställningen är markerad (aktiverad). Mer information finns i [ZAP (Zero-hour auto purge) för skräppost.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)
     - **Avsnittet** Meddelanden:
       - Välj **Aktivera skräppost-aviseringar för slutanvändaren.**
         - **Skicka skräppost-aviseringar till slutanvändare var (dagar)**: Verifiera värdet **3** dagar.
         - **Språk:** Verifiera värdet **Standard eller** välj ett språk.

     Klicka på **Spara** när du är klar.

   - **Avsnittet Tillåtna** och blockerade avsändare och domäner: Granska eller redigera tillåtna avsändare och tillåtna domäner enligt beskrivningen i Skapa spärrade avsändarlistor i [EOP](create-block-sender-lists-in-office-365.md) eller Skapa listor över betrodda avsändare [i EOP.](create-safe-sender-lists-in-office-365.md)

     Klicka på **Spara** när du är klar.

4. Klicka på **Stäng** när du är klar.

Detaljerade instruktioner för hur du konfigurerar principer för skydd mot skräppost finns [i Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Del 4 – Skydd mot skadliga URL:er och filer (Valv och bifogade Valv i Defender för Office 365)

Skydd vid klickning från skadliga URL:er och filer är tillgängligt i prenumerationer som inkluderar [Microsoft Defender för Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Den konfigureras via principer [Valv Och](safe-attachments.md) [Valv Länkar.](safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Valv Principer för bifogade filer i Microsoft Defender för Office 365

Mer information om rekommenderade inställningar för bifogade Valv finns i . [Valv för bifogade filer](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

1. Öppna sidan **Valv bifogade** filer i Microsoft 365 Defender portal på <https://security.microsoft.com/safeattachmentv2> .

2. På sidan **Valv bifogade** filer klickar du **på Globala** inställningar och konfigurerar sedan följande inställningar på den utfäll sida som visas:
   - **Aktivera Defender för Office 365 för SharePoint, OneDrive** och Microsoft Teams : Aktivera den här inställningen ![ ](../../media/scc-toggle-on.png) (aktivera).

     > [!IMPORTANT]
     > **Innan du aktiverar Valv för SharePoint, OneDrive** och Microsoft Teams kontrollerar du att granskningsloggning har aktiverats i organisationen. Den här åtgärden utförs vanligtvis av någon som har rollen Granskningsloggar tilldelad i Exchange Online. Mer information finns i Aktivera [eller inaktivera granskningsloggsökning!](../../compliance/turn-audit-log-search-on-or-off.md)

   - **Aktivera Valv dokument för Office**: Aktivera den här inställningen ![ (växlingsknapp ](../../media/scc-toggle-on.png) på). Observera att den här funktionen endast är tillgänglig och meningsfull med Microsoft 365 E5 eller Microsoft 365 E5 Security licenser.
   - **Tillåt att andra klickar i Skyddad vy även om Valv** dokument identifierat filen som skadlig : Kontrollera att den här inställningen är inaktiverad ![ ](../../media/scc-toggle-off.png) (inaktivera).

   När du är klar klickar du på **Spara**

3. På sidan för **Valv klickar** du på Skapa ![ ikon ](../../media/m365-cc-sc-create-icon.png) .

4. I guiden **skapa Valv bifogade** filer som öppnas konfigurerar du följande inställningar:
   - **Namnge principsidan:**
     - **Namn**: Ange något unikt och beskrivande.
     - **Beskrivning**: Ange en valfri beskrivning.
   - **Sidan Användare och** domäner: Eftersom det här är din första princip och du förmodligen vill maximera täckningen kan du ange dina godkända [domäner](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i **rutan** Domäner. Annars kan du använda **rutorna Användare** **och** Grupper för en mer detaljerad kontroll. Du kan ange undantag genom att **välja Exkludera dessa användare, grupper och domäner och** ange värden.
   - **Inställningar** sidan:
     - **Valv som är okänt svar på skadlig programvara:** Välj **Blockera**.
     - **Omdirigera bifogade filer med identifierade bifogade filer** : **Aktivera** omdirigering: Aktivera (markera) den här inställningen och ange en e-postadress för att ta emot identifierade meddelanden.
     - Använd Valv för identifiering av bifogade filer om genomsökning inte kan **slutföras (timeout** eller fel) : Kontrollera att den här inställningen är markerad.

5. När du är klar klickar du på **Skicka** och sedan på **Klar**.

6. (Rekommenderas) Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** med _parametern DisallowInfectedFileDownload_ inställd på `$true` i SharePoint Online PowerShell.
   - `$true` blockerar alla åtgärder (utom Ta bort) för identifierade filer. Användare kan inte öppna, flytta, kopiera eller dela identifierade filer.
   - `$false` blockerar alla åtgärder utom Ta bort och Ladda ned. Användare kan välja att acceptera risken och ladda ned en upptäckt fil.

7. Det kan ta upp till 30 minuter innan ändringarna sprids till alla Microsoft 365 datacenter.

Detaljerade instruktioner för hur du konfigurerar Valv principer för bifogade filer och globala inställningar Valv bifogade filer finns i följande avsnitt:

- [Konfigurera principer Valv för bifogade filer i Microsoft Defender för Office 365](set-up-safe-attachments-policies.md)
- [Aktivera säkra bilagor för SharePoint, OneDrive och Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)
- [Säkra dokument i Microsoft 365 E5](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Valv Länkprinciper i Microsoft Defender för Office 365

Mer information om rekommenderade inställningar för Valv finns i Valv [Inställningar för länkar.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

1. Öppna sidan **Valv Länkar** i Microsoft 365 Defender på <https://security.microsoft.com/safelinksv2> .

2. På sidan **Valv länkar** klickar du **på Globala** inställningar och konfigurerar sedan följande inställningar på den utfäll sida som visas:
   - **Inställningar som gäller för innehåll i avsnittet Office 365 program** som stöds:
     - **Använd Valv länkar i Office 365:** Kontrollera att den här inställningen är aktiverad ![ ](../../media/scc-toggle-on.png) (aktivera).
     - **Spåra inte när användare klickar på skyddade länkar i Office 365**: Inaktivera den här inställningen ![ ](../../media/scc-toggle-off.png) (inaktivera)
     - **Låt inte användare klicka till den ursprungliga URL:en i Office 365-appar:** Kontrollera att den här inställningen är aktiverad ![ (växlingsknapp ](../../media/scc-toggle-on.png) på).

   När du är klar klickar du på **Spara**

3. På sidan **Valv klickar** du på Skapa ikon ![ ](../../media/m365-cc-sc-create-icon.png) .

4. I **principguiden Valv Länkar** som öppnas konfigurerar du följande inställningar:
   - **Namnge principsidan:**
     - **Namn**: Ange något unikt och beskrivande.
     - **Beskrivning**: Ange en valfri beskrivning.
   - **Sidan Användare och** domäner: Eftersom det här är din första princip och du förmodligen vill maximera täckningen kan du ange dina godkända [domäner](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i **rutan** Domäner. Annars kan du använda **rutorna Användare** **och** Grupper för en mer detaljerad kontroll. Du kan ange undantag genom att **välja Exkludera dessa användare, grupper och domäner och** ange värden.
   - **Inställningssidan för** skydd:
     - **Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden:** Aktivera den här **inställningen**.
     - **Välj åtgärden för okända eller potentiellt skadliga URL-adresser i Microsoft Teams**: Aktivera den **här inställningen.** Från och med mars 2020 är den här inställningen förhandsversion och kan bara användas av medlemmar i Microsoft Teams Technology Adoption Program (TAP).
     - **Använd URL-skanning i realtid för misstänkta länkar och länkar som pekar på filer**: Välj den här inställningen (aktivera).
       - **Vänta tills URL-skanningen är klar innan du levererar meddelandet:** Välj den här inställningen (aktivera).
     - **Använd Valv länkar till e-postmeddelanden som skickas inom organisationen:** Välj den här inställningen (aktivera).
     - **Spåra inte användarklick: Kontrollera** att den här inställningen inte är markerad (inaktiverad).
     - **Låt inte användarna klicka sig fram till den ursprungliga URL:en:** Kontrollera att den här inställningen är aktiverad (markerad).
     - **Visa företagets** varumärke på aviserings- och varningssidor: Det är meningsfullt att välja den här inställningen (aktivera den) när du har följt instruktionerna i [Anpassa Microsoft 365](../../admin/setup/customize-your-organization-theme.md) för din organisation för att ladda upp företagets logotyp.
     - **Omskrivning inte av följande URL:er: Vi** har ingen särskild rekommendation för den här inställningen. Mer information finns i ["Skriva inte om följande URL-listor" i avsnittet Valv Principer för länkar.](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)
   - **Meddelandesida:**
     - **Hur vill du meddela användarna?** avsnitt: Alternativt kan du välja Använd anpassad **meddelandetext för** att ange anpassad meddelandetext som ska användas. Du kan också välja **Använd Microsoft Translator för automatisk lokalisering** för att översätta den anpassade aviseringstexten till användarens språk. Annars lämnar du **Använd standardmeddelandetexten** markerad.

5. När du är klar klickar du på **Skicka** och sedan på **Klar**.

Detaljerade instruktioner för hur du konfigurerar Valv principer för länkar och globala inställningar Valv länkar finns i följande avsnitt:

- [Konfigurera principer Valv Länkar i Microsoft Defender för Office 365](set-up-safe-links-policies.md)
- [Konfigurera globala inställningar för Valv Länkar i Microsoft Defender för Office 365](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>Konfigurera nu aviseringar för identifierade filer i SharePoint Online eller OneDrive för företag

Om du vill få ett meddelande när en fil i SharePoint Online eller OneDrive för företag har identifierats som skadlig kan du konfigurera en avisering enligt beskrivningen i det här avsnittet.

1. I den Microsoft 365 Defender på <https://security.microsoft.com> går du till E-post **och &-&** \> **princip för** \> **avisering.**

2. Klicka på **Ny aviseringsprincip** **på sidan Aviseringsprincip.**

3. Guiden **Ny aviseringsprincip** öppnas. Konfigurera **följande** inställningar på sidan Namn:
   - **Namn**: Ange ett unikt och beskrivande namn. Du kan till exempel skriva Skadliga filer i bibliotek.
   - **Beskrivning**: Ange en valfri beskrivning.
   - **Allvarlighetsgrad**: Välj **Låg,** **Medel** eller **Hög.**
   - **Kategori:** Välj **Hantering av hot.**

   Klicka på Nästa när du är **klar**

4. Konfigurera **följande inställningar på** sidan Skapa aviseringsinställningar:
   - **Vad vill du avisering om?** avsnitt: **Aktivitet har** \> **upptäckts av skadlig programvara i filen**.
   - **Hur vill du att aviseringen ska utlösas:** Verifiera **varje gång en aktivitet matchar regeln** markeras.

   Klicka på Nästa när du är **klar**

5. På sidan **Ange mottagare** konfigurerar du följande inställningar:
   - **Skicka** e-postaviseringar: Kontrollera att den här inställningen är gäller.
   - **E-postmottagare:** Välj en eller flera globala administratörer, säkerhetsadministratörer eller säkerhetsläsare som ska få ett meddelande när en skadlig fil identifieras.
   - **Daglig meddelandegräns:** Kontrollera **att ingen gräns** har valts.

   Klicka på Nästa när du är **klar**

6. Granska **inställningarna på sidan** Granska dina inställningar, kontrollera **Ja, aktivera det direkt** är markerat och klicka sedan på **Slutför**

Mer information om aviseringsprinciper finns [i Aviseringsprinciper i Microsoft 365 Efterlevnadscenter](../../compliance/alert-policies.md).

> [!NOTE]
> När du är klar med konfigureringen använder du de här länkarna för att starta undersökningar om arbetsbelastningen:
>
>- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
>- [Använd Microsoft 365 Defender för att hantera filer i karantän i Defender för Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [Vad kan jag göra när en skadlig fil hittas i SharePoint Online, OneDrive och Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>Uppgifter efter installationen och nästa steg

När du har konfigurerat funktionerna för skydd mot hot ska du övervaka hur de här funktionerna fungerar! Granska och ändra dina principer så att de gör det de behöver för dem. Titta också efter nya funktioner och tjänstuppdateringar som kan tillför något.

<br>

****

|Lämplig åtgärd|Resurser för att få mer information|
|---|---|
|Se hur skyddsfunktioner för hot fungerar för organisationen genom att visa rapporter|[Säkerhetsrapporter för e-post](view-email-security-reports.md) <p> [Rapporter för Microsoft Defender för Office 365](view-reports-for-mdo.md) <p> [Hotutforskaren](threat-explorer.md)|
|Regelbundet granska och ändra dina principer för skydd mot hot efter behov|[Secure Score](../defender/microsoft-secure-score.md) <p> [Microsoft 365 undersökning av hot och svarsfunktioner](./office-365-ti.md)|
|Håll utkik efter nya funktioner och tjänstuppdateringar|[Alternativ för standard- och riktad version](../../admin/manage/release-options-in-office-365.md) <p> [Meddelandecentral](../../admin/manage/message-center.md) <p> [Översikt över Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Tjänstbeskrivningar](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
