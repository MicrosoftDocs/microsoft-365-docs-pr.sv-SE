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
description: Administratörer kan läsa mer om förfalsknings intelligens i Exchange Online Protection (EOP), där du kan tillåta eller blockera specifika avsändare.
ms.openlocfilehash: 62964550be161b16767595890872055b56586f1d
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367137"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Konfigurera förfalsknings information i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor skyddas inkommande e-postmeddelanden automatiskt mot förfalskning genom EOP som i oktober 2018. EOP använder förfalsknings intelligens som en del av organisationens allmänna försvar mot nätfiske. Mer information finns i [skydd mot förfalskning i EOP](anti-spoofing-protection.md).

När en avsändare får en e-postadress ser de ut som en användare i en av organisationens domäner eller en användare i en extern domän som skickar e-post till din organisation. Angripare som är falska att skicka skräp post eller nätfiske måste blockeras. Men det finns tillfällen då legitima avsändare är falska. Till exempel:

- Legitima scenarier för falska interna domäner:

  - Avsändare från tredje part använder din domän för att skicka mass utskick till dina egna anställda för företags omröstningar.
  - Ett externt företag genererar och skickar reklam-eller produkt uppdateringar för din räkning.
  - En assistent måste regelbundet skicka e-post till en annan person inom din organisation.
  - Ett internt program skickar e-postaviseringar.

- Legitima scenarier för falska externa domäner:

  - Avsändaren är på en distributions lista (kallas även en diskussions lista) och skickar e-post från den ursprungliga avsändaren till alla deltagare i distributions listan.
  - Ett externt företag skickar e-post på uppdrag av ett annat företag (till exempel en automatiserad rapport eller ett företag med program varu namn).

Förfalsknings intelligens och specifikt standard-(och endast) policy för förfalsknings intelligens säkerställer att det falska e-postmeddelandet som skickas av legitima avsändare inte kan upptäckas i EOP spam filter eller externa e-postsystem, samtidigt som användarna skyddas från skräp post eller nätfiske-attacker.

Du kan hantera förfalsknings intelligens i säkerhets & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>. För att gå direkt till **nätfiske-** sidan, Använd <https://protection.office.com/antiphishing> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:

  - Om du vill ändra policyn för förfalsknings information eller aktivera förfalsknings intelligens måste du vara medlem i någon av följande roll grupper:

    - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Om du vill ha skrivskyddad åtkomst till policyn för förfalsknings intelligens måste du vara medlem i någon av följande roll grupper:

    - **Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
    - **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- För våra rekommenderade inställningar för Spoof-intelligens, se [EOP standardinställningar för skydd mot nätfiske](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Hantera falska avsändare genom att använda säkerhets & Compliance Center

> [!NOTE]
> Om du har ett Microsoft 365 Enterprise, E5-abonnemang eller har separat inköpt ett tillägg för Microsoft Defender för Office 365 kan du även hantera avsändare som har falska din domän via [förfalsknings information](walkthrough-spoof-intelligence-insight.md).

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräp post** klickar du på ![ ikonen Expandera ](../../media/scc-expand-icon.png) för att utöka **policyn för förfalsknings information**.

   ![Välj policy för förfalsknings intelligens](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Gör något av följande:

   - **Granska nya avsändare**
   - **Visa mig-avsändare som jag redan har granskat**

4. I **Bestäm om dessa avsändare får använda falska användare** som visas, väljer du någon av följande flikar:

   - **Domänerna**: avsändare förfalskningar användare i de interna domänerna.
   - **Externa domäner**: avsändare falska användare i externa domäner.

5. Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) i kolumnen **tillåts till förfalskning?** . Välj **Ja** om du vill tillåta falska avsändare eller Välj **Nej** om du vill markera meddelandet som falsk. Åtgärden styrs av standard policyn för skydd mot nätfiske eller anpassade anti-phishing-principer (Standardvärdet är **Flytta meddelandet till mappen skräp post**). Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md#spoof-settings).

   ![Skärm bild som visar utfällda falska avsändare och om avsändaren är tillåten för förfalskning](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Kolumnerna och värdena som visas förklaras i följande lista:

   - **Falsk användare**: det användar konto som används för falskas. Det här är meddelandets avsändare i den från-adress (kallas även `5322.From` adress) som visas i e-postklienter. Giltigheten för denna adress kontrol leras inte av SPF.

     - På fliken **dina domäner** innehåller värdet en enda e-postadress, eller om käll-e-postservern är falsk för flera användar konton innehåller den **fler än en**.

     - På fliken **externa domäner** innehåller värdet för domänen med falsk användare, inte den fullständiga e-postadressen.

   - **Skicka infrastruktur**: domänen hittades i en omvänd DNS-sökning (PTR-post) av käll-e-postserverns IP-adress, eller IP-adressen om källan inte har någon PTR-post.

     Mer information om meddelande källor och meddelande avsändare finns i [Översikt över e-poststandarder](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

   - antal **meddelanden**: antalet meddelanden från infrastrukturen för sändning till din organisation som innehåller angivna avsändare eller avsändare inom de senaste 30 dagarna.

   - **antal användare klagomål**: klagomål som lämnats av användarna mot denna avsändare inom de senaste 30 dagarna. Klagomål är vanligt vis i form av skräp post försändelser till Microsoft.

   - **Resultat**: ett av följande värden:

      - **Lyckades**: avsändaren skickade e-postkontroller (SPF eller DKIM).
      - **Misslyckades**: avsändaren misslyckades EOP.
      - **Okänt**: resultatet av dessa kontroller är inte känt.

   - **Beslut inställt av**: visar vilka som har fastställt om den sändande infrastrukturen har tillstånd att skicka falska användare:

       - **Policy för förfalsknings information** (automatiskt)
       - **Administratör** (manuell)

   - **Senast sedd**: det sista datum då ett meddelande togs emot från den sändande infrastrukturen som innehåller den falskade användaren.

   - Har du **tillstånd för falska identiteter?**: de värden som visas här är:

     - **Ja**: meddelanden från en kombination av falsk användare och överföring av infrastrukturen tillåts och behandlas inte som falsk e-post.

     - **Nej**: meddelanden från en kombination av falsk användare och överföring av infrastrukturen markeras som falska. Åtgärden styrs av standard policyn för skydd mot nätfiske eller anpassade anti-phishing-principer (Standardvärdet är **Flytta meddelandet till mappen skräp post**). Se nästa avsnitt för mer information.

     - **Vissa användare** (endast **din domän** -flik): en annan infrastruktur är falsk för flera användare, där vissa falska användare är tillåtna och andra inte är det. Använd den **detaljerade** fliken för att visa specifika adresser.

6. Klicka på **Spara** längst ned på sidan.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Använda PowerShell för att hantera falska avsändare

Använd följande syntax för att Visa tillåtna och spärrade avsändare i Spoof-intelligens:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

I det här exemplet returneras detaljerad information om alla avsändare som får falska användare i dina domäner.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Detaljerad information om syntax och parametrar finns i [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).

Följ de här stegen om du vill konfigurera tillåtna och spärrade avsändare i Spoof-intelligens:

1. Avbilda den aktuella listan med identifierade avsändare genom att skriva utdata från cmdleten **Get-PhishFilterPolicy** till en CSV-fil:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Redigera CSV-filen för att lägga till eller ändra värdena för **SpoofedUser** (e-postadress) och **AllowedToSpoof** (Ja eller Nej). Spara filen, Läs filen och lagra innehållet som en variabel som heter `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Använd `$UpdateSpoofedSenders` variabeln för att konfigurera policyn för förfalsknings intelligens:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Detaljerad information om syntax och parametrar finns i [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Använda säkerhets & Compliance Center för att konfigurera förfalsknings intelligens

Konfigurations alternativen för förfalsknings intelligens beskrivs i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md#spoof-settings).

Du kan konfigurera inställningar för förfalsknings information i standard principen för Antinätfiske och även i anpassade principer. Anvisningar som baseras på ditt abonnemang finns i följande avsnitt:

- [Konfigurera AntiPhishing-principer i EOP](configure-anti-phishing-policies-eop.md).

- [Konfigurera AntiPhishing-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Gör så här för att kontrol lera att du har konfigurerat falsk intelligens med avsändare som är tillåtna och inte har tillåtelse att få åtkomst till falska inställningar:

- I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **anti-spam** \> expandera **policy för förfalsknings information** \> Markera **Visa mig avsändare som jag redan har granskat** \> Välj fliken **dina domäner** eller **externa domäner** och kontrol lera om det är **tillåtet att falska** för avsändaren.

- I PowerShell kör du följande kommandon för att Visa avsändare som är tillåtna och inte tillåtna för falska användare:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- I PowerShell kör du följande kommando för att exportera listan med alla falska avsändare till en CSV-fil:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **mot nätfiske** eller **ATP-nätfiske** och gör något av följande:  

  - Välj en princip i listan. I den utfällbara filen som visas kontrollerar du värdena i avsnittet **Spoof** .
  - Klicka på **standard policy**. I den utfällbara filen som visas kontrollerar du värdena i avsnittet **Spoof** .

- I Exchange Online PowerShell ersätter \<Name\> du med Office365 AntiPhish default eller namnet på en anpassad princip och kör följande kommando för att kontrol lera inställningarna:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Andra sätt att hantera förfalskningar och nätfiske

Var noggrann om förfalskning och nätfiske. Här är relaterade sätt att kontrol lera avsändare som falsk din domän och hjälpa till att förhindra att den inte skadar organisationen:

- Kontrol lera **rapporten med falsk e-post**. Du kan använda den här rapporten ofta för att visa och hjälpa till att hantera falska avsändare. Mer information finns i [rapporten om identifieringar av förfalskningar](view-email-security-reports.md#spoof-detections-report).

- Granska din SPF-konfiguration (avsändare Policy Framework). En introduktion till SPF finns i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt. För att få en djupare förståelse av hur Office 365 använder SPF, eller om du vill veta hur du felsöker eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing (Så här använder Office 365 SPF för att förhindra förfalskning)](how-office-365-uses-spf-to-prevent-spoofing.md).

- Granska din DomainKeys identifieras-konfiguration (DKIM). Du bör använda DKIM utöver SPF och DMARC för att förhindra att angripare skickar meddelanden som ser ut som om de kommer från din domän. Med DKIM kan du lägga till en digital signatur i e-postmeddelanden i meddelandehuvudet. Mer information finns i [använda DKIM för att verifiera utgående e-post som skickas från din egen domän i Office 365](use-dkim-to-validate-outbound-email.md).

- Granska din domänbaserade meddelande identifiering, rapportering och konfiguration av ändringar (DMARC). Implementering av DMARC med SPF och DKIM ger ytterligare skydd mot förfalsknings- och nätfiske-e-post. DMARC gör så att mottagande e-postsystem kan bestämma vad som ska göras med meddelanden som skickats från din domän som misslyckas i SPF- eller DKIM-kontroller. Mer information finns i [använda DMARC för att verifiera e-post i Office 365](use-dmarc-to-validate-email.md).
