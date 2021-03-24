---
title: Konfigurera förfalskningsinformation
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
description: Administratörer kan läsa mer om förfalskningsinformation i Exchange Online Protection (EOP), där du kan tillåta eller blockera specifika förfalskningsavsändare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c13c080829236b9a27b6a1a82e1c27256749b5c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073265"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Konfigurera förfalskningsinformation i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor skyddas inkommande e-postmeddelanden automatiskt mot förfalskning via EOP från och med oktober 2018. EOP använder förfalskningsinformation som en del av organisationens totala skydd mot nätfiske. Mer information finns i [Skydd mot förfalskning i EOP.](anti-spoofing-protection.md)

När en avsändare kapar en e-postadress verkar det vara en användare i en av organisationens domäner eller en användare i en extern domän som skickar e-post till organisationen. Attacker som förfalskning av avsändare för att skicka skräppost eller nätfiske måste blockeras. Men det finns situationer där legitima avsändare är förfalskning. Ett exempel:

- Legitima scenarier för förfalskning av interna domäner:

  - Avsändare från tredje part använder din domän för att skicka massutskick till dina egna anställda för företags omröstningar.
  - Ett externt företag genererar och skickar reklam- eller produktuppdateringar åt dig.
  - En assistent behöver regelbundet skicka e-post till en annan person i din organisation.
  - Ett internt program skickar e-postaviseringar.

- Legitima scenarier för förfalskning av externa domäner:

  - Avsändaren finns på en distributionslista (kallas även diskussionslista) och distributionslistan vidarebefordrar e-post från den ursprungliga avsändaren till alla deltagare på distributionslistan.
  - Ett externt företag skickar e-post åt ett annat företag (till exempel en automatiserad rapport eller ett företag som använder en programvara).

Med förfalskningsinformation, och speciellt standardprincipen (och endast) förfalskningsinformation, kan du se till att förfalskning som skickas av legitima avsändare inte fångas i EOP-skräppostfilter eller externa e-postsystem, samtidigt som dina användare skyddas mot skräppost- och nätfiskeattacker.

Du kan hantera & förfalskningsinformation i Säkerhets- och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>. Om du vill gå direkt **till sidan Mot nätfiske** använder du <https://protection.office.com/antiphishing> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill ändra förfalskningsprincipen eller aktivera eller inaktivera förfalskningsinformation måste  du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till förfalskningsinformationsprincipen måste du vara medlem i **rollgrupperna Global Reader** **eller Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Anteckningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Vi rekommenderar inställningar för förfalskningsinformation i [EOP:s standardinställningar för nätfiskeprincip.](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Använda Säkerhets- & efterlevnadscenter för att hantera förfalskningsavsändare

> [!NOTE]
> Om du har ett Microsoft 365 Enterprise, E5-abonnemang eller har köpt ett tillägg för Microsoft Defender för Office 365 separat kan du också hantera avsändare som förfalskning av din domän via [Spoof](walkthrough-spoof-intelligence-insight.md)Intelligence-insikt.

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Anti-spam settings klickar** du på ![ Expand-ikonen ](../../media/scc-expand-icon.png) för att expandera **Spoof intelligence-principen**.

   ![Välj förfalskningsinformationsprincipen](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Gör något av följande:

   - **Granska nya avsändare**
   - **Visa avsändare som jag redan har granskat**

4. Välj **någon av följande** flikar i Bestäm om dessa avsändare får kapa användarnas utfällbar lista som visas:

   - **Dina domäner:** Avsändare förfalskning av användare i dina interna domäner.
   - **Externa domäner:** Avsändare förfalskning av användare i externa domäner.

5. Klicka ![ på ](../../media/scc-expand-icon.png) Expandera-ikonen **i kolumnen Tillåts att förfalskning?.** Välj **Ja** om du vill tillåta en förfalskning eller välj **Nej** för att markera meddelandet som förfalskning. Åtgärden styrs av standardprincipen för skydd mot nätfiske eller anpassade principer för skydd mot nätfiske (standardvärdet är Flytta **meddelandet till mappen Skräppost).** Mer information finns i [Inställningar för förfalskning i principer mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)

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

## <a name="use-powershell-to-manage-spoofed-senders"></a>Använda PowerShell för att hantera förfalskningsavsändare

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

1. Spara den aktuella listan med identifierade förfalskningsavsändare genom att skriva utdata från cmdlet:en **Get-PhishFilterPolicy** till en CSV-fil:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Redigera CSV-filen för att lägga till eller ändra värdena **SpoofedUser** (e-postadress) och **AllowedToSpoof** (Ja eller No). Spara filen, läs filen och lagra innehållet som en variabel med namnet `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Använd `$UpdateSpoofedSenders` variabeln för att konfigurera förfalskningsinformationsprincipen:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Detaljerad information om syntax och parametrar finns [i Set-PhishFilterPolicy.](/powershell/module/exchange/set-phishfilterpolicy)

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Använda Säkerhets- & efterlevnadscenter för att konfigurera förfalskningsinformation

Konfigurationsalternativ för förfalskningsinformation beskrivs i [inställningarna för förfalskning i principer mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)

Du kan konfigurera inställningarna för förfalskningsinformation i standardprincipen för nätfiske och även i anpassade principer. Anvisningar som baseras på din prenumeration finns i följande avsnitt:

- [Konfigurera principer för skydd mot nätfiske i EOP.](configure-anti-phishing-policies-eop.md)

- [Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Om du vill verifiera att du har konfigurerat förfalskningsinformation med avsändare som tillåts och inte får kapa, och att du har konfigurerat förfalskningsinställningar, gör du något av följande:

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

- Gå till & Policy  \>  \> **Anti-phishing** eller **ATP anti-phishing** i säkerhets- och efterlevnadscentret och gör något av följande:  

  - Välj en princip i listan. Kontrollera värdena i avsnittet Förfalskning i den **utfäll vata som** visas.
  - Klicka **på Standardprincip.** Kontrollera värdena i avsnittet Förfalskning i den **utfäll vata som** visas.

- I Exchange Online PowerShell ersätter du med Office365 AntiPhish Default eller namnet på en anpassad princip och kör följande kommando för \<Name\> att verifiera inställningarna:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Andra sätt att hantera förfalskning och nätfiske

Var flitig om förfalskning och nätfiskeskydd. Här är relaterade sätt att kontrollera avsändare som förfalskning av din domän och se till att de inte skadar din organisation:

- Kontrollera **förfalskningsrapporten**. Du kan använda den här rapporten ofta för att visa och hjälpa till att hantera förfalskningsavsändare. Mer information finns [i rapporten Identifiering av förfalskning.](view-email-security-reports.md#spoof-detections-report)

- Granska SPF-konfigurationen (Sender Policy Framework). En introduktion till SPF finns i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt. För att få en djupare förståelse av hur Office 365 använder SPF, eller om du vill veta hur du felsöker eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing (Så här använder Office 365 SPF för att förhindra förfalskning)](how-office-365-uses-spf-to-prevent-spoofing.md).

- Granska din DKIM-konfiguration (DomainKeys Identified Mail). Du bör använda DKIM utöver SPF och DMARC för att förhindra attacker från att skicka meddelanden som ser ut som de kommer från din domän. Med DKIM kan du lägga till en digital signatur i e-postmeddelanden i meddelandehuvudet. Mer information finns i [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Office 365.](use-dkim-to-validate-outbound-email.md)

- Granska din domänbaserade konfiguration av meddelandeautentisering, rapportering och överensstämmelse (DMARC). Implementering av DMARC med SPF och DKIM ger ytterligare skydd mot förfalsknings- och nätfiske-e-post. DMARC gör så att mottagande e-postsystem kan bestämma vad som ska göras med meddelanden som skickats från din domän som misslyckas i SPF- eller DKIM-kontroller. Mer information finns i [Använda DMARC för att verifiera e-post i Office 365.](use-dmarc-to-validate-email.md)