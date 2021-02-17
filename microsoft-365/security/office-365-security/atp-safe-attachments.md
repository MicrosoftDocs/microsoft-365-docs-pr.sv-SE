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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Administratörer kan läsa mer om funktionen Säkra bifogade filer i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5d2d348856dbd51cabe2b320d315406076921fee
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261543"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Säkra bifogade filer i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Säkra bifogade filer i Microsoft Defender för [Office 365](office-365-atp.md) ger ytterligare ett skyddslager för e-postbilagor som redan har skannats med skydd mot skadlig programvara [i Exchange Online Protection (EOP).](anti-malware-protection.md) Specifikt använder säkra bifogade filer en virtuell miljö för att kontrollera bifogade filer i e-postmeddelanden innan de levereras till mottagare (en process som kallas _detonation)._

Skydd mot säkra bifogade filer för e-postmeddelanden styrs av principer för säkra bifogade filer. Det finns ingen standardprincip för säkra bifogade filer, så för att få skydd med säkra bifogade filer måste du skapa en eller flera principer för **säkra bifogade filer.** Instruktioner finns i Konfigurera [principer för säkra bifogade filer i Defender för Office 365.](set-up-atp-safe-attachments-policies.md)

I följande tabell beskrivs scenarier för säkra bifogade filer i Microsoft 365- och Office 365-organisationer där Microsoft Defender för Office 365 ingår (brist på licensiering är alltså aldrig ett problem i exemplen).

****

|Scenario|Resultat|
|---|---|
|Pats Microsoft 365 E5-organisation har inga principer för säkra bifogade filer konfigurerade.|Pat är inte skyddad av säkra bifogade filer. <p> En administratör måste skapa minst en princip för säkra bifogade filer för att skyddet av säkra bifogade filer ska vara aktivt. Dessutom måste villkoren i principen inkludera Pat om Pat ska skyddas av säkra bifogade filer.|
|Lees organisation har en princip för säkra bifogade filer som endast gäller ekonomipersonal. Lee är medlem i säljavdelningen.|Lee är inte skyddad av säkra bifogade filer. <p> Ekonomianställda skyddas av säkra bifogade filer, men försäljningsanställda (och andra anställda) skyddas inte.|
|I går skapade en administratör i Administrationsorganisation en princip för säkra bifogade filer som gäller för alla anställda. Tidigare idag fick Han ett e-postmeddelande som innehöll en bifogad fil.|Han är skyddad av säkra bifogade filer. <p> Det brukar ta ungefär 30 minuter innan en ny princip börjar gälla.|
|Chris organisation har sedan länge principer för säkra bifogade filer för alla i organisationen. Chris får ett e-postmeddelande som innehåller en bifogad fil och vidarebefordrar sedan meddelandet till externa mottagare.|Chi2 skyddas av säkra bifogade filer. <p> Om de externa mottagarna också har principer för säkra bifogade filer i organisationen gäller de principerna för vidarebefordrade meddelanden.|
|

Genomsökning av säkra bifogade filer sker i samma region som dina Microsoft 365-data finns. Mer information om datacentergeografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Följande funktioner finns i de globala inställningarna för principer för säkra bifogade filer i & Säkerhets- och efterlevnadscenter. Men de här inställningarna är aktiverade eller inaktiverade globalt och kräver inte principer för säkra bifogade filer:
>
> - [Säkra bifogade filer i SharePoint, OneDrive och Microsoft Teams.](atp-for-spo-odb-and-teams.md)
>
> - [Säkra dokument i Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Principinställningar för säkra bifogade filer

I det här avsnittet beskrivs inställningarna i principer för säkra bifogade filer:

- **Okända säkra bifogade filer som skadlig kod:** Den här inställningen styr åtgärden för sökning efter säkra bifogade filer i e-postmeddelanden. De tillgängliga alternativen beskrivs i följande tabell:

  ****

  |Alternativ|Effekt|Använd det här när du vill:|
  |---|---|---|
  |**Av**|Bifogade filer genomsöks inte efter skadlig programvara genom säkra bifogade filer. Meddelanden genomsöks fortfarande efter skadlig programvara [genom skydd mot skadlig programvara i EOP.](anti-malware-protection.md)|Inaktivera skanning för valda mottagare. <p> Förhindra onödiga fördröjningar i dirigering av intern e-post. <p> **Det här alternativet rekommenderas inte för de flesta användare. Du bör endast använda det här alternativet för att inaktivera säker genomsökning av bifogade filer för mottagare som bara tar emot meddelanden från betrodda avsändare.**|
  |**Övervaka**|Levererar meddelanden med bifogade filer och spårar sedan vad som händer med identifierade skadlig programvara. <p> Leveransen av säkra meddelanden kan fördröjas på grund av säker genomsökning av bifogade filer.|Se var den identifierade skadlig programvara går i organisationen.|
  |**Blockera**|Förhindrar att meddelanden med identifierade bifogade filer från skadlig programvara levereras. <p> Meddelanden [sätts i karantän](manage-quarantined-messages-and-files.md) där bara administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden. <p> Blockerar automatiskt framtida förekomster av meddelanden och bifogade filer. <p> Leveransen av säkra meddelanden kan fördröjas på grund av säker genomsökning av bifogade filer.|Skyddar organisationen från upprepade attacker med hjälp av samma bifogade filer i skadlig programvara. <p> Det här är standardvärdet och det rekommenderade värdet i de förinställda säkerhetsprinciperna Standard [och Strikt.](preset-security-policies.md)|
  |**Ersätt**|Tar bort identifierade bifogade filer från skadlig programvara. <p> Meddelar mottagarna att bifogade filer har tagits bort. <p>  Meddelanden [sätts i karantän](manage-quarantined-messages-and-files.md) där bara administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden. <p> Leveransen av säkra meddelanden kan fördröjas på grund av säker genomsökning av bifogade filer.|Se till mottagarna att bifogade filer har tagits bort på grund av upptäckt skadlig programvara.|
  |**Dynamisk leverans**|Levererar meddelanden omedelbart, men ersätter bifogade filer med platshållare tills skanningen av säkra bifogade filer är klar. <p> Mer information finns i avsnittet [Om dynamisk leverans i principer för säkra](#dynamic-delivery-in-safe-attachments-policies) bifogade filer senare i den här artikeln.|Undvik meddelandefördröjningar medan du skyddar mottagare från skadliga filer. <p> Gör det möjligt för mottagarna att förhandsgranska bifogade filer i felsäkert läge medan genomsökning sker.|
  |

- **Omdirigering av** bifogade filer vid identifiering: Aktivera omdirigering och Skicka  den bifogade filen till följande e-postadress: För åtgärder som  **Blockera,** Övervaka eller Ersätt kan du skicka meddelanden som innehåller bifogade filer med skadlig programvara till den angivna interna eller externa e-postadressen för analys och undersökning.

  Rekommendationen för standardinställningar och strikt-principinställningar är att aktivera omdirigering. Mer information finns i inställningarna [för säkra bifogade filer.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

- Använd ovanstående val om skadlig programvara söker efter bifogade filer  på tider eller fel uppstår: Åtgärden som anges av okända säkra bifogade filer som är okänt svar på skadlig programvara vidtas på meddelanden även när genomsökning av bifogade filer inte kan **slutföras.** Välj alltid det här alternativet om du väljer **Aktivera omdirigering.** Annars kan meddelanden gå förlorade.

- **Mottagarfilter:** Du måste ange mottagarens villkor och undantag som bestämmer vem principen gäller för. Du kan använda de här egenskaperna för villkor och undantag:

  - **Mottagaren**
  - **Mottagardomänen är**
  - **Mottagaren är medlem i**

  Du kan bara använda ett villkor eller undantag en gång, men villkoret eller undantaget kan innehålla flera värden. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

- **Prioritet:** Om du skapar flera principer kan du ange i vilken ordning de ska tillämpas. Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

  För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Principer för dynamisk leverans i säkra bifogade filer

> [!NOTE]
> Dynamisk leverans fungerar endast för Exchange Online-postlådor.

Med åtgärden Dynamisk leverans i principer för säkra bifogade filer vill du eliminera alla e-postleveransfördröjningar som kan orsakas av genomsökning av säkra bifogade filer. Brödtexten i e-postmeddelandet levereras till mottagaren med en platshållare för varje bifogad fil. Platshållaren finns kvar tills den bifogade filen visat sig vara säker, och sedan blir den bifogade filen tillgänglig att öppna eller ladda ned.

Om en bifogad fil visas som skadlig sätts meddelandet i karantän. Endast administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden som satt i karantän genom sökning efter säkra bifogade filer. Mer information finns i [Hantera meddelanden i karantän och filer som administratör.](manage-quarantined-messages-and-files.md)

De flesta PDF-filer och Office-dokument kan förhandsgranskas i felsäkert läge medan sökning av säkra bifogade filer pågår. Om en bifogad fil inte är kompatibel med förhandsgranskningen av dynamisk leverans ser mottagarna en platshållare för den bifogade filen tills skanningen av säkra bifogade filer är klar.

Om du använder en mobil enhet och PDF-filer inte återges i förhandsgranskningen av Dynamisk leverans på din mobila enhet kan du försöka öppna meddelandet i Outlook på webben (tidigare Kallat Outlook Web App) i din mobila webbläsare.

Här är några överväganden för dynamisk leverans och vidarebefordrade meddelanden:

- Om den vidarebefordrade mottagaren skyddas av en princip för säkra bifogade filer som använder alternativet Dynamisk leverans ser mottagaren platshållaren med möjlighet att förhandsgranska kompatibla filer.

- Om den vidarebefordrade mottagaren inte skyddas av en princip för säkra bifogade filer levereras meddelandet och de bifogade filerna utan någon säker genomsökning av bifogade filer eller platshållare för bifogade filer.

Det finns scenarier där dynamisk leverans inte kan ersätta bifogade filer i meddelanden. De här scenarierna omfattar:

- Meddelanden i gemensamma mappar.

- Meddelanden som dirigeras från och sedan tillbaka till en användares postlåda med hjälp av anpassade regler.

- Meddelanden som flyttas (automatiskt eller manuellt) från molnbaserade postlådor till andra platser, inklusive arkivmappar.

- Borttagna meddelanden.

- Användarens sökmapp för postlåda har ett feltillstånd.

- Exchange Online-organisationer där Utser har aktiverats. Information om hur du löser det [finns i KB4014438.](https://support.microsoft.com/help/4014438)

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) krypterade meddelanden.

- Du har konfigurerat åtgärden Dynamisk leverans i en princip för säkra bifogade filer, men mottagaren har inte stöd för dynamisk leverans (till exempel är mottagaren en postlåda i en lokal Exchange-organisation). Men med säkra länkar i Microsoft Defender för [Office 365](set-up-atp-safe-links-policies.md) kan du skanna [](configure-global-settings-for-safe-links.md) bifogade Office-filer som innehåller URL-adresser (beroende på hur de globala inställningarna för säkra länkar har konfigurerats).

## <a name="submitting-files-for-malware-analysis"></a>Skicka filer för analys av skadlig programvara

- Om du får en fil som du vill skicka till Microsoft för analys kan du gå till Skicka skadlig programvara och [icke-skadlig programvara till Microsoft för analys.](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)

- Om du får ett e-postmeddelande (med eller utan bifogad fil) som du vill skicka till Microsoft för analys, se [Rapportmeddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)
