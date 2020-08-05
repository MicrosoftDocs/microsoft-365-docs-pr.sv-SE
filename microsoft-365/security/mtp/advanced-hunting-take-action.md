---
title: Vidta åtgärder för avancerade jaktfrågeresultat i Microsoft Threat Protection
description: Ta snabbt itu med hot och påverkade tillgångar i dina avancerade jaktfrågeresultat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, vidta åtgärder
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4ebf220472db69d48127b805256e15246bd400cb
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552754"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Vidta åtgärder för avancerade jaktfrågeresultat

**Gäller:**
- Microsoft Hotskydd

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Du kan snabbt innehålla hot eller hantera komprometterade tillgångar som du hittar i [avancerad jakt](advanced-hunting-overview.md) med kraftfulla och omfattande åtgärdsalternativ. Med dessa alternativ kan du:

- Vidta olika åtgärder på enheter
- Karantänfiler

## <a name="required-permissions"></a>Nödvändiga behörigheter
För att kunna vidta åtgärder genom avancerad jakt behöver du en roll i Microsoft Defender ATP med [behörighet att skicka åtgärder för reparation på enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options). Om du inte kan vidta åtgärder kontaktar du en global administratör om du vill ha följande behörighet:

*Aktiva åtgärder för reparation > hot- och sårbarhetshantering - Reparationshantering*

## <a name="take-various-actions-on-devices"></a>Vidta olika åtgärder på enheter
Du kan vidta följande åtgärder på enheter som identifieras av `DeviceId` kolumnen i frågeresultaten:

- Isolera berörda enheter för att innehålla en infektion eller förhindra att attacker rör sig i sidled
- Samla in utredningspaket för att få mer kriminalteknisk information
- Kör en antivirussökning för att hitta och ta bort hot med hjälp av de senaste uppdateringarna av säkerhetsinformation
- Starta en automatiserad undersökning för att kontrollera och åtgärda hot på enheten och eventuellt andra berörda enheter
- Begränsa appkörningen till endast Microsoft-signerade körbara filer, förhindra efterföljande hotaktivitet via skadlig kod eller andra ej betrodda körbara filer

Om du vill veta mer om hur dessa svarsåtgärder utförs via Microsoft Defender ATP [läser du om svarsåtgärder på enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).
   
## <a name="quarantine-files"></a>Karantänfiler
Du kan distribuera *karantänåtgärden* på filer så att de automatiskt sätts i karantän när de påträffas. När du väljer den här åtgärden kan du välja mellan följande kolumner för att identifiera vilka filer i frågeresultatet som ska sättas i karantän:

- `SHA1`— I de mest avancerade jakttabellerna är detta SHA-1 i filen som påverkades av den registrerade åtgärden. Om en fil till exempel kopierades är det den kopierade filen.
- `InitiatingProcessSHA1`— I de mest avancerade jakttabellerna är detta den akt som ansvarar för att inleda den registrerade åtgärden. Om till exempel en underordnad process startades är det den överordnade processen. 
- `SHA256`— Detta är SHA-256-motsvarigheten till den fil som identifieras av `SHA1` kolumnen.
- `InitiatingProcessSHA256`— Detta är SHA-256-motsvarigheten till den fil som identifieras av `InitiatingProcessSHA1` kolumnen.

Om du vill veta mer om hur karantänåtgärder vidtas och hur filer kan återställas [läser du om svarsåtgärder på filer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>För att hitta filer och sätta dem i karantän bör frågeresultatet även innehålla `DeviceId` värden som enhetsidentifierare.  

## <a name="take-action"></a>Vidta åtgärder
Om du vill vidta någon av de beskrivna åtgärderna markerar du en eller flera poster i frågeresultatet och väljer sedan **Vidta åtgärder**. En guide guidar dig genom processen att välja och sedan skicka in önskade åtgärder.

![Bild på vald post med panel för att kontrollera posten](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Granska vidtagna åtgärder
Varje åtgärd registreras individuellt i [åtgärdscentret](mtp-action-center.md) under **ÅtgärdscenterHistorik**  >  **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)). Gå till åtgärdscentret för att kontrollera status för varje åtgärd.
 
## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Översikt över åtgärdscenter](mtp-action-center.md)