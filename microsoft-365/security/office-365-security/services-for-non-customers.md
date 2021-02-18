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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: För att se till att användarna litar på användningen av e-post har Microsoft lagt till olika principer och tekniker som hjälper oss att skydda våra användare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 879d2c9d3bc2af0f78a25eb1381a74b67171e939
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290769"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Tjänster för icke-kunder som skickar e-post till Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Missbruk, skräppost och bedrägliga e-postmeddelanden (nätfiske) fortsätter att belasta hela e-postsystemet. För att se till att användarna litar på användningen av e-post har Microsoft fört med sig olika principer och tekniker för att skydda våra användare. Microsoft förstår dock att legitima e-postmeddelanden inte ska påverkas negativt. Därför har vi upprättat en uppsättning tjänster som hjälper avsändare att förbättra sin förmåga att leverera e-post till Microsoft 365-användare genom att proaktivt hantera deras rykte.

Den här översikten ger information om de fördelar vi ger din organisation även om du inte är kund.

## <a name="sender-solutions"></a>Avsändarlösningar

****

|Tjänst|Fördelar|
|---|---|
|Det här onlinehjälpinnehållet|Innehåller: <ul><li>En utgångspunkt för frågor om att leverera kommunikation till EOP-användare.</li><li>Innehåller en enkel onlineguide med våra principer och krav.</li><li>En översikt över skräppostfilter och autentiseringstekniker som används av Microsoft.</li><ul>|
|[Microsoft Support](#microsoft-support)|Ger stöd för egenhjälp och eskalering för leveransproblem.|
|[Avlistportalen för IP-skydd mot skräppost](#anti-spam-ip-delist-portal)|Ett verktyg för att skicka en IP-begäran om avlistning. Innan den här begäran skickas är det avsändarens ansvar att säkerställa att all ytterligare e-post som kommer från ip-adressen i fråga inte är olämplig eller skadlig.|
|[Rapportering av missbruk och skräppost för skräppost som kommer från Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Gör att skräppost och annan oönskad e-post inte skickas från Exchange Online och gör att Internet och ditt e-postsystem blir rörigt.|
|

## <a name="microsoft-support"></a>Microsoft Support

Microsoft erbjuder flera supportalternativ för användare som har problem med att skicka e-post till Microsoft 365-mottagare. Vi rekommenderar att du:

- Följ instruktionerna i den rapport om utebliven leverans som du får.

- Kolla in de vanligaste problemen som icke-kunder stöter på vid [felsökning av e-post som skickas till Office 365.](troubleshooting-mail-sent-to-office-365.md)

- Använd [Microsoft 365-portalen för att](https://sender.office.com) skicka en begäran om att få din IP borttagen från listan med spärrade avsändare.

- Läs [Microsoft-forumen på communityn.](https://community.office365.com/f/)

- Kontakta kunden som du försöker e-posta med en annan metod och be honom eller henne att kontakta Microsoft Support och öppna ett support ärende åt dig. I vissa fall måste Microsoft Support kommunicera direkt med avsändaren som äger det IP-utrymme som blockeras. Men icke-kunder kan vanligtvis inte öppna supportärenden.

  Mer information om Microsofts tekniska support för Office 365 finns i [Support.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)

## <a name="anti-spam-ip-delist-portal"></a>Avlistportalen för IP-skydd mot skräppost

Det här är en självbetjäningsportal som du kan använda för att ta bort dig själv från listan med spärrade avsändare i Microsoft 365. Använd den här portalen om du får ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365 och du inte tror att du ska vara det. Mer information finns i Använda [avlisteportalen för att ta bort dig själv från listan med spärrade avsändare.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Rapportering av missbruk och skräppost för skräppost som kommer från Exchange Online

Ibland används Microsoft365 av tredje part för att skicka skräppost, i strid med våra användningsvillkor och vår policy. Om du får skräppost från Office 365 kan du rapportera dessa meddelanden till Microsoft. Instruktioner finns i Rapportera [meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)
