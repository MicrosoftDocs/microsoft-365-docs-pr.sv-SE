---
title: Hantera förfalskningsavsändare med förfalsknings- och förfalskningsinformation
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att använda förfalsknings- och förfalskningsinformationsinsikter för att tillåta eller blockera identifierade förfalskningsavsändare.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a683ed93e4e483e63fe01281b32661f0b803d1ce
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029303"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>Hantera förfalskningsavsändare med förfalsknings- och förfalskningsinformation i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> I den här artikeln beskrivs den äldre version av hantering av avsändare som ersätts. Mer information om den nya upplevelsen finns i [Förfalskningsinformation i EOP](learn-about-spoof-intelligence.md)

I Microsoft 365 organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor skyddas inkommande e-postmeddelanden automatiskt mot förfalskning via EOP från och med oktober 2018. EOP använder **förfalskningsinformation som** en del av organisationens totala skydd mot nätfiske. Mer information finns i [Skydd mot förfalskning i EOP.](anti-spoofing-protection.md)

Standardprincipen (och endast) **förfalskningsinformation** bidrar till att förfalskningsmeddelanden som skickas av legitima avsändare inte fångas i EOP-skräppostfilter och samtidigt skyddar användarna från skräppost- och nätfiskeattacker. Du kan också använda **Spoof Intelligence-insikt** för att snabbt avgöra vilka externa avsändare som på ett legitimt sätt skickar oauthenticerad e-post (meddelanden från domäner som inte klarar SPF-, DKIM- eller DMARC-kontroller).

Du kan hantera & förfalskningsinformation i Säkerhets- och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.
  - Om du vill gå **direkt till sidan inställningar för skydd** mot skräppost för förfalskningsprincipen använder du <https://protection.office.com/antispam> .
  - Om du vill gå direkt **till sidan Säkerhetsinstrumentpanel** för förfalskningsinformation använder du <https://protection.office.com/searchandinvestigation/dashboard> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill ändra förfalskningsprincipen eller aktivera eller inaktivera förfalskningsinformation måste  du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till förfalskningsinformationsprincipen måste du vara medlem i **rollgrupperna Global Reader** **eller Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Anteckningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Alternativen för förfalskningsinformation beskrivs i inställningarna [för förfalskning i principer mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)

- Du kan aktivera, inaktivera och konfigurera inställningarna för förfalskningsinformation i principer mot nätfiske. Anvisningar som baseras på din prenumeration finns i följande avsnitt:

  - [Konfigurera principer för skydd mot nätfiske i EOP.](configure-anti-phishing-policies-eop.md)
  - [Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365](configure-mdo-anti-phishing-policies.md).

- Vi rekommenderar inställningar för förfalskningsinformation i inställningarna för [EOP-policy mot nätfiske.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)

## <a name="manage-spoofed-senders"></a>Hantera falska avsändare

Det finns två sätt att tillåta och blockera falska avsändare:

- [Använda förfalskningsinformationsprincipen](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [Använda förfalskningsinformation](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a>Hantera förfalskningsavsändare i förfalskningsprincipen

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Anti-spam settings klickar** du på ![ Expand-ikonen ](../../media/scc-expand-icon.png) för att expandera **Spoof intelligence-principen**.

   ![Välj förfalskningsinformationsprincipen](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Gör något av följande:

   - **Granska nya avsändare**
   - **Visa avsändare som jag redan har granskat**

4. Välj **någon av följande** flikar i Bestäm om dessa avsändare får kapa användarnas utfällbar lista som visas:

   - **Dina domäner:** Avsändare förfalskning av användare i dina interna domäner.
   - **Externa domäner:** Avsändare förfalskning av användare i externa domäner.

5. Klicka ![ på ](../../media/scc-expand-icon.png) Expandera-ikonen **i kolumnen Tillåts att förfalskning?.** Välj **Ja** om du vill tillåta en förfalskning eller välj **Nej** för att markera meddelandet som förfalskning. Åtgärden styrs av standardprincipen för skydd mot nätfiske eller anpassade principer för skydd mot nätfiske (standardvärdet är Flytta **meddelandet till mappen Skräppost).** Mer information finns i [Principer för skydd mot nätfiske](set-up-anti-phishing-policies.md#spoof-settings).

   ![Skärmbild som visar de utfällda avsändarna och om avsändaren tillåts kapa](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Kolumnerna och värdena som visas förklaras i följande lista:

   - **Spoofed användare**: Användarkontot som falskas. Det här är meddelandets avsändare i från-adressen (kallas även adressen) som visas `5322.From` i e-postklienter. Adressens giltighet kontrolleras inte av SPF.
     - På fliken **Dina domäner** innehåller värdet en enda e-postadress, eller om käll-e-postservern förfalskning innehåller flera användarkonton innehåller den Fler **än en**.
     - På fliken **Externa domäner** innehåller värdet domänen för den kapade användaren, inte den fullständiga e-postadressen.

   - **Skicka infrastruktur:** Den domän som finns i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress. Om käll-IP-adressen inte har någon PTR-post identifieras den avsändande infrastrukturen som \<source IP\> /24 (till exempel 192.168.100.100/24).

     Mer information om meddelandekällor och avsändare finns i En [översikt över e-poststandarder.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

   - **Antal meddelanden:** Antalet meddelanden från den avsändande infrastrukturen till organisationen som innehåller den angivna förfalskningsavsändaren eller avsändarna under de senaste 30 dagarna.

   - **# av användarklagomål:** Klagomål från användare mot denna avsändare inom de senaste 30 dagarna. Klagomål är vanligtvis i form av skräppostinskick till Microsoft.

   - **Autentiseringsresultat:** Något av följande värden:
      - **Godkänd**: Avsändaren har skickat e-postautentiseringskontroller (SPF eller DKIM).
      - **Misslyckades:** Avsändaren misslyckades autentiseringskontroller för EOP-avsändare.
      - **Okänt:** Resultatet av de här kontrollerna är inte känt.

   - **Beslut som angetts** av : Visar vem som avgör om den avsändande infrastrukturen är tillåten att kapa användaren:
       - **Spoof intelligence-princip** (automatisk)
       - **Administratör** (manuellt)

   - **Senast** sedd: Det sista datumet när ett meddelande togs emot från den avsändande infrastrukturen som innehåller den beskickade användaren.

   - **Tillåts kapa?**: Värdena som visas här är:
     - **Ja:** Meddelanden från kombination av förfalskningsanvändare och avsändarinfrastruktur är tillåtna och hanteras inte som falska e-postmeddelanden.
     - **Nej:** Meddelanden från kombination av förfalskningsanvändare och avsändarinfrastruktur markeras som falska. Åtgärden styrs av standardprincipen för skydd mot nätfiske eller anpassade principer för skydd mot nätfiske (standardvärdet är Flytta **meddelandet till mappen Skräppost).** Mer information finns i nästa avsnitt.

     - **Vissa användare** (**endast fliken** Dina domäner): En avsändande infrastruktur förfalskning av flera användare, där vissa förfalskningsanvändare tillåts och andra inte. Använd fliken **Detaljerad** om du vill se de specifika adresserna.

6. Klicka på Spara längst ned på **sidan.**

#### <a name="use-powershell-to-manage-spoofed-senders"></a>Använda PowerShell för att hantera förfalskningsavsändare

Om du vill visa tillåtna och blockerade avsändare i förfalskningsinformation använder du följande syntax:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

Det här exemplet returnerar detaljerad information om alla avsändare som tillåts kapa användare i domänerna.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Detaljerad information om syntax och parametrar finns i [Get-PhishFilterPolicy.](/powershell/module/exchange/get-phishfilterpolicy)

Om du vill konfigurera tillåtna och blockerade avsändare i förfalskningsinformation gör du så här:

1. Spara den aktuella listan över identifierade förfalskningsavsändare genom att skriva utdata från cmdlet:en **Get-PhishFilterPolicy** till en CSV-fil genom att köra följande kommando:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Redigera CSV-filen för att lägga till eller ändra följande värden:
   - **Avsändare** (domän i källserverns PTR-post eller IP/24-adress)
   - **SpoofedUser**: Något av följande värden:
     - Den interna användarens e-postadress.
     - Den externa användarens e-postdomän.
     - Ett tomt värde som anger att du vill spärra eller tillåta alla falska meddelanden från den angivna **avsändaren,** oavsett förfalskningsadress.
   - **AllowedToSpoof** (Ja eller Nej)
   - **SpoofType** (intern eller extern)

   Spara filen, läs filen och lagra innehållet som en variabel med `$UpdateSpoofedSenders` namnet genom att köra följande kommando:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Använd `$UpdateSpoofedSenders` variabeln för att konfigurera förfalskningsinformationsprincipen genom att köra följande kommando:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Detaljerad information om syntax och parametrar finns [i Set-PhishFilterPolicy.](/powershell/module/exchange/set-phishfilterpolicy)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a>Hantera falska avsändare med förfalskningsinformation

1. I Säkerhets- & efterlevnadscenter går du till **Instrumentpanelen för hantering av** \> **hot.**

2. På **Insights** kan du leta efter något av följande:

   - **Troliga förfalskningsdomäner de** senaste sju dagarna: Den här insikten anger att förfalskningsinformation är aktiverad (den är aktiverad som standard).
   - **Aktivera förfalskningsskydd:** Den här insikten anger att förfalskningsinformation är inaktiverad och om du klickar på insikten kan du aktivera förfalskningsinformation.

3. Insikten på instrumentpanelen visar dig information så här:

   ![Skärmbild av förfalskningsinformation](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Den här insikten har två lägen:

   - **Insiktsläge:** Om förfalskningsinformation har aktiverats visar insikten hur många meddelanden som påverkats av vår förfalskningsinformation under de senaste sju dagarna.
   - **Vad händer** om-läge: Om förfalskningsinformation är inaktiverad  visar insikten hur många meddelanden som skulle ha påverkats av våra förfalskningsfunktioner under de senaste sju dagarna.

   Oavsett vilket så är de förfalskningsdomäner som visas i insikten uppdelade i två kategorier: **Misstänkta domäner** och **Icke-misstänkta domäner.**

   - **Misstänkta domäner:**
     - **Betrodd** förfalskning : Baserat på de historiska avsändarmönster och rykteshistoriken för domänerna är vi mycket säkra på att domänerna är förfalskning och att meddelanden från dessa domäner är mer troliga att de är skadliga.
     - **Måttlig konfidens** förfalskning: Baserat på historiska sändningsmönster och rykteshistoriken för domänerna är vi ganska säkra på att domänerna är förfalskning och att meddelanden som skickas från dessa domäner är legitima. Falska positiva resultat är mer troliga i den här kategorin än förfalskning med hög konfidens.
   - **Icke-misstänkta domäner:** Domänen misslyckades med explicit e-postautentisering kontrollerar [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC](use-dmarc-to-validate-email.md)). Domänen klarade emellertid vår implicita e-postautentisering[(sammansatt autentisering).](email-validation-and-authentication.md#composite-authentication) Därför vidtogs ingen förfalskning i meddelandet.

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a>Visa detaljerad information om misstänkta och icke-återanvända domäner

1. Gå till sidan Förfalskningsinformation  genom att klicka på Misstänkta domäner eller **Icke-misstänkta** domäner på sidan **Förfalskningsinformation.** På **sidan Spoof Intelligence-insikter** finns följande information:

   - **Spoofed domain**: Domänen för den kapade användaren som  visas i rutan Från i e-postklienter. Den här adressen kallas även `5322.From` för adressen.
   - **Infrastruktur:** Kallas även _avsändarinfrastrukturen._ Domänen finns i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress. Om käll-IP-adressen inte har någon PTR-post identifieras den avsändande infrastrukturen som \<source IP\> /24 (till exempel 192.168.100.100/24).
   - **Antal meddelanden:** Antalet meddelanden från den avsändande infrastrukturen till organisationen som innehåller den angivna förfalskningsdomänen under de senaste 7 dagarna.
   - **Senast** sedd: Det sista datumet när ett meddelande togs emot från den avsändande infrastrukturen som innehåller den falska domänen.
   - **Förfalskningstyp:** Det här värdet är **Externt.**
   - **Tillåts kapa?**: Värdena som visas här är:
     - **Ja:** Meddelanden från kombination av förfalskningsanvändares domän och infrastrukturen för att skicka meddelanden är tillåtna och hanteras inte som falska e-postmeddelanden.
     - **Nej:** Meddelanden från kombination av förfalskningsanvändares domän och avsändande infrastruktur markeras som förfalskning. Åtgärden styrs av standardprincipen för skydd mot nätfiske eller anpassade principer för skydd mot nätfiske (standardvärdet är Flytta **meddelandet till mappen Skräppost).**

2. Markera ett objekt i listan om du vill visa information om domän/skicka infrastrukturpar i en utfällad meny. Informationen omfattar:
   - Därför att vi inte kunde göra detta.
   - Det här behöver du göra.
   - En domänsammanfattning.
   - WhoIs data about the sender.
   - Liknande meddelanden som vi har sett i klientorganisationen från samma avsändare.

   Härifrån kan du även välja att lägga till eller ta bort infrastrukturparet för domänen/skicka i listan Tillåtna **till förfalskning av** avsändare. Ställ bara in växlingsknappen efter det.

   ![Skärmbild av en domän i informationsfönstret för förfalskningsinformation](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Använd något av följande steg för att verifiera att du har konfigurerat förfalskningsinformation med avsändare som tillåts och inte har tillåtelse att kapa:

- I Säkerhets- &  och efterlevnadscenter går du till Policy Anti-spam expand Spoof Intelligence-princip för skydd mot skräppost och väljer Visa avsändare som jag redan har granskat genom att välja fliken Your Domains eller External Domains och verifiera värdet Allowed to \>  \>  \>  \>  \> **spoof?för** avsändaren.  

- Kör följande kommandon i PowerShell för att visa avsändare som tillåts och inte får kapa:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- Kör följande kommando i PowerShell för att exportera listan över alla falska avsändare till en CSV-fil:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
