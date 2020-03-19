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
description: Läs om hur du tilldelar licenser till grupper som ska användas med enheter.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826285"
---
# <a name="manage-licenses-for-devices"></a>Hantera licenser för enheter

Om du har Office 365 ProPlus (enhet) eller Office 365 ProPlus för utbildning (enhet) kan du tilldela licenser till enheter med hjälp av Azure AD-grupper. När en enhet har en licens kan alla som använder den enheten använda Office 365. Anta till exempel att du har 20 bärbara datorer och surfplattor som används av personer i organisationen. När du tilldelar en licens till varje enhet använder varje person som loggar in på en av enheterna Office 365 utan att behöva sin egen licens.

> [!IMPORTANT]
> Enhetsbaserad licensiering för Office 365 ProPlus är endast tillgänglig som tilläggslicens för vissa kommersiella kunder och vissa utbildningskunder. För kommersiella kunder är licensen *Office 365 ProPlus (enhet)* och är endast tillgänglig via Enterprise Agreement/Enterprise Agreement Subscription. För utbildningskunder är licensen *Office 365 ProPlus för utbildning (enhet)* och är endast tillgänglig via Inskrivning för utbildningslösningar (EES). För mer information, läs blogginlägget om [utbildning tillgänglighet](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Kontakta din Microsoft-kontorepresentant om du vill ha kommersiell tillgänglighet.

Till att börja med skapar du en grupp i Administrationscentret för Azure Active Directory och tilldelar sedan enheter till gruppen. Mer information om enhetslicensiering, inklusive enhetskrav, vilka typer av grupper du kan använda och hur du konfigurerar Office 365 ProPlus för att använda enhetslicensiering finns i [Enhetsbaserad licensiering för Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Du måste vara global administratör för att kunna utföra uppgifterna i den här artikeln.

## <a name="assign-licenses-to-devices"></a>Tilldela licenser till enheter

När du tilldelar licenser till en grupp tilldelar du licenser till alla enheter i gruppen. Du kan bara tilldela en prenumeration till en enskild grupp.

1. Gå till sidan<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i **administrationscentret** > för Microsoft 365.
2. På sidan **Licenser** väljer du **Office 365 ProPlus för utbildning (enhet)** eller **Office ProPlus (enhet).**
3. Välj en prenumeration på nästa sida och välj sedan **Tilldela licenser**.
4. I fönstret **Tilldela licenser i en grupp** börjar du skriva ett gruppnamn och väljer det sedan från resultaten för att lägga till det i listan.
5. Välj **Tilldela**och välj sedan **Stäng**.

## <a name="unassign-licenses-from-devices"></a>Ta bort licenser från enheter

När du tar bort licenser från en grupp tar du bort licenserna från alla enheter i gruppen. Alla appar och tillhörande data är sedan skrivskyddade.

1. Gå till sidan<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i **administrationscentret.** > 
2. På sidan **Licenser** väljer du **Office 365 ProPlus för utbildning (enhet)** eller **Office ProPlus (enhet).**
3. Välj en prenumeration på nästa sida, välj **Fler åtgärder**och välj sedan Ta **bort tilldelningslicenser**.
4. Välj **Ta bort tilldelning i**dialogrutan Ta bort **licenser** .