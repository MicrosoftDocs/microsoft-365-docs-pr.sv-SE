---
title: Konfigurera och kontrol lera extern e-postvidarekoppling, automatisk vidarebefordran, 5.7.520 åtkomst nekad, inaktivera extern vidarebefordran, administratören har inaktiverat extern vidarebefordran, utgående princip för skräp post
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
ms.openlocfilehash: 727f14e8158f7e024b6029231fed18adb2d56a62
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949706"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Konfigurera extern vidarebefordran av e-post i Office 365

Extern vidarebefordran styrs av *principen för utgående skräp post* och omfattning för användare baserat på den konfigurerade inställningen. För närvarande finns det stöd för tre inställningar:

- **Automatiskt** – i det här läget är systemet ansvarigt för att bestämma om ett vidarebefordrat meddelande tillåts eller inte.  Det här är standard läget och i det här läget blockerar systemet automatisk extern vidarebefordran.

- **På** – automatisk extern vidarebefordran är tillåten och inte begränsad.

- **Av** – automatisk extern vidarekoppling är inaktiverat och resulterar i en rapport om utebliven leverans (NDR) för slutanvändaren.

Mer information om hur du konfigurerar dessa inställningar finns i [Konfigurera filtrering för utgående e-post i EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) .

> [!NOTE]
> Inaktive ring av automatisk vidarebefordran kommer också att dsable som dirigerar meddelanden till externa adresser.

## <a name="controlling-external-email-forwarding"></a>Styra extern e-postvidarebefordran

Som administratör för en organisation kan du ha företags krav för att begränsa eller kontrol lera vem som kan vidarebefordra e-postmeddelanden med hjälp av regler för Inkorgen, eller SMTP-vidarekoppling utanför organisationen. Vidarebefordran av e-post kan vara en användbar funktion, men du kan också skapa en risk genom att informationen avslöjas, även genom att tillhandahålla information till angripare som kan utnyttja organisationen eller dess partners.

Office 365 tillåter inte automatisk extern vidarebefordran av antingen Inkorgshanteraren eller konfiguration av e-postlåda, vilket ger en säker standard princip. Administratören kan dock ändra dessa inställningar för alla eller vissa användare i organisationen. Vidarebefordrade meddelanden mellan interna användare påverkas inte av en sådan modifiering.

> [!NOTE]
> Det går inte att inaktivera automatisk vidarebefordran till externa adresser i Office 365 i faser med uppgifter som kommunicerats via [meddelanden i meddelande Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) . För att administratörer ska kunna förbereda sig för dessa ändringar har de ändrat principer i förväg för att säkerställa att användarna inte störs.

Mer information om användare som använder automatisk vidarebefordran (regler för Inkorgen eller SMTP-vidarekoppling) i din organisation finns i [rapporten automatisk vidarebefordrade meddelanden](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a>Hur fungerar den här principen med andra kontroller för vidarekoppling av automatiskt

Som administratör kan du ha andra typer av kontroller på plats, så blockering av automatisk vidarebefordran i [fjärrdomäner](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) och användning av en Exchange-Exchange. Båda de här kontrollerna är oberoende av den här funktionen, till exempel om du tillåter automatisk vidarebefordran av en fjärrdomän, men blockerar automatisk vidarebefordran via den skräp post princip som visas, blir det automatiskt vidarebefordrade meddelandet blockerat. Om du tillåter automatisk vidarebefordran i principen för utgående skräp post men blockerar den i en Exchange eller fjärrdomän blockeras meddelandet av någon av dessa kontroller. Då kan du till exempel tillåta automatisk vidarebefordran i principen för utgående skräp post och använda fjärrdomäner för att styra domänerna som användarna kan vidarekoppla meddelanden automatiskt till.


## <a name="the-blocked-email-forwarding-message"></a>Meddelande om blockerad e-post

När ett meddelande identifieras som automatiskt vidarebefordrat och organisations princip *blocken* som **aktivitet kommer att** genereras tillbaka till slutanvändaren. Rapporten indikerar att meddelandet inte har levererats. NDR har följande format: 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
