---
title: Förinställda säkerhetsprinciper
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
description: Administratörer kan lära sig hur du använder standard- och strikta principinställningar för skyddsfunktionerna i Exchange Online Protection (EOP) och Office 365 Advanced Threat Protection (ATP)
ms.openlocfilehash: 34445c617d2dda59a65b197db2f42324d0085ab3
ms.sourcegitcommit: 688d62a8c52e4fb0feb721bb92b535effc278f54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2020
ms.locfileid: "45389882"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a>Förinställda säkerhetsprinciper i EOP och Office 365 ATP

Förinställda säkerhetsprinciper ger en centraliserad plats för att tillämpa alla rekommenderade principer för skräppost, skadlig kod och nätfiske på användare samtidigt. Principinställningarna kan inte konfigureras. Istället är de som av oss och bygger på våra observationer och erfarenheter i datacenter för en balans mellan att hålla skadligt innehåll borta från användare utan att störa deras arbete.

I resten av det här avsnittet beskrivs förinställda säkerhetsprinciper och hur du konfigurerar dem.

## <a name="what-preset-security-policies-are-made-of"></a>Vilka förinställda säkerhetsprinciper som görs av

Förinställda säkerhetsprinciper består av följande element:

- Profiler
- Politik
- Principinställningar

Dessutom är prioritetsordningen viktig om flera förinställda säkerhetsprinciper och andra principer gäller för samma person.

### <a name="profiles-in-preset-security-policies"></a>Profiler i förinställda säkerhetsprinciper

En profil bestämmer skyddsnivån. Följande profiler är tillgängliga:

- **Standardskydd**: En baslinjeskyddsprofil som är lämplig för de flesta användare.
- **Strikt skydd**: En mer aggressiv skyddsprofil för utvalda användare (högt värdemål eller prioriterade användare).

Du använder regler med villkor och undantag som avgör vilka profilerna är eller inte tillämpas på.

Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

De tillgängliga villkoren och undantagen är:

- **Mottagarna är**: Postlådor, e-postanvändare eller e-postkontakter i organisationen.
- **Mottagarna är medlemmar**i : Grupper i organisationen.
- **Mottagarnatrdomäner är**: Godkända domäner som är konfigurerade i Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Principer i förinställda säkerhetsprinciper

Förinställda säkerhetsprinciper använder motsvarande principer från de olika skyddsfunktionerna i EOP och Office 365 ATP. Dessa principer skapas _när_ du har tilldelat **standardskydd** eller förinställda säkerhetsprinciper **för strikt skydd** till användare. Du kan inte ändra dessa principer.

- **EOP-principer (Exchange Online Protection):** Detta inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:
  
  - [Anti-spam-principer](configure-your-spam-filter-policies.md) med namnet **Standard förinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip**.
  - [Principer mot skadlig kod](configure-anti-malware-policies.md) med namnet **Standardförinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip**.
  - [EOP:s principer för phishing-phishing](set-up-anti-phishing-policies.md#spoof-settings) med namnet **Standardförinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip** (falska inställningar).

- **Office 365 Advanced Threat Protection (ATP)-principer**: Detta inkluderar organisationer med Microsoft 365 E5- eller Office 365 ATP-tilläggsprenumerationer:

  - ATP-principer för nätfiske med namnet **Standard förinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip**, som omfattar:

    - Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP:s policyer för nätfiske.
    - [Inställningar för personifiering](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [Avancerade tröskelvärden för nätfiske](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [Principer för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) med namnet **Standardförinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip**.

  - [Principer för säkra bifogade filer](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) med namnet **Standardförinställd säkerhetsprincip** och **strikt förinställd säkerhetsprincip**.

Observera att du kan använda EOP-skydd för andra användare än ATP-skydd.

### <a name="policy-settings-in-preset-security-policies"></a>Principinställningar i förinställda säkerhetsprinciper

Du kan inte ändra principinställningarna i skyddsprofilerna. Principinställningsvärdena **Standard** och **Strikt** beskrivs i [Rekommenderade inställningar för EOP- och Office 365 ATP-säkerhet](recommended-settings-for-eop-and-office365-atp.md).

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Prioritetsordning för förinställda säkerhetsprinciper och andra principer

När flera principer tillämpas på en användare tillämpas följande ordning från högsta prioritet till lägsta prioritet:

1. **Strikt säkerhetsprincip** för skydd
2. Förinställd säkerhetsprincip för **standardskydd**
3. Alla andra relaterade policyer.

Med andra ord åsidosätter inställningarna i principen **Strikt skydd** inställningarna för **standardskyddsprincipen,** som åsidosätter inställningarna från andra relaterade principer.

## <a name="assign-preset-security-policies-to-users"></a>Tilldela förinställda säkerhetsprinciper till användare

### <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **Förinställda säkerhetsprinciper** använder du <https://protection.office.com/presetSecurityPolicies> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:

  - Om du vill konfigurera förinställda säkerhetsprinciper måste du vara medlem i någon av följande rollgrupper:

    - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - För skrivskyddad åtkomst till förinställda säkerhetsprinciper måste du vara medlem i någon av följande rollgrupper:

    - **Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
    - **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Använda Säkerhets- & Compliance Center för att tilldela förinställda säkerhetsprinciper till användare

1. Gå till **Threat management** \> **Policy** \> **säkerhetsprinciper för principförinställda säkerhetsprinciper i säkerhetsprinciper**för & säkerhetsprinciper för & efterlevnad.

2. Klicka på **Redigera**under **Standardskydd** eller **Strikt skydd**.

3. Guiden **Använd standardskydd** eller **Använd strikt skydd** startar. När det gäller **EOP-skydd för** steg, identifiera de interna mottagare som [EOP-skydd](#policies-in-preset-security-policies) gäller för

   1. Klicka på **Lägg till ett villkor**. I listrutan som visas väljer du ett villkor under **Tillämpad om:**

      - **Mottagarna är**
      - **Mottagarna är medlemmar i**
      - **De mottagande domänerna är**

      Du kan bara använda ett villkor en gång, men du kan ange flera värden för villkoret. Flera värden med samma villkor använder ELLER-logik (till exempel _\<recipient1\>_ _\<recipient2\>_ eller ).

   2. Villkoret som du valde visas i ett skuggat avsnitt. Klicka i rutan **Någon av dessa** i det avsnittet. Om du väntar ett ögonblick visas en lista så att du kan välja ett värde. Du kan också börja skriva ett värde för att filtrera listan och välja ett värde. Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett enskilt värde klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) värdet. Om du vill ta bort hela villkoret klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) villkoret.

   3. Om du vill lägga till ett annat villkor klickar du på **Lägg till ett villkor** och väljer från de återstående villkoren. Olika villkor använder OCH logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).

      Upprepa föregående steg för att lägga till värden i villkoret och upprepa det här steget så många gånger som det behövs eller tills villkoren har tagit.

   4. Om du vill lägga till ett undantag klickar du på **Lägg till ett villkor**. I listrutan som visas väljer du ett villkor under **Förutom när**. Inställningarna och beteendet är likadana som villkoren.

   När du är klar klickar du på **Nästa**.

4. Om din organisation har Office 365 ATP tas du till **ATP-skydden för** att gå för att identifiera de interna mottagare som [Office 365 ATP-skydd](#policies-in-preset-security-policies) gäller för.

   Inställningarna och beteendet är precis som **eop-skydden gäller för** steg.

   När du är klar klickar du på **Nästa**.

5. Kontrollera dina val i steget **Bekräfta** och klicka sedan på **Bekräfta**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Använd Säkerhets- & Compliance Center för att ändra tilldelningarna av förinställda säkerhetsprinciper

Stegen för att ändra tilldelningen av **säkerhetsprincipen Standardskydd** eller **Strikt skydd** är desamma som när du först [tilldelade användarna de förinställda säkerhetsprinciperna](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).

Om du vill inaktivera säkerhetsprinciperna **för standardskydd** eller **strikt skydd** samtidigt som de befintliga villkoren och undantagen bevaras, drar du växlingsknappen till **Inaktiverad**. Om du vill aktivera principerna drar du växlingsknappen till **Aktiverad**.

### <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Om du vill kontrollera att du har tilldelat en användare **standardskydds-** eller strikt skyddssäkerhetsprincip använder du en skyddsinställning där standardvärdet skiljer sig från **standardskyddsinställningen,** vilket är annorlunda än inställningen **Strikt skydd.** **Strict protection**

Till exempel, för e-post som upptäcks som skräppost (inte hög förtroende spam) kontrollera att meddelandet levereras till skräppostmappen för **standardskydd** användare, och karantän för **strikt skydd** användare.

Eller, för [massmeddelande](bulk-complaint-level-values.md), kontrollera att BCL-värdet 6 eller högre levererar meddelandet till mappen Skräppost för **standardskyddsanvändare** och BCL-värdet 4 eller högre i karantän meddelandet för **användare av strikt skydd.**
