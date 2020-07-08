---
title: Konfigurera och styra extern vidarebefordran av e-post, Automatisk vidarebefordran, 5.7.520 Åtkomst nekad, inaktivera extern vidarebefordran, Administratören har inaktiverat extern vidarebefordran, utgående policy mot skräppost
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080119"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Konfigurera extern vidarebefordran av e-post i Office 365

Extern vidarebefordran styrs av principen *om utgående skräppost* och begränsas till användare baserat på den konfigurerade inställningen. För närvarande stöds 3 inställningar:

- **Automatisk** – I det här läget är systemet ansvarigt för att avgöra om ett vidarebefordrat meddelande är tillåtet eller inte.  Detta är standardläget och i det här läget blockerar systemet automatisk extern vidarebefordran.

- **På** – Automatisk extern vidarebefordran är tillåten och inte begränsad.

- **Av** – Automatisk extern vidarebefordran är inaktiverad och resulterar i en rapport om utebliven leverans (NDR) till slutanvändaren.

Mer information om hur du konfigurerar dessa inställningar finns [i Konfigurera skräppostfiltrering i EOP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide)

## <a name="controlling-external-email-forwarding"></a>Styra vidarebefordran av extern e-post

Som administratör för en organisation kan du ha företagskrav för att begränsa eller kontrollera vem som automatiskt kan vidarebefordra e-postmeddelanden med hjälp av inkorgsregler, eller SMTP-vidarebefordran, utanför organisationen. Vidarebefordran av e-post kan vara en användbar funktion, men kan också utgöra en risk genom att eventuellt lämna ut information, även genom att tillhandahålla information till angripare som kan utnyttjas för att attackera organisationen eller dess partner.

Office 365 tillåter inte automatisk extern vidarekoppling av vare sig inkorgsregler eller e-postboxkonfiguration, vilket ger en säker standardprincip. Administratören kan dock ändra dessa inställningar för alla eller vissa användare i organisationen. Vidarebefordra meddelanden mellan interna användare påverkas inte av en sådan ändring.

> [!NOTE]
> Inaktivera automatisk vidarebefordran till externa adresser i Office 365 rullas ut i faser med information som kommuniceras via [Message Center-inlägg.](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) För att hjälpa administratörer att förbereda sig för dessa ändringar får de ändra principer i förväg för att säkerställa att det inte finns några störningar för användarna.

Mer information om användare som använder automatisk vidarebefordran (inkorgsregler eller SMTP-vidarebefordran) i organisationen finns i [rapporten Automatiskt vidarebefordrade meddelanden](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).

## <a name="the-blocked-email-forwarding-message"></a>Meddelandet om vidarebefordran av e-post

När ett meddelande identifieras som automatiskt vidarebefordras och *organisationsprincipen blockerar* aktiviteten genereras en rapport **om utebliven leverans (NDR)** tillbaka till slutanvändaren. Rapporten visar att meddelandet inte levererades. NDR kommer att ha följande format: 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
