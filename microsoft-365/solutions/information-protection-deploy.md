---
title: Distribuera informationsskydd för bestämmelser om datasekretess med Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: Konfigurera informationsskydd i Microsoft 365 för dataskyddsföreskrifter som GDPR och California Consumer Privacy Act (CCPA), inklusive Microsoft Teams, SharePoint och e-post.
ms.openlocfilehash: c0ffe7cf850ec6e7ae8c974f983ce43668bf6f30
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287717"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Distribuera informationsskydd för bestämmelser om datasekretess med Microsoft 365

Din organisation kan omfattas av regionala bestämmelser om datasekretess som kräver att du skyddar, hanterar och ger rättigheter och kontroll över personlig information som lagras i din IT-infrastruktur, både lokalt och i molnet. Det bästa exemplet på en dataskyddsförordning är EU:s dataskyddsförordning (GDPR). Om datasekretessföreskrifter inte efterlevs kan det leda till betydande vite.

Exempel på datatyper i Microsoft 365 är chattsessioner i Microsoft Teams, e-postmeddelanden i Exchange och filer i SharePoint och OneDrive. Den här lösningen ger vägledning för hur du bedömer risker och vidta lämpliga åtgärder för att skydda personuppgifter i Microsoft 365. Detta omfattar identifiering av personlig information så att du kan skydda, styra och hantera datasekretesstillbud.

![Vad är informationsskydd för bestämmelser om datasekretess](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

Ytterligare information ges också om hur du använder Microsoft 365, kontroller av identitet, enhet och hot för dina datasekretessbehov.

Titta på den här videon för att få en översikt över distributionsprocessen.
<br>
<br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4NHCQ]

De Microsoft 365 funktioner hjälper dig att uppfylla kriterierna för att skydda information.

| Resurs eller funktion | Beskrivning | Licensiering |
|:-------|:-----|:-------|
| Efterlevnadshanteraren | Hantera aktiviteter för regelefterlevnad, få en övergripande poäng för din aktuella efterlevnadskonfiguration och hitta rekommendationer för förbättring. Det här är ett arbetsflödesbaserat riskutvärderingsverktyg i Microsoft 365 Efterlevnadscenter. | Microsoft 365 E3 och E5 |
| Microsoft Defender för Office 365 | Skydda dina Microsoft 365-appar och data – t.ex. e-postmeddelanden, Office-dokument och samarbetsverktyg – från angrepp. | Microsoft 365 E3 och E5 |
| Känslighetsetiketter | Klassificera och skydda organisationens data utan att hindra användarnas produktivitet och deras förmåga att samarbeta. Placera etiketter med olika skyddsnivåer på e-post, filer eller webbplatser. | Microsoft 365 E3 och E5 |
| Dataförlustskydd (DLP) | Identifiera, varna och blockera riskabel, oavsiktlig eller olämplig delning av data som innehåller personlig information, både internt och externt. | Microsoft 365 E3 och E5 |
| Etiketter och principer för kvarhållning av data | Implementera kontroller för informationsstyrning. De kan innefatta att fastställa hur lång tid data (till exempel personuppgifter relaterade till kunder) ska följa organisationens regler eller dataregler. | Microsoft 365 E3 och E5 |
| E-postkryptering | Skydda personliga data genom att skicka och ta emot krypterade e-postmeddelanden mellan personer inom och utanför organisationen. | Microsoft 365 E3 och E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organisation av vägledningen i den här lösningen

För att hjälpa dig att Microsoft 365 de verktyg som finns för att hjälpa dig att uppfylla en eller flera sekretessrelaterade bestämmelser är den här vägledningen ordnad i avsnitt.

![Steg för att implementera informationsskydd för bestämmelser om datasekretess](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

Vart och ett av dessa avsnitt motsvarar en separat artikel i den här lösningen.

> [!NOTE]
> Om du redan är bekant med dina sekretesskrav för data och kör mot ett befintligt abonnemang kanske du vill fokusera på vägledningen Förhindra, skydda, behålla och undersöka.

> [!IMPORTANT]
> Om du följer de här anvisningarna följer du inte nödvändigtvis alla regler om datasekretess, särskilt när det gäller antalet steg som krävs utanför funktionerna. Du är ansvarig för att säkerställa din efterlevnad och att kontakta dina grupper för lagstiftning och efterlevnad eller söka vägledning och råd från tredje part som är berörda av efterlevnad.

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Planera: Utvärdera datasekretessrisker och identifiera känsliga objekt

Att utvärdera bestämmelser om datasekretess och risker som finns i organisationen är ett viktigt första steg innan du börjar implementera förbättringar, inklusive konfigurering av funktioner i Microsoft 365. Det här arbetet kan omfatta en övergripande bedömning av eller identifiering av särskilda typer av känslig information som omfattas av reglerande kontroller som din organisation behöver följa.

Mer information finns i Utvärdera [datasekretessrisker och identifiera känsliga objekt.](information-protection-deploy-assess.md)

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>Spåra: Kör riskbedömning och kontrollera ditt efterlevnadsresultat

Efterlevnadshanteraren, som finns i Microsoft 365 Efterlevnadscenter, ger dig en inbyggd möjlighet att spåra och hantera förbättringsåtgärder övergripande och de som gäller flera bestämmelser om datasekretess som gäller för dig.

Du kan använda inbyggda utvärderingsmallar som är specifika för varje regel, där du kan spåra uppgifter för varje vald bedömningsmall, visa specifika regler och relatera dem till specifika åtgärder.

Mer information finns i Hantera [förbättringsåtgärder med efterlevnadshanteraren.](information-protection-deploy-compliance.md)

## <a name="prevent-protect-personal-data"></a>Förhindra: Skydda personliga data

Microsoft 365 tillhandahåller funktioner för skydd mot identitet, enheter och hot som du kan använda för att uppfylla efterlevnad av datasekretess.

Mer information finns i Använda [identitet, enhet och skydd mot datasekretess.](information-protection-deploy-identity-device-threat.md)

Den här artikeln ger en kort beskrivning av vad sekretessregler för data vanligtvis anropar för dessa områden och innehåller en lista med relaterade Microsoft 365-lösningar, med länkar till mer information som hjälper dig att hantera eventuella implementeringskrav.

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Skydda information som omfattas av datasekretess

Bestämmelser om datasekretess dikterar ett antal kontroller för skydd av personuppgifter som kan användas i din miljö, inklusive fler än 40 kontroller för att skydda information i bara de fyra bestämmelser om datasekretess i vår exempeluppsättning av GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States Health Care Privacy Act) och Brazil Data Protection Act (LGPD).

Mer information finns i Skydda [information som omfattas av datasekretessförordningen i din organisation.](information-protection-deploy-protect-information.md)

I den här artikeln beskrivs de huvudsakliga kontrollscheman som kan användas för att tillgodose informationsskyddsbehoven för organisationens datasekretess.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Behåll: Reglera information som omfattas av sekretessförordningen

Informationssekretessbestämmelser anropar för kontroller för personlig informationsstyrning som kan användas i din miljö, inklusive fler än 24 kontroller över de fyra datasekretessreglerna i vår exempeluppsättning av GDPR, CCPA, HIPAA-HITECH och LGPD.

Mer information finns i Reglera [information som omfattas av sekretessförordningen för data i din organisation.](information-protection-deploy-govern.md)

Även om datasekretessreglerna kan vara vaga när det gäller informationsstyrning, till exempel syftesfull lagring, borttagning och arkivering i den här artikeln, placerar vi de primära kontrollscheman som du kan använda för att tillgodose informationsstyrningsbehov för datasekretess i &mdash; &mdash; organisationen.

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>Kontrollera: Övervaka, undersök och svara på sekretessincidenter för data

Det finns Microsoft 365 funktioner som hjälper dig att övervaka, undersöka och svara på datasekretessincidenter i din organisation när du driftiserar relaterade funktioner.

Att ha processer, procedurer och annan dokumentation för att använda dessa funktioner kan vara viktigt för att visa efterlevnad för reglerande myndigheter.

Mer information finns i Övervaka [och svara på sekretessincidenter för data i din organisation.](information-protection-deploy-monitor-respond.md)

## <a name="training-for-administrators"></a>Utbildning för administratörer

De här utbildningsmodulerna från Microsoft Learn kan hjälpa dig att lära dig mer om funktioner som är viktiga för informationsskydd.


#### <a name="information-protection"></a>Informationsskydd

|Utbildning:|Skydda företagsinformation med Microsoft 365|
|:---|:---|
|![Teams för utbildning om informationsskydd](../media/protect-enterprise-information-microsoft-365.svg)|Det är svårare än någonsin att skydda och skydda organisationens information. I utbildningsvägen Skydda företagsinformation med Microsoft 365 diskuteras hur du skyddar känslig information från att oavsiktligt skriva över eller felaktigt använda data, hur du identifierar och klassificerar data, hur du skyddar dem med känslighetsetiketter och hur du både övervakar och analyserar din känsliga information för att skydda mot förlust. Den här utbildningsvägen kan hjälpa dig att förbereda för Microsoft 365 Certified: Security Administrator Associate och Microsoft 365 Certified: Enterprise Administration Expert-certifieringar.<br><br>1 t - Learning sökväg - 5 moduler|

> [!div class="nextstepaction"]
> [Starta >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Identitet och åtkomst

|Utbildning:|Skydda identitet och åtkomst med Azure Active Directory|
|:---|:---|
|![Ikon för identitets- och åtkomstutbildning](../media/protect-identity-and-access-with-microsoft-365.svg)|Utbildningsvägen för identitet och åtkomst omfattar de senaste identitets- och åtkomsttekniker, verktyg för att förstärka autentisering och vägledning om identitetsskydd i organisationen. Med microsofts teknik för åtkomst och identitet kan du skydda organisationens identitet, oavsett om den är lokal eller i molnet, och ge dina användare möjlighet att arbeta säkert från valfri plats. Den här utbildningsvägen kan hjälpa dig att förbereda för Microsoft 365 Certified: Security Administrator Associate och Microsoft 365 Certified: Enterprise Administration Expert-certifieringar.<br><br>2 t 52 min - Learning bana - 6 moduler|

> [!div class="nextstepaction"]
> [Starta >](/learn/modules/m365-identity-overview/introduction/)