---
title: Säkra bifogade filer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Administratörer kan läsa mer om de säkra funktionerna för bifogade filer i Microsoft Defender för Office 365.
ms.openlocfilehash: d38f95991a1d310e8a894a32e06b5891ebb498a9
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616686"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Säkra bifogade filer i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Säkra bifogade filer i [Microsoft Defender för Office 365](office-365-atp.md) innehåller ett ytterligare skydds nivå för bifogade filer som redan har skannats med [skydd mot skadlig program vara i Exchange Online Protection (EOP)](anti-malware-protection.md). Med säkra bilagor används en virtuell miljö för att kontrol lera bifogade filer i e-postmeddelanden innan de skickas till mottagarna (en process som kallas _sprängning_).

Skyddade bilagor skyddar mot e-postmeddelanden genom principer för säkra bifogade filer. Det finns ingen standard princip för säkra bifogade filer, **så för att skydda säkra bilagor måste du skapa en eller flera principer för säker bifogad fil**. Anvisningar finns i [Konfigurera principer för säkra bifogade filer i Defender för Office 365](set-up-atp-safe-attachments-policies.md).

I följande tabell beskrivs scenarier för säkra bifogade filer i Microsoft 365 och Office 365 organisationer som innehåller Microsoft Defender för Office 365 (med andra ord är bristande licenser aldrig ett problem i exemplen).

****

|Ovanligt|Resultat|
|---|---|
|Pat för Microsoft 365 E5 har inga principer för säkra bifogade filer konfigurerade.|Pat skyddas inte av säkra bifogade filer. <p> En administratör måste skapa minst en princip för säkra bifogade filer för att skydda säkra bifogade filer. Dessutom måste principens villkor innehålla Pat om Pat skyddas av säkra bifogade filer.|
|Aaron Lee organisation har en policy för säker bifogad fil som endast gäller för finans anställda. Aaron Lee är en medlem i Sales-avdelningen.|Aaron Lee skyddas inte av säkra bifogade filer. <p> Finans personalen skyddas av säkra bilagor, men försäljnings personal (och andra anställda) är inte.|
|Igår en administratör i Jean organisation en policy för säker bifogad fil som gäller för alla anställda. Tidigare i dag har Jean fått ett e-postmeddelande som innehåller en bifogad fil.|Jean skyddas av säkra bifogade filer. <p> Vanligt vis tar det ungefär 30 minuter innan en ny princip börjar gälla.|
|Chriss organisation har långa principer för säkra bifogade filer för alla i organisationen. Chris får ett e-postmeddelande som innehåller en bifogad fil och vidarebefordrar sedan meddelandet till externa mottagare.|Chis skyddas av säkra bifogade filer. <p> Om de externa mottagarna också har principer för säkert bifogade filer i sin organisation, lyder de vidarebefordrade meddelandena för dessa principer.|
|

Säkra sökningar i bifogade filer sker i samma region där dina Microsoft 365-data finns. Mer information om data Center geografi finns i [var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Följande funktioner finns i de globala inställningarna för principer för säker bifogade filer i säkerhets & Compliance Center, men dessa inställningar aktive ras eller inaktive ras globalt och kräver inte principer för säkra bifogade filer:
>
> - [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).
>
> - [Säkra dokument i Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Princip inställningar för säkra bifogade filer

I det här avsnittet beskrivs inställningarna i principer för säkra bifogade filer:

- **Osäkra bifogade filer – svar på skadlig program vara**: den här inställningen styr åtgärden för genomsökning av skadligt bifogade filer i e-postmeddelanden. De tillgängliga alternativen beskrivs i följande tabell:

  ****

  |Alternativ|Fungerar|Använd när du vill:|
  |---|---|---|
  |**Av**|Bifogade filer genomsöks inte efter skadlig program vara. Meddelanden genomsöks fortfarande efter skadlig program vara via [skydd mot skadlig program vara i EOP](anti-malware-protection.md).|Inaktivera inaktive avsökning för markerade mottagare. <p> Förhindra onödiga fördröjningar i routning av intern e-post. <p> **Det här alternativet rekommenderas inte för de flesta användare. Du bör bara använda det här alternativet om du vill inaktivera genomsökning av säkra bilagor för mottagare som bara får meddelanden från betrodda avsändare.**|
  |**Övervaka**|Skickar meddelanden med bifogade filer och sedan spåras vad som händer med identifiering av skadlig kod. <p> Leverans av säkra meddelanden kan komma att försenas på grund av genomsökning av säkra bifogade filer.|Se var upptäckta skadlig kod hamnar i din organisation.|
  |**Blockera**|Förhindrar att meddelanden som hittas av skadliga program levereras. <p> Meddelanden är i [karantän](manage-quarantined-messages-and-files.md) där endast administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden. <p> Blockerar automatiskt framtida instanser av meddelanden och bifogade filer. <p> Leverans av säkra meddelanden kan komma att försenas på grund av genomsökning av säkra bifogade filer.|Skyddar din organisation från upprepade attacker med samma bifogade filer. <p> Det här är standardvärdet och det rekommenderade värdet i standard-och Strict- [förvalda säkerhets principer](preset-security-policies.md).|
  |**Byter**|Tar bort hittade bifogade filer. <p> Meddelar mottagare om att bifogade filer har tagits bort. <p>  Meddelanden är i [karantän](manage-quarantined-messages-and-files.md) där endast administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden. <p> Leverans av säkra meddelanden kan komma att försenas på grund av genomsökning av säkra bifogade filer.|Öka synligheten för mottagarna att de bifogade filerna har tagits bort på grund av upptäckt skadlig kod.|
  |**Dynamisk leverans**|Skickar meddelanden direkt men ersätter bifogade filer med plats hållare tills Safe Attachment scanning är klar. <p> Mer information finns i avsnittet [dynamisk leverans i principer för säker bifogade filer](#dynamic-delivery-in-safe-attachments-policies) längre fram i det här avsnittet.|Undvik meddelande fördröjningar när du skyddar mottagare från skadliga filer. <p> Aktivera mottagare för förhands granskning av bifogade filer i fel säkert läge när genomsökning sker.|
  |

- **Omdirigera bilaga: Aktivera omdirigera** och **skicka den bifogade filen till följande e-post adress**: för att **blockera**, **övervaka** eller **ersätta** åtgärder kan du skicka meddelanden som innehåller bifogade filer med skadlig kod till angiven intern eller extern e-postadress för analys och undersökning.

  Rekommendationen för standard-och strikta princip inställningar är att aktivera omdirigering. Mer information finns i [Inställningar för säkra bifogade filer](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- **Använda ovanstående markering om genomsökning av skadlig kod för bifogade filer eller fel inträffar**: åtgärden som anges av **osäkra bifogade filer inget svar på skadlig program** vara tas med när säkra bilagor inte kan slutföras. Välj alltid det här alternativet om du väljer **Aktivera omdirigering**. Annars kan meddelanden gå förlorade.

- **Mottagar filter**: du måste ange de mottagar villkor och undantag som avgör vem principen gäller för. Du kan använda dessa egenskaper för villkor och undantag:

  - **Mottagaren är**
  - **Mottagar domänen är**
  - **Mottagaren är medlem i**

  Du kan bara använda ett villkor eller ett undantag, men villkoret eller undantaget kan innehålla flera värden. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

- **Prioritet**: om du skapar flera principer kan du ange i vilken ordning de används. Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

  För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Dynamisk leverans i principer för säkra bifogade filer

> [!NOTE]
> Dynamisk leverans fungerar bara för Exchange Online-postlådor.

Den dynamiska leverans åtgärden i principer för säker bifogad fil gör det möjligt att eliminera eventuella fördröjningar för e-postleverans som kan orsakas av genomsökning av säkra bilagor. Bröd texten i e-postmeddelandet skickas till mottagaren med en plats hållare för varje bifogad fil. Plats hållaren fortsätter tills den bifogade filen har säkrats och sedan blir bilagan tillgänglig för att öppnas eller hämtas.

Om en bifogad fil verkar vara skadlig visas meddelandet i karantän. Endast administratörer (ej slutanvändare) kan granska, frigöra eller ta bort meddelanden som satts i karantän genom att söka efter skadlig bifogad fil. Mer information finns i [Hantera meddelanden och filer i karantän som administratör](manage-quarantined-messages-and-files.md).

De flesta PDF-filer och Office-dokument kan förhandsgranskas i fel säkert läge medan genomsökning av säkra bifogade filer körs. Om en bifogad fil inte är kompatibel med förhands granskningen av dynamisk leverans visas en plats hållare för bilagan tills Safe Attachment scanning är klar.

Om du använder en mobil enhet och PDF-filer inte återges i förhands granskningen av dynamisk leverans på din mobila enhet kan du försöka öppna meddelandet i Outlook på webben (tidigare Outlook Web App) med webbläsaren.

Här är några saker att tänka på vid dynamisk leverans och vidarebefordrade meddelanden:

- Om den vidarebefordrade mottagaren skyddas av en princip för ett säkert bifogade filer som använder alternativet dynamisk leverans ser mottagaren plats hållaren och kan förhandsgranska kompatibla filer.

- Om den vidarebefordrade mottagaren inte är skyddad av en policy för säker bifogad fil levereras meddelandet och bifogade filer utan vissa plats hållare för att skanna eller bifogade filer.

Det finns scenarier där dynamisk leverans inte kan ersätta bifogade filer i meddelanden. Det här är bland annat:

- Meddelanden i gemensamma mappar.

- Meddelanden som skickas från och sedan tillbaka till en användares post låda med hjälp av anpassade regler.

- Meddelanden som flyttas (automatiskt eller manuellt) från moln post lådor till andra platser, inklusive arkivmappar.

- Borttagna meddelanden.

- Användarens sökmapp i post lådan är i fel tillstånd.

- Exchange Online-organisationer där Exclaimer är aktiverat. Information om hur du löser detta finns i [KB4014438](https://support.microsoft.com/help/4014438).

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) krypterade meddelanden.

- Du konfigurerade åtgärden för dynamisk leverans i en policy för säker bifogad fil, men mottagaren stöder inte dynamisk leverans (till exempel att mottagaren är en post låda i en lokal Exchange-organisation). Däremot kan de [säkra länkarna i Microsoft Defender för Office 365](set-up-atp-safe-links-policies.md) söka i Office-filer som innehåller URL-adresser (beroende på hur de [globala inställningarna för säkra länkar](configure-global-settings-for-safe-links.md) är konfigurerade).

## <a name="submitting-files-for-malware-analysis"></a>Skicka filer för analys av skadlig program vara

- Om du får en fil som du vill skicka till Microsoft för analys kan du läsa [Skicka skadlig program vara och icke-malware till Microsoft för analys](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).

- Om du får ett e-postmeddelande (med eller utan en bifogad fil) som du vill skicka till Microsoft för analys kan du läsa [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).
