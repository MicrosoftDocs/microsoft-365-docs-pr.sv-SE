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
description: Administratörer kan läsa mer om Valv i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc5fabf7b0bb4a649aeb7c4e09155037fc09e9f9
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625011"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Valv Bifogade filer i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Valv Bifogade filer [i Microsoft Defender](defender-for-office-365.md) för Office 365 ger ytterligare ett skyddslager för e-postbilagor som redan har genomsökts med skydd mot skadlig programvara i Exchange Online Protection [(EOP).](anti-malware-protection.md) Mer specifikt Valv bifogade filer använder en virtuell miljö för att kontrollera bifogade filer i e-postmeddelanden innan de levereras till mottagare (en process som kallas _detonation)._

Valv Skydd för bifogade filer i e-postmeddelanden styrs av Valv principer för bifogade filer. Det finns ingen standardprincip Valv för bifogade filer, så för att få skydd Valv bifogade filer måste du skapa en eller flera principer **Valv bifogade filer.** Instruktioner finns i Konfigurera [principer Valv för bifogade filer i Defender för Office 365.](set-up-safe-attachments-policies.md)

I följande tabell beskrivs scenarier för Valv Bifogade filer i Microsoft 365- och Office 365-organisationer som inkluderar Microsoft Defender för Office 365 (med andra ord är brist på licensiering aldrig ett problem i exemplen).

<br>

****

|Scenario|Resultat|
|---|---|
|Pats Microsoft 365 E5 inte har Valv principer för bifogade filer.|Pat skyddas inte av Valv Bifogade filer. <p> En administratör måste skapa minst en Valv för att Valv skydd för bifogade filer ska vara aktivt. Villkoren i principen måste dessutom innehålla Pat om Pat ska skyddas av Valv bilagor.|
|Lees organisation har en princip Valv bifogade filer som endast gäller för anställda inom ekonomi. Lee är medlem i säljavdelningen.|Lee skyddas inte av Valv bifogade filer. <p> Ekonomipersonal skyddas av Valv, men inte av försäljningsanställda (och andra anställda).|
|I går skapade en administratör i Organisations organisation en Valv för bifogade filer som gäller för alla anställda. Tidigare i dag fick Jens ett e-postmeddelande som innehöll en bifogad fil.|Jag är skyddad Valv Bifogade filer. <p> Det brukar ta ungefär 30 minuter innan en ny princip börjar gälla.|
|Chris organisation har länge ständiga principer Valv för alla i organisationen. Chris får ett e-postmeddelande som har en bifogad fil och vidarebefordrar sedan meddelandet till externa mottagare.|Chi2 skyddas av Valv Bifogade filer. <p> Om de externa mottagarna även Valv principer för bifogade filer i organisationen gäller de vidarebefordrade meddelandena dessa principer.|
|

Valv Genomsökning av bifogade filer sker i samma region där Microsoft 365 data finns. Mer information om datacentrets geografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Följande funktioner finns i de globala inställningarna för principer Valv bilagor i Säkerhets- och & Säkerhets- och efterlevnadscenter. Men de här inställningarna är aktiverade eller inaktiverade globalt och kräver Valv principer för bifogade filer:
>
> - [Valv bifogade filer SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md).
> - [Säkra dokument i Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Valv Principinställningar för bifogade filer

I det här avsnittet beskrivs inställningarna i Valv principer för bifogade filer:

- **Valv som inte är okänt svar på** skadlig programvara: Den här inställningen styr hur Valv genomsökning av skadlig programvara för bifogade filer i e-postmeddelanden. De tillgängliga alternativen beskrivs i följande tabell:

  <br>

  ****

  |Alternativ|Effekt|Använd det här när du vill:|
  |---|---|---|
  |**Av**|Bifogade filer genomsöks inte efter skadlig programvara genom att Valv bifogade filer. Meddelanden genomsöks fortfarande efter skadlig programvara med [skydd mot skadlig programvara i EOP.](anti-malware-protection.md)|Inaktivera genomsökning för valda mottagare. <p> Förhindra onödiga fördröjningar i dirigering av intern e-post. <p> **Det här alternativet rekommenderas inte för de flesta användare. Du bör bara använda det här alternativet för Valv sökning efter bifogade filer för mottagare som bara tar emot meddelanden från betrodda avsändare.**|
  |**Övervaka**|Levererar meddelanden med bifogade filer och spårar sedan vad som händer med identifierade skadlig programvara. <p> Leverans av säkra meddelanden kan fördröjas på grund av Valv genomsökning av bifogade filer.|Se var skadlig programvara hamnar i organisationen.|
  |**Blockera**|Förhindrar att meddelanden med bifogade filer från skadlig programvara levereras. <p> Meddelanden ligger [i karantän](manage-quarantined-messages-and-files.md) där bara administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden. <p> Blockerar automatiskt framtida instanser av meddelanden och bifogade filer. <p> Leverans av säkra meddelanden kan fördröjas på grund av Valv genomsökning av bifogade filer.|Skyddar organisationen från upprepade attacker med hjälp av samma bifogade filer från skadlig programvara. <p> Det här är standardvärdet och det rekommenderade värdet i de förinställda säkerhetsprinciperna Standard [och Strikt.](preset-security-policies.md)|
  |**Ersätt**|Tar bort bifogade filer från skadlig programvara. <p> Meddelar mottagarna att bifogade filer har tagits bort. <p>  Meddelanden ligger [i karantän](manage-quarantined-messages-and-files.md) där bara administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden. <p> Leverans av säkra meddelanden kan fördröjas på grund av Valv genomsökning av bifogade filer.|Synliggöra mottagare om att bifogade filer har tagits bort på grund av skadlig programvara.|
  |**Dynamisk leverans**|Levererar meddelanden direkt, men ersätter bifogade filer med platshållare tills Valv har slutfört genomsökning av bifogade filer. <p> Mer information finns i avsnittet [Principer för dynamisk Valv bifogade filer](#dynamic-delivery-in-safe-attachments-policies) längre fram i den här artikeln.|Undvik meddelandefördröjningar och skydda mottagare från skadliga filer. <p> Gör det möjligt för mottagarna att förhandsgranska bifogade filer i felsäkert läge medan genomsökning sker.|
  |

- Omdirigera bifogade filer vid **identifiering:** Aktivera omdirigering och Skicka bilagan till  följande e-postadress: För åtgärder **blockera,** övervaka eller ersätt ska du skicka meddelanden som innehåller bifogade filer som är bifogade till skadlig programvara till den angivna interna eller externa e-postadressen för analys och undersökning.

  Rekommendationen för standard- och strikt-principinställningarna är att aktivera omdirigering. Mer information finns i Valv [Inställningar för bifogade filer](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

- Använd markeringen ovan om genomsökning efter bifogade filer på tider eller fel inträffar: Åtgärden som anges av **Valv** Okänt svar på skadlig programvara tillämpas på meddelanden även när Valv Genomsökning av bifogade filer inte kan **slutföras.** Välj alltid det här alternativet om du väljer **Aktivera omdirigering.** Annars kan meddelanden gå förlorade.

- **Mottagarfilter:** Du måste ange mottagarens villkor och undantag som avgör vem principen gäller för. Du kan använda de här egenskaperna för villkor och undantag:
  - **Mottagaren**
  - **Mottagarens domän är**
  - **Mottagaren är medlem i**

  Du kan bara använda ett villkor eller undantag en gång, men villkoret eller undantaget kan innehålla flera värden. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

- **Prioritet:** Om du skapar flera principer kan du ange i vilken ordning de ska användas. Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

  För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Principer för dynamisk leverans Valv bifogade filer

> [!NOTE]
> Dynamisk leverans fungerar endast för Exchange Online postlådor.

Med åtgärden Dynamisk leverans i Valv principer för bifogade filer vill du eliminera alla e-postleveransfördröjningar som kan orsakas av Valv genomsökning av bifogade filer. Brödtexten i e-postmeddelandet levereras till mottagaren med en platshållare för varje bifogad fil. Platshållaren blir kvar tills den bifogade filen har varit säker, och sedan blir den bifogade filen tillgänglig att öppna eller ladda ned.

Om en bifogad fil skulle vara skadlig sätts meddelandet i karantän. Endast administratörer (inte slutanvändare) kan granska, släppa eller ta bort meddelanden som har satts i karantän Valv genomsökning av bifogade filer. Mer information finns i [Hantera meddelanden i karantän och filer som administratör.](manage-quarantined-messages-and-files.md)

De flesta PDF-filer Office dokument kan förhandsgranskas i felsäkert läge medan Valv sökning efter bifogade filer pågår. Om en bifogad fil inte är kompatibel med förhandsgranskningen av dynamisk leverans visas en platshållare för den bifogade filen tills Valv genomsökning av bifogade filer har slutförts.

Om du använder en mobil enhet och PDF-filer inte återges i förhandsgranskningen av dynamisk leverans på din mobila enhet kan du försöka öppna meddelandet i Outlook på webben (tidigare kallat Outlook Web App) i din mobila webbläsare.

Här är några saker att tänka på när det gäller dynamisk leverans och vidarebefordrade meddelanden:

- Om den vidarebefordrade mottagaren skyddas av en princip Valv för bifogade filer som använder alternativet Dynamisk leverans ser mottagaren platshållaren med möjlighet att förhandsgranska kompatibla filer.
- Om den vidarebefordrade mottagaren inte skyddas av en princip för bifogade filer i Valv, levereras meddelandet och de bifogade filerna utan några Valv genomsökning av bifogade filer eller platshållare för bifogade filer.

Det finns scenarier där dynamisk leverans inte kan ersätta bifogade filer i meddelanden. Scenarierna omfattar:

- Meddelanden i gemensamma mappar.
- Meddelanden som dirigeras ut från och sedan tillbaka till en användares postlåda med hjälp av anpassade regler.
- Meddelanden som flyttas (automatiskt eller manuellt) från molnbaserade postlådor till andra platser, inklusive arkivmappar.
- Inkorgsregler flyttar meddelandet från Inkorgen till en annan mapp.
- Borttagna meddelanden.
- Användarens sökmapp i postlådan är i ett felläge.
- Exchange Online organisationer där Exclaimer är aktiverat. Information om hur du löser problemet finns [i KB4014438.](https://support.microsoft.com/help/4014438)
- [S/MIME)](/exchange/security-and-compliance/smime-exo/smime-exo) krypterade meddelanden.
- Du har konfigurerat åtgärden Dynamisk leverans i en Valv-princip för bifogade filer, men mottagaren stöder inte dynamisk leverans (till exempel är mottagaren en postlåda i en lokal Exchange organisation). Men [med Valv-länkar](set-up-safe-links-policies.md) i Microsoft Defender för Office 365 kan du söka igenom bifogade Office-filer som innehåller URL-adresser (beroende på hur de globala inställningarna för [Valv-länkar](configure-global-settings-for-safe-links.md) konfigureras).

## <a name="submitting-files-for-malware-analysis"></a>Skicka filer för analys av skadlig programvara

- Om du får en fil som du vill skicka till Microsoft för analys kan du gå till Skicka skadlig programvara och [icke-skadlig programvara till Microsoft för analys.](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)
- Om du får ett e-postmeddelande (med eller utan bifogad fil) som du vill skicka till Microsoft för analys, se [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)
