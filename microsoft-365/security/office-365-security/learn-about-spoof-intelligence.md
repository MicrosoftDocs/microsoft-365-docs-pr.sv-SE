---
title: Insikt för förfalskningsinformation
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan få mer information om förfalskningsinformation i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 94dc1e438f913c1103154afb8803ef4cf89f64af
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028817"
---
# <a name="spoof-intelligence-insight-in-eop"></a>Falska intelligensinsikter i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Funktionerna som beskrivs i den här artikeln är förhandsversioner, kan komma att ändras och är inte tillgängliga i alla organisationer. Om organisationen inte har de funktioner som beskrivs i den här artikeln kan du läsa den äldre hanteringsupplevelsen för förfalskning på Hantera [förfalskningsavsändare](walkthrough-spoof-intelligence-insight.md)med hjälp av förfalsknings- och förfalskningsinformation i EOP.

I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor skyddas inkommande e-postmeddelanden automatiskt mot förfalskning. EOP använder **förfalskningsinformation som** en del av organisationens totala skydd mot nätfiske. Mer information finns i [Skydd mot förfalskning i EOP.](anti-spoofing-protection.md)

När en avsändare kapar en e-postadress verkar det vara en användare i en av organisationens domäner eller en användare i en extern domän som skickar e-post till organisationen. Attacker som förfalskning av avsändare för att skicka skräppost eller nätfiske måste blockeras. Men det finns situationer där legitima avsändare är förfalskning. Till exempel:

- Legitima scenarier för förfalskning av interna domäner:
  - Avsändare från tredje part använder din domän för att skicka massutskick till dina egna anställda för företags omröstningar.
  - Ett externt företag genererar och skickar reklam- eller produktuppdateringar åt dig.
  - En assistent behöver regelbundet skicka e-post till en annan person i din organisation.
  - Ett internt program skickar e-postaviseringar.

- Legitima scenarier för förfalskning av externa domäner:
  - Avsändaren finns på en distributionslista (kallas även diskussionslista) och distributionslistan vidarebefordrar e-post från den ursprungliga avsändaren till alla deltagare på distributionslistan.
  - Ett externt företag skickar e-post åt ett annat företag (till exempel en automatiserad rapport eller ett företag som använder en programvara).


Du kan använda **förfalskningsinformation** i Microsoft 365 Defender-portalen för att snabbt identifiera förfalskningsavsändare som på ett legitimt sätt skickar oauthenticerad e-post (meddelanden från domäner som inte klarar SPF-, DKIM- eller DMARC-kontroller) och manuellt tillåta dessa avsändare.


Genom att tillåta kända avsändare att skicka falska meddelanden från kända platser kan du minska falska positiva resultat (bra e-postmeddelande markerat som dåligt). Genom att övervaka tillåtna förfalskningsavsändare tillhandahåller du ytterligare en säkerhetsnivå för att förhindra att osäkra meddelanden kommer till organisationen.

På samma sätt kan du granska falska avsändare som tillåts av förfalskningsinformation och manuellt blockera dessa avsändare från förfalskningsinformation.

Resten av den här artikeln förklarar hur du använder förfalskningsinformation i Microsoft 365 Defender-portalen och i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).


> [!NOTE]
>
> - Endast falska avsändare som identifierats av förfalskningsinformation visas i förfalskningsinformation. När du åsidosätter blockeringen av tillåtande eller blockering i insikten blir den förfalskningsberättigade avsändaren en manuell tillåta-eller blockeringspost som bara visas på fliken Förfalskning i klientorganisationens lista över tillåtna/blockerade avsändare.  Du kan även manuellt skapa tillåta eller blockera poster för förfalskningsavsändare innan de identifieras av förfalskningsinformation. För mer information se [Hantera Tillåten av klient/blockeringslista i EOP](tenant-allow-block-list.md).
>
> - Förfalskningsinsikter och **förfalskningsfliken** i listan Tillåt/blockera för klientorganisationen ersätter funktionerna i förfalskningsinformationsprincipen som fanns tillgänglig på sidan policy för skydd mot skräppost i Säkerhets- och & efterlevnadscenter.
>
>- Förfalskningsinsikten visar data för 7 dagar. Cmdleten **Get-SpoofIntelligenceInsight** visar data för 30 dagar.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com/>. Om du vill gå direkt **till sidan Mot nätfiske** använder du <https://security.microsoft.com/antiphishing> . För att gå direkt till **sidan Spoof intelligence insight** använder du <https://security.microsoft.com/spoofintelligence> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill ändra förfalskningsprincipen eller aktivera eller inaktivera förfalskningsinformation måste  du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till förfalskningsinformationsprincipen måste du vara medlem i **rollgrupperna Global Reader** **eller Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Anteckningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Du aktiverar och inaktiverar förfalskningsinformation i principer för nätfiske i EOP och Microsoft Defender för Office 365. Förfalskningsinformation är aktiverat som standard. Mer information finns i Konfigurera principer för skydd [mot nätfiske i EOP](configure-anti-phishing-policies-eop.md) eller Konfigurera principer för skydd mot nätfiske [i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)

- Vi rekommenderar inställningar för förfalskningsinformation i inställningarna för [EOP-policy mot nätfiske.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-phishing-policy-settings)

## <a name="open-the-spoof-intelligence-insight-in-the-microsoft-365-defender-portal"></a>Öppna förfalskningsinformationsinsikten i Microsoft 365 Defender portalen

1. I Microsoft 365 Defender går du till avsnittet Principer **för &-&** e-& principer för hot mot \>  \>  \>  \> **nätfiske.**

2. På sidan **Mot nätfiske** ser förfalskningsinformation ut så här:

   ![Spoof intelligence-information på sidan Policy mot nätfiske](../../media/m365-sc-spoof-intelligence-insight.png)

   Insikten har två lägen:

   - **Insiktsläge:** Om förfalskningsinformation har aktiverats visar insikten hur många meddelanden som har upptäckts av förfalskningsinformation under de senaste sju dagarna.
   - **Vad händer** om-läge: Om förfalskningsinformation är inaktiverad  visar insikten hur många meddelanden som skulle ha upptäckts av förfalskningsinformation under de senaste sju dagarna.

Om du vill visa information om förfalskningsinformation klickar du på Visa **förfalskningsaktivitet** i förfalskningsinformation.

### <a name="view-information-about-spoofed-messages"></a>Visa information om falska meddelanden

> [!NOTE]
> Kom ihåg att endast falska avsändare som identifierats av förfalskningsinformation visas på den här sidan. När du åsidosätter blockeringen av tillåtande eller blockering i insikten blir den förfalskningsberättigade avsändaren en manuell tillåta-eller blockeringspost som bara visas på fliken Förfalskning i klientorganisationens lista över tillåtna/blockerade avsändare. 

På sidan **Förfalskningsinformation** som visas när  du klickar på Visa förfalskningsaktivitet i förfalskningsinformation innehåller sidan följande information:

- **Spoofed användare**: Domänen **för** den falska användaren som visas i rutan Från i e-postklienter.  Från-adressen kallas även `5322.From` för adressen.
- **Skicka infrastruktur:** kallas även _för infrastrukturen._ Den avsändande infrastrukturen kommer att vara ett av följande värden:
  - Domänen finns i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress.
  - Om käll-IP-adressen inte har någon PTR-post identifieras den avsändande infrastrukturen som \<source IP\> /24 (till exempel 192.168.100.100/24).
- **Antal meddelanden:** Antalet meddelanden från kombinationen av förfalskningsdomänen och den avsändande infrastrukturen till organisationen under de senaste 7 dagarna. 
- **Senast** sedd: Det sista datumet när ett meddelande togs emot från den avsändande infrastrukturen som innehåller den falska domänen.
- **Förfalskningstyp:** Ett av följande värden:
  - **Internt**: Förfalskningsavsändare finns i en domän som tillhör din organisation (en [godkänd domän).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
  - **Extern:** Den falska avsändaren finns i en extern domän.
- **Åtgärd:** Det här värdet **är tillåtet** **eller blockerat:**
  - **Tillåtet:** Domänen misslyckades med explicit e-postautentisering kontrollerar [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC](use-dmarc-to-validate-email.md)). Domänen klarade emellertid vår implicita e-postautentisering[(sammansatt autentisering).](email-validation-and-authentication.md#composite-authentication) Därför vidtogs ingen förfalskning i meddelandet.
  - **Blockerad:** Meddelanden från kombination av förfalskningsdomän och avsändarinfrastruktur markeras som dåliga av förfalskningsinformation.  Den åtgärd som vidtas på falska meddelanden styrs av standardprincipen för skydd mot nätfiske eller anpassade principer för nätfiske (standardvärdet är Flytta meddelandet till mappen **Skräppost).** Mer information finns i Konfigurera [principer för skydd mot nätfiske i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)

Du kan klicka på markerade kolumnrubriker för att sortera resultatet.

Du har följande alternativ för att filtrera resultaten:

- Klicka på **knappen** Filter. I  den utfällfällade filterfällan som visas kan du filtrera resultaten genom att:
  - **Förfalskningstyp**
  - **Åtgärd**
- Använd **sökrutan** för att ange en kommaavgränsad lista med falska domänvärden eller genom att skicka infrastrukturvärden för att filtrera resultaten.

### <a name="view-details-about-spoofed-messages"></a>Visa information om falska meddelanden

När du väljer en post i listan visas en utfäll kant med följande information och funktioner:

-  Tillåt förfalskning eller blockering av förfalskning: Välj ett av dessa värden för att åsidosätta den ursprungliga förfalskningsanalysen och flytta posten från förfalskningsinformation till klientorganisationens lista över tillåtna/blockerade listor som ett tillåtet eller blockerat förfalskningspost.
- Därför att vi inte kunde göra detta.
- Det här behöver du göra.
- En domänsammanfattning som innehåller de flesta av samma information från huvudsidan för förfalskningsinformation.
- WhoIs data about the sender.
- En länk till att [öppna Hotutforskaren](threat-explorer.md) för att visa ytterligare information om avsändaren (Microsoft Defender för Office 365).
- Liknande meddelanden som vi har sett i klientorganisationen från samma avsändare.

### <a name="about-allowed-spoofed-senders"></a>Om tillåtna förfalskningsavsändare

En tillåten förfalskningsavsändare i förfalskningsinsikter eller en blockerad förfalskningsavsändare som du manuellt har ändrat till  Tillåt förfalskning tillåter endast meddelanden från kombinationen av förfalskningsdomänen och avsändarinfrastrukturen.  E-post från den falska domänen från någon källa tillåts inte heller e-post från avsändarinfrastrukturen för någon domän.

Följande falska avsändare får till exempel kapa:

- **Domän:** gmail.com
- **Infrastruktur:** tms.mx.com

Endast e-post från den domänen/det avsändande infrastrukturparet kommer att tillåtas förfalskning. Andra avsändare som försöker kapa gmail.com-post tillåts inte automatiskt. Meddelanden från avsändare i andra domäner som kommer tms.mx.com kontrolleras fortfarande av förfalskningsinformation och kan blockeras.

## <a name="use-the-spoof-intelligence-insight-in-exchange-online-powershell-or-standalone-eop-powershell"></a>Använda förfalskningsinformation i PowerShell Exchange Online eller fristående EOP PowerShell

I PowerShell använder du cmdleten **Get-SpoofIntelligenceInsight** till att visa tillåtna och blockerade förfalskningsavsändare som identifierats av förfalskningsinformation.  Om du vill tillåta eller blockera förfalskningsavsändarna manuellt måste du använda cmdleten **New-TenantAllowBlockListSpoofItems.** Mer information finns i Använda [PowerShell för att konfigurera listan över tillåtna/blockerade klientorganisationen.](tenant-allow-block-list.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list)

Om du vill visa informationen i förfalskningsinformation kör du följande kommando:

```powershell
Get-SpoofIntelligenceInsight
```

Detaljerad information om syntax och parametrar finns i [Get-SpoofIntelligenceInsight.](/powershell/module/exchange/get-spoofintelligenceinsight)

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Andra sätt att hantera förfalskning och nätfiske

Var flitig om förfalskning och nätfiskeskydd. Här är relaterade sätt att kontrollera avsändare som förfalskning av din domän och se till att de inte kan skada organisationen:

- Kontrollera **förfalskningsrapporten**. Du kan använda den här rapporten ofta för att visa och hjälpa till att hantera förfalskningsavsändare. Mer information finns [i rapporten Identifiering av förfalskning.](view-email-security-reports.md#spoof-detections-report)

- Granska SPF-konfigurationen (Sender Policy Framework). En introduktion till SPF finns i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt. För att få en djupare förståelse av hur Office 365 använder SPF, eller om du vill veta hur du felsöker eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing (Så här använder Office 365 SPF för att förhindra förfalskning)](how-office-365-uses-spf-to-prevent-spoofing.md).

- Granska din DKIM-konfiguration (DomainKeys Identified Mail). Du bör använda DKIM utöver SPF och DMARC för att förhindra attacker från att skicka meddelanden som ser ut som de kommer från din domän. Med DKIM kan du lägga till en digital signatur i e-postmeddelanden i meddelandehuvudet. Mer information finns i [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).

- Granska din domänbaserade konfiguration av meddelandeautentisering, rapportering och överensstämmelse (DMARC). Implementering av DMARC med SPF och DKIM ger ytterligare skydd mot förfalsknings- och nätfiske-e-post. DMARC gör så att mottagande e-postsystem kan bestämma vad som ska göras med meddelanden som skickats från din domän som misslyckas i SPF- eller DKIM-kontroller. Mer information finns i Använda [DMARC för att verifiera e-post i Office 365](use-dmarc-to-validate-email.md).
