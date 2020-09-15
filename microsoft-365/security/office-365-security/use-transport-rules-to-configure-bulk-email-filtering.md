---
title: Filtrera Mass utskick via e-post
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de använder regler för e-postflöde (transport regler) för att identifiera och filtrera Mass utskick (grå e-post) i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 62db73ea917139d81a29569d5b452637fd053c92
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775201"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Använda e-postflödesregler för att filtrera massutskick i EOP

I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor används principer för skräp post filtrering (kallas även för skräp post filter principer eller innehålls filter principer) för att söka igenom inkommande meddelanden för spam och Mass utskick (kallas även gråskala). Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

Om du vill ha fler alternativ för att filtrera Mass utskick kan du skapa regler för e-postflöde (kallas även transport regler) för att söka efter text mönster eller fraser som ofta hittas i Mass utskick och markera dessa meddelanden som skräp post. Mer information om Mass utskick finns i [Vad är skillnaden mellan skräp post och Mass utskick?](what-s-the-difference-between-junk-email-and-bulk-email.md) och bulk- [nivå (BCL) i EOP](bulk-complaint-level-values.md).

I det här avsnittet förklaras hur du skapar dessa regler för e-post i administrations centret för Exchange (UK) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste tilldelas behörigheter innan du kan göra följande:

  - I Exchange Online kan du läsa "mail flöde"-posten i [funktioner i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).
  
  - I fristående EOP behöver du Transport regel rollen som är tilldelad till rollerna i, ComplianceManagement och RecordsManagement som standard. Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Om du vill öppna UK i Exchange Online läser du [administrations Center för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Information om hur du öppnar UK i fristående EOP finns i [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Mer information om regler för e-postflöden i Exchange Online och fristående EOP finns i följande avsnitt:

  - [Regler för e-postflöde (transport regler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Villkor och undantag för e-postflödes regel (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Åtgärder för e-postflödes regler i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- Listan med ord och text mönster som används för att identifiera Mass utskick i de här exemplen är inte uttömmande; Du kan lägga till och ta bort poster vid behov. Men de är en bra start punkt.

- Sök efter ord eller text mönster i ämnes raden ämne eller andra rubrik fält i meddelandet inträffar *när* meddelandet har avkodats från den kodnings metod för MIME-innehålls överföring som användes för att överföra det binära meddelandet mellan SMTP-servrar i ASCII-text. Du kan inte använda villkor eller undantag för att söka efter råa (vanligt vis base64) kodade värden för ämne eller andra huvud fält i meddelanden.

- Här beskrivs ett Mass meddelande som skräp post för hela organisationen. Du kan emellertid bara lägga till ett annat villkor för att tillämpa dessa regler på specifika mottagare, så att du kan använda aggressiv filtrering på några få, ytterst riktade användare, medan resten av dina användare (som mest får det Mass utskick som de har registrerat sig för) inte påverkas.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Använd UK för att skapa regler för e-postflöde som filtrerar Mass utskick

1. Gå till regler för **e-postflöde** i UK \> **Rules**.

2. Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och välj sedan **skapa en ny regel**.

3. På sidan **ny regel** som öppnas konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln.

   - Klicka på **fler alternativ**.

   - **Använd den här regeln om**: Konfigurera en av följande inställningar för att söka efter innehåll i meddelanden med hjälp av reguljära uttryck (regex) eller ord eller fraser:

     - **Ämne eller brödtext** \> **ämne eller brödtext matchar dessa text mönster**: ange något av följande värden i dialog rutan **Ange ord eller fraser** , klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och upprepa tills du har angett alla värden.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      Om du vill redigera en post markerar du den och klickar på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) . För att ta bort en post markerar du den och klickar på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-DeleteIcon.png) .

       När du är klar klickar du på **OK**.

     - **Ämne eller brödtext** \> **ämne eller brödtext inkluderar något av**följande: i dialog rutan **Ange ord eller fraser** som visas anger du ett av nedanstående värden, klickar på **Lägg** till ![ Lägg till ikonen ](../../media/ITPro-EAC-AddIcon.png) och upprepar tills du har angett alla värden.

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      Om du vill redigera en post markerar du den och klickar på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) . För att ta bort en post markerar du den och klickar på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-DeleteIcon.png) .

       När du är klar klickar du på **OK**.

   - **Gör följande**: Välj **ändra meddelande egenskaper** \> **ange nivån för skräp post (SCL)**. I dialog rutan **Ange SCL** som visas konfigurerar du en av följande inställningar:

     - Om du vill markera meddelanden som **skräp post**väljer du **6**. Den åtgärd som du har konfigurerat för **skräp post** filtrering verdicts i policyn för skräp post hantering tillämpas på meddelandena (standardvärdet **flyttas till mappen skräp post**).

     - Om du vill markera meddelanden som **skräp post** väljer du **9**. Den åtgärd som du har konfigurerat för filtrering av skräp post med **hög exakthet** verdicts i dina meddelanden (standardvärdet **flyttas till mappen skräp post**).

    Mer information om SCL-värden finns i [säkerhet för skräp post (SCL) i EOP](spam-confidence-levels.md).

   När du är klar klickar du på **Spara**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Använda PowerShell för att skapa e-postflödes regler som filtrerar Mass utskick

Använd följande syntax för att skapa en eller båda regler för e-postflöden (vanliga uttryck jämfört med ord):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

I det här exemplet skapas en ny regel med namnet "Mass utskick av e-post-RegEx" som använder samma lista med vanliga uttryck från tidigare i avsnittet för att ange meddelanden som **skräp post**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

I det här exemplet skapas en ny regel med namnet "Mass utskick av e-post" som använder samma lista med ord från tidigare i avsnittet för att ange meddelanden som **skräp post**.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Gör något av följande om du vill kontrol lera att du har konfigurerat regler för e-postflöde för filtrering av Mass utskick:

- Gå till regler för **e-postflöde** i UK och \> **Rules** \> Välj regeln \> Klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) och kontrol lera inställningarna.

- Ersätt \<Rule Name\> med regel namnet i PowerShell och kör följande kommando för att verifiera inställningarna:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Från ett externt konto kan du skicka ett test meddelande till en mottagare som innehåller en av fraserna eller text mönstren och bekräfta resultaten.
