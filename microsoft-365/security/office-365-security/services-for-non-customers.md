---
title: Tjänster för icke-kunder som skickar e-post till Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/2/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: För att upprätthålla användarnas förtroende för användningen av e-post har Microsoft infört olika policyer och tekniker för att skydda våra användare.
ms.openlocfilehash: f6dc3cdb4ffb20fba1dbaa8d57d5041bf1cdbeae
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811484"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a>Tjänster för icke-kunder som skickar e-post till Office 365

Missbruk av e-post, skräppost och bedrägliga e-postmeddelanden (nätfiske) fortsätter att belasta hela e-postekosystemet. För att upprätthålla användarnas förtroende för användningen av e-post har Microsoft infört olika policyer och tekniker för att skydda våra användare. Microsoft förstår dock att legitim e-post inte bör påverkas negativt. Därför har vi upprättat en uppsättning tjänster som hjälper avsändare att förbättra deras förmåga att leverera e-post till Office 365-användare genom att proaktivt hantera deras sändande rykte.

Den här översikten innehåller information om fördelar som vi ger din organisation även om du inte är en Office 365-kund.

## <a name="sender-solutions"></a>Avsändareslösningar

|**Tjänst**|**Fördelar**|
|:-----|:-----|
|Detta online hjälpinnehåll| Ger:  <br/>  En utgångspunkt för frågor som rör leverans av kommunikation till EOP-användare  <br/>  Innehåller en enkel onlineguide med våra policyer och krav  <br/>  En översikt över skräppostfilter och autentiseringstekniker som används av Microsoft|
|[Microsoft-support](#microsoft-support)|Ger självhjälps- och eskaleringsstöd för leveransproblem.|
|[Office 365 Anti-Spam IP Delist Portal](#office-365-anti-spam-ip-delist-portal)|Ett verktyg för att skicka IP-avlistbegäran. Innan du skickar in denna begäran är det avsändarens ansvar att se till att ytterligare e-post som kommer från undersökningsperioden i fråga inte är kränkande eller skadlig.|
|[Missbruk och skräppost rapportering för skräppost från Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Håller skräppost och annan oönskad e-post från att skickas från Exchange Online och belamra Internet och ditt e-postsystem.|

## <a name="microsoft-support"></a>Microsoft-support

Microsoft erbjuder flera supportalternativ för personer som har problem med att skicka e-post till Office 365-inkorgar. Vi rekommenderar att du:

- Följ instruktionerna i alla rapporter om utebliven leverans som du får.

- Kolla in de vanligaste problemen som icke-kunder stöter på i [Felsökning av e-post som skickas till Office 365](troubleshooting-mail-sent-to-office-365.md).

- Använd [avlistningsportalen Office 365](https://sender.office.com) för att skicka en begäran om att din IP ska tas bort från listan över blockerade avsändare.

- Läs [Microsoft-communityforumen](https://community.office365.com/f/).

- Kontakta Office 365-kunden som du försöker skicka e-post med en annan metod och be dem kontakta Microsoft Support och öppna en supportbiljett för din räkning. I vissa fall måste Microsoft Support av juridiska skäl kommunicera direkt med avsändaren som äger IP-utrymmet som blockeras. Icke-kunder kan dock vanligtvis inte öppna supportbiljetter.

  Mer information om Microsoft Technical-support för Office 365 finns i [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).

## <a name="office-365-anti-spam-ip-delist-portal"></a>Office 365 Anti-Spam IP Delist Portal

Det här är en självbetjäningsportal som du kan använda för att ta bort dig själv från listan över blockerade avsändare i Office 365. Använd den här portalen om du får ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Office 365 och du tycker inte att du ska vara det. Mer information finns i [Använda delist-portalen för att ta bort dig själv från listan med spärrade avsändare i Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Missbruk och skräppost rapportering för skräppost från Exchange Online

Ibland används Office 365 av tredje part för att skicka skräppost, i strid med våra användarvillkor och policy. Om du får skräppost från Office 365 kan du rapportera dessa meddelanden till [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com). Bifoga de felande meddelandena, inklusive hela meddelandehuvudet, i RFC 5322- eller ARF-format. Outlook på webben användare kan använda inbyggda verktyg för att rapportera skräppost. Information finns i [Rapportera skräppost och nätfiskebedrägerier i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).
