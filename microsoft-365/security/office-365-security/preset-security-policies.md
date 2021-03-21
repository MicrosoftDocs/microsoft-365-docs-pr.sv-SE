---
title: Förvalda säkerhetsprinciper
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de tillämpar standard- och striktprincipinställningar i alla skyddsfunktioner i Exchange Online Protection (EOP) och Microsoft Defender för Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b57c13517d9fd41bcafea5c9d672da0e6b581ad7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926766"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Förinställda säkerhetsprinciper i EOP och Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Förinställda säkerhetsprinciper tillhandahåller en central plats där användarna kan använda alla rekommenderade principer för skräppost, skadlig programvara och nätfiske på en gång. Principinställningarna kan inte konfigureras. De ställs i stället in av oss och baseras på våra observationer i datacenter för en balans mellan att hålla skadligt innehåll borta från användare utan att störa deras arbete.

Resten av det här avsnittet beskriver förinställda säkerhetsprinciper och hur du konfigurerar dem.

## <a name="what-preset-security-policies-are-made-of"></a>Vilka förinställda säkerhetsprinciper görs av

Förinställda säkerhetsprinciper består av följande element:

- Profiler
- Principer
- Principinställningar

Prioritetsordningen är dessutom viktig om flera förinställda säkerhetsprinciper och andra principer gäller för samma person.

### <a name="profiles-in-preset-security-policies"></a>Profiler i förinställda säkerhetsprinciper

En profil avgör skyddsnivån. Följande profiler är tillgängliga:

- **Standardskydd:** En profil för baslinjeskydd som är lämplig för de flesta användare.
- **Strikt skydd:** En mer aggressiva skyddsprofil för valda användare (högvärdesmålen eller prioriterade användare).

Du använder regler med villkor och undantag som avgör vilka profiler som profilerna ska tillämpas på eller inte.

Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

Tillgängliga villkor och undantag är:

- **Mottagarna är: Postlådor,** e-postanvändare eller e-postkontakter i organisationen.
- **Mottagarna är medlemmar i**: Grupper i organisationen.
- **Mottagardomänerna är:** Godkända domäner som är konfigurerade i Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Principer i förinställda säkerhetsprinciper

Förinställda säkerhetsprinciper använder motsvarande principer från de olika skyddsfunktionerna i EOP och Microsoft Defender för Office 365. Dessa principer skapas när _du_ tilldelar **standardskydds- eller** **strikt skyddsförinställda** säkerhetsprinciper till användarna. Du kan inte ändra dessa principer.

- **Principer för Exchange Online Protection (EOP):** Det här omfattar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:

  - [Principer för skydd mot skräppost](configure-your-spam-filter-policies.md) med **standardförvald säkerhetspolicy** **och strikt förinställd säkerhetspolicy.**
  - [Skydd mot skadlig programvara med](configure-anti-malware-policies.md) standard **förvald säkerhetspolicy** **och strikt förinställd säkerhetspolicy.**
  - [EOP-principer för skydd mot nätfiske](set-up-anti-phishing-policies.md#spoof-settings) med standard **förvald** säkerhetsprincip **och strikt förinställd** säkerhetsprincip (förfalskningsinställningar).

- **Principer för Microsoft Defender för Office 365:** Detta omfattar organisationer med Microsoft 365 E5 eller Defender för tilläggsprenumerationer för Office 365:

  - Skydd mot nätfiske i Microsoft Defender för Office 365 med namnet **Standardförvald** säkerhetsprincip och **Strikt förinställd** säkerhetsprincip, som omfattar:

    - Samma [förfalskningsinställningar som](set-up-anti-phishing-policies.md#spoof-settings) finns i EOP-principer för skydd mot nätfiske.
    - [Inställningar för personifiering](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Avancerade tröskelvärden för nätfiske](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Principer för säkra länkar](set-up-atp-safe-links-policies.md) **med standard förvald säkerhetsprincip** **och strikt förinställd säkerhetsprincip.**

  - [Principer för säkra bifogade](set-up-atp-safe-attachments-policies.md) filer **med standard förvald säkerhetsprincip** **och strikt förinställd säkerhetsprincip.**

Observera att du kan använda EOP-skydd för olika användare än Microsoft Defender för Office 365-skydd.

### <a name="policy-settings-in-preset-security-policies"></a>Principinställningar i förinställda säkerhetsprinciper

Du kan inte ändra principinställningarna i skyddsprofilerna. **Standard-** och Strikt-principinställningsvärdena beskrivs i [Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet.](recommended-settings-for-eop-and-office365-atp.md) 

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Prioritetsordningen för förinställda säkerhetsprinciper och andra principer

När flera principer tillämpas på en användare tillämpas följande ordning från högsta prioritet till lägsta prioritet:

1. **Strikt skydd förvald** säkerhetsprincip
2. **Förvald** säkerhetsprincip för standardskydd
3. Anpassade säkerhetsprinciper
4. Standardsäkerhetsprinciper

Inställningarna i principen för  strikt skydd åsidosätter med andra ord inställningarna i **standardskyddsprincipen,** som åsidosätter inställningarna från en anpassad princip som åsidosätter inställningarna från standardprincipen.

## <a name="assign-preset-security-policies-to-users"></a>Tilldela förinställda säkerhetsprinciper till användare

### <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Använd för att gå direkt **till sidan Förinställda** <https://protection.office.com/presetSecurityPolicies> säkerhetsprinciper.

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill konfigurera förinställda säkerhetsprinciper måste du vara medlem i **rollgrupperna Organisationshantering** **eller Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till förinställda säkerhetsprinciper måste du vara medlem i **rollgruppen Global Reader.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Obs!** Om du lägger till användare i motsvarande Azure Active Directory-roll  i administrationscentret för Microsoft 365 får användarna de behörigheter och behörigheter som krävs för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Använd Säkerhets- & säkerhets- och efterlevnadscenter för att tilldela förinställda säkerhetsprinciper till användare

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **Förvalda** \> **säkerhetsprinciper** \> **för hothanteringspolicy.**

2. Under **Standardskydd eller** **Strikt skydd klickar** du på **Redigera**.

3. Guiden **Använd standardskydd** **eller Använd strikt skydd** startas. Om **EOP-skydden gäller för** steg identifierar du de interna mottagare som [EOP-skydd gäller](#policies-in-preset-security-policies) för:

   1. Klicka **på Lägg till ett villkor.** I listrutan som visas väljer du ett villkor under **Används om:**

      - **Mottagarna är**
      - **Mottagarna är medlemmar i**
      - **Mottagardomänerna är**

      Du kan bara använda ett villkor en gång, men du kan ange flera värden för villkoret. Flera värden med samma villkor använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_ ).

   2. Det villkor som du har markerat visas i ett skuggat avsnitt. I det avsnittet klickar du i **rutan Någon av dessa.** Om du väntar en stund visas en lista så att du kan välja ett värde. Du kan också börja skriva ett värde för att filtrera listan och välja ett värde. Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett enskilt värde klickar du **på ta** ![ ](../../media/scc-remove-icon.png) bort-ikonen för värdet. Om du vill ta bort hela villkoret klickar du **på Ta** bort ikon ![ för ](../../media/scc-remove-icon.png) villkoret.

   3. Om du vill lägga till ytterligare ett villkor **klickar du på** Lägg till ett villkor och väljer något av de återstående villkoren. Olika villkor använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).

      Upprepa föregående steg för att lägga till värden i villkoret och upprepa det här steget så många gånger som behövs eller tills villkoren tar slut.

   4. Om du vill lägga till ett undantag klickar du **på Lägg till ett villkor.** I listrutan som visas väljer du ett villkor under **Utom när**. Inställningarna och beteendet är likadana som villkoren.

   Klicka på Nästa när du är **klar.**

4. Om din organisation har Microsoft Defender för Office 365 tas du till **de atp-skydd** som gäller för steg för att identifiera de interna mottagare som Microsoft Defender för [Office 365-skydd](#policies-in-preset-security-policies) gäller för.

   Inställningarna och beteendet är exakt som **EOP-skydden gäller för** steg.

   Klicka på Nästa när du är **klar.**

5. I steget **Bekräfta** kontrollerar du dina val och klickar sedan på **Bekräfta**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Använd Säkerhets- & säkerhets- och efterlevnadscenter för att ändra tilldelningar av förinställda säkerhetsprinciper

Stegen för att ändra tilldelningen av  **säkerhetsprincipen Standard** eller Strikt skydd är desamma som när du först tilldelade de förinställda [säkerhetsprinciperna till användare.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)

Om du vill **inaktivera säkerhetsprinciperna** **Standardskydd** eller Strikt skydd, samtidigt som de befintliga villkoren och undantagen bibehålls, drar du reglaget till **Inaktiverad.** Om du vill aktivera principerna drar du reglaget till **Aktiverad**.

### <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

För att verifiera att du har  tilldelat en användare **säkerhetsprincipen Standardskydd** eller Strikt skydd använder du en skyddsinställning där standardvärdet skiljer sig från **inställningen för Standardskydd,** vilket skiljer sig från inställningen Strikt **skydd.**

För e-post som identifieras som skräppost (med god säkerhet) verifierar du till exempel att meddelandet levereras till mappen Skräppost för användare med **standardskydd** och sätts i karantän för strict **protection** users.

För massutskick kontrollerar du att BCL-värdet 6 eller senare levererar meddelandet till mappen Skräppost för användare med **standardskydd** och  BCL-värdet 4 eller högre karantäner meddelandet för strikt skyddsanvändare. [](bulk-complaint-level-values.md)