---
title: Distribuera informations skydd för data integritets regler med Microsoft 365
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
description: Konfigurera säkerhet och tjänst infrastruktur för att skydda din information och följa data integritets regler.
ms.openlocfilehash: 4296e2f08d9dada62cc45226885d9519a33e6532
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655823"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Distribuera informations skydd för data integritets regler med Microsoft 365

Din organisation kan vara föremål för nationella data integritets regler som kräver att du skyddar, hanterar och ger rättigheter och kontroll över person uppgifter som lagras i IT-infrastrukturen, inklusive både lokalt och i molnet. Det bästa exemplet på en data integritets förordning är Europeiska unionens allmänna data skydds förordning (GDPR). Underlåtenhet att uppfylla data integritets regler kan leda till avsevärda problem.

Exempel på data typer i Microsoft 365 inkluderar chatt i Microsoft Teams, e-postmeddelanden i Exchange och filer i SharePoint och OneDrive. Den här lösningen ger råd om hur man bedömer risker och identifierar information, skyddar, styr och svarar på data integritets incidenter för person uppgifter som lagras i Microsoft 365-tjänster som lyder under data integritets regler.

![Vad är informations skydd för data integritets regler](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

Ytterligare information om användning av Microsoft 365-inställningar för identitets-, enhets-och hot skydd för dina data integritets behov. 

För att uppfylla villkoren för att skydda information om efterlevnad av data integritets regler, Använd dessa Microsoft 365-funktioner och-funktioner.

| Resurs eller funktion | Beskrivning | Licensiering |
|:-------|:-----|:-------|
| Efterlevnadshanteraren | Hantera efterlevnad av myndighets aktiviteter, få en total poäng för din aktuella konfiguration av efterlevnad och hitta rekommendationer för förbättringar i det här arbets flödes verktyget för riskbedömning i Microsoft 365 Compliance Center. | Microsoft 365 E3 och E5 |
| Office Avancerat skydd (ATP) | Skydda dina Microsoft 365-appar och data – t.ex. e-postmeddelanden, Office-dokument och samarbetsverktyg – från angrepp. | Microsoft 365 E3 och E5 | 
| Känslighetsetiketter | Med hjälp av etiketter med olika nivåer av skydd för e-post, filer och webbplatser kan du klassificera och skydda din organisations data utan att hindra användarnas produktivitet och möjligheter att samarbeta. | Microsoft 365 E3 och E5 |
| Dataförlustskydd (DLP) | Identifiera, varna för och blockera riskfylld, oavsiktlig eller olämplig delning, t.ex. av data som innehåller personuppgifter, både internt och externt. | Microsoft 365 E3 och E5 | 
| Etiketter och principer för kvarhållning av data | Implementera kontrollerna för informationsstyrning, t.ex. hur länge data ska behållas och kraven för lagring av personuppgifter för kunder, för att uppfylla organisationens principer och dataföreskrifter. | Microsoft 365 E3 och E5 |
| E-postkryptering | Skicka och ta emot krypterade e-postmeddelanden som innehåller reglerade data, t.ex. personliga data om kunder, mellan personer i och utanför din organisation. | Microsoft 365 E3 och E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organisation för vägledningen i den här lösningen

För att hjälpa dig att förstå de Microsoft 365-verktyg som är tillgängliga för att identifiera, hantera, kontrol lera och övervaka person uppgifter som gäller för en eller flera integritets regler är den här vägledningen ordnad i avsnitt.
 
![Steg för att implementera informations skydd för data integritets regler](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

Varje avsnitt motsvarar en separat artikel i den här lösningen.

>[!Note]
>Om du redan är bekant med dina data integritets åtaganden och kör ett befintligt abonnemang kanske du vill fokusera på att råd för att förhindra, skydda, hålla och undersöka.

>[!Important]
>Om du följer den här vägledningen blir du inte nödvändigt vis kompatibel med någon data integritets förordning, särskilt med tanke på hur många steg som krävs för att funktionerna ska bli ännu bättre. Du är ansvarig för att se till att du uppfyller dina krav och att du kan söka råd och råd från tredje part som specialiserar sig på efterlevnaden.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Planera: utvärdera data integritets risker och identifiera känsliga objekt

Att utvärdera data integritets regler och risker som din organisation är föremål för är en viktig åtgärd innan du börjar implementera förbättringar, inklusive de som kan nås via Microsoft 365-konfigurationen. Detta kan inkludera en övergripande beredskaps bedömning eller identifiering av särskilda känsliga informations typer som lyder under myndighets regler som din organisation måste uppfylla, samt förekomsten av dem i din Microsoft 365-miljö.

Mer information finns i [utvärdera data integritets risker och identifiera känsliga objekt](information-protection-deploy-assess.md).

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>Spåra: kör riskbedömning och kontrol lera resultatet

Compliance Manager, som är tillgänglig i Microsoft 365 Compliance Center, ger dig en inbyggd funktion för att spåra och hantera förbättrings åtgärder generellt samt de som är relaterade till flera informations integritets regler som gäller för dig.

Använd inbyggda Analyskolumnmallar som är specifika för varje förordning, där du kan spåra uppgifter för varje bedömnings mall som valts, samt för att visa särskilda kontroller och relatera dem till vissa åtgärder.

Mer information finns i [använda överensstämmelse hanteraren för att hantera förbättrings åtgärder](information-protection-deploy-compliance.md).

## <a name="prevent-protect-personal-data"></a>Förhindra: skydda person uppgifter

Microsoft 365 tillhandahåller ett antal funktioner för identitets-, enhets-och hot skydd som du kan använda för att uppfylla data integritets reglernas efterlevnad. 

Mer information finns i [använda identitets-, enhets-och hot skydd för data integritets reglering](information-protection-deploy-identity-device-threat.md).

I den här artikeln beskrivs vad som gäller för data integritets reglerna i allmänhet för dessa områden och ger en lista över relaterade Microsoft 365-lösningar, med länkar till mer information som hjälper dig att hantera eventuella implementerings krav. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Skydda information som lyder under data integritets förordning

Data integritets regler anger ett antal skydds kontroller för person uppgifter som kan användas i din miljö, inklusive mer än 40 skydda informations kontroller med bara de fyra data integritets reglerna i vår GDPR, California konsument skydd Act (CCPA), HIPAA-HITECH (USA Health Policy för sjukvårds vård) och språkskydds Act (LGPD).

Mer information finns i [skydda information som lyder under data integritets regler i din organisation](information-protection-deploy-protect-information.md).

I den här artikeln beskrivs de viktigaste kontroll systemen som kan användas för att skydda informations skydd i din organisation.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Behåll: styr information som lyder under data integritets förordning

Data integritets regler för att ringa till kontroller för person uppgifter som kan användas i din miljö, inklusive fler än 21 kontroller i de fyra olika sekretess bestämmelserna i vårt exempel på GDPR, CCPA, HIPAA-HITECH och LGPD.

Mer information finns i [regler för informations integritets reglering i din organisation](information-protection-deploy-govern.md).

Även om data integritets reglerna kan vag information &mdash; som betydelsefullt bevarande, borttagning och arkivering &mdash; av den här artikeln innehåller de primära kontroll systemen som du kan använda för att hantera data integritet i din organisation.

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>Undersök: övervaka, undersöka och svara på data integritets tillbud

Det finns Microsoft 365-funktioner som hjälper dig att övervaka, undersöka och svara på data integritets tillbud i din organisation när du operationalize relaterade funktioner. 

Att ha processer, procedurer och annan dokumentation för var och en av dessa kan vara viktiga för att påvisa efterlevnad av myndighets organ.

Mer information finns i [övervaka och svara på data integritets tillbud i din organisation](information-protection-deploy-monitor-respond.md).
