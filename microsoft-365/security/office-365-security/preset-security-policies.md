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
description: Administratörer kan läsa om hur standard- och strikt-principinställningarna används i alla skyddsfunktioner i Exchange Online Protection (EOP) och Microsoft Defender för Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e41edb6c2d77a69ee3d4fa28ff86e0e77410caa5
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108301"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Förinställda säkerhetsprinciper i EOP och Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Förinställda säkerhetsprinciper tillhandahåller en central plats där användarna kan använda alla rekommenderade principer för skräppost, skadlig programvara och nätfiske på en gång. Principinställningarna kan inte konfigureras. De ställs i stället in av oss och baseras på våra observationer i datacenter för en balans mellan att hålla skadligt innehåll borta från användare och undvika onödiga störningar.

I resten av den här artikeln beskrivs förinställda säkerhetsprinciper och hur du konfigurerar dem.

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

Tillgängliga villkor och undantag är:

- **Användare**: De angivna postlådorna, e-postanvändarna eller e-postkontakterna i organisationen.
- **Grupper**: De angivna distributionsgrupper, e-postaktiverade säkerhetsgrupper eller Microsoft 365-grupper i organisationen.
- **Domäner**: Alla mottagare i den angivna [godkända domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i organisationen.

Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

### <a name="policies-in-preset-security-policies"></a>Principer i förinställda säkerhetsprinciper

Förinställda säkerhetsprinciper använder motsvarande principer från de olika skyddsfunktionerna i EOP och Microsoft Defender för Office 365. Dessa principer skapas när _du_ tilldelar **standardskydds- eller** **strikt skyddsförinställda** säkerhetsprinciper till användarna. Du kan inte ändra dessa principer.

- **Exchange Online Protection (EOP):** Det här omfattar Microsoft 365 organisationer med Exchange Online e-postlådor och fristående EOP-organisationer utan Exchange Online postlådor:

  - [Principer för skydd mot skräppost](configure-your-spam-filter-policies.md) med **standardförvald säkerhetspolicy** **och strikt förinställd säkerhetspolicy.**
  - [Skydd mot skadlig programvara med](configure-anti-malware-policies.md) standard **förvald säkerhetspolicy** **och strikt förinställd säkerhetspolicy.**
  - [EOP-principer för skydd mot nätfiske](set-up-anti-phishing-policies.md#spoof-settings) med standard **förvald** säkerhetsprincip **och strikt förinställd** säkerhetsprincip (förfalskningsinställningar).

- **Microsoft Defender Office 365 principer:** Detta omfattar organisationer med Microsoft 365 E5 eller Defender för Office 365 tilläggsprenumerationer:

  - Principer för skydd mot nätfiske i Microsoft Defender Office 365 som **heter Standardförvald** säkerhetsprincip **och Strikt förinställd** säkerhetsprincip, som omfattar:

    - Samma [förfalskningsinställningar som](set-up-anti-phishing-policies.md#spoof-settings) finns i EOP-principer för skydd mot nätfiske.
    - [Inställningar för personifiering](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Avancerade tröskelvärden för nätfiske](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Valv som heter](set-up-safe-links-policies.md) **Standardförvald säkerhetsprincip** **och Strikt förinställd säkerhetsprincip.**

  - [Valv principer för bifogade filer](set-up-safe-attachments-policies.md) med standard **förvald** **säkerhetsprincip och strikt förinställd säkerhetsprincip.**

Observera att du kan använda EOP-skydd för olika användare än Microsoft Defender för Office 365 skydd.

### <a name="policy-settings-in-preset-security-policies"></a>Principinställningar i förinställda säkerhetsprinciper

Du kan inte ändra principinställningarna i skyddsprofilerna. Standard- och **Strikt-principinställningsvärdena** beskrivs [i Rekommenderade inställningar för EOP och Microsoft Defender för Office 365 säkerhet.](recommended-settings-for-eop-and-office365.md) 

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Prioritetsordningen för förinställda säkerhetsprinciper och andra principer

När flera principer tillämpas på en användare tillämpas följande ordning från högsta prioritet till lägsta prioritet:

1. **Strikt skydd förvald** säkerhetsprincip
2. **Förvald** säkerhetsprincip för standardskydd
3. Anpassade säkerhetsprinciper
4. Standardsäkerhetsprinciper

Inställningarna i principen för  strikt skydd åsidosätter med andra ord inställningarna i **standardskyddsprincipen,** som åsidosätter inställningarna från en anpassad princip som åsidosätter inställningarna från standardprincipen.

## <a name="assign-preset-security-policies-to-users"></a>Tilldela förinställda säkerhetsprinciper till användare

### <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>. Använd för att gå direkt **till sidan Förinställda** <https://security.microsoft.com/presetSecurityPolicies> säkerhetsprinciper.

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill konfigurera förinställda säkerhetsprinciper måste du vara medlem i **rollgrupperna Organisationshantering** **eller Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till förinställda säkerhetsprinciper måste du vara medlem i **rollgruppen Global Reader.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Obs!** Om du lägger till användare Azure Active Directory motsvarande roll i Administrationscenter för Microsoft 365  får användarna nödvändiga behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a>Använd Microsoft 365 Defender-portalen för att tilldela förinställda säkerhetsprinciper till användare

1. I Microsoft 365 Defender-portalen går du till avsnittet **Förinställda** säkerhetsprinciper & e-& principer för säkerhetsprinciper för regler och \>  \>  \>  \> **hot.**

2. Under **Standardskydd eller** **Strikt skydd klickar** du på **Redigera**.

3. Guiden **Använd standardskydd** **eller Använd strikt skydd** startas. På sidan **EOP-skydd gäller för** identifierar du de interna mottagare som [EOP-skydd gäller](#policies-in-preset-security-policies) för (mottagarvillkor):
   - **Användare**
   - **Grupper**
   - **Domäner**

   Klicka i lämplig ruta, börja skriva in ett värde och välj det värde du vill använda i resultatet. Upprepa det här steget så många gånger som det behövs. Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

   För användare eller grupper kan du använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn osv.), men motsvarande visningsnamn visas i resultatet. Om du vill visa alla tillgängliga värden för användare anger du en asterisk (\*) för sig själv.

   - **Uteslut dessa användare, grupper** och domäner: Om du vill lägga till undantag för de interna mottagare som principen gäller för (mottagarundantag), väljer du det här alternativet och konfigurerar undantagen. Inställningarna och beteendet är likadana som villkoren.

   Klicka på **Nästa** när du är klar.

4. I Microsoft Defender för Office 365-organisationer tas du till sidan med Defender för **Office 365-skydd** för att identifiera de interna mottagare som [Microsoft Defender för Office 365-skydd](#policies-in-preset-security-policies) gäller för (mottagarvillkor).

   Inställningarna och beteendet är exakt som **EOP-skydden gäller för** sidan.

   Klicka på **Nästa** när du är klar.

5. På sidan **Granska och bekräfta ändringarna** verifierar du dina val och klickar sedan på **Bekräfta**.

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a>Använd Microsoft 365 Defender-portalen för att ändra tilldelningar av förinställda säkerhetsprinciper

Stegen för att ändra tilldelningen av  **säkerhetsprincipen Standard** eller Strikt skydd är desamma som när du först tilldelade de förinställda [säkerhetsprinciperna till användare.](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users)

Om du vill  **inaktivera säkerhetsprinciperna Standardskydd** eller Strikt skydd samtidigt som de befintliga villkoren och undantagen bibehålls drar du reglaget **till Inaktiverad** ![ ](../../media/scc-toggle-off.png) av. Du aktiverar principerna genom att dra reglaget till **Aktiverad** ![ växlingsknapp På ](../../media/scc-toggle-on.png) .

### <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

För att verifiera att du har  tilldelat en användare **säkerhetsprincipen Standardskydd** eller Strikt skydd använder du en skyddsinställning där standardvärdet skiljer sig från **inställningen för Standardskydd,** vilket skiljer sig från inställningen Strikt **skydd.**

För e-post som identifieras som skräppost (med god säkerhet) verifierar du till exempel att meddelandet levereras till mappen Skräppost för användare med **standardskydd** och sätts i karantän för strict **protection** users.

För massutskick kontrollerar du att BCL-värdet 6 eller senare levererar meddelandet till mappen Skräppost för användare med **standardskydd** och  BCL-värdet 4 eller högre karantäner meddelandet för strikt skyddsanvändare. [](bulk-complaint-level-values.md)
