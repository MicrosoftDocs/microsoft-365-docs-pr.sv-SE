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
ms.openlocfilehash: 2a65400d1b48abfc6ac0e4dd38a8245dd7b4f87b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289693"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Konfigurera förfalskningsinformation i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor skyddas inkommande e-postmeddelanden automatiskt mot förfalskning av EOP från och med oktober 2018. EOP använder förfalskningsinformation som en del av organisationens totala skydd mot nätfiske. Mer information finns i [Förfalskningsskydd i EOP.](anti-spoofing-protection.md)

När en avsändare förfalskning en e-postadress, de verkar vara en användare i en av organisationens domäner eller en användare i en extern domän som skickar e-post till din organisation. Attacker som kapar avsändare för att skicka skräppost eller nätfiske måste blockeras. Men det finns situationer där legitima avsändare förfalskning. Till exempel:

- Legitima scenarier för förfalskning av interna domäner:

  - Avsändare från tredje part använder din domän för att skicka massutskick till dina egna anställda för företags omröstningar.
  - Ett externt företag genererar och skickar reklam- eller produktuppdateringar åt dig.
  - En assistent behöver regelbundet skicka e-post till en annan person i organisationen.
  - Ett internt program skickar e-postaviseringar.

- Legitima scenarier för förfalskning av externa domäner:

  - Avsändaren finns på en distributionslista (kallas även diskussionslista) och distributionslistan vidarebefordrar e-post från den ursprungliga avsändaren till alla deltagare på distributionslistan.
  - Ett externt företag skickar e-post åt ett annat företag (till exempel en automatiserad rapport eller ett företag med programvara som tjänst).

Med standardprincipen för förfalskningsinformation, och specifikt standardprincipen för förfalskning, ser du till att förfalskningsmeddelande som skickas av legitima avsändare inte håller sig i EOP-skräppostfilter eller externa e-postsystem, samtidigt som dina användare skyddas från skräppost- eller nätfiskeattacker.

Du kan hantera förfalskningsinformation i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>. Om du vill gå direkt **till sidan mot nätfiske** använder du <https://protection.office.com/antiphishing> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill ändra förfalskningsprincipen eller aktivera eller inaktivera förfalskningsinformation  måste du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till förfalskningsinformationsprincipen måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Vi rekommenderar inställningar för förfalskningsinformation i EOP:s standardinställningar [för skydd mot nätfiske.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Använd Säkerhets- & Efterlevnadscenter för att hantera förfalskningsavsändare

> [!NOTE]
> Om du har en Microsoft 365 Enterprise, E5-prenumeration eller har köpt ett tillägg till Microsoft Defender för Office 365 separat kan du också hantera avsändare som förfalskning av din domän via [Spoof](walkthrough-spoof-intelligence-insight.md)Intelligence-insikten.

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På **inställningssidan Skydd mot skräppost klickar** du på ikonen Expandera för att expandera ![ ](../../media/scc-expand-icon.png) **Spoof Intelligence-principen.**

   ![Välj förfalskningsinformationsprincipen](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Gör något av följande:

   - **Granska nya avsändare**
   - **Visa avsändare som jag redan har granskat**

4. I **Bestäm om dessa avsändare får** kapa användarnas utfällbar lista som visas väljer du någon av följande flikar:

   - **Dina domäner:** Avsändarna förfalskning av användare i dina interna domäner.
   - **Externa domäner:** Avsändarna förfalskning av användare i externa domäner.

5. Klicka ![ på ikonen Expandera i kolumnen ](../../media/scc-expand-icon.png) **Tillåts som förfalskning?** Välj **Ja** om du vill tillåta en förfalskning av avsändaren eller **välj** Nej för att markera meddelandet som kapat. Åtgärden styrs av standardprincipen för skydd mot nätfiske eller anpassade principer för nätfiske (standardvärdet är Flytta meddelandet till mappen **Skräppost).** Mer information finns i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)

   ![Skärmbild som visar de utfällda avsändarna och om avsändaren tillåts att kapa](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Kolumnerna och värdena som visas förklaras i följande lista:

   - **Förfalskningsanvändare**: Användarkontot som kapas. Det här är meddelandets avsändare i från-adressen (kallas även adressen) som `5322.From` visas i e-postklienter. Adressens giltighet kontrolleras inte av SPF.

     - På fliken **Dina domäner** innehåller värdet en enda e-postadress, eller om käll-e-postservern förfalskning av flera användarkonton, innehåller den Fler **än en.**

     - På fliken **Externa domäner** innehåller värdet domänen för den förfalskningsanvändaren, inte den fullständiga e-postadressen.

   - **Skicka infrastruktur:** Den domän som finns i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress. Om käll-IP-adressen inte har någon PTR-post identifieras den avsändande infrastrukturen som \<source IP\> /24 (t.ex. 192.168.100.100/24).

     Mer information om meddelandekällor och meddelandeavsändare finns i en översikt över standarder för [e-postmeddelanden.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

   - **# av meddelanden:** Antalet meddelanden från den avsändande infrastrukturen till organisationen som innehåller angivna förfalskningsavsändare eller avsändare inom de senaste 30 dagarna.

   - **# av klagomål från användare:** Klagomål från användare mot denna avsändare inom de senaste 30 dagarna. Klagomål är vanligtvis i form av skräppost som skickas till Microsoft.

   - **Autentiseringsresultat:** Ett av följande värden:
      - **Godkänd:** Avsändaren har skickat e-postautentiseringskontroller (SPF eller DKIM).
      - **Misslyckades:** Det gick inte att autentisera EOP-avsändare med avsändaren.
      - **Okänt:** Resultatet av de här kontrollerna är inte känt.

   - **Beslut som angetts** av : Visar vem som fastställt om den avsändande infrastrukturen tillåts förfalskning av användaren:
       - **Spoof Intelligence-princip** (automatisk)
       - **Administratör** (manuellt)

   - **Sågs** senast: Det senaste datumet då ett meddelande togs emot från den avsändande infrastrukturen som innehåller den kapade användaren.

   - **Tillåtet att kapa?**: Värdena som visas här är:
     - **Ja:** Meddelanden från kombination av förfalskningsanvändare och infrastruktur för att skicka meddelanden tillåts och hanteras inte som falska e-postmeddelanden.
     - **Nej:** Meddelanden från en kombination av kapad användare och infrastruktur som skickas markeras som falska. Åtgärden styrs av standardprincipen för skydd mot nätfiske eller anpassade principer för nätfiske (standardvärdet är Flytta meddelandet till mappen **Skräppost).** Mer information finns i nästa avsnitt.

     - **Vissa användare** **(endast fliken** Dina domäner): En avsändande infrastruktur förfalskning av flera användare, där vissa förfalskningsanvändare tillåts och andra inte. Använd fliken **Detaljerad** för att se de specifika adresserna.

6. Klicka på Spara längst ned på **sidan.**

## <a name="use-powershell-to-manage-spoofed-senders"></a>Använda PowerShell för att hantera falska avsändare

Använd följande syntax för att visa tillåtna och blockerade avsändare i förfalskningsinformation:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

Det här exemplet returnerar detaljerad information om alla avsändare som är tillåtna att kapa användare i domänerna.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Detaljerad information om syntax och parametrar finns i [Hämta-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)

Så här konfigurerar du tillåtna och blockerade avsändare i förfalskningsinformation:

1. Spara den aktuella listan med identifierade förfalskningsavsändare genom att skriva utdata från cmdleten **Get-PhishFilterPolicy** till en CSV-fil:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Redigera CSV-filen för att lägga till eller ändra värdena **för förfalskning** (e-postadress) och **AllowedToSpoof** (Ja eller No). Spara filen, läs filen och lagra innehållet som en variabel med `$UpdateSpoofedSenders` namnet:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Använd `$UpdateSpoofedSenders` variabeln för att konfigurera förfalskningsinformationsprincipen:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Detaljerad information om syntax och parametrar finns [i Set-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Använda Säkerhets- & Center för att konfigurera förfalskningsinformation

Konfigurationsalternativen för förfalskningsinformation beskrivs i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)

Du kan konfigurera inställningar för förfalskningsinformation i standardprincipen för skydd mot nätfiske och även i anpassade principer. Anvisningar baserade på din prenumeration finns i följande avsnitt:

- [Konfigurera principer för skydd mot nätfiske i EOP.](configure-anti-phishing-policies-eop.md)

- [Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Använd något av följande steg för att verifiera att du har konfigurerat förfalskningsinformation med avsändare som tillåts och inte får kapa, och att du har konfigurerat inställningarna för förfalskningsinformation:

- I Säkerhets- &  Efterlevnadscenter går du till Policy för skydd mot skräppost och expanderar \>  \> Spoof **Intelligence-principen.** Välj Visa avsändare som jag redan har granskat genom att välja fliken Dina domäner eller externa domäner och verifiera värdet Tillåten att förfalskning? för \>  \>  \> avsändaren.   

- I PowerShell kör du följande kommandon för att visa avsändare som tillåts och inte får kapa:

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

- I Säkerhets- & Efterlevnadscenter  går du till Policy för hantering av hot mot nätfiske eller ATP – skydd mot nätfiske och \>  \>  gör något av följande:  

  - Välj en princip i listan. Kontrollera värdena i förfalskningsavsnittet i den **utfällo som** visas.
  - Klicka **på Standardprincip.** Kontrollera värdena i förfalskningsavsnittet i den **utfällo som** visas.

- I Exchange Online PowerShell ersätter du med Office365 AntiPhish Default eller namnet på en anpassad princip och kör följande kommando för \<Name\> att verifiera inställningarna:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Andra sätt att hantera förfalskning och nätfiske

Var flitig om förfalskning och nätfiskeskydd. Här är relaterade sätt att kontrollera avsändare som förfalskning av din domän och förhindra att de skadar organisationen:

- Kontrollera **förfalskningsrapporten.** Du kan använda den här rapporten ofta för att visa och hjälpa till att hantera falska avsändare. Mer information finns i [rapporten Identifiering av förfalskning.](view-email-security-reports.md#spoof-detections-report)

- Granska SPF-konfigurationen (Sender Policy Framework). En introduktion till SPF finns i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt. För att få en djupare förståelse av hur Office 365 använder SPF, eller om du vill veta hur du felsöker eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing (Så här använder Office 365 SPF för att förhindra förfalskning)](how-office-365-uses-spf-to-prevent-spoofing.md).

- Granska konfigurationen av DKIM (DomainKeys Identified Mail). Du bör använda DKIM utöver SPF och DMARC för att förhindra attacker från att skicka meddelanden som ser ut som de kommer från din domän. Med DKIM kan du lägga till en digital signatur i e-postmeddelanden i meddelandehuvudet. Mer information finns i Använda [DKIM för att verifiera utgående e-post som skickas från din anpassade domän i Office 365.](use-dkim-to-validate-outbound-email.md)

- Granska din domänbaserade konfiguration av meddelandeautentisering, rapportering och överensstämmelse (DMARC). Implementering av DMARC med SPF och DKIM ger ytterligare skydd mot förfalsknings- och nätfiske-e-post. DMARC gör så att mottagande e-postsystem kan bestämma vad som ska göras med meddelanden som skickats från din domän som misslyckas i SPF- eller DKIM-kontroller. Mer information finns i Använda [DMARC för att verifiera e-post i Office 365.](use-dmarc-to-validate-email.md)
