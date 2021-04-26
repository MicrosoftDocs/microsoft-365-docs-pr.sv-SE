---
title: Rensa en mobil enhet i Basic Mobility and Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Använd inbyggd basic mobility and security för att ta bort information från registrerade enheter.
ms.openlocfilehash: 7830a0f4ef609f6465c171ecab2c9e3c48198424
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023863"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Rensa en mobil enhet i Basic Mobility and Security

Du kan använda den inbyggda grundläggande rörlighet och säkerhet för Microsoft 365 för att ta bort enbart organisationsinformation, eller för att utföra en fabriksåterställning för att ta bort all information från en mobil enhet och återställa den till fabriksinställningarna.

## <a name="before-you-begin"></a>Innan du börjar

Mobila enheter kan lagra känslig information om organisationen och ge åtkomst till organisationens Microsoft 365-resurser. För att skydda organisationens information kan du göra fabriksåterställning eller ta bort företagsdata:

- **Fabriksåterställning:** Tar bort alla data på en användares mobila enhet, inklusive installerade program, foton och personlig information. När rensningen är klar återställs enheten till fabriksinställningarna.

- **Ta bort företagsdata:** Tar bara bort organisationsdata och lämnar installerade program, foton och personlig information på en användares mobila enhet.

- **När en enhet rensas (fabriksåterställning eller ta bort företagsdata)** tas enheten bort från listan med hanterade enheter.
    
- **Återställa en enhet automatiskt:** Du kan konfigurera en grundläggande mobilitets- och säkerhetsprincip som automatiskt fabriksåterställer en enhet när en användare inte lyckats ange enhetslösenordet ett visst antal gånger. Det gör du genom att följa stegen i [Skapa säkerhetsprinciper för enheter i grundläggande rörlighet och säkerhet.](create-device-security-policies.md)
    
- **Om du vill veta hur användarupplevelsen ser ut** när du rensar deras enhet kan du gå till   [Vad påverkar användaren och enheten?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Rensa en mobil enhet

1. Gå till [administrationscentret för Microsoft 365.](../../admin/admin-overview/about-the-admin-center.md)

2. Skriv Hantering av mobila enheter i sökfältet och välj **Hantering av mobila** enheter i listan med resultat.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Alternativ för hantering av mobila enheter med Enkel rörlighet och Secruity":::

3. Välj **Hantera enheter**.

4. Välj den enhet du vill rensa.

5. Välj **Hantera**.

6. Välj den typ av fjärrensning du vill göra.

    - Om du vill göra en fullständig rensning och återställa enheten till fabriksinställningarna väljer du **Fabriksåterställning**.
    - Om du vill göra en selektiv rensning och bara ta bort Microsoft 365-organisationsinformation väljer du **Ta bort företagsdata.**
    - Om du vill ta bort enheten från din organisation väljer du **Ta bort enhet**.

7. Bekräfta genom att välja **Ja**.

## <a name="how-do-i-know-it-worked"></a>Hur vet jag att det fungerade?

Du ser inte längre den mobila enheten i listan över hanterade enheter.

## <a name="why-would-you-want-to-wipe-a-device"></a>Varför skulle du vilja rensa en enhet?

Rensa en enhet av följande anledningar:

- Mobila enheter som smartphones och surfplattor blir allt mer fullödig hela tiden. Det innebär att det är enklare för användarna att lagra känslig företagsinformation som personuppgifter eller konfidentiella meddelanden och att använda den var de än är. Om en av de mobila enheterna försvinner eller blir stulen kan en utparning av enheten förhindra att organisationens information hamnar i fel händer.
- Om en användare lämnar organisationen med en personlig enhet som är registrerad i Basic Mobility and Security kan du förhindra att organisationsinformationen går med den användaren genom att göra en fabriksåterställning.
- Om din organisation tillhandahåller mobila enheter åt användare kan du då och då behöva tilldela om enheterna. Genom att göra en fabriksåterställning på en enhet innan du tilldelar den till en ny användare kan du se till att känslig information från den tidigare ägaren tas bort.

## <a name="whats-the-user-and-device-impact"></a>Hur påverkar det användaren och enheten?

Rensningen skickas direkt till den mobila enheten och enheten markeras som inte kompatibel i Azure Active Directory. Även om alla data tas bort när en enhet återställs till fabriksinställningarna beskriver följande tabell vilket innehåll som tas bort för varje enhetstyp när en enhet tas bort när företagsdata tas bort.

|**Påverkan på innehållet**|**iOS 10 och senare**|**Android 5 och senare**|
|:-----|:-----|:-----|
|Appdata för Microsoft 365 rensas om enheten skyddas av App Protection-principer för Intune. Apparna tas inte bort. För enheter som inte skyddas av MAM-principer (Mobile Application Management) tar Outlook och OneDrive inte bort cachelagrade data.<br/>**Obs!** För att använda Intune-appskyddsprinciper måste du ha en Intune-licens.|Ja|Ja|
|Principinställningarna som används av Basic Mobility och Security på enheter tillämpas inte längre. användare kan ändra inställningarna.|Ja|Ja|
|E-postprofiler som skapats med Basic Mobility and Security tas bort och cachelagrad e-post på enheten tas bort.|Ja|Uppgift saknas|
>[!NOTE]
>Företagsportalappen finns i App Store för iOS och Play Store för Android-enheter.

## <a name="related-topics"></a>Relaterade ämnen

[Konfigurera grundläggande Mobility and Security](set-up.md)
