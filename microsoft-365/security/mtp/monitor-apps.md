---
title: Programövervakning & rapportering – Säkerhetscenter
description: Lär dig hur du får mer insyn i hur du använder molnappen i din organisation. Omfattar olika typer av appar, deras risknivå och aviseringar.
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, appar
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930528"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Appövervakning och -rapportering i Microsoft 365 säkerhetscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


De här rapporterna ger mer insyn i hur molnappar används i organisationen. Omfattar olika typer av appar, deras risknivå och aviseringar.

## <a name="monitor-email-accounts-at-risk"></a>Övervaka e-postkonton som är riskerade

**E-postskydd** visar att e-postkonton är riskerade. Du kan välja ett konto om du vill undersöka ytterligare i Microsoft Defender Säkerhetscenter.

![Kort för e-postskydd](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Övervaka programbehörigheter som beviljas av användare

**Cloud App Security – OAuth-appar** visar appar som upptäcks av Cloud App Security och som har beviljats behörighet av användare. Cloud App Securitys riskkatalog innehåller över 16 000 appar som bedöms använda mer än 70 riskfaktorer.

Riskfaktorerna börjar med allmän information, som programutgivaren. Sedan flyttas programmet till säkerhetsåtgärder och kontroller, till exempel om appen stöder kryptering i vila eller ger en granskningslogg över användaraktivitet.

![OAuth-appskort för Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Övervaka användarkonton i molnappen

**Molnappkonton för granskning listar** konton som kan behöva uppmärksammas.

![Cloud App-konton för granskningskort](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Förstå vilka molnappar som används

**Identifierade molnappar (kategorier)** visar vilka typer av appar som används i organisationen. Den länkar till instrumentpanelen för molnidentifiering i Cloud App Security. Mer information finns i [Snabbstart: Arbeta med identifierade appar.](https://docs.microsoft.com/cloud-app-security/discovered-apps)  

![Identifierat kategorikort för molnappar](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Övervaka var användare får åtkomst till molnappar

**Platser för aktivitet i molnappar** visar var användare använder molnappar.

![Kort för aktivitet i Molnapp](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Övervaka hälsotillståndet för arbetsbelastningen för infrastrukturen

**Infrastrukturstatus visar** hälsostatusvarningar om infrastrukturarbetsbelastningar i Azure Defender.

Azure Defender ger enhetlig säkerhetshantering och Defender för Office 365 i både lokala och molnbaserade arbetsbelastningar. Du kan samla in, söka efter och analysera säkerhetsdata från olika källor, inklusive brandväggar och andra partnerlösningar.

Mer information finns i [Azure Defender-dokumentationen.](https://docs.microsoft.com/azure/security-center/)

![Hälsokort för infrastruktur](../../media/infrastructure-health.png)
