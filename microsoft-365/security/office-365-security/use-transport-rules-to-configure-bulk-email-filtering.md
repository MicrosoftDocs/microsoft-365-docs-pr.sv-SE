---
title: Använda regler för e-postflöde för att filtrera massutskick
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du använder regler för e-postflöde (transportregler) för att identifiera och filtrera massutskick (grå e-post) i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 860c9a1af2cb560c4fd966b303501686a1cbfea7
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613318"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Använda e-postflödesregler för att filtrera massutskick i EOP

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor använder EOP policyer mot skräppost (kallas även principer för skräppostfilter eller innehållsfilter) för att söka igenom inkommande meddelanden efter skräppost och massutskick (kallas även grå e-post). Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

Om du vill att fler alternativ ska filtrera massutskick kan du skapa regler för e-postflöde (kallas även transportregler) för att söka efter textmönster eller fraser som ofta finns i massutskick och markera dessa meddelanden som skräppost. Mer information om massutskick finns i Vad är skillnaden mellan [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md)skräppost [och massmeddelande?](what-s-the-difference-between-junk-email-and-bulk-email.md)

I det här avsnittet beskrivs hur du skapar dessa regler för e-postflöde i Administrationscenter för Exchange (EAC) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste tilldelas behörigheter innan du kan göra följande:

  - I Exchange Online läser du posten "E-postflöde" i [Funktionsbehörigheter i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).
  
  - I fristående EOP behöver du rollen Transportregler, som tilldelas rollerna OrganizationManagement, ComplianceManagement och RecordsManagement som standard. Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om hur du öppnar EAC i Exchange Online finns [i Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Om du vill öppna EAC i fristående EOP finns [i Exchange admin center i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Mer information om regler för e-postflöde i Exchange Online och fristående EOP finns i följande avsnitt:

  - [Regler för e-postflöde (transportregler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Villkor och undantag för e-postflödesregel (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Regelåtgärder för e-postflöde i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- Listan över ord och textmönster som används för att identifiera massutskick i exemplen är inte uttömmande. Du kan lägga till och ta bort poster efter behov. Men de är en bra utgångspunkt.

- Sökningen efter ord eller textmönster i ämnet eller andra rubrikfält i meddelandet sker *efter* att meddelandet har avkodats från MIME-innehållsöverföringskodningsmetoden som användes för att överföra det binära meddelandet mellan SMTP-servrar i ASCII-text. Du kan inte använda villkor eller undantag för att söka efter de råa (vanligtvis Base64) kodade värdena för ämnet eller andra rubrikfält i meddelanden.

- Följande procedurer markerar ett massmeddelande som skräppost för hela organisationen. Du kan dock lägga till ett annat villkor för att tillämpa dessa regler endast för specifika mottagare, så att du kan använda aggressiv filtrering på ett fåtal, mycket riktade användare, medan resten av användarna (som oftast får den mass-e-post de registrerat sig för) inte påverkas.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Använd EAC för att skapa regler för e-postflöde som filtrerar massutskick av e-post

1. Gå till Regler för **e-postflöde** i EAC \> **Rules**.

2. Klicka på **Ikonen Lägg till** och välj sedan Skapa en ny ![ ](../../media/ITPro-EAC-AddIcon.png) **regel**.

3. Konfigurera följande inställningar på sidan **Ny regel** som öppnas:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln.

   - Klicka på **Fler alternativ**.

   - **Använd den här regeln om:** Konfigurera någon av följande inställningar för att söka efter innehåll i meddelanden med reguljära uttryck (RegEx) eller ord eller fraser:

     - **Ämnet eller kroppen** \> **ämne eller brödtext matchar dessa textmönster**: Ange **ord eller fraser** som visas, ange ett av följande värden, klicka på Lägg **till** ikonen och upprepa ![ ](../../media/ITPro-EAC-AddIcon.png) tills du har angett alla värden.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      Om du vill redigera en post markerar du den och klickar på **Ikonen Redigera** ![ redigering ](../../media/ITPro-EAC-EditIcon.png) . Om du vill ta bort en post markerar du den och klickar på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-DeleteIcon.png) .

       När du är klar klickar du på **OK**.

     - **Ämnet eller kroppen** \> **ämne eller brödtext innehåller något av dessa ord**: Ange ord eller **fraser** som visas anger du ett av följande värden, klickar på **Lägg till** ![ ikon och upprepar ](../../media/ITPro-EAC-AddIcon.png) tills du har angett alla värden.

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

      Om du vill redigera en post markerar du den och klickar på **Ikonen Redigera** ![ redigering ](../../media/ITPro-EAC-EditIcon.png) . Om du vill ta bort en post markerar du den och klickar på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-DeleteIcon.png) .

       När du är klar klickar du på **OK**.

   - **Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **ange scl (Spam Confidence Level)**. Konfigurera någon av följande inställningar i dialogrutan **Ange SCL:**

     - Om du vill markera meddelanden som **skräppost**väljer du **6**. Åtgärden som du har konfigurerat för skräppostfiltreringsutslag i dina anti-spam-principer tillämpas på meddelandena (standardvärdet är **Flytta meddelande till mappen Skräppost**). **Spam**

     - Om du vill markera meddelanden som **skräppost med högt förtroende** väljer du **9**. Åtgärden som du har konfigurerat för skräppostfiltreringsdomar med **högt förtroende** i dina anti-spam-principer tillämpas på meddelandena (standardvärdet är **Flytta meddelande till mappen Skräppost**).

    Mer information om SCL-värden finns i [SCL (Spam Confidence Level) i EOP](spam-confidence-levels.md).

   När du är klar klickar du på **Spara**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Använda PowerShell för att skapa regler för e-postflöde som filtrerar massutskick av e-post

Använd följande syntax för att skapa en eller båda av reglerna för e-postflöde (reguljära uttryck kontra ord):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

I det här exemplet skapas en ny regel med namnet "Massfiltrering av e-post - RegEx" som använder samma lista med reguljära uttryck från tidigare i avsnittet för att ange meddelanden som **skräppost**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

Det här exemplet skapar en ny regel med namnet "Mass-e-filtrering - Ord" som använder samma lista med ord från tidigare i avsnittet för att ange meddelanden som **skräppost med högt förtroende**.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Så här kontrollerar du att du har konfigurerat regler för e-postflöde för att filtrera massutskick av e-post:

- Gå till **EAC-regler** för att skicka till \> **E-postflödesregler** \> och markera regeln klicka på \> **Redigera** ![ redigera ikon och kontrollera ](../../media/ITPro-EAC-EditIcon.png) inställningarna.

- Ersätt med namnet på regeln i PowerShell \<Rule Name\> och kör följande kommando för att verifiera inställningarna:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Från ett externt konto skickar du ett testmeddelanden till en berörd mottagare som innehåller en av fraserna eller textmönstren och verifierar resultaten.
