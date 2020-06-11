---
title: Distribuera informationsskydd för dataskydd med Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Konfigurera säkerhets- och tjänstinfrastrukturen för att skydda din information och följa datasekretessreglerna.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695116"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Distribuera informationsskydd för dataskydd med Microsoft 365

Den här lösningen ger vägledning om hur du planerar för och skyddar personuppgifter som lagras i Microsoft 365-tjänster och eventuellt omfattas av dataskyddsbestämmelser som EU:s allmänna dataskyddsförordning (GDPR). Den här lösningen fokuserar på tillämpliga funktioner för microsofts informationsskydd och efterlevnad, Microsofts efterlevnadsresultat och bedömningsverktyg som hjälper dig att känna till dina data. 
 
Ytterligare information finns också om användningen av Microsofts identitets-, enhets- och hotskyddskontroller för dina datasekretessbehov samt verktyg för identifiering av dataincidenter och svar. 

## <a name="organization-of-this-guidance-material"></a>Organisation av detta vägledningsmaterial

För att hjälpa dig att förstå de Microsoft 365-verktyg som finns tillgängliga för att identifiera, hantera, kontrollera och övervaka personliga data som omfattas av en eller flera sekretessrelaterade bestämmelser, är den här vägledningen uppdelad i avsnitt.
 
![Distribuera informationsskydd för datasekretessregler](../media/information-protection-deploy/information-protection-deploy-grid.png)

Var och en av dessa avsnitt motsvarar en separat artikel i den här lösningen.

>[!Note]
>Om du redan är bekant med dina datasekretessskyldigheter och utför mot en befintlig plan kanske du vill fokusera på vägledningen Förhindra, Skydda, Behåll och Undersök.

>[!Important]
>Att följa den här vägledningen kommer inte nödvändigtvis att göra dig kompatibel med någon datasekretessreglering, särskilt med tanke på antalet steg som krävs som ligger utanför ramen för funktionerna. Du är ansvarig för att säkerställa din efterlevnad och att konsultera dina juridiska och efterlevnadsteam eller för att söka vägledning och råd från tredje part som är specialiserade på efterlevnad.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Planera: Bedöma datasekretessrisker och identifiera känsliga objekt 

Att bedöma datasekretessregler och risker som din organisation omfattas av är ett viktigt första steg att ta innan du börjar implementera förbättringar, inklusive de som kan uppnås via Microsoft 365-konfiguration. Detta kan omfatta en övergripande beredskapsbedömning eller identifiering av särskilda känsliga informationstyper som omfattas av regelkontroller som din organisation måste följa, samt förekomsten av dem i din Microsoft 365-miljö.

Mer information finns i [Bedöma datasekretessrisker och identifiera känsliga objekt](information-protection-deploy-assess.md).

## <a name="track-use-compliance-score-and-compliance-manager"></a>Spår: Använd efterlevnadspoäng och efterlevnadshanterare 

Compliance Score and Compliance Manager innehåller en integrerad uppsättning verktyg som är tillgängliga i Microsoft 365 Compliance admin center och Services Trust Portal. Tillsammans ger dessa verktyg dig en inbyggd förmåga att spåra och hantera förbättringsåtgärder totalt sett samt de som rör flera datasekretessbestämmelser som du utsätts för.

Med verktygen kan du också utnyttja inbyggda bedömningsmallar som är specifika för varje förordning, där du kan spåra åtgärdsobjekt för varje vald bedömningsmall, samt visa specifika regelkontroller och relatera dem till specifika åtgärder.

Mer information finns i [Använd efterlevnadspoäng och efterlevnadshanteraren för att hantera förbättringsåtgärder](information-protection-deploy-compliance.md).

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Förhindra: Använd identitet, enhet och hotskydd för datasekretessreglering

Microsoft 365 tillhandahåller ett antal funktioner för identitets-, enhets- och hotskydd som du kan använda för att följa efterlevnaden av datasekretessregleringen. 

Mer information finns i [Använda identitet, enhet och hotskydd för dataskyddsreglering](information-protection-deploy-identity-device-threat.md).

I den här artikeln beskrivs kortfattat vad de dataskyddsbestämmelser som vanligtvis kräver inom dessa områden och innehåller en lista över relaterade Microsoft 365-lösningar, med länkar till mer information som hjälper dig att hantera eventuella implementeringskrav. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Skydda information som omfattas av dataskyddsförordningen

Dataskyddsregler dikterar ett antal kontroller för skydd av personuppgifter som kan användas i din miljö, inklusive mer än fyrtio Protect Information-kontroller över bara de fyra dataskyddsbestämmelserna i vår urvalsuppsättning AV GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act) och Brazil Data Protection Act (LGPD).

Mer information finns i [Skydda information som omfattas av datasekretessreglering i din organisation](information-protection-deploy-protect-information.md).

I den här artikeln beskrivs de viktigaste kontrollscheman som kan användas för att tillgodose informationsskyddsbehov för datasekretess i din organisation.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Behåll: Reglera information som omfattas av dataskyddsförordningen

Datasekretessbestämmelser kräver kontroller för styrning av personlig information som kan användas i din miljö, inklusive mer än tjugofyra kontroller i de fyra datasekretessreglerna i vår urvalsuppsättning GDPR, CCPA, HIPAA-HITECH och LGPD.

Mer information finns i [Styra information som omfattas av dataskyddsreglering i din organisation](information-protection-deploy-govern.md).

Även om reglerna för datasekretess kan vara vaga när det gäller informationsstyrning, &mdash; till exempel målmedveten lagring, borttagning och arkivering &mdash; av den här artikeln innehåller de primära kontrollscheman som du kan använda behov av adressinformationsstyrning för datasekretess i din organisation.

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a>Undersöka: Övervaka och svara på datasekretessreglering

Det finns Microsoft 365-funktioner som hjälper dig att övervaka, undersöka och svara på datasekretessincidenter i organisationen när du operationaliserar relaterade funktioner. 

Att ha processer, förfaranden och annan dokumentation för var och en av dessa kan vara viktigt för att visa efterlevnad för tillsynsorgan.

Mer information finns i [Övervaka och svara på datasekretessincidenter i organisationen](information-protection-deploy-monitor-respond.md).
