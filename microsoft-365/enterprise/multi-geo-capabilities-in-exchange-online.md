---
title: Exchange multi-geo
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Lär dig mer om multi-geo-funktioner i Exchange Online, till exempel begränsningar för funktioner och post lådans placering.
ms.openlocfilehash: ca7203c72f23fd03512bf23eaa5a4687e4bac1b5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694636"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a>Multi-geo-funktioner i Exchange Online

I en multi-geo-miljö kan du välja plats för Exchange Online Mailbox-innehåll (data på rest) per användare.

Du kan placera post lådor på satellitbaserade platser genom att:

- Skapa en ny Exchange Online-postlåda direkt i en satellit-Geo-plats.

- Flytta en befintlig Exchange Online-postlåda till en satellit-Geo-plats genom att ändra användarens önskade data plats.

- Hantera en post låda från en lokal Exchange-organisation direkt i en satellits Geo-plats.

## <a name="mailbox-placement-and-moves"></a>Post lådans placering och flyttningar

När Microsoft har slutfört kraven för multi-geo-konfiguration följer Exchange Online ett **PreferredDataLocation** -attribut på användar objekt i Azure AD.

Exchange Online synkroniserar egenskapen **PreferredDataLocation** från Azure AD till egenskapen **MailboxRegion** i Exchange Online-katalogtjänsten. Värdet för **MailboxRegion** bestämmer den Geo-plats där användar post lådor och alla associerade Arkiv post lådor ska placeras. Det går inte att konfigurera användarens primära post låda och Arkiv post lådor på olika geo-platser. Endast en Geo-plats kan konfigureras per User-objekt.

- När **PreferredDataLocation** är konfigurerad för en användare med en befintlig post låda placeras post lådan i en kö för flyttning och flyttas automatiskt till angiven Geo-plats.

- När **PreferredDataLocation** är konfigurerad för en användare utan en befintlig post låda kommer den att tillhandahållas till den angivna geo-platsen när du tillhandahåller post lådan.

- När **PreferredDataLocation** inte anges för en användare etableras den i den centrala geo-platsen när du tillhandahåller post lådan.

- Om **PreferredDataLocation** -koden är felaktig (t. ex. en typ av Nan i stället för sig) etableras post lådan på den centrala geo-platsen.

**Obs!** multi-geo-funktioner och Skype för företag – Online interregionala värdbaserade möten båda använder egenskapen **PreferredDataLocation** för användar objekt för att hitta tjänster. Om du konfigurerar **PreferredDataLocation** -värden för regionala värd möten flyttas post lådan för användarna automatiskt till angiven Geo-plats efter att multi-geo är aktiverat på Microsoft 365-klienten.

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Funktions begränsningar för multi-geo i Exchange Online

- De funktioner för säkerhet och efterlevnad (till exempel granskning och eDiscovery) som är tillgängliga i administrations centret för Exchange (UK) är inte tillgängliga i flera geo-organisationer. Istället måste du använda [Microsoft 365 Security & Compliance Center](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) för att konfigurera funktioner för säkerhet och efterlevnad.

- Outlook för Mac-användare kan få tillfällig åtkomst till sina arkivmappar när de flyttas till en ny Geo-plats. Det här problemet uppstår när användarens primära och arkiverade post lådor finns på olika geo-platser, eftersom flyttningar av flera geo-postlådor kan slutföras vid olika tillfällen.

- Användare kan inte dela *Mailbox-mappar* över geo-platser i Outlook på webben (tidigare Outlook Web App eller OWA). En användare i Europeiska unionen kan till exempel inte använda Outlook på webben för att öppna en delad mapp i en post låda som finns i USA. Däremot kan Outlook på webben öppna *andra post lådor* på olika geo platser genom att använda ett separat webbläsarfönster enligt beskrivningen i [öppna en annan persons post låda i ett separat webbläsarfönster i Outlook Web App](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362).

  **Obs!** mappdelning för flera geo-filer stöds i Outlook för Windows.

- Offentliga mappar stöds i flera geo organisationer. Däremot måste de gemensamma mapparna finnas kvar på den centrala geo platsen. Du kan inte flytta gemensamma mappar till satellitiska platser.

- I en flerdimensionell miljö stöds inte granskning mellan flera geo-postlådor. Om en användare till exempel har behörighet att komma åt en delad post låda på en annan Geo-plats, loggas inte post lådor som utförs av den användaren i gransknings loggen för den delade post lådan. Mer information finns i [hantera granskning av post låda](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing?view=o365-worldwide).
