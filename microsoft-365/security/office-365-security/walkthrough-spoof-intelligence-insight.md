---
title: Genom gång – Insight-inblick
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur inblicken för förfalsknings information fungerar, inklusive hur man snabbt tar reda på vilka avsändare som skickar ett overifierat e-postmeddelande.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6fc934491606a53ebfb4bae4f46ab9e1ee93467b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198577"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a>Genom gång – ATP-information i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med avancerat skydd (ATP) kan du använda falsk IT-insyn för att snabbt avgöra vilka avsändare som skickar ett legitimt e-postmeddelande till dig. Genom att tillåta att de skickar falska meddelanden kan du minska risken för falsk positiv identifiering till användarna. Du kan också använda falsk information för att övervaka och hantera tillåtna domän par för att tillhandahålla ett ytterligare säkerhets lager och förhindra osäkra meddelanden från att komma i din organisation.

Om du inte har använt [rapporter och insikter i säkerhets & Compliance Center](reports-and-insights-in-security-and-compliance.md)kan det vara bra att se hur du enkelt kan navigera från en instrument panel till en inblick och Rekommenderad åtgärd.

Den här genom gången är en av flera för säkerhets & Compliance Center. Information om hur du navigerar i rapporter och insikter finns i avsnittet närliggande information.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. För att gå direkt till sidan **säkerhets instrument panel** <https://protection.office.com/searchandinvestigation/dashboard> .

  Du kan visa inblick från fler än en instrument panel i säkerhets & Compliance Center. Oavsett vilken instrument panel du tittar på, ger inblicken samma uppgifter och gör att du snabbt kan utföra samma uppgifter.

- Du måste tilldelas behörigheter innan du kan utföra procedurerna i det här avsnittet. Om du vill använda falsk IT-insikt måste du vara medlem i någon av följande roll grupper:

  - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
  - **Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).
  - **Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
  - **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Du aktiverar och inaktiverar förfalsknings information i AntiPhishing-principer för ATP. Mer information finns i [Konfigurera AntiPhishing-principer för ATP i Microsoft 365](configure-atp-anti-phishing-policies.md).

- I Microsoft 365-organisationer med Exchange Online-postlådor och i fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor kan du använda falsk intelligens för att övervaka och hantera avsändare som skickar dig overifierade meddelanden. Mer information finns i [Konfigurera förfalskningsinformation i Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Öppna inblicken för falsk identitet i säkerhets & efterlevnad

1. Gå till instrument panelen **Threat Management** i säkerhets & efterlevnad \> **.**

2. Leta efter något av följande i raden **insikter** :

   - **Förfalsknings intelligens är aktiverat**: inblicken heter **falska domäner som inte kunde verifieras av de senaste 30 dagarna**. Det här är standardinställningen.

   - **Förfalsknings intelligens är inaktiverat**: inblicken i namngivna **Aktivera förfalsknings skydd**och när du klickar på den kan du aktivera förfalsknings intelligens.

3. Inblicken på instrument panelen visar information så här:

   ![Skärm bild av inblick i Spoof intelligens](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Denna inblick har två lägen:

   - **Insight-läge**. Om du har en förfalsknings princip aktive rad visar inblicken hur många e-postmeddelanden som har påverkats av våra förfalsknings funktioner under de senaste 30 dagarna.

   - **Vad händer om-läge**. Om du inte har någon förfalsknings princip aktive rad visar inblicken hur många e-postmeddelanden  *som har*  påverkats av våra förfalsknings uppgifter under de senaste 30 dagarna.

   Oavsett vilket är de falska domänerna som visas i inblicken indelade i två kategorier: **misstänkta domän par** och **icke misstänkt domän par**. Dessa kategorier är indelade i tre olika buckets för att du ska kunna granska.

   Ett **domän par** är en kombination av från-adressen och den sändande infrastrukturen:

   - Från-adressen är avsändarens e-postadress som visas i e-postklienter. Adressen identifierar e-postmeddelandets upphovsman. Det vill säga, postlådan för personen eller systemet som ansvarar för att skriva meddelandet. Denna adress kallas också `5322.From` adress.

   - Den sändande infrastrukturen, eller avsändaren, är domän domänen för omvänd DNS-sökning (PTR-post) för den sändande IP-adressen. Om den sändande IP-adressen inte har någon PTR-post identifieras avsändaren av den sändande undernätet med den 255.255.255.0 nät masken i CIDR-notation (/24). Om IP-adressen till exempel är 192.168.100.100 är avsändarens fullständiga IP-adress 192.168.100.100/24.

   **Misstänkta domän par** är:

   - **Falska säkerhets**problem: Microsoft 365 fick starka signaler som de här domänerna är misstänkta, baserat på de historiska sändnings mönstren och platsens ryktes poäng. Microsoft 365 är mycket säkert att domänerna är falska och att meddelanden som skickas från dessa domäner är mindre troligt att de är felfria.

   - **Falska problem med måttlig exakthet**: Microsoft 365 tog emot måttliga signaler som de här domänerna är misstänkta, baserat på historiska sändnings mönster och företagets ryktes poäng. Office 365 är ganska säkert med att domänerna är falska och att meddelanden som skickas från dessa domäner är giltiga. Den här Bucket har större chans att innehålla falskt positiva (FPs) än en Spoof-Bucket med hög exakthet.

   - **Icke misstänkt domän par** (inklusive **räddad förfalskning**): räddade förfalskningar är domäner som inte har de explicita autentiseringsmetoderna för kontroll av [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)), men klarade med den implicita kontrollen av e-postverifikationen ([sammansatt verifikation](email-validation-and-authentication.md#composite-authentication)). Därför har Microsoft 365 räddat e-postmeddelandet och ingen åtgärd mot förfalskning vidtogs för meddelandet.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Visa detaljerad information om misstänkta domän par från inblicken för falska uppgifter

1. Klicka på något av de här domän paren (High, måttlig eller räddat) i den här funktionen.

   Sidan med **information om falska** uppgifter visas med en lista över avsändare som skickar overifierad e-post till din organisation. Informationen på den här sidan hjälper dig att avgöra om falska meddelanden är godkända eller om du behöver vidta ytterligare åtgärder. Du kan sortera informationen efter antal meddelanden, det datum då datafilen senast upptäcktes och mer. (Klicka på kolumn rubriker, till exempel **antal meddelanden** eller **senaste**).)

2. Välj ett objekt i tabellen för att öppna en informations ruta som innehåller omfattande information om domän paret, inklusive orsaken till att vi upptäckte att det här är en domän sammanfattning, WhoIs information om avsändaren och liknande e-postmeddelanden som vi har sett i din klient organisation från samma avsändare. Härifrån kan du också välja att lägga till eller ta bort domän paret från **AllowedToSpoof** Safe delistion.

   ![Skärm bild av en domän i informations fönstret för förfalsknings information](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Lägga till eller ta bort en domän från AllowedToSpoof Safe Sender List

Du lägger till eller tar bort en domän från AllowedToSpoof Safe details list och läser in domän paret i informations fönstret i inblicken med falsk syn. Ställ in växlings knappen på motsvarande sätt.

Detta ändrar den unika kombinationen av domän par i den falska domänen och den sändande infrastrukturen och ger inte täckning för hela den falska domänen eller den sändande infrastrukturen i isolering.

Om du till exempel lägger till följande domän par i listan Tillåt avsändare för AllowedToSpoof:  *falsk domän*  "gmail.com" och *skickar infrastruktur* "TMS *. MX.com",* kommer endast e-post från det domän paret att tillåtas för falska. Andra avsändare försöker få falska falsk "gmail.com" och andra domäner som "tms.mx.com" försöker att skydda förfalskningarna genom förfalsknings intelligens.

## <a name="related-topics"></a>Relaterade ämnen

[Skydd mot förfalskning i Microsoft 365](anti-spoofing-protection.md)
