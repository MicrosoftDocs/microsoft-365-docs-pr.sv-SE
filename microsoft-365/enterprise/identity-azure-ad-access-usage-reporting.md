---
title: 'Steg 13: Övervaka klientorganisationen och inloggningsaktivitet'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och konfigurera rapportering av Azure AD-åtkomst och användning.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42806440"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a>Steg 13: Övervaka klientorganisationen och inloggningsaktivitet

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

I det här steget ska du granska granskningsloggar och inloggningsaktivitet med hjälp av Azure AD-rapportering. Det finns två typer av rapporter.

I **aktivitetsrapporten för granskningsloggar** registreras historiken för varje aktivitet som utförs i Azure AD-klientorganisationen. Den här rapporten besvarar frågor som:

- Vem har lagt till någon i en administratörsgrupp?
- Vilka användare är inloggade på en specifik app?
- Hur många återställningar av lösenord görs?

I **rapporten för inloggningsaktivitet** registreras vem som utförde de aktiviteter som rapporterades i granskningsloggrapporten. Den här rapporten besvarar frågor som:

- Vilket inloggningsmönster har en specifik användare som undersöks?
- Hur många inloggningar har jag under en dag, vecka eller månad?
- Hur många av de här inloggningarna misslyckades och för vilka konton?

Mer information om rapporterna och hur du kommer åt dem finns i [Azure Active Directory-rapportering](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).

I det här steget får veta mer om rapporterna och du förstår hur du kan använda dem för att få insikter om Azure AD-händelser och aktiviteter för planering och säkerhet.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [Tillåta att användare skapar och hanterar egna grupper](identity-self-service-group-management.md) |
