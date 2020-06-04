---
title: Skapa listor med spärrade avsändare
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Administratörer kan lära sig mer om tillgängliga och önskade alternativ för att blockera inkommande meddelanden i Exchange Online Protection (EOP).
ms.openlocfilehash: 2862fa4a33a31eac9c61f94aa929133d2dc69fc8
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545906"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Skapa blockerade avsändarelistor i EOP

I Microsoft 365-organisationer med postlådor i Exchange Online- eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor erbjuder EOP flera sätt att blockera e-post från oönskade avsändare. Dessa alternativ inkluderar Outlook-blockerade avsändare, blockerade avsändare eller blockerade domänlistor i anti-spam-principer, Exchange-regler för e-postflöde (kallas även transportregler) och IP-blockeringslistan (anslutningsfiltrering). Tillsammans kan du se dessa alternativ som _blockerade avsändarelistor_.

Den bästa metoden för att blockera avsändare varierar beroende på omfattningen av påverkan. För en enskild användare kan rätt lösning vara Outlook-blockerade avsändare. För många användare skulle ett av de andra alternativen vara lämpligare. Följande alternativ rangordnas efter både effektomfång och bredd. Listan går från smal till bred, men *läs detaljerna* för fullständiga rekommendationer.

1. Outlook-blockerade avsändare (listan Blockerade avsändare som lagras i varje postlåda)

2. Blockerade avsändande listor eller blockerade domänlistor (policyer mot skräppost)

3. Regler för e-postflöde

4. IP-blockeringslistan (anslutningsfiltrering)

> [!NOTE]
> Även om du kan använda organisationsomfattande blockinställningar för att åtgärda falska negativ (missat skräppost), bör du också skicka dessa meddelanden till Microsoft för analys. Om du hanterar falska negativ genom att använda blockeringslistor ökar dina administrativa kostnader avsevärt. Om du använder blockeringslistor för att avleda missade skräppost måste du hålla ämnet [Rapportmeddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md) redo.

Däremot har du också flera alternativ för att alltid tillåta e-post från specifika källor med hjälp av _säkra avsändarelistor_. Mer information finns i [Skapa listor över betrodda avsändare](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Grunderna i e-postmeddelande

Ett standardmeddelande för SMTP-meddelanden består av ett *meddelandekuvert* och meddelandeinnehåll. Meddelandekuvertet innehåller information som krävs för att överföra och leverera meddelandet mellan SMTP-servrar. Meddelandeinnehållet innehåller fält för meddelandehuvud (kallas gemensamt *meddelandehuvudet)* och meddelandetexten. Meddelandekuvertet beskrivs i RFC 5321 och meddelandehuvudet beskrivs i RFC 5322. Mottagarna ser aldrig det faktiska meddelandekuvertet eftersom det genereras av meddelandeöverföringsprocessen och det är faktiskt inte en del av meddelandet.

- `5321.MailFrom`Adressen (kallas även **MAIL FROM-adressen,** P1-avsändaren eller kuvertavsändaren) är den e-postadress som används i SMTP-överföringen av meddelandet. Den här e-postadressen registreras vanligtvis i fältet **Retursökväg** i meddelandehuvudet (även om avsändaren kan ange en annan **e-postadress för retursökväg).** Om meddelandet inte kan levereras är det mottagaren för rapporten om utebliven leverans (kallas även NDR eller avvisningsmeddelande).

- `5322.From`(även känd som **Från-adressen** eller P2-avsändaren) är e-postadressen i fältet **Från-huvud** och är avsändarens e-postadress som visas i e-postklienter.

Ofta är `5321.MailFrom` adresserna och `5322.From` desamma (kommunikation mellan person och person). Men när e-post skickas på uppdrag av någon annan, kan adresserna vara olika.

Blockerade avsändarelistor och blockerade domänlistor i anti-spam-principer i EOP inspekterar både `5321.MailFrom` `5322.From` och adresser. Outlook Blockerade avsändare använder bara `5322.From` adressen.

## <a name="use-outlook-blocked-senders"></a>Använda Outlook-blockerade avsändare

När endast ett litet antal användare fick oönskad e-post kan användare eller administratörer lägga till avsändarens e-postadresser i listan Blockerade avsändare i postlådan. Instruktioner finns i [Konfigurera inställningar för skräppost på Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).

När meddelanden har blockerats på grund av en användares lista Blockerade avsändare innehåller huvudfältet **X-Forefront-Antispam-Report** värdet `SFV:BLK` .

> [!NOTE]
> Om de oönskade meddelandena är nyhetsbrev från en ansedd och igenkännlig källa, är avskrivning från e-postmeddelandet ett annat alternativ för att hindra användaren från att ta emot meddelandena.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Använda blockerade avsändarelistor eller blockerade domänlistor

När flera användare påverkas är omfattningen bredare, så det näst bästa alternativet är blockerade avsändarelistor eller blockerade domänlistor i anti-spam-principer. Meddelanden från avsändare i listorna markeras som **Skräppost**och den åtgärd som du har konfigurerat för domen i **skräppostfiltret** tas med i meddelandet. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).

Den maximala gränsen för dessa listor är cirka 1000 poster.

## <a name="use-mail-flow-rules"></a>Använda regler för e-postflöde

Om du behöver blockera meddelanden som skickas till specifika användare eller i hela organisationen kan du använda regler för e-postflöde. Regler för e-postflöde är mer flexibla än blockavsändare eller blockerade avsändaredomänlistor eftersom de också kan söka efter nyckelord eller andra egenskaper i de oönskade meddelandena.

Oavsett de villkor eller undantag som du använder för att identifiera meddelandena konfigurerar du åtgärden för att ställa in skräppostförtroendenivån (SCL) för meddelandet till 9, vilket markerar meddelandet som ett **skräppost med högt förtroende**. Mer information finns i [Använda regler för e-postflöde för att ange SCL i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> Det är enkelt att skapa regler som är *alltför* aggressiva, så det är viktigt att du bara identifierar de meddelanden som du vill blockera med mycket specifika kriterier. Se också till att aktivera granskning av regeln och testa resultatet av regeln för att säkerställa att allt fungerar som förväntat.

## <a name="use-the-ip-block-list"></a>Använda IP-blockeringslistan

När det inte är möjligt att använda något av de andra alternativen för att blockera en avsändare bör du *först då* använda IP-blockeringslistan i anslutningsfilterprincipen. Mer information finns i [konfigurera policy för anslutningsfilter](configure-the-connection-filter-policy.md). Det är viktigt att hålla antalet blockerade IP-adresser till ett minimum, så att blockera hela IP-adressintervall rekommenderas *inte.*

Du bör *särskilt* undvika att lägga till IP-adressintervall som tillhör konsumenttjänster (till exempel outlook.com) eller delade infrastrukturer, och även se till att du granskar listan över blockerade IP-adresser som en del av regelbundet underhåll.
