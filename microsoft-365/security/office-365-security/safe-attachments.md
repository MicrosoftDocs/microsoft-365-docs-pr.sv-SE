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
description: Administratörer kan läsa mer om funktionen säkra bifogade filer i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2f097cddce4afe2b3242ae34bbcfa242c3af601
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207392"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Säkra bifogade filer i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Säkra bifogade filer i Microsoft Defender för [Office 365](defender-for-office-365.md) ger ytterligare ett skyddslager för e-postbilagor som redan har genomsökts med skydd mot skadlig programvara [i Exchange Online Protection (EOP).](anti-malware-protection.md) Mer specifikt används en virtuell miljö för att kontrollera bifogade filer i e-postmeddelanden innan de levereras till mottagare (en process som kallas _detonation)._

Skydd för säkra bifogade filer för e-postmeddelanden styrs av principer för säkra bifogade filer. Det finns ingen standardprincip för säkra bifogade filer, så för att få skydd av säkra bifogade filer måste du skapa en eller **flera principer för säkra bifogade filer.** Anvisningar finns i Konfigurera [principer för säkra bifogade filer i Defender för Office 365.](set-up-safe-attachments-policies.md)

I följande tabell beskrivs scenarier för säkra bifogade filer i Microsoft 365- och Office 365-organisationer som inkluderar Microsoft Defender för Office 365 (med andra ord är brist på licensiering aldrig ett problem i exemplen).

****

|Scenario|Resultat|
|---|---|
|Pats Microsoft 365 E5-organisation har inga principer för säkra bifogade filer konfigurerade.|Pat skyddas inte av Säkra bifogade filer. <p> En administratör måste skapa minst en princip för säkra bifogade filer för att skydda säkra bifogade filer för att vara aktiv. Villkoren i principen måste dessutom omfatta Pat om Pat ska skyddas av säkra bifogade filer.|
|Lees organisation har en princip för säkra bifogade filer som endast gäller för anställda inom ekonomi. Lee är medlem i säljavdelningen.|Lee skyddas inte av Säkra bifogade filer. <p> Ekonomianställda skyddas av Säkra bifogade filer, men säljpersonal (och andra anställda) har det inte.|
|I går skapade en administratör i Organisations organisation en princip för säkra bifogade filer som gäller för alla anställda. Tidigare i dag fick Jens ett e-postmeddelande som innehöll en bifogad fil.|Jag är skyddad av Säkra bifogade filer. <p> Det brukar ta ungefär 30 minuter innan en ny princip börjar gälla.|
|Chris organisation har sedan länge principer för säkra bifogade filer för alla i organisationen. Chris får ett e-postmeddelande som har en bifogad fil och vidarebefordrar sedan meddelandet till externa mottagare.|Chi2 skyddas av säkra bifogade filer. <p> Om de externa mottagarna också har principer för säkra bifogade filer i organisationen gäller de principerna för vidarebefordrade meddelanden.|
|

Genomsökning av säkra bifogade filer sker i samma region som dina Microsoft 365-data finns. Mer information om datacentrets geografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Följande funktioner finns i de globala inställningarna för principer för säkra bifogade filer i Säkerhets- & Efterlevnadscenter. Men de här inställningarna är aktiverade eller inaktiverade globalt och kräver inte principer för säkra bifogade filer:
>
> - [Säkra bifogade filer i SharePoint, OneDrive och Microsoft Teams.](mdo-for-spo-odb-and-teams.md)
>
> - [Säkra dokument i Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Principinställningar för säkra bifogade filer

I det här avsnittet beskrivs inställningarna i principer för säkra bifogade filer:

- **Okänd information om säkra bifogade filer via skadlig** programvara: Den här inställningen styr åtgärden för sökning efter skadlig programvara med säkra bifogade filer i e-postmeddelanden. De tillgängliga alternativen beskrivs i följande tabell:

  ****

  |Alternativ|Effekt|Använd det här när du vill:|
  |---|---|---|
  |**Av**|Bifogade filer genomsöks inte efter skadlig programvara genom säkra bifogade filer. Meddelanden genomsöks fortfarande efter skadlig programvara med [skydd mot skadlig programvara i EOP.](anti-malware-protection.md)|Inaktivera genomsökning för valda mottagare. <p> Förhindra onödiga fördröjningar i dirigering av intern e-post. <p> **Det här alternativet rekommenderas inte för de flesta användare. Du bör endast använda det här alternativet för att inaktivera genomsökning av betrodda bifogade filer för mottagare som endast får meddelanden från betrodda avsändare.**|
  |**Övervaka**|Levererar meddelanden med bifogade filer och spårar sedan vad som händer med identifierade skadlig programvara. <p> Leveransen av säkra meddelanden kan fördröjas på grund av genomsökning av bifogade filer.|Se var skadlig programvara hamnar i organisationen.|
  |**Blockera**|Förhindrar att meddelanden med bifogade filer från skadlig programvara levereras. <p> Meddelanden ligger [i karantän](manage-quarantined-messages-and-files.md) där bara administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden. <p> Blockerar automatiskt framtida instanser av meddelanden och bifogade filer. <p> Leveransen av säkra meddelanden kan fördröjas på grund av genomsökning av bifogade filer.|Skyddar organisationen från upprepade attacker med hjälp av samma bifogade filer från skadlig programvara. <p> Det här är standardvärdet och det rekommenderade värdet i de förinställda säkerhetsprinciperna Standard [och Strikt.](preset-security-policies.md)|
  |**Ersätt**|Tar bort bifogade filer från skadlig programvara. <p> Meddelar mottagarna att bifogade filer har tagits bort. <p>  Meddelanden ligger [i karantän](manage-quarantined-messages-and-files.md) där bara administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden. <p> Leveransen av säkra meddelanden kan fördröjas på grund av genomsökning av bifogade filer.|Synliggöra mottagare om att bifogade filer har tagits bort på grund av skadlig programvara.|
  |**Dynamisk leverans**|Levererar meddelanden direkt, men ersätter bifogade filer med platshållare tills skanning av säkra bifogade filer är klar. <p> Mer information finns i avsnittet [Principer för dynamisk leverans i säkra bifogade filer](#dynamic-delivery-in-safe-attachments-policies) längre fram i den här artikeln.|Undvik meddelandefördröjningar och skydda mottagare från skadliga filer. <p> Gör det möjligt för mottagarna att förhandsgranska bifogade filer i felsäkert läge medan genomsökning sker.|
  |

- Omdirigera bifogade filer vid **identifiering:** Aktivera omdirigering och Skicka bilagan till  följande e-postadress: För åtgärder **blockera,** övervaka eller ersätt ska du skicka meddelanden som innehåller bifogade filer som är bifogade till skadlig programvara till den angivna interna eller externa e-postadressen för analys och undersökning.

  Rekommendationen för standard- och strikt-principinställningarna är att aktivera omdirigering. Mer information finns i Inställningarna [för säkra bifogade filer.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- **Använd markeringen ovan** om genomsökning av skadlig programvara för  bifogade filer på tider eller fel inträffar: Åtgärden som anges av okänt svar på säkra bifogade filer används på meddelanden även om genomsökning av säkra bifogade filer inte kan slutföras. Välj alltid det här alternativet om du väljer **Aktivera omdirigering.** Annars kan meddelanden gå förlorade.

- **Mottagarfilter:** Du måste ange mottagarens villkor och undantag som avgör vem principen gäller för. Du kan använda de här egenskaperna för villkor och undantag:

  - **Mottagaren**
  - **Mottagarens domän är**
  - **Mottagaren är medlem i**

  Du kan bara använda ett villkor eller undantag en gång, men villkoret eller undantaget kan innehålla flera värden. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

- **Prioritet:** Om du skapar flera principer kan du ange i vilken ordning de ska användas. Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

  För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Principer för dynamisk leverans i principer för säkra bifogade filer

> [!NOTE]
> Dynamisk leverans fungerar endast för Exchange Online-postlådor.

Med åtgärden Dynamisk leverans i principerna för säkra bifogade filer vill du eliminera alla fördröjningar av e-postleveransen som kan orsakas av genomsökning av säkra bifogade filer. Brödtexten i e-postmeddelandet levereras till mottagaren med en platshållare för varje bifogad fil. Platshållaren blir kvar tills den bifogade filen har varit säker, och sedan blir den bifogade filen tillgänglig att öppna eller ladda ned.

Om en bifogad fil skulle vara skadlig sätts meddelandet i karantän. Endast administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden som har satts i karantän genom genomsökning av bifogade filer. Mer information finns i [Hantera meddelanden i karantän och filer som administratör.](manage-quarantined-messages-and-files.md)

De flesta PDF-filer och Office-dokument kan förhandsgranskas i felsäkert läge medan genomsökning av bifogade filer pågår. Om en bifogad fil inte är kompatibel med förhandsgranskningen av dynamisk leverans ser mottagarna en platshållare för den bifogade filen tills skanningen av säkra bifogade filer är klar.

Om du använder en mobil enhet och PDF-filer inte återges i förhandsgranskningen av dynamisk leverans på din mobila enhet kan du försöka öppna meddelandet i Outlook på webben (tidigare kallat Outlook Web App) i din mobila webbläsare.

Här är några saker att tänka på när det gäller dynamisk leverans och vidarebefordrade meddelanden:

- Om den vidarebefordrade mottagaren skyddas av en princip för säkra bifogade filer som använder alternativet Dynamisk leverans ser mottagaren platshållaren med möjlighet att förhandsgranska kompatibla filer.

- Om den vidarebefordrade mottagaren inte skyddas av en princip för säkra bifogade filer levereras meddelandet och de bifogade filerna utan några platshållare för säker genomsökning av bifogade filer eller bifogade filer.

Det finns scenarier där dynamisk leverans inte kan ersätta bifogade filer i meddelanden. Scenarierna omfattar:

- Meddelanden i gemensamma mappar.

- Meddelanden som dirigeras ut från och sedan tillbaka till en användares postlåda med hjälp av anpassade regler.

- Meddelanden som flyttas (automatiskt eller manuellt) från molnbaserade postlådor till andra platser, inklusive arkivmappar.

- Borttagna meddelanden.

- Användarens sökmapp i postlådan är i ett felläge.

- Exchange Online-organisationer där Exclaimer är aktiverat. Information om hur du löser det [finns i KB4014438](https://support.microsoft.com/help/4014438).

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) krypterade meddelanden.

- Du har konfigurerat åtgärden Dynamisk leverans i en princip för säkra bifogade filer, men mottagaren stöder inte dynamisk leverans (till exempel är mottagaren en postlåda i en lokal Exchange-organisation). Men med Säkra länkar i Microsoft Defender för [Office 365](set-up-safe-links-policies.md) kan du skanna [](configure-global-settings-for-safe-links.md) bifogade Office-filer som innehåller URL-adresser (beroende på hur de globala inställningarna för Säkra länkar har konfigurerats).

## <a name="submitting-files-for-malware-analysis"></a>Skicka filer för analys av skadlig programvara

- Om du får en fil som du vill skicka till Microsoft för analys kan du gå till Skicka skadlig programvara och [icke-skadlig programvara till Microsoft för analys.](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)

- Om du får ett e-postmeddelande (med eller utan bifogad fil) som du vill skicka till Microsoft för analys, se [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)
