---
title: Hantera appar för programvara som en tjänst för din organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
search.appverid: MET150
description: Lär dig hur du aktiverar och hanterar appar från tredje part i Microsoft 365 administrationscenter.
ms.openlocfilehash: eb2826a4b0c69d61eb35a9dfff37e9dc2dd6ad71
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141194"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a>Hantera appprenumerationer från tredje part för din organisation

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Du kan hantera licenser och fakturering för appar från tredje part i Microsoft 365-administrationscentret med förhandsgranskningsläge aktiverat. Uppdaterade funktioner inkluderar förbättrad prenumerationshantering, förbättrad åtkomst till faktureringsinformation och förbättrad flexibilitet för att hantera räkningar. Prenumerationshanteringen baseras på Microsofts uppdaterade handelsplattform. Detta gäller appar som kunder köper direkt eller från tredjepartsleverantörer.

## <a name="how-to-get-software-as-a-service-apps"></a>Så här skaffar du appar för programvara som en tjänst

Det finns några sätt att köpa appar från tredje part.

- **Direktköp** – Kunder kan direkt köpa prenumerationer från [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)eller [AppSource](https://www.appsource.com/).
- **Partnerköp** – Arbeta med en partner via Partner Center för att köpa prenumerationer.
- **Microsoft-förslag** – Svara på ett förslag från Microsoft Sales som innehåller appar från tredje part.

När kunderna har köpt apparna och accepterat Microsofts kundavtal kan de hantera dem i Microsoft 365-administrationscentret eller Microsoft Store för företag.

Appleverantörer säljer sina appar antingen till ett schablonbelopp eller genom att köpa licenser för användare.

- **Schablonbelopp** – Även kallad platsbaserad prissättning, appar är prissatta med ett månads- eller årspris. På appsidan visas licenskvantitet på Unlimited.
- **Licenser** – Appar prissätts efter licens. Kunder tilldelar licenser till varje användare i organisationen

## <a name="supported-regions"></a>Regioner som stöds

Stöd för appar från tredje part är tillgängligt i följande regioner:

- Argentina
- Australien
- Kanada
- Chile
- Frankrike
- Tyskland
- Grekland
- Puerto Rico
- Sydafrika
- Storbritannien
- USA
- Västeuropa

## <a name="activate-third-party-apps"></a>Aktivera appar från tredje part

Administratörer måste aktivera appar från tredje part innan de tilldelas användare. Dessa appar aktiveras i tredjepartsutgivarens portal.

1. Gå till sidan > **Faktureringsappar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> i administrationscentret. **Billing**
2. Hitta och välj den app du vill hantera.
3. Under **Inställningar & åtgärder**väljer du Hantera i **utgivarens portal**.

Du dirigeras till apputgivarens webbplats där du kan aktivera appen.

## <a name="manage-third-party-apps"></a>Hantera appar från tredje part

Administratörer hanterar appar från tredje part på två platser: Microsoft 365 admincenter och tredjepartsappleverantörens portal.

Det här kan du göra i varje portal.

| Administrationscenter för Microsoft 365 | Portal för apputgivare |
| --- | --- |
| Ändra licenskvantitet <br> Hantera hur du betalar din faktura <br> Hantera hur du betalar din faktura <br> Ändra betalningsmetod (kreditkort) <br> Visa faktura <br> Avbryt appprenumeration | Konfigurera app (en gång för varje app) <br> Tilldela licenser till användare <br> Teknisk support |

När appen har aktiverats förblir den aktiv om den inte avbryts, upphör att gälla eller om betalningen inte hålls aktuell. Dessa händelser ändrar appstatusen till inaktiverad. När en app har inaktiverats kan den inte återaktiveras. Om du vill fortsätta använda appen köper du en annan kopia av den.

## <a name="assign-licenses"></a>Tilldela licenser

Administratörer måste aktivera appar från tredje part innan de tilldelas användarna. De aktiveras i tredjepartsutgivarens portal. Välj länken för att tilldela licenser under **Inställningar & åtgärder**på appsidan.

1. Gå till sidan > **Faktureringsappar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> i administrationscentret. **Billing**
2. Hitta och välj den app du vill hantera.
3. Under **Inställningar & åtgärder**väljer du länken till Hantera i **utgivarens portal**.

## <a name="change-license-quantity"></a>Ändra licenskvantitet

Administratörer kan ändra antalet licenser som ägs av organisationen. Detta gäller endast appar som köpts med platsbaserad prissättning.

1. Gå till sidan > **Faktureringsappar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> i administrationscentret. **Billing**
2. Hitta och välj den app du vill hantera.
3. Välj **Ändra licenskvantitet**.

## <a name="manage-payment-methods"></a>Hantera betalningsmetoder

Appar för programvara som en tjänst har var sin faktureringsprofil tilldelad. Med faktureringsprofiler kan du anpassa vilka produkter som ingår på fakturan och hur du betalar dina fakturor. De omfattar:

- **Betalningsmetoder** – Kreditkort eller check/banköverföring
- **Kontaktuppgifter** – Faktureringsadress och kontaktnamn
- **Roller** – Roller som gör att du kan ändra faktureringsprofilen, betala räkningar eller använda betalningsmetoden i faktureringsprofilen för att göra inköp.

Mer information om faktureringsprofiler finns i [Förstå faktureringsprofiler](https://docs.microsoft.com/microsoft-store/billing-profile).

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a>Ändra faktureringsprofilen för en prenumeration på app för programvara som en tjänst

1. Gå till sidan > **Faktureringsappar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> i administrationscentret. **Billing**
2. Hitta och välj den app du vill hantera.
3. Välj Redigera **bredvid faktureringsprofil** **.**

Mer information om fakturor finns i [Förstå fakturan](billing-and-payments/understand-your-invoice.md).

## <a name="cancel-a-software-as-a-service-app-subscription"></a>Avbryta en prenumeration på app för programvara som en tjänst

Du kan avbryta en app som en tjänst från appsidan.

1. Gå till sidan > **Faktureringsappar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> i administrationscentret. **Billing**
2. Hitta och välj den app du vill hantera.
3. Under **Inställningar & åtgärder**väljer du Avbryt **prenumeration**.
