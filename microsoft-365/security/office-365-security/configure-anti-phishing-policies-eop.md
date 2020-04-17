---
title: Konfigurera standardprincipen mot nätfiske i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du ändrar de inställningar mot förfalskning som är tillgängliga i standardpolicyn mot nätfiske i Office 365-organisationer med Exchange Online-postlådor.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537539"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a>Konfigurera standardprincipen mot nätfiske i EOP

Office 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor har en standardprincip mot nätfiske. Den här principen innehåller ett begränsat antal anti-spoofing-funktioner som är aktiverade som standard. Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).

Office 365-organisationer med Exchange Online-postlådor kan ändra standardprincipen mot nätfiske i Office 365 Security & Compliance Center eller Exchange Online PowerShell. Fristående EOP-organisationer utan Exchange Online-postlådor kan inte ändra sin standardpolicy mot nätfiske.

Information om hur du skapar och ändrar de mer avancerade ATP-principerna för nätfiske som är tillgängliga i Office 365 Advanced Threat Protection finns [i Konfigurera ATP-principer för nätfiske i Office 365](configure-atp-anti-phishing-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till <https://protection.office.com/antiphishing>sidan **Mot nätfiske** använder du .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Om du vill lägga till, ändra och ta bort principer för nätfiske måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.** För skrivskyddad åtkomst till anti-phishing-principer måste du vara medlem i rollgruppen **Säkerhetsläsare.** Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md).

- Våra rekommenderade inställningar för standardpolicyn mot nätfiske finns i [EOP:s standardinställningar för anti-nätfiske](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

- Tillåt upp till 30 minuter för den uppdaterade principen som ska tillämpas.

- Information om var principer mot nätfiske tillämpas i filtreringspipelinen finns [i Ordning och prioritet för e-postskydd i Office 365](how-policies-and-protections-are-combined.md).

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Använd Security & Compliance Center för att ändra standardprincipen mot nätfiske

Standardprincipen mot nätfiske heter Office365 AntiPhish Default och visas inte i listan över principer. Så här ändrar du standardpolicyn mot nätfiske:

1. Gå till **Policy** \> **Anti-phishing** **Threat management** \> i Security & Compliance Center .

2. Klicka på **Standardprincip**på sidan **Anti-phishing.**

3. Sidan **Redigera din princip office365 AntiPhish Standard** visas. Klicka på **Redigera**i avsnittet **Spoof.**

   Observera att dessa inställningar är identiska med de falska inställningar som är tillgängliga i ATP:s principer för phishing.Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.

   - **Spoofing filterinställningar:** Standardvärdet är **På**, och vi rekommenderar att du lämnar den på. Om du vill inaktivera den drar du växlingsknappen till **Av**. Mer information finns [i Konfigurera falska underrättelser i Office 365](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Du behöver inte inaktivera förfalskningsskydd om MX-posten inte pekar på Office 365. du aktiverar utökad filtrering för kopplingar i stället. Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Aktivera funktionen Oautentiserade avsändare**: Lägger till ett frågetecken i avsändarens foto om meddelandet inte fungerar e-postautentisering. Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings). Standardvärdet är **På**. Om du vill inaktivera den drar du växlingsknappen till **Av**.

   - **Åtgärder**: Ange vilken åtgärd som ska vidtas för meddelanden som inte innehåller falska underrättelser:

     **Om e-post skickas av någon som inte får förfalska din domän:**

     - **Flytta meddelande till mottagarnas skräppostmappar** (Detta är standardvärdet.)
     - **Karantän meddelandet**

   - **Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.

     - Du kan klicka på **Redigera** i varje avsnitt om du vill gå tillbaka till den aktuella sidan.
     - Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:

       - **Aktivera skydd mot förfalskning**
       - **Aktivera funktionen Oautentiserad avsändare**

   När du är klar klickar du på **Spara** på valfri sida.

4. Tillbaka på sidan **Redigera din princip Office365 AntiPhish Standard,** granska dina inställningar och klicka sedan på **Stäng**.

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a>Använda Security & Compliance Center för att visa standardprincipen mot nätfiske

1. I Security & Compliance Center och gå till **Atp-anti-phishing-principen** **mot hothanteringspolicy** \> **Policy** \> .

2. Klicka på **Standardprincip** om du vill visa standardprincipen mot nätfiske.

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a>Använda Exchange Online PowerShell för att konfigurera standardprincipen mot nätfiske

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a>Använda PowerShell för att visa standardprincipen mot phish

Om du vill visa standardprincipen mot phish kör du följande kommando:

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a>Använda PowerShell för att ändra standardprincipen mot phish

Om du vill ändra standardprincipen mot phish använder du följande syntax:

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

I det här exemplet ändras åtgärden för falska meddelanden som misslyckas med autentiseringskontroller till karantän.

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Så här kontrollerar du att du har konfigurerat standardprincipen mot nätfiske:

- Gå till **Policy** \> **Anti-phishing-principen** \> mot **nätfiske** \> **i** Security & Compliance Center och visa information i det utfällbara utfällbara energiläget.

- I Exchange Online PowerShell kör du följande kommando och verifierar inställningarna:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
