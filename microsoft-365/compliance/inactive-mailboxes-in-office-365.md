---
title: Översikt över inaktiva postlådor
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du bevarar postlådeinnehåll för tidigare anställda genom att göra postlådan till en inaktiv postlåda.
ms.openlocfilehash: 6aeb10f1557a991523b60b8e8e85a99fc61f4b87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161993"
---
# <a name="overview-of-inactive-mailboxes"></a>Översikt över inaktiva postlådor

Organisationen kan behöva behålla före detta anställdas e-post när de har lämnar organisationen. Beroende på organisationens bevarandekrav kan du behöva behålla postlådeinnehållet i några månader eller år efter att du slutar, eller så kanske du måste behålla postlådeinnehållet på obestämd tid. Oavsett hur länge du behöver behålla e-post kan du skapa inaktiva postlådor för att behålla postlådan från tidigare anställda.

## <a name="what-are-inactive-mailboxes"></a>Vad är inaktiva postlådor?

När en anställd lämnar organisationen (eller fortsätter att vara frånvarande) kan du ta bort deras Microsoft 365 konto. Den anställdas postlådedata sparas i 30 dagar efter att kontot tagits bort. Under den här perioden kan du fortfarande återställa e-postdata genom att avdeklarera kontot. Efter 30 dagar tas data bort permanent.

Men om din organisation behöver behålla postlådeinnehåll för tidigare anställda kan du omvandla postlådan till en inaktiv postlåda genom att placera postlådan på Bevarande av juridiska skäl eller använda en Microsoft 365-bevarandeprincip för postlådan i Säkerhets- och efterlevnadscenter för & och sedan ta bort motsvarande Microsoft 365-konto. Innehållet i en inaktiv postlåda behålls under hela det bevarande av juridiska skäl som gjorts för postlådan eller lagringstiden för den bevarandeprincip som tillämpats på den innan postlådan togs bort. Du kan fortfarande återställa motsvarande användarkonto under en period på 30 dagar. Men efter 30 dagar behålls den inaktiva postlådan i Microsoft 365 tills bevarande- eller bevarandeprincipen tas bort.

> [!IMPORTANT]
> Medan vi fortsätter att investera på olika sätt för att bevara postlådeinnehållet presenterar vi att innehållet i In-Place Holds har Exchange i administrationscentret. Det innebär att du bör använda bevarandeprinciper för Microsoft 365 och bevarandeprinciper för att skapa en inaktiv postlåda. Från och med den 1 juli 2020 kan du inte skapa nya In-Place i Exchange Online. Men du kan fortfarande ändra varaktigheten för ett aktivt In-Place som gjorts på en inaktiv postlåda. Men med början den 1 oktober 2020 kan du inte ändra varaktigheten för varaktigheten. Du kan bara ta bort en inaktiv postlåda genom att ta bort In-Place inaktiv. Befintliga inaktiva postlådor som finns på In-Place behålls fortfarande tills brytningen tas bort. Mer information om när eDiscovery-In-Place kommer att dras tillbaka finns i [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).

## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>Inaktiva postlådor och Microsoft 365 bevarandeprinciper

Utöver bevarande av juridiska skäl kan du även göra en postlåda inaktiv genom Microsoft 365 den nya funktionen för bevarandeprincip i Microsoft 365 för bevarande av juridiska skäl. Så här använder du en bevarandeprincip för att göra en inaktiv postlåda:

- Det måste konfigureras för att behålla innehåll eller behålla och sedan ta bort innehåll. Om en bevarandeprincip endast har konfigurerats för att ta bort innehåll blir en postlåda som principen tillämpas på inte inaktiv när användarkontot tas bort.

- Den måste tillämpas Exchange postlådor eller Skype för företag (eftersom Skype-relaterat innehåll lagras i användarens postlåda).

- Det kan frågebaserat så att det bara behåller objekt som matchar en sökfråga.

Mer information om bevarandeprinciper finns i Läs [mer om bevarandeprinciper och bevarandeetiketter.](retention.md)

Om du använder en bevarandeprincip för att göra en inaktiv postlåda fortsätter Microsoft 365 att bearbeta kvarhållningsprincipen för den inaktiva postlådan. Det innebär att om bevarandeprincipen är konfigurerad för att behålla och ta bort innehåll flyttas objekt till mappen återställningsbara objekt när tiden för kvarhållningen löper ut och så småningom rensas bort från den inaktiva postlådan. Om bevarandeprincipen inte är konfigurerad till borttagna objekt flyttas inte objekt som inte har tagits bort permanent av användaren (innan postlådan blev inaktiv) till mappen Återställningsbara objekt och behålls ett obestämt sätt när postlådan blir inaktiv.

Du kan skapa en Microsoft 365 specifika bevarandeprincip för inaktiva postlådor. Här är några anledningar till varför du gör detta och saker att tänka på.

- Du kan konfigurera bevarandeprincipen för att behålla postlådeinnehållet så länge det behövs för att uppfylla organisationens krav för tidigare anställda.

- Det är ett bra sätt att identifiera inaktiva postlådor eftersom kvarhållningsprincipen endast kommer att användas för inaktiva postlådor.

- Du kan snabbt identifiera kvarhållningsprincipen som tilldelas till inaktiva postlådor i organisationen. Det gör det enklare att ändra inställningarna för bevarande (eller borttagning) om det behövs. Det gör det också enklare att permanent ta bort en inaktiv postlåda eftersom du kan ta bort den från principen med hjälp av Säkerhets- & efterlevnadscenter. Annars måste du använda Exchange Online PowerShell för att ta bort ett bevarande av juridiska skäl från en inaktiv postlåda eller använda Säkerhets- och efterlevnadscenter för & PowerShell för att utesluta en inaktiv postlåda från en organisationsomfattande Microsoft 365-bevarandeprincip.

- Om du skapar Microsoft 365 specifika bevarandeprinciper för inaktiva postlådor kan du lägga till högst 1 000 postlådor i principen. Om organisationen är stor kan du behöva skapa flera olika bevarandeprinciper Microsoft 365 inaktiva postlådor.

> [!CAUTION]
> Om du använder en bevarandeprincip för att göra en postlåda inaktiv ska du inte ändra eller ta bort postlådans huvudnamn (UPN) innan du tar bort användarkontot. Ändra inte heller den primära SMTP-adressen (som härleds från UPN) eller ta bort den här e-postadressen från listan med sekundära SMTP-adresser som är kopplade till postlådan innan du gör postlådan inaktiv. Om du ändrar UPN- eller e-postadresserna (som tilldelades till postlådan när bevarandeprincipen tillämpats på den) och sedan tar bort användarkontot så att postlådan blir inaktiv kan du inte ta bort den inaktiva postlådan när du inte längre behöver behålla den. Det beror på att du inte kan ta bort den inaktiva postlådan från bevarandeprincipen med hjälp av ett UPN eller en e-postadress (för att identifiera den inaktiva postlådan) som skiljer sig från dem som fanns när kvarhållningsprincipen först tillämpats på postlådan. Mer information om hur du tar bort inaktiva postlådor finns [i Ta bort en inaktiv postlåda i Office 365](delete-an-inactive-mailbox.md).

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Inaktiva postlådor och eDiscovery-ärende som sätts i spärrade eDiscovery-fall

Om ett ärende som är kopplat till ett eDiscovery-ärende i säkerhets- och efterlevnadscentret för & placeras på en postlåda och postlådan eller användarens konto sedan tas bort blir postlådan en inaktiv postlåda. Vi rekommenderar dock inte att eDiscovery-ärende kan spärras för att göra en postlåda inaktiv. Det beror på att eDiscovery-ärenden är avsedda för specifika, tidsbundna ärenden relaterade till ett juridiskt ärende. Förr eller senare avslutas förmodligen ett juridiskt ärende och det som är kopplat till ärendet kommer att tas bort och eDiscovery-ärendet kommer att avslutas. Faktum är att om ett väntande ärende som placerats i en inaktiv postlåda kopplas till ett eDiscovery-ärende och sedan frisläpps från servern eller eDiscovery-ärendet stängs (eller tas bort) tas den inaktiva postlådan bort permanent. Du kan inte heller skapa ett tidsbaserat eDiscovery-håll. Det innebär att innehållet i en inaktiv postlåda bevaras permanent eller tills det tas bort från servern och den inaktiva postlådan tas bort. Därför rekommenderar vi att du använder bevarande av juridiska skäl eller en bevarandeprincip för inaktiva postlådor.

Mer information om eDiscovery-ärenden och eDiscovery-ärenden finns i [eDiscovery-ärenden.](./get-started-core-ediscovery.md)

## <a name="inactive-mailboxes-and-labels"></a>Inaktiva postlådor och etiketter

Med bevarandeetiketter kan du klassificera e-postdata i organisationen för styrning och tillämpa bevaranderegler baserat på den klassificeringen. En bevarandeetikett kan tillämpas på ett e-postobjekt, antingen manuellt av användare eller automatiskt av administratörer, och ett e-postobjekt kan bara ha en enstaka etikett tilldelad. Om en enskild e-postobjekt i en användares postlåda har tilldelats en etikett (och det är konfigurerat att behålla eller behålla och sedan ta bort objektet) och postlådan eller användarens konto tas bort blir postlådan en inaktiv postlåda. På liknande sätt som eDiscovery-ärende kan spärras rekommenderar vi att du inte använder bevarandeetiketter för att göra en postlåda inaktiv. Vi rekommenderar i stället att du använder bevarande av juridiska skäl eller en bevarandeprincip. När det gäller bevarandeetiketter kanske du inte inser att en bevarandeetikett har använts på ett e-postobjekt och sedan oavsiktligt göra en inaktiv postlåda när du tar bort användarens konto.

Mer information om bevarandeprinciper och bevarandeetiketter finns i [Läs mer om bevarandeprinciper och bevarandeetiketter i Office 365.](retention.md)

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Inaktiva postlådor och automatiskt expanderande arkiv

En inaktiv postlåda som är konfigurerad med ett automatiskt expanderande arkiv kan inte återställas eller återställas. I situationer där det är nödvändigt att återställa data från en inaktiv postlåda med ett automatiskt expanderande arkiv rekommenderar vi att du använder verktyget för innehållssökning för att exportera data från postlådan och sedan importera till en annan postlåda. Stegvisa instruktioner för att söka i en inaktiv postlåda och exportera sökresultaten finns i:

- [Innehållssökning](content-search.md)

- [Exportera sökresultat för innehåll](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Inaktiva postlådor och Exchange MRM-bevarandeprinciper

Om en Exchange-bevarandeprincip (hantering av meddelandeposter eller MRM, i Exchange Online) tillämpats på postlådan när den gjordes inaktiv kommer alla  borttagningsprinciper (som är bevarandetaggar som konfigurerats med en bevarandeåtgärd Ta bort) att bearbetas i den inaktiva postlådan. Det innebär att objekt som är märkta med en borttagningsprincip flyttas till mappen Återställningsbara objekt när bevarandetiden löper ut. De objekten rensas från den inaktiva postlådan när varaktigheten för undantaget upphör. Om ingen varaktighet för att bevara objekt anges för den inaktiva postlådan behålls objekten i mappen Återställ objekt på obestämd tid.

Och alla arkiveringsprinciper (som är bevarandetaggar som konfigurerats med bevarandeåtgärden **FlyttaTillArkiv)** som ingår i den bevarandeprincip som tilldelats en inaktiv postlåda ignoreras. Det innebär att objekt i en inaktiv postlåda som är märkta med en arkiveringsprincip finns kvar i den primära postlådan när lagringsperioden går ut. De flyttas inte till arkivpostlådan eller till mappen Återställningsbara objekt i arkivpostlådan. De kommer att behållas under en obegränsad tid.

## <a name="creating-an-inactive-mailbox"></a>Skapa en inaktiv postlåda

För att göra en postlåda inaktiv måste den tilldelas en Exchange Online abonnemang 2-licens (eller en Exchange Online abonnemang 1-licens med en Exchange Online - arkivering-tilläggslicens) så att bevarandeprinciper för bevarande av juridiska skäl eller Microsoft 365 kan tillämpas på postlådan innan den tas bort. När användarkontot har tagits bort kan Exchange Online licens som är kopplad till användarkontot tilldelas till en ny användare.

I följande tabell sammanfattas processen med att göra en inaktiv postlåda för olika lagringsscenarier. Mer information finns i Hantera [inaktiva postlådor.](create-and-manage-inactive-mailboxes.md)

****

|Om du vill...|Gör du så här ...|Resultat|
|---|---|---|
|Behålla postlådeinnehåll på obestämd tid efter att en anställd lämnar organisationen|Placera postlådan i Bevarande av juridiska skäl eller Microsoft 365 bevarandeprincip (som är konfigurerad för att behålla innehåll) på postlådan. <br/> Ange inte varaktigheten för bevarande av juridiska skäl eller konfigurera inte bevarandeprincipen för att ta bort objekt. Du kan också använda en bevarandeprincip som bevarar objekt för alltid. <br/> Ta bort användarens Microsoft 365 konto.|Allt innehåll i den inaktiva postlådan, inklusive objekt i mappen Återställningsbara objekt, bevaras på obestämd tid.|
|Behålla postlådeinnehåll under en viss period efter att en anställd lämnar organisationen och sedan ta bort det|Tillämpa Microsoft 365 bevarandeprincip på postlådan. <br/> Konfigurera bevarandeprincipen för att behålla och sedan ta bort objekt när de blir kvar. <br/> Ta bort användarens Microsoft 365 konto.|När bevarandetiden för ett postlådeobjekt löper ut flyttas objektet till mappen Återställningsbara objekt och tas sedan bort permanent från den inaktiva postlådan när bevarandeperioden för borttagna objekt (för Exchange postlådor) upphör att gälla. Bevarandetiden för den Microsoft 365 kan konfigureras utifrån det ursprungliga datumet då ett postlådeobjekt togs emot eller skapades, eller när det senast ändrades.|
|

**OBS!** Om ett bevarande av juridiska skäl redan finns i en postlåda, eller om en Microsoft 365-bevarandeprincip (som är konfigurerad för att behålla eller behålla och sedan ta bort innehåll) redan tillämpas på postlådan, är allt du behöver göra att ta bort motsvarande användarkonto för att skapa en inaktiv postlåda.

## <a name="managing-inactive-mailboxes"></a>Hantera inaktiva postlådor

När du har inaktiverat en postlåda kan du utföra olika hanteringsuppgifter på inaktiva postlådor.

- **Ändra varaktigheten för väntande ändringar för en inaktiv postlåda.** När en postlåda har gjorts inaktiv kan du ändra varaktigheten för bevarande av juridiska skäl Microsoft 365 bevarandeprincip som tillämpas på den inaktiva postlådan. Stegvisa instruktioner finns i Ändra [varaktigheten för varaktigheten för en inaktiv postlåda.](change-the-hold-duration-for-an-inactive-mailbox.md)

  > [!NOTE]
  > Du kan inte tillämpa andra bevarandeprinciper på en inaktiv postlåda. Du kan bara ändra varaktigheten för en befintlig bevarandeprincip som tillämpas på den inaktiva postlådan.

- **Återställa en inaktiv postlåda.** Om en tidigare anställd (eller en anställd som är frånvarande) återgår till organisationen, eller om en ny anställd anställs för att ta på sig arbetsansvaret för den tidigare anställde, kan du återställa innehållet i den inaktiva postlådan. När du återställer en inaktiv postlåda konverteras postlådan till en ny postlåda, innehållet och mappstrukturen för den inaktiva postlådan behålls och postlådan länkas till ett nytt användarkonto. När den har återställts finns den inaktiva postlådan inte längre. Stegvisa instruktioner och information om vad som händer när du återställer en inaktiv postlåda finns i [Återställa en inaktiv postlåda.](recover-an-inactive-mailbox.md)

  > [!NOTE]
  > Om du återställer en inaktiv postlåda som har tilldelats en bevarandeprincip med bevarandelås (kallas låst bevarandeprincip) tilldelas den återskapade postlådan samma låsta bevarandeprincip. Om du återställer en inaktiv postlåda som har tilldelats en bevarandeprincip utan Bevarandelås tas den återskapade postlådan bort från principen för olåst bevarande. Bevarande av juridiska skäl är aktiverat för den återställda postlådan för att förhindra borttagning av postlådeinnehåll baserat på bevarandeprinciper för hela organisationen som tar bort innehåll som är äldre än en viss ålder.

- **Återställa en inaktiv postlåda.** Om en annan anställd tar på sig arbetsansvaret som en tidigare anställd har, eller om någon annan behöver åtkomst till innehållet i den inaktiva postlådan, kan du återställa (eller sammanfoga) innehållet i den inaktiva postlådan till en befintlig postlåda. När du återställer en inaktiv postlåda kopieras innehållet till en annan postlåda. Den inaktiva postlådan behålls och förblir en inaktiv postlåda. Du kan fortfarande söka i den inaktiva postlådan med hjälp av eDiscovery-verktygen, innehållet kan återställas till en annan postlåda och återställas eller tas bort senare. Stegvisa instruktioner finns i Återställa [en inaktiv postlåda.](restore-an-inactive-mailbox.md)

- **Ta bort en inaktiv postlåda.** När du inte längre behöver behålla innehållet i en inaktiv postlåda kan du ta bort den permanent genom att ta bort alla innehåll innehåll Microsoft 365 bevarandeprinciper som tillämpas på den inaktiva postlådan. Om en postlåda gjordes inaktiv för mer än 30 dagar sedan markeras den för permanent borttagning när du tar bort undantarposten. Om postlådan har gjorts inaktiv under de senaste 30 dagarna kan du göra den aktiv igen när du har tagit bort bevarande- eller bevarandeprincipen. Stegvisa instruktioner finns i Ta bort [en inaktiv postlåda.](delete-an-inactive-mailbox.md)