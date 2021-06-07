---
title: Omdirigera användare från säkerhets- Office 365 säkerhets- och efterlevnadscentret till Microsoft 365 säkerhets- och efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Läs mer om hur du automatiskt Office 365 användare i Säkerhets- och efterlevnadscenter Microsoft 365 säkerhets- och efterlevnadscenter.
ms.collection: M365-security-compliance
ms.openlocfilehash: b51b2e225c833ac499379bbee119f8cb6f4216e9
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782843"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>Omdirigera användare från säkerhets- Office 365 säkerhets- och efterlevnadscentret till Microsoft 365 säkerhets- och efterlevnadscenter

Den här artikeln förklarar hur automatisk omdirigering fungerar för användare som använder efterlevnadslösningar från säkerhets- och efterlevnadscentret för Office 365 (protection.office.com) till efterlevnadscentret för Microsoft 365 (compliance.microsoft.com).

## <a name="what-to-expect"></a>Vad du kan förvänta dig

Automatisk omdirigering är som standard aktiverad för alla användare som har åtkomst till följande efterlevnadsrelaterade lösningar Office 365 säkerhet och efterlevnad (protection.office.com):

- Skydd mot dataförlust (DLP)
- Klassificering
- Informationsstyrning
- Hantering av arkivhandlingar
- Kommunikationsefterlevnad (tidigare "överlevnad")

Användare dirigeras automatiskt till samma efterlevnadslösningar i kompatibilitetscentret för Microsoft 365 (compliance.microsoft.com).

>[!NOTE]
>För andra efterlevnadslösningar som ingår i Säkerhets- och efterlevnadscenter för Office 365 fortsätter användarna att hantera lösningarna i antingen Microsoft 365-efterlevnadscentret eller Säkerhets- och efterlevnadscenter för Office 365- och efterlevnadscenter. Den automatiska omdirigeringen för dessa efterlevnadslösningar kommer snart att bli tillgänglig.*

Den här funktionen och tillhörande kontroller aktiverar inte automatisk omdirigering av säkerhetsfunktioner för Microsoft Defender för Office 365. Mer information om hur du aktiverar omdirigeringen av säkerhetsfunktionerna finns i Omdirigera konton från Microsoft Defender för [Office 365 till Microsoft 365 säkerhetscenter.](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan jag använda den tidigare portalen igen?

Om något inte fungerar för dig eller om det finns något som du inte kan slutföra via portalen för efterlevnadscenter för Microsoft 365 kan du tillfälligt inaktivera den automatiska omdirigeringen för alla användare.

>[!IMPORTANT]
>Efterlevnadscenter Microsoft 365 är en ersättningshanteringsportal för efterlevnadslösningar som för närvarande hanteras i Office 365 Säkerhets- och efterlevnadscenter. Alla Microsoft 365-efterlevnadslösningar hanteras enbart i Microsoft 365 efterlevnadscenter. Att inaktivera omdirigering till Microsoft 365 efterlevnadscenter bör vara en kort lösning.*

Om du vill gå Office 365 säkerhets- och efterlevnadscenter (protection.microsoft.com) för alla användare gör du följande:

1. Logga in på [Microsoft 365 som global](https://compliance.microsoft.com) administratör eller använd ett konto med efterlevnadsadministratörsbehörigheter i Azure Active Directory.
2. Gå till **Inställningar**  >  **omdirigering av efterlevnadscentret.**
3. Ändra inställningen för automatisk omdirigering till **Av**.
4. Välj **Inaktivera och** dela feedback när du uppmanas att göra det.

När den är inaktiverad dirigeras användarna inte längre till compliance.microsoft.com och de dirigeras Office 365 Säkerhets- och efterlevnadscenter (protection.microsoft.com). Den här inställningen kan aktiveras igen när som helst av globala administratörer eller efterlevnadsadministratörer.

## <a name="related-information"></a>Relaterad information

- [Microsoft 365 översikt över efterlevnadscenter](/microsoft-365/compliance/microsoft-365-compliance-center)
