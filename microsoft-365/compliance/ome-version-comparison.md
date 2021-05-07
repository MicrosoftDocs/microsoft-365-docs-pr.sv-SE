---
title: Jämförelse av meddelandekryptering (OME)
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: I den här artikeln förklaras skillnaderna mellan olika versioner av Meddelandekryptering i Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 92beb3625c0b115fe77f1667a448bf0bf9589040
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "52162658"
---
# <a name="compare-versions-of-ome"></a>Jämföra OME-versioner

> [!IMPORTANT]
> Den 28 februari 2021 utfasade Microsoft stöd för AD RMS i Exchange Online. Om du har distribuerat en hybridmiljö där dina Exchange-postlådor är online och du använder IRM med Active Directory RMS lokalt måste du migrera till Azure. Organisationer som har distribuerat till den GCC måttliga miljön påverkas också. Mer information finns i "Översikt över UTfasning av AD RMS Exchange Online" i den här artikeln.

I resten av den här artikeln jämförs äldre Meddelandekryptering i Office 365 (OME) med de nya OME-funktionerna och Office 365 Advanced Message Encryption. De nya funktionerna är en sammanslagning och nyare version av både OME och IRM (Information Rights Management). Unika egenskaper för distribution till GCC Hög beskrivs också. De två kan vara med i organisationen. Information om hur de nya funktionerna fungerar finns i Meddelandekryptering i Office 365 [(OME).](ome.md)

Den här artikeln är en del av en större serie artiklar om Meddelandekryptering i Office 365. Den här artikeln är avsedd för administratörer och ITPros. Om du bara letar efter information om att skicka eller ta emot ett krypterat meddelande kan du läsa listan med artiklar i [Meddelandekryptering i Office 365 (OME)](ome.md) och leta reda på den artikel som bäst passar dina behov.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Översikt över AD RMS-utfasning i Exchange Online

Exchange Online innehåller IRM-funktioner (Information Rights Management) som skyddar e-postmeddelanden och bifogade filer både online och offline. Som standard Exchange Online Azure Information Protection. Organisationen kan dock ha konfigurerat Exchange Online IRM för att använda en lokal AD RMS (Active Directory Rights Management Service). AD RMS stöd för Exchange Online kommer att ta tillbaka. I stället ersätter Azure Information Protection AD RMS helt och hållet.

Om du vill bedöma om den här utfasningen påverkar organisationen kan du gå till Migrera AD RMS till [Azure RMS i Exchange Online.](https://support.microsoft.com/help/5001237) Den här artikeln innehåller rekommendationer om migreringsalternativ.

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>Jämförelse sida vid sida av OME-funktioner

|           **Situation**           | **Äldre OME**    | **IRM i AD RMS**        | **Nya OME-funktioner** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Skicka krypterade e-postmeddelanden*        |Via Exchange för e-postflöde|Slutanvändare som initierats från Outlook eller Outlook på webben. eller Exchange för e-postflöde|Slutanvändare som initierats från Outlook, Outlook för Mac eller Outlook på webben. genom Exchange e-postflödesregler (kallas även transportregler) och skydd mot dataförlust (DLP)|
|*Mall för rättighetshantering*       |   Uppgift saknas      |Alternativet Vidarebefordra inte och anpassade mallar|Alternativet Vidarebefordra inte, endast krypterat och anpassade mallar|
|*Mottagartyp*                   |Interna och externa mottagare|Endast interna mottagare         |Interna och externa mottagare|
|*Funktion för intern mottagare*|Mottagarna får ett HTML-meddelande som de laddar ned och öppnar i en webbläsare eller mobilapp|Inbyggd upplevelse i Outlook klienter|Inbyggd upplevelse för mottagare i samma organisation med hjälp av Outlook klienter.  Mottagarna kan läsa meddelanden från OME-portalen med andra klienter än Outlook (ingen nedladdning eller app krävs).|
|*Upplevelse för extern mottagare*|Mottagarna får ett HTML-meddelande som de laddar ned och öppnar i en webbläsare eller mobilapp|Uppgift saknas|Inbyggd upplevelse för Microsoft 365 mottagare. Alla andra mottagare kan läsa meddelanden från OME-portalen (ingen nedladdning eller app krävs).|
|*Behörigheter för bifogade filer*           |Inga begränsningar för bifogade filer|Bifogade filer är skyddade|Bifogade filer är skyddade för alternativet Vidarebefordra inte och anpassade mallar. Administratörer kan välja om bifogade filer ska vara skyddade eller inte.|
|*Ta med din egen knapp (BYOK) stöd*|Inga                |Inga               |BYOK stöds          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Fördelar med de nya OME-funktionerna jämfört med äldre OME

De nya funktionerna har följande fördelar:

- Möjligheten att använda det krypterade alternativet (som möjliggör säkert samarbete), alternativet Vidarebefordra inte och anpassade begränsningar.
- Avsändare kan skicka e-post som krypteras med de nya funktionerna manuellt Outlook skrivbordet, Outlook för Mac och Outlook på webbklienter.
- Microsoft 365 mottagarna att använda en direkt infogade upplevelse i de Outlook klienter som stöds. Administratörer kan också välja att visa Microsoft 365 en profilerad upplevelse för mottagarna.
- Konton utanför Microsoft 365, till exempel Gmail-, Yahoo- och Microsoft-konton, externa med OME-portalen, vilket ger en bättre användarupplevelse för de här mottagarna. Alla andra identiteter använder en lösenordskod för att komma åt krypterade meddelanden.
- Administratörer kan anpassa varumärken och skapa flera varumärkesmallar.
- Administratörer kan återkalla e-postmeddelanden som krypteras med de nya funktionerna.
- Med de nya funktionerna får du detaljerade användningsrapporter via &amp; Säkerhetsefterlevnadscenter.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 Advanced Message Encryption funktioner

Office 365 Advanced Message Encryption har fler funktioner utöver de nya OME-funktionerna. Du måste ha de Meddelandekryptering i Office 365 funktionerna i din organisation för att kunna använda den avancerade meddelandekrypteringsfunktionerna. För att kunna använda de här funktionerna måste mottagarna också visa och svara på säker e-post via OME-portalen. De avancerade funktionerna omfattar:

- Återkallade meddelanden

- Förfallotid för meddelande

- Flera varumärkesmallar

Office 365 Advanced Message Encryption stöds inte i GCC Hög.

Information om hur du använder avancerad meddelandekryptering finns [i Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Unika egenskaper hos Meddelandekryptering i Office 365 i en GCC hög distribution

Om du planerar att använda Meddelandekryptering i Office 365 i en GCC hög miljö finns det vissa unika egenskaper för mottagarens upplevelse.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Krypterad e-post GCC hög och GCC mottagare med hög

Avsändare kan manuellt kryptera e-postmeddelanden i Outlook för PC, Mac och Outlook på webben, eller så kan organisationer konfigurera en princip för att kryptera e-postmeddelanden Exchange e-postflödesregler.

Mottagare i GCC Hög får samma infogade läsupplevelse i Outlook pc och Mac och Outlook på webben som alla andra användare.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Krypterad e-GCC hög och icke-GCC hög mottagare

Avsändare inom GCC Hög kan skicka krypterade e-postmeddelanden utanför GCC Hög gräns och vice versa.

Alla mottagare utanför GCC Hög, inklusive kommersiella Microsoft 365-användare, Outlook.com-användare och andra användare från andra e-postleverantörer som Gmail och Yahoo, får ett postomslag. Med det här figursättningsmeddelandet omdirigeras mottagaren till OME-portalen där mottagaren kan läsa och svara på meddelandet. Det gäller även avsändare utanför GCC hög skickar OME-krypterad e-post till GCC hög.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Samexistens av äldre OME och de nya funktionerna i samma klientorganisation

Du kan använda både äldre OME och de nya funktionerna i samma klientorganisation. Som administratör gör du det genom att välja vilken version av OME du vill använda när du skapar e-postflödesregler.

- Om du vill ange den äldre versionen av OME använder du Exchange-postflödesregelåtgärden **Använd den föregående versionen av OME.**

- Ange de nya funktionerna med hjälp av Exchange-postflödesregelåtgärd **Tillämpa Meddelandekryptering i Office 365 och rättighetsskydd**.

Användare kan skicka e-post manuellt som krypteras med de nya funktionerna Outlook skrivbordet, Outlook för Mac och Outlook på webben.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migrera från äldre OME till de nya funktionerna

Även om båda versionerna av OME kan användas tillsammans rekommenderar vi att du redigerar dina gamla e-postflödesregler som använder regelåtgärden Använd den tidigare versionen av **OME** för att använda de nya funktionerna. Uppdatera dessa regler för att använda e-postflödesregelåtgärden **Tillämpa Meddelandekryptering i Office 365 och rättighetsskydd**. Anvisningar finns i Definiera [e-postflödesregler för att kryptera e-postmeddelanden i Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Komma igång med OME

Vanligtvis är de nya OME-funktionerna automatiskt aktiverade för organisationen. Mer information om de nya OME-funktionerna i din organisation finns i [Konfigurera Meddelandekryptering i Office 365 funktioner.](set-up-new-message-encryption-capabilities.md)

Den äldre versionen av OME aktiveras automatiskt för organisationen om du har aktiverat Azure Information Protection. Tidigare fungerade omE även om Azure Information Protection inte var aktiverat. Så är inte längre fallet.

Om du vill börja använda äldre OME konfigurerar du e-postflödesregler som använder regelåtgärden Använd den tidigare versionen av **OME** om du har aktiverat Azure Information Protection. Anvisningar finns i Definiera [e-postflödesregler för att kryptera e-postmeddelanden.](define-mail-flow-rules-to-encrypt-email.md)