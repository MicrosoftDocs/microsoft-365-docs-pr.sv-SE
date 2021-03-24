---
title: Använda e-postflödesregler för att filtrera massutskick
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att använda e-postflödesregler (transportregler) för att identifiera och filtrera massutskick (grå e-post) i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069889"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Använda e-postflödesregler för att filtrera massutskick i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående organisationer som har Exchange Online Protection (EOP) utan Exchange Online-postlådor använder EOP principer för skräppostskydd (kallas även principer för skräppostfilter eller principer för innehållsfilter) för att söka efter inkommande meddelanden efter skräppost och massutskick (kallas även grå e-post). Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

Om du vill ha fler alternativ för att filtrera massutskick kan du skapa e-postflödesregler (kallas även transportregler) för att söka efter textmönster eller fraser som ofta förekommer i massutskick och markera dessa meddelanden som skräppost. Mer information om massutskick finns i Vad är skillnaden mellan skräppost och massutskick [av](what-s-the-difference-between-junk-email-and-bulk-email.md) e-post? och Nivå för mass klagomål [(BCL) i EOP.](bulk-complaint-level-values.md)

I det här avsnittet beskrivs hur du skapar de här e-postflödesreglerna i administrationscentret för Exchange (EAC) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste ha tilldelats behörigheter i Exchange Online eller Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du rollen **Transportregler,** som är tilldelad rollgrupperna **Organisationshantering,**  Efterlevnadshantering (globala administratörer) och **Hantering** av arkivhandlingar som standard.

  Mer information finns i följande avsnitt:

  - [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Behörigheter i fristående EOP](feature-permissions-in-eop.md)
  - [Använd EAC för att ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Information om hur du öppnar EAC i Exchange Online finns i [Administrationscenter för Exchange i Exchange Online.](/Exchange/exchange-admin-center) Information om hur du öppnar EAC i fristående EOP finns i [Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Mer information om e-postflödesregler i Exchange Online och fristående EOP finns i följande avsnitt:

  - [E-postflödesregler (transportregler) i Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Villkor och undantag för e-postflödesregel (predikat) i Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Åtgärder för e-postflödesregel i Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- Listan med ord och textmönster som används för att identifiera massutskick i exemplen är inte uttömmande. du kan lägga till och ta bort poster efter behov. De är dock en bra utgångspunkt.

- Sökningen efter ord eller textmönster i ämnes- eller andra  rubrikfält i meddelandet inträffar när meddelandet har avkodats från kodningsmetoden för MIME-innehållsöverföring som användes för att överföra det binära meddelandet mellan SMTP-servrar i ASCII-text. Du kan inte använda villkor eller undantag för att söka efter rådata (vanligtvis Base64) kodade värden för ämnesfält eller andra rubrikfält i meddelanden.

- Så här markerar du ett massmeddelande som skräppost för hela organisationen. Du kan dock lägga till ytterligare ett villkor för att tillämpa de här reglerna endast för specifika mottagare, så att du kan använda aggressiv filtrering på några få användare med hög målgrupp, medan övriga användare (som i de flesta fall får massutskick som de registrerat sig för) inte påverkas.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Använda EAC för att skapa e-postflödesregler som filtrerar massutskick av e-post

1. Gå till E-postflödesregler **i** \> EAC.

2. Klicka **på ikonen** Lägg till lägg till och välj sedan Skapa en ny ![ ](../../media/ITPro-EAC-AddIcon.png) **regel.**

3. På sidan **Ny regel** som öppnas konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln.

   - Klicka **på Fler alternativ.**

   - **Använd den här regeln om:** Konfigurera någon av följande inställningar för att söka efter innehåll i meddelanden med hjälp av reguljära uttryck (RegEx) eller ord eller fraser:

     - **Ämnet eller brödtexten** \> ämne eller brödtext matchar dessa textmönster: I dialogrutan Ange ord eller fraser som  visas anger du något av följande värden, klickar på Lägg till ikon och upprepar **tills** du har angett alla  ![ ](../../media/ITPro-EAC-AddIcon.png) värden.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      Om du vill redigera en post markerar du den och klickar **på Redigera** ![ redigeringsikon ](../../media/ITPro-EAC-EditIcon.png) . Om du vill ta bort en post markerar du den och klickar på **ta** ![ bort-ikonen ](../../media/ITPro-EAC-DeleteIcon.png) .

       När du är klar klickar du på **OK.**

     - **Ämnet eller brödtexten** \> **ämne eller** brödtext innehåller något av följande ord: I dialogrutan Ange ord eller  fraser som visas anger du något av följande värden, klickar på Lägg till ikon och upprepar **tills** du har angett alla ![ ](../../media/ITPro-EAC-AddIcon.png) värden.

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

      Om du vill redigera en post markerar du den och klickar **på Redigera** ![ redigeringsikon ](../../media/ITPro-EAC-EditIcon.png) . Om du vill ta bort en post markerar du den och klickar på **ta** ![ bort-ikonen ](../../media/ITPro-EAC-DeleteIcon.png) .

       När du är klar klickar du på **OK.**

   - **Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **för att ange SCL (Spam Confidence Level).** I dialogrutan **Ange SCL** konfigurerar du någon av följande inställningar:

     - Om du vill markera meddelanden **som skräppost** väljer du **6**. Åtgärden som du har konfigurerat  för filtrering av skräppost i dina principer mot skräppost tillämpas på meddelandena (standardvärdet är Flytta meddelandet till mappen **Skräppost).**

     - Om du vill markera meddelanden **som skräppost med hög konfidens** väljer du **9**. Åtgärden som du har konfigurerat  för hög konfidens för skräppostfiltrering av skräppost-bedömningar i dina principer för skydd mot skräppost tillämpas på meddelandena (standardvärdet är Flytta meddelandet till **mappen Skräppost).**

    Mer information om SCL-värden finns [i SCL (Spam Confidence Level) i EOP.](spam-confidence-levels.md)

   När du är klar klickar du på **Spara**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Använda PowerShell för att skapa e-postflödesregler som filtrerar massutskick av e-post

Använd följande syntax för att skapa en eller båda e-postflödesreglerna (reguljära uttryck kontra ord):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

I det här exemplet skapas en ny regel med namnet "Massfiltrering av e-post – RegEx" som använder samma lista med reguljära uttryck från tidigare i avsnittet för att ange meddelanden som **Skräppost.**

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

I det här exemplet skapas en ny regel med namnet "Massfiltrering av e-post – ord" som använder samma lista med ord från tidigare i avsnittet för att ange skräppost med **hög konfidens.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Detaljerad information om syntax och parametrar finns i [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera att du har konfigurerat e-postflödesregler för att filtrera massutskick genom att göra något av följande:

- I EAC går du till **E-postflödesregler** \>  \> väljer regeln och \> klickar på **Redigera** ![ ](../../media/ITPro-EAC-EditIcon.png) redigeringsikon och kontrollerar inställningarna.

- I PowerShell \<Rule Name\> ersätter du med namnet på regeln och kör följande kommando för att verifiera inställningarna:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Skicka ett testmeddelande från ett externt konto till en mottagare som innehåller något av fraserna eller textmönstren och verifiera resultatet.