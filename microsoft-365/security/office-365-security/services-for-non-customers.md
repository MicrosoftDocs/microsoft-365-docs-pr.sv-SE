---
title: Tjänster för icke-kunder som skickar e-post till Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.openlocfilehash: 3a3dc26d757de84f5abd46c85f3596db67d676ae
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208240"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Tjänster för icke-kunder som skickar e-post till Microsoft 365

E-postmissbruk, skräppost och bedrägliga e-postmeddelanden (nätfiske) fortsätter att belasta hela e-postekosystemet. För att upprätthålla användarnas förtroende för användningen av e-post har Microsoft infört olika policyer och tekniker för att skydda våra användare. Microsoft förstår dock att legitim e-post inte bör påverkas negativt. Därför har vi etablerat en uppsättning tjänster som hjälper avsändare att förbättra sin förmåga att leverera e-post till Microsoft 365-användare genom att proaktivt hantera deras sändningsrykte.

Den här översikten innehåller information om fördelar som vi ger din organisation även om du inte är kund.

## <a name="sender-solutions"></a>Avsändare lösningar

|**Tjänst**|**Fördelar**|
|:-----|:-----|
|Detta online-hjälpinnehåll|Ger: <br/> En utgångspunkt för alla frågor som rör leverans av kommunikation till EOP-användare. <br/><br/> Innehåller en enkel onlineguide med våra policyer och krav. <br/><br/> En översikt över skräppostfilter och autentiseringstekniker som används av Microsoft.|
|[Microsoft-support](#microsoft-support)|Ger självhjälp och eskaleringsstöd för leveransproblem.|
|[Ip-portal för skräppost](#anti-spam-ip-delist-portal)|Ett verktyg för att skicka IP-avlistningsbegäran. Innan denna begäran lämnas in är det avsändarens ansvar att se till att ytterligare post från ip-adressen i fråga inte är kränkande eller skadlig.|
|[Missbruks- och skräppostrapportering för skräppost från Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Förhindrar att skräppost och annan oönskad e-post skickas från Exchange Online och belamar internet och ditt e-postsystem.|

## <a name="microsoft-support"></a>Microsoft-support

Microsoft erbjuder flera supportalternativ för personer som har problem med att skicka e-post till Microsoft 365-mottagare. Vi rekommenderar att du:

- Följ instruktionerna i alla rapporter om utebliven leverans som du får.

- Ta reda på de vanligaste problemen som icke-kunder stöter på vid [Felsökning av e-post som skickas till Office 365](troubleshooting-mail-sent-to-office-365.md).

- Använd [Microsoft 365-avlistningsportalen](https://sender.office.com) för att skicka en begäran om att få din IP borttagen från den blockerade avsändarens lista.

- Läs [Microsofts communityforum](https://community.office365.com/f/).

- Kontakta kunden som du försöker skicka e-post med en annan metod och be dem kontakta Microsoft Support och öppna en supportbiljett för din räkning. I vissa fall måste Microsoft Support av juridiska skäl kommunicera direkt med avsändaren som äger IP-utrymmet som blockeras. Icke-kunder kan dock vanligtvis inte öppna supportbiljetter.

  Mer information om Microsofts tekniska support för Office 365 finns i [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).

## <a name="anti-spam-ip-delist-portal"></a>Ip-portal för skräppost

Det här är en självbetjäningsportal som du kan använda för att ta bort dig själv från listan med blockerade avsändare från Microsoft 365. Använd den här portalen om du får ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365 och du inte tycker att du ska vara det. Mer information finns i [Använda avlistningsportalen för att ta bort dig själv från listan blockerade avsändare](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Missbruks- och skräppostrapportering för skräppost från Exchange Online

Ibland används Microsoft365 av tredje part för att skicka skräppost, i strid med våra användarvillkor och policyer. Om du får skräppost från Office 365 kan du rapportera dessa meddelanden till Microsoft. Instruktioner finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).
