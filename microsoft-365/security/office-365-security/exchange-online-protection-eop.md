---
title: Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 70ab4af2-fec4-4886-8e12-27d348649204
description: Här är några saker du bör vara medveten om innan du börjar arbeta med EOP.
ms.openlocfilehash: 9c027d6c1ded10becd7c73dc3468270ff50edb55
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811848"
---
# <a name="exchange-online-protection"></a>Exchange Online Protection

Välkommen till Microsoft Exchange Online Protection (EOP) värd e-postfiltrering tjänst. Här är några saker du bör vara medveten om innan du börjar arbeta med EOP och använda det här innehållet:

- Om du vill veta mer om EOP kan du läsa [beskrivningen av tjänsten Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Andra användbara resurser är [Exchange Online Protection översikt,](exchange-online-protection-overview.md) [EOP allmänna FAQ,](eop-general-faq.md)och [EOP funktioner,](eop-features.md)samt [Exchange Online Protection hemsida](https://products.office.com/exchange/exchange-email-security-spam-protection).

- För att komma igång med EOP bör nya kunder [bege sig till Konfigurera din EOP-tjänst.](set-up-your-eop-service.md) Det här avsnittet innehåller steg som hjälper dig att få Igång EOP.

- Om du behöver mer hjälp eller vill dela idéer, [eop forumet](https://go.microsoft.com/fwlink/?LinkId=285351) är ett bra ställe att börja.

## <a name="eop-help-for-administrators"></a>EOP-hjälp för administratörer

Hjälpinnehållet för EOP-administratörer består av följande kategorier på den översta nivån:

- [Översikt över Exchange Online Protection](exchange-online-protection-overview.md): Introducerar hur EOP fungerar och innehåller länkar till ytterligare information.

- [EOP-funktioner:](eop-features.md)Innehåller en lista över funktioner som finns i EOP.

- [Konfigurera eop-tjänsten:](set-up-your-eop-service.md)Innehåller steg för att konfigurera eop-tjänsten och länkar till ytterligare information.

- [Byt till EOP från Google Postini, Barracuda Spam and Virus Firewall eller Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Beskriver processen för att byta till EOP från en annan e-skyddsprodukt.

- [Hantera mottagare och administratörsrollgrupper i EOP](manage-recipients-and-admin-role-groups-in-eop.md): Beskriver hur du hanterar mottagare och hur du tilldelar användare till administratörsrollgrupper.

- [E-postflöde i EOP](mail-flow-in-eop.md): Beskriver hur du konfigurerar scenarier för anpassade e-postmeddelanden med hjälp av kopplingar, hur du hanterar domäner som är associerade med tjänsten och hur du aktiverar dbeb-funktionen (Directory Based Edge Blocking).

- [Metodtips för att konfigurera EOP](best-practices-for-configuring-eop.md): Beskriver rekommenderade konfigurationsinställningar och överväganden för när du har konfigurerat och etablerat tjänsten.

- [Meddelandepolicy och efterlevnad i EOP](messaging-policy-and-compliance-in-eop.md): Beskriver hur du använder Exchange-flödesregler (kallas även transportregler) för att genomdriva specifika företagsregler och principer och hur du använder granskningsrapporter för att spåra konfigurationsändringar i tjänsten.

- [Skydd mot skräppost och skadlig kod i Office 365](anti-spam-and-anti-malware-protection.md): Beskriver filtrering av skräppost och filtrering av skadlig kod och visar hur du anpassar dem så att de bäst uppfyller organisationens behov. Beskriver också uppgifter som administratörer och slutanvändare kan utföra på meddelanden i karantän.

- [Rapportering och meddelandespårning i Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Beskriver de rapporter och felsökningsverktyg som är tillgängliga.

- [Exchange administrationscenter i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md): Beskriver hur du kommer åt och navigerar via EAC-hanteringsgränssnittet (Exchange Admin Center) för att hantera eop-tjänsten.

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell): Ger information om remote PowerShell, som gör att du kan hantera eOP-tjänsten från kommandoraden.

- [Hjälp och stöd för EOP](help-and-support-for-eop.md) Ger information om hur du hämtar hjälp och teknisk support.

## <a name="eop-help-for-end-users"></a>EOP-hjälp för slutanvändare

Hjälpinnehållet för att hjälpa EOP-slutanvändare att hantera skräppost består av följande avsnitt:

- [Hitta och släpp meddelanden i karantän som användare](find-and-release-quarantined-messages-as-a-user.md): Beskriver hur slutanvändare kan hitta och släppa sina egna meddelanden om skräppost i karantäni skräppostkarantänen och eventuellt rapportera dem som inte skräp till Microsoft.

- [Skicka meddelanden om skräppost, icke-skräppost och nätfiskebedrägerier till Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md): Beskriver de olika sätt som slutanvändarna kan skicka in skräppostmeddelanden (skräppost) och icke-skräppostmeddelanden till Microsoft. Det här avsnittet innehåller länkar till de rapporteringsverktyg som finns i Microsoft Outlook och Outlook på webben (tidigare känt som Outlook Web App).

- [Skicka skadlig kod och skadlig kod till Microsoft för analys](submitting-malware-and-non-malware-to-microsoft-for-analysis.md): Beskriver hur slutanvändare kan skicka skadlig kod som gjorde det förbi filtren eller skicka in en fil som felaktigt identifierades som skadlig kod.

- Slutanvändare kan lägga till specifika användare eller domäner i en lista över betrodda avsändare eller en blockerad avsändarlista genom att konfigurera sina skräppostinställningar i Outlook eller Outlook på webben. Observera att meddelanden som skickas från blockerade avsändare markeras som skräppost, inte avvisade, vilket innebär att de kan hämtas från mappen Skräppost eller karantän (beroende på var administratören har konfigurerat tjänsten för att skicka skräppost.) Mer information finns [i Använda tillägget Rapportmeddelande](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

- [Hjälp och stöd för EOP](help-and-support-for-eop.md) Ger information om hur du hämtar hjälp och teknisk support.
