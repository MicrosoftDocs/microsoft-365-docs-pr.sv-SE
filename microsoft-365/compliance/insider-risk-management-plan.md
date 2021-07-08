---
title: Planera för hantering av insiderrisker
description: Lär dig hur du planerar att använda insider-riskhanteringsprinciper i din organisation.
keywords: Microsoft 365, insiderrisk, riskhantering, efterlevnad
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: a6a0ebb6ef15a6d4746d72a73feb16e53f89354e
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326789"
---
# <a name="plan-for-insider-risk-management"></a>Planera för hantering av insiderrisker

Innan du börjar med [insider-riskhantering](insider-risk-management.md) i din organisation finns det viktiga planeringsaktiviteter och överväganden som bör granskas av dina team för informationsteknik och efterlevnadshantering. Genom att noggrant förstå och planera för distribution inom följande områden kan du säkerställa att din implementering och användning av insider-riskhanteringsfunktioner går smidigt och följer metodtipsen för lösningen.

## <a name="work-with-stakeholders-in-your-organization"></a>Arbeta med intressenter i organisationen

Identifiera rätt intressenter i organisationen för att samarbeta för att vidta åtgärder för varningar och ärenden inom insider-riskhantering. Några rekommenderade intressenter att överväga att ta med i den inledande planeringen och arbetsflödet för [insider-riskhantering](insider-risk-management.md#workflow) är personer från följande områden i organisationen:

- Informationsteknik
- Efterlevnad
- Sekretess
- Säkerhet
- Personalavdelningen
- Villkor

## <a name="determine-any-regional-compliance-requirements"></a>Fastställa eventuella regionala efterlevnadskrav

Olika geografiska områden och organisationsområden kan ha efterlevnads- och sekretesskrav som skiljer sig från andra områden i organisationen. Arbeta med intressenterna i dessa områden för att säkerställa att de förstår efterlevnads- och sekretesskontroller i Insider-riskhantering och hur de ska användas i olika områden i organisationen. I vissa fall kan efterlevnads- och sekretesskrav kräva principer som utser eller begränsar vissa intressenter från undersökningar och ärenden utifrån ett ärende för en användare eller ett regelverk eller policykrav för området.

Om du har krav för att specifika intressenter ska vara inblandade i ärendeundersökningar som involverar användare i vissa regioner, roller eller avdelningar, kanske du vill implementera separata (även om identiska) [insider-riskhanteringsprinciper](insider-risk-management-policies.md) som är riktade till olika regioner och populationer. Den här konfigurationen gör det enklare för rätt intressenter att administrera och hantera ärenden som är relevanta för deras roller och regioner. Du kan även överväga att skapa processer och principer för regioner där slutanvändare och granskare talar samma språk som användarna för att effektivisera eskaleringsprocessen för varningar och ärenden inom insiderriskhantering.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planera arbetsflödet för granskning och undersökning

Välj dedikerade intressenter för att övervaka och granska aviseringar och ärenden regelbundet i [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/). Se till att du förstår hur du tilldelar olika intressenter till de olika rollgrupperna som är tillgängliga i Insider-riskhantering.

Beroende på strukturen hos ditt team för efterlevnadshantering finns alternativ för att tilldela användare till specifika rollgrupper för att hantera olika uppsättningar med insider-riskhanteringsfunktioner. Om du  vill visa fliken Behörigheter i Office 365 säkerhets- & Säkerhets- och efterlevnadscenter  i & och hantera rollgrupper, måste du vara tilldelad till rollgruppen Organisationshantering eller ha rollen *Rollhantering.* Välj bland de här rollgruppsalternativen när du konfigurerar insider-riskhantering:

| **Rollgrupp** | **Rollbehörigheter** |
| :------------- | :------------------- |
| **Insider-riskhantering** | Använd den här rollgruppen för att hantera insider-riskhantering för organisationen i en enda grupp. Genom att lägga till alla användarkonton för angivna administratörer, analytiker, ekonomi och granskare kan du konfigurera behörigheter för Insider-riskhantering i en enda grupp. Den här rollgruppen innehåller alla behörighetsroller för Insider-riskhantering och associerade behörigheter. Den här konfigurationen är det enklaste sättet att snabbt komma igång med insider-riskhantering och är en god passform för organisationer som inte behöver separata behörigheter som definierats för separata användargrupper. När du använder den här konfigurationen bör du se till att alltid ha minst en användare tilldelad till den här rollgruppen för att säkerställa att dina principer fungerar som förväntat och så att användaren kan skapa och redigera principer, konfigurera lösningsinställningar och granska hälsovarningar för principer. |
| **Insider-riskhanteringsadministratör** | Använd den här rollgruppen till att först konfigurera Insider-riskhantering och senare för att dela upp Insider-riskadministratörer i en definierad grupp. Användare i den här rollgruppen kan aktivera och visa analysinsikter och skapa, läsa, uppdatera och ta bort principer för insider-riskhantering, globala inställningar och tilldelningar av rollgrupper. När du använder den här konfigurationen bör du se till att alltid ha minst en användare tilldelad till den här rollgruppen för att säkerställa att dina principer fungerar som förväntat och så att användaren kan skapa och redigera principer, konfigurera lösningsinställningar och granska hälsovarningar för principer. |
| **Analytiker för hantering av interna risker** | Använd den här gruppen för att tilldela behörigheter till användare som fungerar som insider-riskfallsanalytiker. Användare i den här rollgruppen kan komma åt och visa alla varningar för Insider-riskhantering, fall, analysinsikter och meddelandemallar. De kan inte komma åt Insider-risken i Innehållsutforskaren. |
| **Utredare för hantering av interna risker** | Använd den här gruppen för att tilldela behörigheter till användare som ska agera som insider-riskgruppsbehörigheter. Användare i den här rollgruppen kan komma åt alla varningar för insider-riskhantering, ärenden, meddelandemallar och Innehållsutforskaren för alla ärenden. |
| **Insider-riskhanteringsgranskningar** | Använd den här gruppen för att tilldela behörigheter till användare som ska granska aktiviteter inom insider-riskhantering. Användare i den här rollgruppen kan komma åt granskningsloggen för Insider-risker. |

## <a name="understand-requirements-and-dependencies"></a>Förstå krav och beroenden

Beroende på hur du planerar att implementera principer för insider-riskhantering måste du ha rätt Microsoft 365 för licensieringsprenumerationer och förstå och planera för vissa lösningsförutsättningarna.

**Licensiering:** Insider-riskhantering finns tillgängligt som en del av ett brett urval Microsoft 365 licensprenumerationer. Mer information finns i [artikeln Komma igång med insider-riskhantering.](insider-risk-management-configure.md#subscriptions-and-licensing)

Om du inte har ett befintligt Microsoft 365 Enterprise E5-abonnemang och vill prova insider-riskhantering kan du lägga [](https://www.microsoft.com/microsoft-365/enterprise) till [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) i din befintliga prenumeration eller registrera dig för en utvärderingsversion av Microsoft 365 Enterprise E5.

**Krav på principmall:** Beroende på vilken principmall du väljer finns det krav som du måste förstå och planera för innan du konfigurerar insiderriskhantering i organisationen:

- När du använder **mallen Datastöld** genom avgående användare måste du konfigurera en hr-Microsoft 365-koppling för att regelbundet importera information om här och slutdatum för användarna i organisationen. Se artikeln [Importera data med HR-anslutning](import-hr-data.md) för steg-för-steg-vägledning för att konfigurera Microsoft 365 HR-anslutning för din organisation.
- När du **använder mallar för Dataläckor** måste du konfigurera minst en DLP-princip (Data Loss Prevention) för att definiera känslig information i organisationen och få varningar om insiderrisker för varningar om hög allvarlighetsgrad (DLP-princip). Se artikeln [Skapa, testa och ställa in en DLP-princip](create-test-tune-dlp-policy.md) för en steg-för-steg-vägledning för att konfigurera DLP-principer för din organisation.
- När du **använder mallar för brott mot** säkerhetsprinciper måste du aktivera Microsoft Defender för Slutpunkt för integrering av insiderriskhantering i Defender Säkerhetscenter för att importera aviseringar om säkerhetsöverträdelser. Stegvisa anvisningar för hur du aktiverar Defender för slutpunktsintegrering med Insider-riskhantering finns i artikeln Konfigurera avancerade funktioner i [Microsoft Defender.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features)
- När du **använder förvandrade** användarmallar måste du konfigurera en Microsoft 365 personalkontakt för att med jämna mellanrum importera prestanda- eller nedgraderingsstatusinformation för användare i organisationen. Se artikeln [Importera data med HR-anslutning](import-hr-data.md) för steg-för-steg-vägledning för att konfigurera Microsoft 365 HR-anslutning för din organisation.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Testa med en liten grupp användare i en produktionsmiljö

Innan du aktiverar lösningen i produktionsmiljön allmänt kan du överväga att testa principerna med ett litet antal produktionsanvändare samtidigt som du genomför nödvändiga ändringar för efterlevnad, sekretess och juridisk granskning i organisationen. Utvärdering av insider-riskhantering i en testmiljö skulle kräva att du skapar simulerade användaråtgärder och andra signaler för att skapa varningar för triage och fall för bearbetning. Den här metoden är inte praktisk för de flesta organisationer, så det är bättre att testa insider-riskhantering med en liten grupp användare i en produktionsmiljö.

Låt anonymiseringsfunktionen i principinställningarna vara aktiverad för att anonymisera användarnamn i insider-riskhanteringskonsolen under denna testning för att upprätthålla integriteten i verktyget. Den här inställningen skyddar integriteten för användare som har principmatchningar och kan öka objektivityen vid dataundersökning och analysgranskningar för insiderriskvarningar.

Om du inte ser några aviseringar direkt efter att du konfigurerat en princip för insiderriskhantering kan det innebära att tröskelvärdet för minsta risk inte har uppfyllts ännu. Ett bra sätt att kontrollera om principen utlöses och fungerar som förväntat är att se om användaren finns inom omfattningen för principen på **sidan** Användare.

## <a name="resources-for-stakeholders"></a>Resurser för intressenter

Dela dokumentation om insider-riskhantering med intressenter i organisationen som ingår i ditt arbetsflöde för hantering och åtgärder:

- [Skapa och hantera principer för hantering av insiderrisker](insider-risk-management-policies.md)
- [Undersöka Insider-riskaktiviteter](insider-risk-management-activities.md)
- [Vidta åtgärder för insiderriskärenden](insider-risk-management-cases.md)
- [Granska ärendedata med Innehållsutforskaren för Insider-risk](insider-risk-management-content-explorer.md)
- [Skapa mallar för insiderriskaviseringar](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Är du redo att börja?

Är du redo att konfigurera Insider-riskhantering för din organisation? Läs följande artiklar:

- [Kom igång med inställningar för Insider-riskhantering för](insider-risk-management-settings.md) att konfigurera globala principinställningar.
- [Kom igång med Insider-riskhantering för](insider-risk-management-configure.md) att konfigurera förutsättningar, skapa principer och börja ta emot aviseringar.
