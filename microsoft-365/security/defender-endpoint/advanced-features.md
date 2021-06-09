---
title: Konfigurera avancerade funktioner i Microsoft Defender för Slutpunkt
description: Aktivera avancerade funktioner, till exempel blockeringsfil i Microsoft Defender för Endpoint.
keywords: avancerade funktioner, inställningar, blockering av fil, automatisk undersökning, automatisk lösning, skype, microsoft defender för identitet, office 365, azure informationsskydd, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7fd9ec25c21b2d70238bd5b0d6b58b60731088ea
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845480"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Konfigurera avancerade funktioner i Defender för Slutpunkt

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

Beroende på vilka Microsoft-säkerhetsprodukter du använder kan vissa avancerade funktioner vara tillgängliga för dig att integrera Defender för Slutpunkt med.

## <a name="enable-advanced-features"></a>Aktivera avancerade funktioner

1. I navigeringsfönstret väljer du **Inställningar inställningar Avancerade**  >  **funktioner**.
2. Välj den avancerade funktion du vill konfigurera och växla inställningen **mellan** På och **Av.**
3. Klicka **på Spara inställningar.**

Använd följande avancerade funktioner för att få bättre skydd från potentiellt skadliga filer och få bättre insyn under säkerhetsundersökningen.

## <a name="automated-investigation"></a>Automatiserad undersökning

Aktivera den här funktionen för att dra nytta av tjänstens funktioner för automatisk undersökning och åtgärder. Mer information finns i [Automatiserad undersökning](automated-investigations.md).

## <a name="live-response"></a>Livesvar

Aktivera den här funktionen så att användare med rätt behörighet kan starta en direkt svarssession på enheter.

Mer information om rolltilldelningar finns i [Skapa och hantera roller.](user-roles.md)

## <a name="live-response-for-servers"></a>Live-svar för servrar
Aktivera den här funktionen så att användare med rätt behörighet kan starta en live-svarssession på servrar.

Mer information om rolltilldelningar finns i [Skapa och hantera roller.](user-roles.md)


## <a name="live-response-unsigned-script-execution"></a>Körning av skript som inte har signerats med Live Response

Om du aktiverar den här funktionen kan du köra osignerade skript i en svarssession i direktsändning.

## <a name="always-remediate-pua"></a>Åtgärda alltid PUA
Potentiellt oönskade program (PUA) är en kategori av programvara som kan få datorn att köras långsamt, visa oväntade annonser eller i värsta fall installera annan programvara som kan vara oväntad eller oönskad. 

Aktivera den här funktionen så att potentiellt oönskade program (PUA) åtgärdas på alla enheter i klientorganisationen även om PUA-skyddet inte har konfigurerats på enheterna. Det här hjälper till att skydda användare från att oavsiktligt installera oönskade program på enheten. När den är inaktiverad beror åtgärder på enhetens konfiguration. 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a>Begränsa korrelationen till inom begränsade enhetsgrupper
Den här konfigurationen kan användas för scenarier där lokala SOC-åtgärder vill begränsa korrelationer endast till enhetsgrupper som de kan komma åt. Genom att aktivera den här inställningen kommer en incident som består av aviseringar som inte längre kan ses som en enda incident i en grupp av enheter. Den lokala soc-datagruppen kan sedan vidta åtgärder för incidenten eftersom de har åtkomst till en av de berörda enhetsgrupper. Globala SOC ser emellertid flera olika incidenter efter enhetsgrupp istället för ett incident. Vi rekommenderar inte att du slår på den här inställningen om det inte gäller fördelarna med incidentrelationer i hela organisationen
>[!NOTE]
>Om du ändrar den här inställningen påverkas bara framtida korrelationer.

## <a name="enable-edr-in-block-mode"></a>Aktivera Identifiering och åtgärd på slutpunkt i blockeringsläge
Identifiering och svar av slutpunkt (Identifiering och åtgärd på slutpunkt) i blockeringsläge ger skydd mot skadliga artefakter, även när Microsoft Defender Antivirus körs i passivt läge. När den är Identifiering och åtgärd på slutpunkt blockeras skadliga artefakter eller beteenden som upptäcks på en enhet. Identifiering och åtgärd på slutpunkt i blockeringsläge fungerar bakom kulisserna för att åtgärda skadliga artefakter som upptäcks efter intrånget.


## <a name="autoresolve-remediated-alerts"></a>Åtgärdat autoresole-aviseringar

För klientprogram som skapats på eller efter Windows 10, version 1809, konfigureras automatisk undersökning och åtgärd som standard för att lösa varningar där status för automatisk analys är "Inga hot hittades" eller "Åtgärdat".  Om du inte vill att aviseringarna ska matchas automatiskt måste du inaktivera funktionen manuellt.

> [!TIP]
> För klientorganisationen som skapats tidigare än den versionen måste du manuellt aktivera den här funktionen på sidan [Avancerade](https://securitycenter.windows.com/preferences2/integration) funktioner.

> [!NOTE]
>
> - Resultatet av åtgärden för automatisk lösning kan påverka beräkningen av enhetrisknivå som baseras på de aktiva aviseringarna som finns på en enhet.
> - Om en analytiker för säkerhetsåtgärder manuellt anger statusen för en avisering till "Pågår" eller "Löst" skriver funktionen för automatisk resolve inte över den.

## <a name="allow-or-block-file"></a>Tillåta eller blockera fil

Blockering är bara tillgängligt om din organisation uppfyller följande krav:

- Använder Microsoft Defender Antivirus som den aktiva antimalwarelösningen och
- Den molnbaserade skyddsfunktionen är aktiverad

Med den här funktionen kan du blockera potentiellt skadliga filer i nätverket. När du blockerar en fil förhindrar du att den läses, skrivs eller körs på enheter i organisationen.

Aktivera Tillåt **eller blockera** filer:

1. Välj Tillåt eller blockera **fil Inställningar** avancerade funktioner i  >    >  **navigeringsfönstret.**

1. Ändra inställningen mellan **På och** **Av.**

    ![Bild av avancerade inställningar för filblockeringsfunktionen](images/atp-preferences-setup.png)

1. Välj **Spara inställningar** längst ned på sidan.

När du har aktiverat den här funktionen kan [du blockera](respond-file-alerts.md#allow-or-block-file) filer via **fliken** Lägg till indikator på en fils profilsida.

## <a name="custom-network-indicators"></a>Anpassade nätverksindikatorer

Om du slår på den här funktionen kan du skapa indikatorer för IP-adresser, domäner och URL-adresser, som avgör om de tillåts eller blockeras baserat på en anpassad indikatorlista.

Om du vill använda den här funktionen måste enheterna köra Windows 10 version 1709 eller senare. De bör också ha nätverksskydd i blockläge och version 4.18.1906.3 eller senare av program mot skadlig programvara, se [KB 4052623.](https://go.microsoft.com/fwlink/?linkid=2099834)

Mer information finns i [Hantera indikatorer](manage-indicators.md).

> [!NOTE]
> Nätverksskydd utnyttjar ryktestjänster som bearbetar förfrågningar på platser som kan vara utanför den plats du har valt för Defender för Slutpunktsdata.

## <a name="tamper-protection"></a>Skydd mot manipulering
Under vissa typer av cyberattacker försöker dåliga aktör att inaktivera säkerhetsfunktioner, till exempel antivirusskydd, på dina datorer. Dåliga aktör vill inaktivera dina säkerhetsfunktioner för att få enklare åtkomst till dina data, installera skadlig programvara eller på annat sätt utnyttja dina data, din identitet och dina enheter.

Skydd mot manipulering låser Microsoft Defender Antivirus och förhindrar att säkerhetsinställningarna ändras genom appar och metoder.

Den här funktionen är tillgänglig om din organisation Microsoft Defender Antivirus skydd och Molnbaserat skydd är aktiverat. Mer information finns i [Använda nästa generations teknik i Microsoft Defender Antivirus skydd mot molnlösningar.](cloud-protection-microsoft-defender-antivirus.md)

Behåll skydd mot manipulering aktiverat för att förhindra oönskade ändringar i din säkerhetslösning och dess viktiga funktioner.


## <a name="show-user-details"></a>Visa användarinformation

Aktivera den här funktionen så att du kan se användarinformation som lagras i Azure Active Directory. Informationen omfattar en användares bild, namn, titel och avdelningsinformation när du undersöker enheter med användarkonton. Användarkontoinformationen finns i följande vyer:

- Instrumentpanel för säkerhetsåtgärder
- Aviseringskö
- Sidan Enhetsinformation

Mer information finns i [Undersöka ett användarkonto.](investigate-user.md)


## <a name="skype-for-business-integration"></a>Skype för företag integration

Genom att Skype för företag kan du kommunicera med användare via e-Skype för företag, e-post eller telefon. Det kan vara praktiskt när du behöver kommunicera med användaren och minimera risker.

> [!NOTE]
> När en enhet isoleras från nätverket visas ett popup-fönster där du kan välja att aktivera Outlook- och Skype-kommunikationer som tillåter kommunikation till användaren medan de kopplas bort från nätverket. Den här inställningen gäller Skype och Outlook kommunikation när enheter är i avgränsningsläge.

## <a name="microsoft-defender-for-identity-integration"></a>Microsoft Defender för identitetsintegrering

Integreringen med Microsoft Defender för identitet gör att du kan pivotera direkt till en annan Microsoft Identity-säkerhetsprodukt. Microsoft Defender för identitet utökar en undersökning med ytterligare insikter om ett misstänkt komprometterat konto och relaterade resurser. Genom att aktivera den här funktionen kan du utöka den enhetsbaserade undersökningsfunktionen genom att pivotera över nätverket från en synpunkt.

> [!NOTE]
> Du måste ha rätt licens för att aktivera den här funktionen.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 Anslutning till Threat Intelligence

Den här funktionen är endast tillgänglig om du har en Office 365 E5 eller tillägget Threat Intelligence. Mer information finns på sidan Office 365 Enterprise E5.

När du aktiverar den här funktionen kan du införliva data från Microsoft Defender för Office 365 i Microsoft Defender Säkerhetscenter för att genomföra en omfattande säkerhetsundersökning över alla Office 365 postlådor och Windows enheter.

> [!NOTE]
> Du måste ha rätt licens för att aktivera den här funktionen.

Om du vill få sammanhangsbaserad enhetsintegration i Office 365 Threat Intelligence måste du aktivera Defender för Slutpunktsinställningar i instrumentpanelen för & säkerhet och efterlevnad. Mer information finns i Undersökning [av hot och svar.](/microsoft-365/security/office-365-security/office-365-ti)

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Microsoft Hotexperter – riktade attackmeddelanden

Av de två Microsoft Threat Expert-komponenterna är riktade attackmeddelanden i allmän tillgänglighet. Experter på begäran är fortfarande i förhandsversion. Du kan bara använda funktionen för experter på begäran om du har tillämpat en förhandsgranskning och programmet har godkänts. Du kan få riktade attackmeddelanden från Microsoft Hotexperter Via Defender för Endpoint-portalens aviseringar-instrumentpanel och via e-post om du konfigurerar den.

> [!NOTE]
> Funktionen Microsoft Hotexperter Defender för Slutpunkt är tillgänglig med en E5-licens för [Enterprise Mobility + Security.](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Om du aktiverar den här inställningen vidarebefordras Defender för Slutpunktssignaler Microsoft Cloud App Security bättre insyn i användningen av molnprogram. Vidarebefordrade data lagras och bearbetas på samma plats som dina Cloud App Security data.

> [!NOTE]
> Den här funktionen är tillgänglig med en E5-licens för [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) på enheter med Windows 10, version 1709 (OS-version 16299.1085 med [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, version 1803 (OS Version 17134.704 med [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 med [KB4489899](https://support.microsoft.com/help/4489899)) eller senare Windows 10 versioner.

## <a name="microsoft-secure-score"></a>Microsoft Secure Score

Vidarebefordrar Microsoft Defender för Endpoint-signaler till Microsoft Secure Score Microsoft 365 säkerhetscenter. Om du slår på den här funktionen kan Microsoft Secure Score hålla ordning på enhetens säkerhetssystem. Vidarebefordrade data lagras och bearbetas på samma plats som dina Microsoft Secure Score-data.


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Aktivera Microsoft Defender för slutpunktsintegrering från Microsoft Defender för identitetsportalen

Om du vill få en sammanhangsberoende enhetsintegration i Microsoft Defender för identitet måste du också aktivera funktionen i Microsoft Defender för identitetsportalen.

1. Logga in på [Microsoft Defender för identitetsportalen med](https://portal.atp.azure.com/) en global administratör eller säkerhetsadministratörsroll.

2. Klicka **på Skapa din instans**.

3. Ändra inställningen Integration till På **och** klicka på **Spara**.

När du har slutfört integrationsstegen på båda portalerna kan du se relevanta aviseringar på sidan med enhetsinformation eller användarinformation.

## <a name="web-content-filtering"></a>Filtrering av webbinnehåll
Blockera åtkomst till webbplatser som innehåller oönskat innehåll och spåra webbaktivitet i alla domäner. Skapa en princip för webbinnehållsfiltrering om du vill ange vilka [kategorier av webbinnehåll](https://security.microsoft.com/preferences2/web_content_filtering_policy)som du vill blockera. Se till att du har nätverksskydd i blockeringsläge när du distribuerar [Microsoft Defender för slutpunktens säkerhetsbaslinje.](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Dela slutpunktsaviseringar med Microsofts efterlevnadscenter
Vidarebefordrar säkerhetsvarningar för slutpunkter och deras status till Microsofts efterlevnadscenter, så att du kan förbättra principer för insiderriskhantering med varningar och åtgärda interna risker innan de kan orsaka skada. Vidarebefordrade data bearbetas och lagras på samma plats som dina Office 365 data.

När du har [konfigurerat indikatorerna för brott](/microsoft-365/compliance/insider-risk-management-settings#indicators) mot säkerhetsprinciper i inställningarna för Insider-riskhantering delas Defender för Slutpunktsaviseringar med Insider-riskhantering för tillämpliga användare.



## <a name="microsoft-intune-connection"></a>Microsoft Intune anslutning

Defender för Endpoint kan integreras med Microsoft Intune för [att](/intune/what-is-intune) [aktivera enhetsriskbaserad villkorlig åtkomst.](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune) När du [aktiverar den här funktionen](configure-conditional-access.md)kan du dela Information om Endpoint-enheter med Intune och förbättra tvingande policy.

> [!IMPORTANT]
> Du måste aktivera integreringen på både Intune och Defender för Endpoint om du vill använda den här funktionen. Mer information om specifika steg finns i Konfigurera [villkorsstyrd åtkomst i Defender för slutpunkt.](configure-conditional-access.md)

Den här funktionen är endast tillgänglig om du har följande:

- En licensierad klientorganisation för Enterprise Mobility + Security E3 och Windows E5 (eller Microsoft 365 Enterprise E5)
- En aktiv Microsoft Intune med Intune-hanterade enheter Windows 10 [Azure AD-anslutna](/azure/active-directory/devices/concept-azure-ad-join/).


### <a name="conditional-access-policy"></a>Princip för villkorsstyrd åtkomst

När du aktiverar Intune-integrering skapar Intune automatiskt en klassisk CA-princip (Conditional Access). Den här klassiska CA-principen är en förutsättning för att kunna konfigurera statusrapporter till Intune. Den ska inte tas bort.

> [!NOTE]
> Den klassiska CA-principen som skapas av Intune skiljer sig från moderna [villkorsstyrda](/azure/active-directory/conditional-access/overview/)åtkomstprinciper, som används för att konfigurera slutpunkter.


## <a name="device-discovery"></a>Enhetsidentifiering
Hjälper dig att hitta ohanterade enheter anslutna till företagsnätverket utan att behöva extra utrustning eller krångliga processändringar. Med onboarded-enheter kan du hitta ohanterade enheter i nätverket och bedöma svagheter och risker. Mer information finns i [Enhetsidentifiering](device-discovery.md).

> [!NOTE]
> Du kan alltid använda filter för att utesluta ohanterade enheter från enhetsinventeringslistan. Du kan också använda kolumnen onboardingstatus i API-frågor för att filtrera bort ohanterade enheter. 

## <a name="preview-features"></a>Förhandsgranskningsfunktioner

Läs mer om nya funktioner i förhandsversionen av Defender för slutpunkt. Prova kommande funktioner genom att aktivera förhandsgranskningen.

Du har tillgång till kommande funktioner som du kan ge feedback på för att förbättra den övergripande upplevelsen innan funktionerna blir tillgängliga i allmänhet.




## <a name="related-topics"></a>Relaterade ämnen

- [Uppdatera inställningar för datalagring](data-retention-settings.md)
- [Konfigurera varningsaviseringar](configure-email-notifications.md)
