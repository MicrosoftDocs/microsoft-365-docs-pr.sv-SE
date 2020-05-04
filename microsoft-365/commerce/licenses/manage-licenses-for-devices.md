---
title: Hantera licenser för enheter
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Lär dig hur du tilldelar licenser till grupper för användning med enheter.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: 1a525117c25a2471ad696ef1447fd7e4ccb6bed0
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011191"
---
# <a name="manage-licenses-for-devices"></a>Hantera licenser för enheter

Om du har Microsoft 365 Apps for Enterprise (device) eller Microsoft 365 Apps for Education (device) kan du tilldela licenser till enheter med hjälp av Azure AD-grupper. När en enhet har en licens kan alla som använder den enheten använda Microsoft 365 Apps för företag (tidigare office 365 ProPlus). Anta till exempel att du har 20 bärbara datorer och surfplattor som används av personer i organisationen. När du tilldelar en licens till varje enhet använder varje person som loggar in på en av enheterna Microsoft 365 Apps för företag utan att behöva sin egen licens.

> [!IMPORTANT]
> Enhetsbaserad licensiering för Microsoft 365 Apps för företag är endast tillgänglig som tilläggslicens för vissa kommersiella kunder och vissa utbildningskunder. För kommersiella kunder är licensen *Microsoft 365 Apps for enterprise (device)* och är endast tillgänglig via Enterprise Agreement/Enterprise Agreement Subscription. För utbildningskunder är licensen *Microsoft 365 Apps for Education (enhet)* och är endast tillgänglig via Enrollment for Education Solutions (EES). Mer information finns i blogginlägget om [utbildningstillgänglighet](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Kontakta din Microsoft-kontorepresentant för kommersiell tillgänglighet.

Till att börja med skapar du en grupp i Administrationscentret för Azure Active Directory och tilldelar sedan enheter till gruppen. Mer information om enhetslicensiering, inklusive enhetskrav, vilka typer av grupper du kan använda och hur du konfigurerar Microsoft 365 Apps för företag för att använda enhetslicensiering, finns i [Enhetsbaserad licensiering för Microsoft 365 Apps för företag](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Du måste vara global administratör för att kunna utföra uppgifterna i den här artikeln.

## <a name="assign-licenses-to-devices"></a>Tilldela licenser till enheter

När du tilldelar licenser till en grupp tilldelar du licenser till alla enheter i gruppen. Du kan bara tilldela en prenumeration till en enskild grupp.

1. Gå till sidan<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser i administrationscentret</a> **för** > Microsoft 365.
2. På sidan **Licenser** väljer du **Microsoft 365 Apps for Education (enhet)** eller **Microsoft 365 Apps for enterprise (device)**.
3. På nästa sida väljer du en prenumeration och väljer sedan **Tilldela licenser**.
4. I fönstret **Tilldela licenser till en grupp** börjar du skriva ett gruppnamn och väljer det sedan från resultaten för att lägga till det i listan.
5. Välj **Tilldela**och välj sedan **Stäng**.

## <a name="unassign-licenses-from-devices"></a>Ta bort tilldelning av licenser från enheter

När du tar bort licenser från en grupp tar du bort licenserna från alla enheter i gruppen. Alla appar och tillhörande data skrivs sedan skrivskyddade.

1. Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**
2. På sidan **Licenser** väljer du **Microsoft 365 Apps for Education (enhet)** eller **Microsoft 365 Apps for enterprise (device)**.
3. På nästa sida väljer du en prenumeration, väljer **Fler åtgärder**och väljer sedan Ta **bort licenser**.
4. Välj **Ta bort tilldelning**i dialogrutan Ta bort **licenser** .