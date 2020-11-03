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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att använda standard-och strikta princip inställningar i skydds funktionerna i Exchange Online Protection (EOP) och Microsoft Defender för Office 365
ms.openlocfilehash: 38a03727f91878f356d8bc0dc618c711bfc500bb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845738"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Förvalda säkerhets principer i EOP och Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Förvalda säkerhets principer är en central plats för att tillämpa alla rekommenderade spam-, malware-och phishing-principer för användare samtidigt. Princip inställningarna kan inte konfigureras. I stället ställs de in av oss och baseras på våra observationer och erfarenheter i data centret för en avvägning mellan att hålla skadligt innehåll från användare utan att störa deras arbete.

Resten av det här avsnittet beskriver förvalda säkerhets principer och hur du konfigurerar dem.

## <a name="what-preset-security-policies-are-made-of"></a>Vilka säkerhets principer som är gjorda för

Förvalda säkerhets principer består av följande element:

- Principer
- Principerna
- Princip inställningar

Prioritetsordning är dessutom viktigt om flera förvalda säkerhets principer och andra principer gäller för samma person.

### <a name="profiles-in-preset-security-policies"></a>Profiler i förvalda säkerhets principer

En profil bestämmer skydds nivån. Följande profiler är tillgängliga:

- **Standard skydd** : en grundläggande skydds profil som passar de flesta användare.
- **Strikt skydd** : en mer aggressiv skydds profil för utvalda användare (högsta värde mål eller prioriterade användare).

Du använder regler med villkor och undantag som avgör vem profilen är eller inte är kopplad till.

Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_ ). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).

De tillgängliga villkoren och undantagen är:

- **Mottagarna är** : post lådor, e-postanvändare eller e-postkontakter i din organisation.
- **Mottagarna är medlemmar i** : grupper i din organisation.
- **Mottagar domäner är** : godkända domäner som är konfigurerade i Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Principer i förvalda säkerhets principer

Förvalda säkerhets principer Använd motsvarande principer i de olika skydds funktionerna i EOP och Microsoft Defender för Office 365. Dessa principer skapas _efter_ att du har tilldelat **standard** säkerhets principer för förvalda skydd eller **strikta skydd** för användare. Du kan inte ändra dessa principer.

- **Principer för Exchange Online Protection (EOP)** : det inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:
  
  - [Principer för skräp post](configure-your-spam-filter-policies.md) som heter **Standard säkerhets princip** och **strikt förinställd säkerhets policy**.
  - [Principer mot skadlig program vara](configure-anti-malware-policies.md) med namnet **Standard säkerhets princip** och **strikt förinställd säkerhets policy**.
  - [EOP anti-nätfiske-principer](set-up-anti-phishing-policies.md#spoof-settings) som heter **Standard säkerhets princip** och **strikt förinställd säkerhets princip** (Spoof-inställningar).

- **Microsoft Defender för Office 365-principer** : Detta inkluderar organisationer med Microsoft 365 E5-eller Defender för Office 365-tilläggs prenumerationer:

  - Anti-nätfiske-principer i Microsoft Defender för Office 365 heter **standarden för förvalda säkerhets principer** och **strikta förvalda säkerhets principer** , som omfattar:

    - Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP anti-phishing-principer.
    - [Inställningar för personifiering](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Avancerade nät fiske trösklar](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Principer för säkra länkar](set-up-atp-safe-links-policies.md) som heter **Standard säkerhets princip** och **strikt förinställd säkerhets policy**.

  - [Principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md) med **standard** säkerhets princip och **strikt förinställd säkerhets policy**.

Observera att du kan använda EOP skydd för olika användare än Microsoft Defender för Office 365-skydd.

### <a name="policy-settings-in-preset-security-policies"></a>Princip inställningar i förvalda säkerhets principer

Du kan inte ändra princip inställningarna i skydds profilerna. Värdena för **standard** -och **strict** -princip beskrivs i [rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md).

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Prioritetsordning för förvalda säkerhets principer och andra principer

När flera principer tillämpas på en användare tillämpas följande ordning från högsta prioritet till lägsta prioritet:

1. **Strikt skydd** för förvalda säkerhets principer
2. **Standard** säkerhets princip för förinställd skydd
3. Anpassade säkerhets principer
4. Standard säkerhets principer

Med andra ord åsidosätter inställningarna för principen för **strikt skydd** standardinställningarna för **skydds** princip, som åsidosätter inställningarna från en anpassad princip som åsidosätter inställningarna från standard principen.

## <a name="assign-preset-security-policies-to-users"></a>Tilldela användare förvalda säkerhets principer

### <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. För att gå direkt till sidan för **förvalda säkerhets principer** , Använd <https://protection.office.com/presetSecurityPolicies> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:

  - Om du vill konfigurera förvalda säkerhets principer måste du vara medlem i någon av följande roll grupper:

    - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Om du vill ha skrivskyddad åtkomst till förvalda säkerhets principer måste du vara medlem i någon av följande roll grupper:

    - **Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
    - **Global läsare** i [säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Använd säkerhets & Compliance Center för att tilldela förvalda säkerhets principer till användare

1. Gå till säkerhets principer för principer för **hot Management** policy i säkerhets & efterlevnad \> **Policy** \> **Preset security policies**.

2. Under **standard skydd** eller **strikt skydd** klickar du på **Redigera**.

3. Guiden **Använd standard skydd** eller **Använd strikt skydd** startas. På **EOP skydd gäller för** steg hur du identifierar de interna mottagarna som [EOP skydd](#policies-in-preset-security-policies) gäller för:

   1. Klicka på **Lägg till ett villkor**. I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om** :

      - **Mottagarna**
      - **Mottagarna är medlemmar i**
      - **Mottagar domänerna**

      Du kan bara använda ett villkor en gång, men du kan ange flera värden för villkoret. Flera värden med samma villkor används eller logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_ ).

   2. Det villkor som du valde visas i ett skuggat avsnitt. Klicka i **någon av** rutorna i det avsnittet. Om du väntar ett tag visas en lista så att du kan välja ett värde. Eller så kan du börja skriva ett värde för att filtrera listan och välja ett värde. Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett enskilt värde klickar du på **ta bort** - ![ ikonen ](../../media/scc-remove-icon.png) för värdet. Om du vill ta bort hela villkoret klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .

   3. Om du vill lägga till ytterligare villkor klickar du på **Lägg till ett villkor** och väljer bland de återstående villkoren. Olika villkor används och logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).

      Upprepa föregående steg för att lägga till värden i villkoret och upprepa det här steget så många gånger som behövs eller tills du får slut på villkoren.

   4. Om du vill lägga till ett undantag klickar du på **Lägg till ett villkor**. I den nedrullningsbara List rutan som visas väljer du ett villkor under **utom när**. Inställningarna och beteendet är likadana som villkoren.

   När du är klar klickar du på **Nästa**.

4. Om din organisation har Microsoft Defender för Office 365 kommer du **till steget för att identifiera** de interna mottagare som [Microsoft defender för Office 365-skydd](#policies-in-preset-security-policies) gäller för.

   Inställningarna och beteendet är exakt likadant som **EOP skydd gäller för** steg.

   När du är klar klickar du på **Nästa**.

5. I **bekräftelse** steget verifierar du dina val och klickar sedan på **Bekräfta**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Använd säkerhets & Compliance Center för att ändra tilldelningarna för förvalda säkerhets principer

Åtgärderna för att ändra tilldelningen av standard säkerhets principer för **skydd** eller **strikta skydd** är desamma som när du ursprungligen [tilldelade de förvalda säkerhets principerna till användarna](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).

Om du vill inaktivera **standard skydds** -eller **strikta** säkerhets principer och samtidigt behålla de befintliga villkoren och undantagen drar du reglaget till **inaktive rad**. Aktivera principer genom att dra reglaget till **aktiverat**.

### <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Om du vill kontrol lera att du har tilldelat **standard** säkerhets principen för skydd eller **strikt skydd** till en användare använder du en skydds inställning där standardvärdet skiljer sig från standardinställningen för **standard skydd** , som är den **strikta** inställningen för begränsning.

Till exempel, för e-postmeddelanden som identifieras som skräp post (inte med hög exakthet) kontrollerar du att meddelandet levereras till mappen skräp post för **standard skydds** användare och karantän för **strikta skydds** användare.

Om du har ett [Mass utskick av e-post](bulk-complaint-level-values.md)kan du kontrol lera att BCL värde 6 eller högre skickar meddelandet till mappen skräp post för **standard skydds** användare, och BCL värde 4 eller högre gör att meddelandet för **strikta skydds** användare.
