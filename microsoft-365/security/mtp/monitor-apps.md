---
title: Appövervakning och rapportering i säkerhetscentret Microsoft 365
description: Beskriver hur du kan få mer insikt i användningen av molnappar i din organisation
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säkerhetscenter, övervaka, rapportera, appar
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f7b3f2fcaac71eefa2579a0c3fd66666fe00f605
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807654"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Appövervakning och rapportering i säkerhetscentret Microsoft 365

Dessa rapporter ger mer insikt i hur molnappar används i din organisation, inklusive vilka typer av appar, deras risknivå och aviseringar.

## <a name="monitor-email-accounts-at-risk"></a>Övervaka e-postkonton i riskzonen

**E-postskydd** visar e-postkonton i riskzonen. Du kan klicka på ett konto för att undersöka vidare i Microsoft Defender Security Center.

![E-postskyddskort](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Övervaka appbehörigheter som beviljas av användare

**Cloud App Security - OAuth-appar** listar appar som upptäckts av Cloud App Security och som har beviljats behörighet av användare. Cloud App Securitys riskkatalog innehåller över 16 000 appar som bedöms med över 70 riskfaktorer.

Riskfaktorerna utgår från allmän information, till exempel apputgivaren, till säkerhetsåtgärder och kontroller, till exempel om appen stöder kryptering i vila eller tillhandahåller en granskningslogg över användaraktivitet.

![Cloud App Security OAuth apps kort](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Övervaka användarkonton för molnappar

**Molnappkonton för granskning** listar konton som kan behöva uppmärksamhet.

![Cloud App-konton för granskningskort](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Förstå vilka molnappar som används

**Identifierade molnappar (kategorier)** visar vilka typer av appar som används i din organisation och länkar till cloud discovery-instrumentpanelen i Cloud App Security. Mer information finns i [Snabbstart: Arbeta med identifierade appar](https://docs.microsoft.com/cloud-app-security/discovered-apps).  

![Kategorierna för identifierade molnappar](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Övervaka var användare får åtkomst till molnappar

**Aktivitetsplatser för molnappar** visar var användarna har åtkomst till molnappar.

![Cloud App aktivitet platser kort](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Övervaka hälsotillstånd för infrastrukturarbetsbelastningar

**Infrastrukturhälsa** visar hälsotillståndsaviseringar för infrastrukturarbetsbelastningar i Azure Security Center.

Azure Security Center tillhandahåller enhetlig säkerhetshantering och avancerat skydd mot hot över lokala arbetsbelastningar och molnarbetsbelastningar. Du kan samla in, söka efter och analysera säkerhetsdata från en mängd olika källor, inklusive brandväggar och andra partnerlösningar.

Mer information finns i [Dokumentationen till Azure Security Center](https://docs.microsoft.com/azure/security-center/).

![Hälsokort för infrastruktur](../../media/infrastructure-health.png)
