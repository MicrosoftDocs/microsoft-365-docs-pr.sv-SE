---
title: Konfigurera förfalskningsinformation
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du använder och hanterar falska underrättelser för skydd mot förfalskning av e-post.
ms.openlocfilehash: 32a7668edced5c9dbca2f7b16ff00253b56a5988
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034250"
---
# <a name="configure-spoof-intelligence-in-microsoft-365"></a>Konfigurera falska underrättelser i Microsoft 365

Om du är en Microsoft 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor skyddas inkommande e-postmeddelanden automatiskt mot förfalskning av EOP från och med oktober 2018. EOP använder falska underrättelser som en del av organisationens övergripande försvar mot nätfiske. Mer information finns i [Skydd mot förfalskning i Microsoft 365](anti-spoofing-protection.md).

När en avsändare förfalskar en e-postadress verkar de vara en användare i en av organisationens domäner eller en användare i en extern domän som skickar e-post till din organisation. Angripare som förfalskar avsändare för att skicka skräppost eller nätfiske e-post måste blockeras. Men det finns scenarier där legitima avsändare är förfalskning. Till exempel:

- Legitima scenarier för förfalskning av interna domäner:

  - Avsändare från tredje part använder domänen för att skicka massutskick till dina egna anställda för företagsavundersökningar.

  - Ett externt företag genererar och skickar reklam- eller produktuppdateringar för din räkning.

  - En assistent måste regelbundet skicka e-post till en annan person inom organisationen.

  - Ett internt program skickar e-postmeddelanden.

- Legitima scenarier för förfalskning av externa domäner:

  - Avsändaren finns i en e-postlista (kallas även diskussionslista) och e-postlistan vidarebefordrar e-post från den ursprungliga avsändaren till alla deltagare i e-postlistan.

  - Ett externt företag skickar e-post på uppdrag av ett annat företag (till exempel en automatiserad rapport eller ett program-som-en-tjänst företag).

Falska underrättelser, och särskilt standardprincipen (och endast) falska underrättelser, hjälper till att säkerställa att falska e-postmeddelanden som skickas av legitima avsändare inte fastnar i skräppostfilter i Microsoft 365 eller externa e-postsystem, samtidigt som användarna skyddas från skräppost- eller nätfiskeattacker.

Du kan hantera falska underrättelser i Microsoft 365 Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-kunder; Exchange Online Protection PowerShell för fristående EOP-kunder).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>. Om du vill gå direkt till <https://protection.office.com/antiphishing>sidan **Mot nätfiske** använder du .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Om du vill ändra informationsprincipen eller aktivera eller inaktivera falska underrättelser måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.** För skrivskyddad åtkomst till den falska underrättelsepolicyn måste du vara medlem i rollgruppen **Säkerhetsläsare.** Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md).

- För våra rekommenderade inställningar för falska underrättelser, [EOP standard anti-phishing-principinställningar](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Använd Security & Compliance Center för att hantera förfalskade avsändare

> [!NOTE]
> Om du har en Office 365 Enterprise E5-prenumeration eller har köpt och ATP-tillägg (Advanced Threat Protection) separat kan du även hantera avsändare som förfalskar din domän via [Spoof Intelligence-insikten](walkthrough-spoof-intelligence-insight.md).

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för** skräppost ![klickar](../../media/scc-expand-icon.png) du på Ikonen Expandera för att expandera **Spoof intelligence policy**.

   ![Välj informationspolicy för falska underrättelser](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Gör något av följande val:

   - **Granska nya avsändare**
   - **Visa mig avsändare som jag redan har granskat**

4. I **Bestäm om dessa avsändare tillåts förfalska användarnas** utfällbara alternativ som visas väljer du en av följande flikar:

   - **Dina domäner:** Avsändare som förfalskar användare i dina interna domäner.
   - **Externa domäner**: Avsändare som förfalskar användare i externa domäner.

5. Klicka ![på](../../media/scc-expand-icon.png) Ikonen Expandera i kolumnen **Tillåtet att förfalska?** Välj **Ja** om du vill tillåta förfalskad avsändare eller välj **Nej** för att markera meddelandet som förfalskat. Åtgärden styrs av standardpolicyn mot nätfiske eller anpassade ATP-principer för nätfiske (standardvärdet är **Flytta meddelande till mappen Skräppost**). Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).

   ![Skärmbild som visar de utfällda utfällbara avsändare som spoofed och om avsändaren tillåts förfalska](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Kolumnerna och värdena som visas förklaras i följande lista:

   - **Förfalskad användare**: Användarkontot som förfalskas. Det här är meddelandeavsändaren i från-adressen (kallas även `5322.From` adressen) som visas i e-postklienter. Adressens giltighet kontrolleras inte av SPF.

     - På fliken **Dina domäner** innehåller värdet en enda e-postadress, eller om käll-e-postservern förfalskar flera användarkonton innehåller det **mer än en**.

     - På fliken **Externa domäner** innehåller värdet domänen för den förfalskade användaren, inte den fullständiga e-postadressen.

   - **Skicka infrastruktur:** Domänen som hittades i en omvänd DNS-sökning (PTR-post) av käll-e-postserverns IP-adress, eller IP-adressen om källan inte har någon PTR-post.

     Mer information om meddelandekällor och meddelandeavsändare finns i [En översikt över e-postmeddelandenstandarder](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

   - **Antal meddelanden**: Antalet meddelanden från den sändande infrastrukturen till din organisation som innehåller den angivna förfalskade avsändaren eller avsändare inom de senaste 30 dagarna.

   - **Antal klagomål från användare:** Klagomål som lämnats in av dina användare mot denna avsändare inom de senaste 30 dagarna. Klagomål är vanligtvis i form av skräp inlagor till Microsoft.

   - **Autentiseringsresultat**: Ett av följande värden:

      - **Godkänd**: Avsändaren skickade avsändare e-postautentiseringskontroller (SPF eller DKIM).
      - **Misslyckades**: Avsändaren misslyckades EOP-avsänaren autentiseringskontroller.
      - **Okänd**: Resultatet av dessa kontroller är inte känt.

   - **Beslut som fastställts av**: Visar vem som fastställt om den sändande infrastrukturen tillåts förfalska användaren:

       - **Spoof intelligens politik** (automatisk)
       - **Admin** (manuell)

   - **Senast sedd**: Det sista datumet då ett meddelande togs emot från den sändande infrastrukturen som innehåller den falska användaren.

   - **Tillåtet att förfalska?**: De värden som du ser här är:

     - **Ja**: Meddelanden från kombinationen av förfalskad användare och skicka infrastruktur är tillåtna och behandlas inte som förfalskad e-post.

     - **Nej**: Meddelanden från kombinationen av förfalskad användare och skickad infrastruktur markeras som förfalskade. Åtgärden styrs av standardpolicyn mot nätfiske eller anpassade ATP-principer för nätfiske (standardvärdet är **Flytta meddelande till mappen Skräppost**). Mer information finns i nästa avsnitt.

     - **Vissa användare** ( fliken**Domäner** endast): En skickande infrastruktur förfalskar flera användare, där vissa falska användare är tillåtna och andra inte är det. Använd fliken **Detaljerad** om du vill visa de specifika adresserna.

6. Klicka på **Spara**längst ned på sidan .

## <a name="use-powershell-to-manage-spoofed-senders"></a>Använda PowerShell för att hantera förfalskade avsändare

Om du vill visa tillåtna och blockerade avsändare i falska underrättelser använder du följande syntax:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

I det här exemplet returneras detaljerad information om alla avsändare som tillåts förfalska användare i dina domäner.

```powershell
Get-PhishFilter -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Detaljerad syntax- och parameterinformation finns i [Hämta-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).

Så här konfigurerar du tillåtna och blockerade avsändare i falska underrättelser:

1. Fånga den aktuella listan över upptäckta förfalskade avsändare genom att skriva utdata från cmdleten **Get-PhishFilterPolicy** till en CSV-fil:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Redigera CSV-filen för att lägga till eller ändra värdena **SpoofedUser** (e-postadress) och **AllowedToSpoof** (Ja eller Nej). Spara filen, läs filen och lagra innehållet som `$UpdateSpoofedSenders`en variabel med namnet :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Använd `$UpdateSpoofedSenders` variabeln för att konfigurera principen för falska underrättelser:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Detaljerad syntax- och parameterinformation finns i [Ange-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Använd Security & Compliance Center för att konfigurera falska underrättelser

Konfigurationsalternativen för falska underrättelser beskrivs i [Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).

Du kan konfigurera falska intelligensinställningar i standardprincipen mot nätfiske och även i anpassade principer. Instruktioner som baseras på din prenumeration finns i något av följande avsnitt:

- [Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md).

- [Konfigurera ATP-principer för phishing-phishing i Microsoft 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Om du vill kontrollera att du har konfigurerat falska underrättelser med avsändare som är tillåtna och inte får förfalska och att du har konfigurerat falska intelligensinställningar använder du något av följande steg:

- Gå till **Policy** \> **Policy** \> för skräppostutredning av **skräppost** \> för **Spoof intelligence policy** \> & som du redan **har granskat** \> fliken Säkerhet **Your Domains** & **efterlevnadscenter** och verifiera värdet **tillåten att förfalska?**

- I PowerShell kör du följande kommandon för att visa de avsändare som är tillåtna och inte får förfalska:

  ```powershell
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilter -AllowedToSpoof No -SpoofType External
  ```

- I PowerShell kör du följande kommando för att exportera listan över alla falska avsändare till en CSV-fil:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- I Microsoft 365-organisationer med Exchange Online-postlådor gör du något av följande:

  - Gå till **Policy** \> **Anti-phishing-principen** \> mot **nätfiske** \> **i** Security & Compliance Center och visa information i det utfällbara utfällbara energiläget.

  - I Exchange Online PowerShell kör du följande kommando och verifierar inställningarna:

    ```PowerShell
    Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
    ```

- I Microsoft 365 ATP-organisationer gör du något av följande:

  - I Security & Compliance Center går du till **ATP-principen** **mot hothanteringspolicy** \> **Policy** \> och gör något av följande:

    - Välj en princip i listan. I det utfällbara resultatet som visas kontrollerar du värdena i avsnittet **Spoof.**
    - Klicka på **Standardprincip**. I det utfällbara resultatet som visas kontrollerar du värdena i avsnittet **Spoof.**

  - I Exchange Online PowerShell ersätter du \<Namn\> med Office365 AntiPhish Standard eller namnet på en anpassad ATP-anti-phishing-princip och kör följande kommando och verifiera inställningarna:

    ```PowerShell
    Get-AntiPhishPolicy -Identity "<Name>"
    ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Andra sätt att hantera förfalskning och nätfiske

Var flitig om förfalskning och nätfiske skydd. Här är relaterade sätt att kontrollera avsändare som förfalskar din domän och hjälper till att förhindra att de skadar din organisation:

- Kontrollera **spoof-e-postrapporten**. Du kan ofta använda den här rapporten för att visa och hantera förfalskade avsändare. Information finns i [rapporten Spoof Detections](view-email-security-reports.md#spoof-detections-report).

- Granska konfigurationen av avsändbara principramar (SPF). En introduktion till SPF finns i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt. För att få en djupare förståelse av hur Office 365 använder SPF, eller om du vill veta hur du felsöker eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing (Så här använder Office 365 SPF för att förhindra förfalskning)](how-office-365-uses-spf-to-prevent-spoofing.md).

- Granska konfigurationen av identifierade e-postmeddelanden (DomainKeys Identified Mail). Du bör använda DKIM utöver SPF och DMARC för att förhindra att angripare skickar meddelanden som ser ut som om de kommer från domänen. Med DKIM kan du lägga till en digital signatur i e-postmeddelanden i meddelandehuvudet. Information finns i [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Office 365](use-dkim-to-validate-outbound-email.md).

- Granska konfigurationen för domänbaserad meddelandeautentisering, rapportering och överensstämmelse (DMARC). Implementering av DMARC med SPF och DKIM ger ytterligare skydd mot förfalsknings- och nätfiske-e-post. DMARC gör så att mottagande e-postsystem kan bestämma vad som ska göras med meddelanden som skickats från din domän som misslyckas i SPF- eller DKIM-kontroller. Information finns i [Använda DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md).