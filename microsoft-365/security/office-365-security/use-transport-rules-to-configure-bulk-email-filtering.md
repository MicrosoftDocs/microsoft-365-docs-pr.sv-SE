---
title: Använd e-postflödesregler för att konfigurera massfiltrering av e-post i Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: Administratörer kan lära sig hur du använder regler för e-postflöde i Exchange Online Protection för massfiltrering av e-post.
ms.openlocfilehash: 81b0f4cc58d712c3a1c1e09dab02d1c6f56cb69d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809355"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>Använd e-postflödesregler för att konfigurera massfiltrering av e-post i Exchange Online Protection

Du kan ange innehållsfilter för skräppost och masse-e-post med hjälp av standardprinciperna för skräppostinnehåll. Kolla [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md) och [Ange ContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) om hur du ställer in principer för innehållsfilter.

Om du vill ha fler alternativ för att filtrera massmeddelanden kan du skapa regler för e-postflöde (kallas även transportregler) för att söka efter textmönster eller fraser som ofta finns i massmeddelanden. Alla meddelanden som innehåller dessa egenskaper markeras som skräppost. Om du använder dessa regler kan mängden oönskad masse-e-post som organisationen tar emot minskas.

> [!IMPORTANT]
> Innan du skapar reglerna för e-postflöde dokumenteras det här avsnittet, rekommenderar vi att du först läsa [Vad är skillnaden mellan skräppost och mass-e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md) och Bulk [klagomålnivå värden](bulk-complaint-level-values.md).<br>
> Följande procedurer markerar ett meddelande som skräppost för hela organisationen. Du kan dock lägga till ett annat villkor om du bara vill tillämpa dessa regler på specifika mottagare i organisationen. På så sätt kan de aggressiva massinställningarna för filtrering av e-post tillämpas på ett fåtal användare som är mycket målinriktade, medan resten av användarna (som oftast får massmeddelandet de registrerat sig för) inte påverkas.

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>Skapa en regel för e-postflöde för att filtrera massmeddelanden baserat på textmönster

1. Gå till Regler för **e-postflöde** \> **i**administrationscentret för Exchange (EAC).

2. Klicka på](../../media/ITPro-EAC-AddIcon.gif) Lägg **till** ![ikonen och välj sedan Skapa en ny **regel**.

3. Ange ett namn på regeln.

4. Klicka på **Fler** ![](../../media/ITPro-EAC-MoreOptionsIcon.png)alternativ Fler alternativ ikon . Under **Använd den här regeln om**du väljer **Ämnes- eller brödtexteller** \> **brödtext matchar dessa textmönster**.

5. I dialogrutan **Ange ord eller fraser** lägger du till följande reguljära uttryck som vanligen finns i massmeddelanden, en i taget och klickar på **OK** när du är klar:

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

   Listan ovan är inte en uttömmande uppsättning reguljära uttryck som finns i masse-e-postmeddelanden. mer kan läggas till eller tas bort efter behov. Men det är en bra utgångspunkt.

   Sökningen efter ord eller textmönster i ämnes- eller andra rubrikfält en i meddelandet inträffar *efter* att meddelandet har avkodats från MIME-kodningsmetoden för innehållsöverföring som användes för att överföra det binära meddelandet mellan SMTP-servrar i ASCII-text. Du kan inte använda villkor eller undantag för att söka efter de råa (vanligtvis Base64) kodade värdena för ämnes- eller andra rubrikfält i meddelanden.

6. Under **Gör följande**väljer du Ändra **meddelandeegenskaperna** \> som anges på **förtroendenivån för skräppost (SCL).**

7. I dialogrutan **Ange SCL** ställer du in SCL till **5,** **6**eller **9**och klickar på **ok**.

   Om du ställer in SCL till 5 eller 6 krävs **åtgärden Skräppost,** samtidigt som scl-värdet ställs in på 9, vilket är **skräpet på skräpposten,** som konfigurerats i innehållsfilterprincipen. Tjänsten utför åtgärden i innehållsfilterprincipen. Standardåtgärden är att leverera meddelandet till mottagarnas skräppostmapp, men olika åtgärder kan konfigureras enligt beskrivningen i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).

   Om den konfigurerade åtgärden är att sätta meddelandet i karantän i stället för att skicka det till mottagarens skräppostmapp skickas meddelandet till administratörskarantänen som en regel match för e-postflödet, och det kommer inte att vara tillgängligt i slutanvändarens skräppostkarantän eller via slutanvändaren spam-meddelanden.

   Mer information om SCL-värden i tjänsten finns i [Förtroendenivåer för skräppost](spam-confidence-levels.md).

8. Spara regeln.

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>Skapa en regel för e-postflöde för att filtrera massmeddelanden baserat på fraser

1. I EAC går du till **regler för e-postflöde** \> **.**

2. Klicka på](../../media/ITPro-EAC-AddIcon.gif) Lägg **till** ![ikonen och välj sedan Skapa en ny **regel**.

3. Ange ett namn på regeln.

4. Klicka på **Fler alternativ**. Under **Använd den här regeln om**du väljer Ämnet eller **brödtexten** \> eller **brödtexten innehåller något av dessa ord**.

5. I dialogrutan **Ange ord eller fraser** lägger du till följande fraser som vanligen finns i massmeddelanden, en i taget och klickar på **ok** när du är klar:

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

   Den här listan är inte en uttömmande uppsättning fraser som finns i bulk e-postmeddelanden; mer kan läggas till eller tas bort efter behov. Men det är en bra utgångspunkt.

6. Under **Gör följande**väljer du Ändra **meddelandeegenskaperna** \> som anges på **förtroendenivån för skräppost (SCL).**

7. I dialogrutan **Ange SCL** ställer du in SCL till **5,** **6**eller **9**och klickar på **ok**.

   Om du ställer in SCL till 5 eller 6 krävs **åtgärden Skräppost,** samtidigt som scl-värdet ställs in på 9, vilket är **skräpet på skräpposten,** som konfigurerats i innehållsfilterprincipen. Tjänsten utför åtgärden i innehållsfilterprincipen. Standardåtgärden är att leverera meddelandet till mottagarnas skräppostmapp, men olika åtgärder kan konfigureras enligt beskrivningen i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).

   Om den konfigurerade åtgärden är att sätta meddelandet i karantän i stället för att skicka det till mottagarens skräppostmapp skickas meddelandet till administratörskarantänen som en regel match för e-postflödet, och det kommer inte att vara tillgängligt i slutanvändarens skräppostkarantän eller via slutanvändaren spam-meddelanden.

   Mer information om SCL-värden i tjänsten finns i [Förtroendenivåer för skräppost](spam-confidence-levels.md).

8. Spara regeln.

## <a name="for-more-information"></a>Mer information

[Vad är skillnaden mellan skräppost och masse-e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Värden på massklagomålsnivå](bulk-complaint-level-values.md)

[Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md)

[Avancerade alternativ för skräppostfiltrering](advanced-spam-filtering-asf-options.md)
