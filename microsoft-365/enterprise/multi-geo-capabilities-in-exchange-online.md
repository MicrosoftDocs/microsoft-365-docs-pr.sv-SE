---
title: Exchange Multi-Geo
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
description: Läs mer om multi-geofunktioner i Exchange Online, till exempel funktionsbegränsningar och postlådeplacering.
ms.openlocfilehash: 4c8f873039cd14251931125f5af2c04b7cbfe719
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694311"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a>Multi-Geo Capabilities i Exchange Online

I en geomiljö med flera platser kan du välja plats Exchange Online postlådeinnehåll (data i vila) per användare.

Du kan placera postlådor på satellitgeoplatser genom att:

- Skapa en ny Exchange Online postlåda direkt på en satellit geoplats.

- Flytta en Exchange Online postlåda till en satellit geoplats genom att ändra användarens önskade dataplats.

- Introducera en postlåda från en lokal e-Exchange direkt till en satellit geoplats.

## <a name="mailbox-placement-and-moves"></a>Postlådans placering och flyttningar

När Microsoft har slutfört de nödvändiga fler geokonfigurationsstegen Exchange Online attributet **PreferredDataLocation** för användarobjekt i Azure AD.

Exchange Online synkroniserar egenskapen **PreferredDataLocation från** Azure AD till **egenskapen MailboxRegion** i Exchange Online-katalogtjänsten. **Postlåderegionvärdet** bestämmer den geoplats där användarpostlådor och alla associerade arkivpostlådor placeras. Det går inte att konfigurera en användares primära postlåda och arkivpostlådor så att de ligger på olika geoplatser. Endast en geoplats kan konfigureras per användarobjekt.

- När **PreferredDataLocation** har konfigurerats för en användare med en befintlig postlåda läggs postlådan i en kö för att vara i kö och flyttas automatiskt till den angivna geoplatsen.

- När **PreferredDataLocation** har konfigurerats för en användare utan en befintlig postlåda etableras den till den angivna geoplatsen när du etablerar postlådan.

- När **PreferredDataLocation** inte har angetts för en användare etableras postlådan på den centrala geoplatsen när du etablerar postlådan.

- Om **PreferredDataLocation-koden** är felaktig (t.ex. ett stavfel i stället för NAN i stället för NAM) etableras postlådan på den centrala geoplatsen.

**Obs!** Multi-geofunktioner och Skype för företag online-möten som har regional värd använder båda egenskapen **PreferredDataLocation** i användarobjekt för att hitta tjänster. Om du **konfigurerar PreferredDataLocation-värden** för användarobjekt för möten med regional värd flyttas postlådan för dessa användare automatiskt till den angivna geoplatsen när multi-geo har aktiverats på Microsoft 365 klientorganisationen.

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Funktionsbegränsningar för multi-geo i Exchange Online

- Säkerhets- och efterlevnadsfunktioner (till exempel granskning och eDiscovery) som är tillgängliga i administrationscentret för Exchange (EAC) är inte tillgängliga i geoorganisationer. I stället måste du använda Säkerhets- [Microsoft 365 säkerhets- & för att](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) konfigurera säkerhets- och efterlevnadsfunktioner.

- Outlook för Mac användare kan uppleva en tillfällig förlust av åtkomsten till sin onlinearkivmapp när du flyttar postlådan till en ny geoplats. Det här villkoret inträffar när användarens primära postlådor och arkivpostlådor finns på olika geoplatser, eftersom flytt av geopostlådor kan slutföras vid olika tidpunkter.

- Användare kan inte dela *postlådemappar* över geoplatser på Outlook på webben (hette tidigare Outlook Web App eller OWA). En användare i EU kan till exempel inte använda Outlook på webben för att öppna en delad mapp i en postlåda som finns i USA. Däremot kan Outlook på webben öppna  andra postlådor på olika geografiska platser genom att använda ett separat webbläsarfönster enligt beskrivningen i Öppna en annan persons postlåda i ett separat webbläsarfönster [i Outlook Web App](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362).

  **Obs!** Delning av mappar för flera geopostlådor stöds i Outlook på Windows.

- Gemensamma mappar stöds i organisationer med flera geografiska funktioner. De gemensamma mapparna måste dock finnas kvar på den centrala geoplatsen. Det går inte att flytta gemensamma mappar till satellitgeoplatser.

- I en multigeomiljö stöds inte granskning av flera geopostlådor. Om en användare till exempel har tilldelats behörigheter för att komma åt en delad postlåda på en annan geo plats loggas inte postlådeåtgärder som utförs av den användaren i granskningsloggen för postlådan för den delade postlådan. Mer information finns i [Hantera postlådegranskning](../compliance/enable-mailbox-auditing.md?view=o365-worldwide).
