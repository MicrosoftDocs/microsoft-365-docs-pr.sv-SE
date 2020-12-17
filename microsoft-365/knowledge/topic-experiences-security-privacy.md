---
title: Ämnets säkerhet och integritet
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du planerar för funktioner för säkerhet och sekretess i Microsoft 365
ms.openlocfilehash: b3c33a49b8273c5f7830f08de17af9757a858413
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698503"
---
# <a name="topic-experiences-security-and-privacy"></a>Ämnets säkerhet och integritet

Avsnitts upplevelser använder befintliga innehålls säkerhets funktioner i Microsoft 365, tillsammans med kontroller för kunskaps nätverk, för att styra vilket AI-genererat innehåll som visas för användare i organisationen. Det är en kombination av säkerhets inställningar för Microsoft 365 (behörigheter till webbplatser, filer och mappar) och olika administratörs inställningar för ämnen som avgör vad en viss användare kan se.

Om du konfigurerar kunskaps nätet ändras inte befintliga åtkomst kontroller för innehåll i organisationen. Användarna ser bara vad de redan har åtkomst till.

I den här artikeln beskrivs hur erfarenheter fungerar från ett säkerhets perspektiv och alternativen som kunskaps administratörer och kunskaps chefer måste kontrol lera ämnets synlighet. Läs den här artikeln som en del av [planeringen av ämnen](plan-topic-experiences.md).

Du bör vara bekant med [avsnitts upplevelser](topic-experiences-overview.md), [ämnes Center](topic-center-overview.md)och hur du [arbetar med ämnen i ämnes centret](manage-topics.md) innan du läser den här artikeln.

## <a name="what-users-can-see-in-topics"></a>Vad användarna kan se i ämnen

För att se ämnen måste en användare:

- Har en licens för ämne
- Vara en [ämnes läsare](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [deltagare eller kunskaps chef](topic-experiences-user-permissions.md)

De här två sakerna ger användarna åtkomst till ämnes Center och låter dem se högdagrar och ämnes kort.

Ämnes deltagare har dessutom behörigheterna [skapa och redigera](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) för ämnen och kunskaps cheferna kan bekräfta eller ta bort ämnen.

När ett ämne först identifieras kan kunskaps cheferna se det i ämnes centret. Beroende på vad som är komplett och relevans för ämnet kan ämnena som visas eller kanske inte visas i ämnes kort.

Ämnen kan innehålla information som genererats av AI och information som lagts till eller redigerats av ämnes deltagare eller kunskaps chefer.

- Information i ett ämne som lagts till av AI visas bara för personer som har till gång till käll innehållet.
- Text som har lagts till manuellt eller redigerats av en ämnes deltagare eller kunskaps chef visas för alla som kan se avsnittet.

Avsnitts läsare och deltagare kan se en lista över bekräftade och publicerade ämnen i ämnes centret, men de avsnitts uppgifter som en viss person kan se beror på vilka behörigheter de har till käll materialet och om avsnittet har redigerats manuellt.

I följande tabell beskrivs vad användare – avsnitts läsare, deltagare och kunskaps chefer – kan se i ett visst ämne baserat på deras behörigheter.

|Ämnes objekt|Vad användarna kan se|
|:---------|:------------------|
|Namn på avsnitt|Användare kan se ämnes namnet i alla ämnen i ämnes centret. Vissa ämnen kanske inte visas om de har en liten sökrelevans till användaren.|
|Beskrivning av ämnet|AI-genererade beskrivningar visas endast för användare som har behörighet till käll innehållet. Manuellt angivna eller redigerade beskrivningar visas för alla användare.|
|Kontakter|Fästa personer visas för alla användare. Föreslagna personer visas bara för användare som har behörighet till käll innehållet.|
|Hjälpfiler|Filer visas endast för användare som har behörighet till käll innehållet.|
|Målsidor|Sidor visas bara för användare som har behörighet till käll innehållet.|
|Sidor|Webbplatser visas bara för användare som har behörighet till käll innehållet.|

## <a name="best-practices"></a>Metodtips

Ämnen kan visa information om användare baserat på deras befintliga behörigheter till innehåll. I Microsoft 365 finns flera olika sätt att se till att känsligt innehåll begränsas till lämpliga användare. Utöver standard grupp-eller webbplats behörigheter kan du använda [känslighets etiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) eller [förhindra data förlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) för att begränsa åtkomsten till innehåll och [åtkomst granskningar](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) för att regelbundet granska användarnas åtkomst till känslig information.

Vi rekommenderar att du använder dessa verktyg för att se till att dina innehålls behörigheter är korrekt inställda i organisationen. Avsnitts upplevelser kan ge användarna användbar och lämplig information.

Om det finns avsnitt som du vill utesluta helt från avsnitts upplevelser kan du också:

- [Exkludera känsliga SharePoint-webbplatser från identifiering av avsnitt](topic-experiences-discovery.md#select-sharepoint-topic-sources). Innehållet på dessa webbplatser visas inte i ämnes upplevelser.

- [Utelämna ämnen efter namn](topic-experiences-discovery.md#exclude-topics-by-name). Avsnitt som uttryckligen utesluts visas inte i ämnes upplevelser.

- Få kunskaps cheferna att ta bort ämnen i ämnes centret.

Dessutom rekommenderar vi följande metod tips:

- Rekrytera kunskaps chefer från olika delar av organisationen. Att ha kunskaps chefer med en mängd expertis-och åtkomst till underliggande innehåll som används av AI – kan hjälpa dig att granska den mest användbara kunskapen för användarna och ta bort känslig information om den hittas.

- Konfigurera ett arbets flöde för att begära ändringar. Kunskaps chefer eller grupp-eller webbplats ägare bör ha en process där de kan begära uteslutning av ämnen eller webbplatser som nya projekt startas inom organisationen eller om de hittar innehåll med olämpliga behörighets inställningar.

- Observera publiken och känsligheten för informationen när du skapar beskrivningar. De här beskrivningarna kan vara synliga för användare som inte har behörighet till käll innehållet för ämnet.

Du kan ändra behörigheterna för enskilda ämnes sidor för att begränsa åtkomsten till en viss grupp användare, men vi rekommenderar inte den här metoden på grund av den goda administrativa ansträngningen.

## <a name="see-also"></a>Se även

[Konfigurera Teams med tre skyddsnivåer](../solutions/configure-teams-three-tiers-protection.md)

[Planera ämnen](plan-topic-experiences.md)

[Konfigurera ämnen](set-up-topic-experiences.md)
