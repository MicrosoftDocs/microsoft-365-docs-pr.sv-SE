---
title: Konfigurations analys för säkerhets principer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de använder konfigurations analys för att hitta och åtgärda säkerhets principer som innehåller inställningar som finns under standard säkerhets principer för förvalda skydd och begränsande skydd.
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825779"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a>Konfigurations analys för skydds principer i EOP och Office 365 ATP

> [!NOTE]
> De funktioner som beskrivs i det här avsnittet är i för hands version, är inte tillgängliga i alla organisationer och kan komma att ändras.

Med konfigurations analys i säkerhets & Compliance Center får du en central plats för att hitta och åtgärda någon av dina säkerhets principer som innehåller inställningar som är lägre än standard skydds-och strikta skydds inställningar för [säkerhets principer](preset-security-policies.md).

Följande typer av principer analyseras av konfigurations analys:

- **Principer för Exchange Online Protection (EOP)**: det inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:
  
  - [Principer för skräp post](configure-your-spam-filter-policies.md).
  - [Principer mot skadlig program vara](configure-anti-malware-policies.md).
  - [EOP anti-nätfiske-principer](set-up-anti-phishing-policies.md#spoof-settings).

- **Office 365 principer för avancerat skydd (ATP)**: Detta inkluderar organisationer med Microsoft 365 E5 eller Office 365 ATP-tilläggs abonnemang:

  - ATP anti-phishing-principer, som omfattar:

    - Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP anti-phishing-principer.
    - [Inställningar för personifiering](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [Avancerade nät fiske trösklar](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [Principer för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).

  - [Principer för säkra bifogade filer](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).

De **vanliga** och **strikta** princip inställnings värden som används som bas linjer beskrivs i [rekommenderade inställningar för EOP och Office 365 ATP-säkerhet](recommended-settings-for-eop-and-office365-atp.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **konfigurations analys** kan du använda <https://protection.office.com/configurationAnalyzer> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:

  - För att använda konfigurations analys **och** göra uppdateringar av säkerhets principer måste du vara medlem i någon av följande roll grupper:

    - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Om du vill ha skrivskyddad åtkomst till konfigurations analys måste du vara medlem i någon av följande roll grupper:

    - **Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
    - **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Använda Configuration Analyzer i Center för säkerhets &

Gå till **Threat management** \> **Policy** \> **konfigurations analys**för Threat Management policy i säkerhets & efterlevnad.

![Widgeten för konfigurations analys på \> sidan Threat Management policy](../../media/configuration-analyzer-widget.png)

Konfigurations analysen har två primära flikar:

- **Inställningar och rekommendationer**: du väljer standard eller Strict och jämför dessa inställningar med dina befintliga säkerhets principer. I resultatet kan du justera värdena för inställningarna så att de får samma nivå som standard eller strikt.

- **Analys och historik för konfigurations avvikelse**: med den här vyn kan du spåra de ändringar som du har gjort av dina principer baserat på resultaten av Configuration Analyzer över tiden.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Fliken inställning och rekommendationer i konfigurations analys

Som standard öppnas fliken i jämförelsen med standard skydds profilen. Du kan växla till jämförelsen av den strikta skydds profilen genom att klicka på **Visa strikta rekommendationer**. Om du vill gå tillbaka väljer du **Visa standard rekommendationer**.

![Vyn inställningar och rekommendationer i konfigurations analys](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Som standard innehåller kolumnen **princip grupp/inställnings namn** en dold vy av de olika typerna av säkerhets principer och antalet inställningar i de principer som behöver förbättras. Följande typer av principer är:

- **Skydd mot skräp post**
- **Anti-nätfiske**
- **Skadlig program vara**
- **Säkra filer för ATP** (om ditt abonnemang inkluderar ATP)
- **Säkerhet för ATP** (om ditt abonnemang inkluderar ATP)

I standardvyn är allting dolda. Bredvid varje princip visas en sammanfattning av jämförelse resultat från dina principer (som du kan ändra) och inställningarna i motsvarande principer för standard-eller sträng skydds profilerna (som du inte kan ändra). Följande information visas:

- **Grön**: alla inställningar i alla befintliga principer är åtminstone lika säkra som den skydds profil som du jämför med.
- **Gul**: ett litet antal inställningar i de befintliga principerna är inte lika säkert som den skydds profil som du jämför med.
- **Rött**: ett stort antal inställningar i de befintliga principerna är inte lika säkert som den skydds profil som du jämför med. Det här kan vara några få inställningar i många principer eller många inställningar i en princip.

För fördelaktig jämförelser visas texten: **alla inställningar följer** \<**Standard** or **Strict**\> **rekommendationer**. I annat fall ser du antalet rekommenderade inställningar att ändra.

Om du expanderar **princip grupp/inställnings namn**visas alla principer och associerade inställningar i varje specifik princip som kräver åtgärd. Eller så kan du expandera en viss typ av princip (till exempel **anti-spam**) för att se bara de inställningar som gäller för de principer som kräver din uppmärksamhet.

Om jämförelsen inte har några rekommendationer för förbättring (grön) kan du utöka policyn genom att Visa ingenting. Om det finns några rekommendationer för förbättringar (gul eller röd) visas de inställningar som kräver åtgärd och informationen visas i följande kolumner:

- Namnet på den inställning som kräver din uppmärksamhet. I föregående skärm bild är det till exempel att **tröskelvärdet för Mass** utskick av e-post i en policy för skräp post.

- **Princip**: namnet på den berörda policyn som innehåller inställningen.

- **Tillämpas på**: antalet användare som de berörda principerna tillämpas på.

- **Aktuell konfiguration**: det aktuella värdet för inställningen.

- **Senast ändrad**: det datum då principen senast ändrades.

- **Rekommendationer**: värdet för inställningen i standard-eller sträng skydds profilen. Om du vill ändra värdet för inställningen i principen så att det matchar det rekommenderade värdet i skydds profilen klickar du **på Välj.** Om ändringen lyckas visas meddelandet: **rekommendationerna har antagits**. Klicka på **Uppdatera** om du vill visa det nedsänkta antalet rekommendationer och borttagning av raden specifik inställning/princip från resultaten.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Konfiguration av avvikelser och historik i konfigurations analys

Med den här fliken kan du spåra de ändringar som du har gjort i dina anpassade säkerhets principer baserat på informationen i säkerhets analys. Följande information visas som standard:

- **Senast ändrad**
- **Ändrat av**
- **Inställnings namn**
- **Autentiseringsprincip**
- **Typ**

Om du vill filtrera resultaten klickar du på **Filter**. I de utfällbara **filter** som visas kan du välja bland följande filter:

- **Start tid** och **slut tid** (datum)
- **Standard skydd** eller **strikt skydd**

Exportera resultaten till en CSV-fil genom att klicka på **Exportera**.

![Konfiguration av avvikelser och historik i konfigurations analys](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
