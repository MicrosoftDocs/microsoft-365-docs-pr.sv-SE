---
title: Meddelandekryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du skickar och tar emot krypterade e-postmeddelanden mellan personer inom och utanför organisationen.
ms.openlocfilehash: 504fa9918636cd596cde0d242083ccb7b9817e69
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162241"
---
# <a name="message-encryption"></a>Meddelandekryptering

Personer använder ofta e-post för att utbyta känslig information, t.ex. ekonomiska data, juridiska kontrakt, konfidentiell produktinformation, försäljningsrapporter och projektioner, patientinformation eller kund- och personalinformation. Därför kan postlådor bli lagringskorgar för stora mängder potentiellt känslig information och det kan leda till ett allvarligt hot för organisationen.

Med Meddelandekryptering i Office 365 kan din organisation skicka och ta emot krypterade e-postmeddelanden mellan personer inom och utanför organisationen. Meddelandekryptering i Office 365 fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster. Kryptering av e-postmeddelanden säkerställer att endast tilltänkta mottagare kan visa meddelandeinnehållet.

## <a name="how-office-365-message-encryption-works"></a>Så Meddelandekryptering i Office 365 fungerar

Resten av den här artikeln gäller de nya OME-funktionerna.

Meddelandekryptering i Office 365 är en onlinetjänst som bygger på Microsoft Azure Rights Management (Azure RMS) som ingår i Azure Information Protection. Den här tjänsten innehåller principer för kryptering, identitet och auktorisering för att skydda din e-post. Du kan kryptera meddelanden med hjälp av rättighetshanteringsmallar, [alternativet](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)Vidarebefordra inte och [alternativet för endast kryptering.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

Användare kan sedan kryptera e-postmeddelanden och olika bifogade filer med hjälp av dessa alternativ. En fullständig lista över bifogade filtyper som stöds finns i "Filtyper som omfattas av IRM-principer när de bifogas i meddelanden" i Introduktion till [IRM för e-postmeddelanden.](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)

Som administratör kan du också definiera e-postflödesregler för att tillämpa det här skyddet. Du kan till exempel skapa en regel som kräver kryptering av alla meddelanden som är adresserade till en viss mottagare, eller som innehåller specifika ord i ämnesraden, och även ange att mottagare inte kan kopiera eller skriva ut innehållet i meddelandet.

Till skillnad från den föregående versionen av OME ger de nya funktionerna en enhetlig avsändarupplevelse oavsett om du skickar e-post inom organisationen eller till mottagare utanför Microsoft 365. Mottagare som får ett skyddat e-postmeddelande som skickas till ett Microsoft 365-konto i Outlook 2016 eller Outlook på webben behöver inte vidta någon annan åtgärd för att visa meddelandet. Det fungerar smidigt. Mottagare som använder andra e-postklienter och e-posttjänster har också en förbättrad upplevelse. Mer information finns i [Läs om skyddade meddelanden i Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) hur öppnar jag ett [skyddat meddelande.](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)

En detaljerad lista över skillnaderna mellan den tidigare versionen av OME och de nya OME-funktionerna finns i [Jämföra versioner av OME.](ome-version-comparison.md)

När någon skickar ett e-postmeddelande som matchar en krypteringsregel för e-postflöde krypteras meddelandet innan det skickas. Alla Microsoft 365 användare som använder Outlook-klienter för att läsa e-post får inbyggda läsupplevelser i första klassen för krypterad och rättighetsskyddad e-post även om de inte finns i samma organisation som avsändaren. Exempel Outlook klienter är Outlook stationär dator, Outlook Mac, Outlook Mobile på iOS och Android och Outlook på webben (tidigare kallat Outlook Web App).

Mottagare av krypterade meddelanden som får krypterad eller rättighetsskyddad e-post som skickas till sina konton på Outlook.com, Gmail och Yahoo får ett omslagsmeddelande som dirigerar dem till OME-portalen där de enkelt kan autentisera med hjälp av ett Microsoft-konto, Gmail eller Yahoo-autentiseringsuppgifter.

Slutanvändare som läser krypterad eller rättighetsskyddad e-post på andra klienter än Outlook använder också OME-portalen för att visa krypterade och rättighetsskyddade meddelanden som de tar emot.

Om avsändaren av det skyddade e-postmeddelandet finns i GCC Hög och mottagaren är utanför GCC Hög, inklusive kommersiella användare, Outlook.com-användare och användare från andra e-postleverantörer, till exempel Gmail, får mottagaren ett postomslag. Med figursättningsmeddelandet dirigeras mottagaren till OME-portalen där mottagaren kan läsa och svara på meddelandet. Annars, om både avsändaren och mottagaren finns i miljön GCC High, även om de inte finns i samma organisation, får mottagare som använder Outlook-klienter för att läsa e-post inbyggda läsupplevelser i första klassen för krypterad och rättighetsskyddad e-post. Mer information om de olika versionerna i GCC Hög finns i [Jämför versioner av OME.](ome-version-comparison.md)

Mer information om storleksbegränsningar för meddelanden och bifogade filer som du kan kryptera med OME finns [Exchange Online Begränsningar.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Så Office 365 Advanced Message Encryption fungerar med OME

Office 365 Advanced Message Encryption kan du skapa flera varumärkesmallar så att du kan finjustera kontrollen över mottagarens e-post och skapa anpassade varumärkesupplevelser för att stödja en diverse organisationsstruktur.

Avancerad meddelandekryptering i Microsoft 365 hjälper dig att uppfylla efterlevnadsskyldigheter som kräver mer flexibel kontroll över extern mottagares åtkomst till krypterade e-postmeddelanden. Med Avancerad meddelandekryptering i Office 365 kan du som administratör styra känsliga e-postmeddelanden som delas utanför organisationen med automatiska principer som identifierar typer av känslig information (t.ex. PII, FINANS- och hälso-ID) och nyckelord för att förbättra skyddet genom att gå ut genom en säker webbportal för krypterade e-postmeddelanden. Som administratör kan du styra krypterade e-postmeddelanden som nås via en Microsoft 365-webbportal genom att återkalla åtkomsten till ett e-postmeddelande när som helst.

Återkallade meddelanden och förfallodatum fungerar bara för e-postmeddelanden som användarna skickar till mottagare utanför organisationen. Dessutom måste mottagarna få åtkomst till e-post via webbportalen. För att säkerställa att mottagaren använder portalen för att ta emot e-post skapar du en anpassad varumärkesmall som använder wrapper. Därefter använder du varumärkesmallen i en e-postflödesregel. Mer information om avancerad meddelandekryptering finns i [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="defining-rules-for-office-365-message-encryption"></a>Definiera regler för Meddelandekryptering i Office 365

Ett sätt att aktivera de nya funktionerna för Meddelandekryptering i Office 365 är att Exchange Online och Exchange Online Protection definiera e-postflödesregler. Dessa regler avgör under vilka förhållanden e-postmeddelanden ska krypteras. När en krypteringsåtgärd anges för en regel krypteras alla meddelanden som matchar regelvillkoren innan de skickas.

E-postflödesregler är flexibla så att du kan kombinera villkor så att du kan uppfylla specifika säkerhetskrav i en enda regel. Du kan till exempel skapa en regel för att kryptera alla meddelanden som innehåller angivna nyckelord och som är adresserade till externa mottagare. Med de nya funktionerna för Meddelandekryptering i Office 365 också kryptera svar från mottagare av krypterad e-post.

Mer information om hur du skapar e-postflödesregler för att dra nytta av de nya OME-funktionerna finns i [Definiera regler för Meddelandekryptering i Office 365.](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-the-new-ome-capabilities"></a>Kom igång med de nya OME-funktionerna

Om du är redo att börja använda de nya OME-funktionerna i din organisation kan du gå till Konfigurera [Meddelandekryptering i Office 365 funktioner.](set-up-new-message-encryption-capabilities.md)

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Skicka, visa och svara på krypterade e-postmeddelanden

Med Meddelandekryptering i Office 365 kan användare skicka krypterade e-postmeddelanden Outlook och Outlook på webben. Dessutom kan administratörer konfigurera e-postflödesregler i Microsoft 365 att automatiskt kryptera e-postmeddelanden baserat på nyckelordsmatchning eller andra villkor.

Mottagare av krypterade meddelanden som finns i organisationer kommer att kunna läsa dessa meddelanden smidigt i alla versioner av Outlook, inklusive Outlook för PC, Outlook för Mac, Outlook på webben, Outlook för iOS och Outlook för Android. Användare som tar emot krypterade meddelanden på andra e-postklienter kan visa meddelandena i OME-portalen.

Detaljerad information om hur du skickar och visar krypterade meddelanden finns i dessa artiklar.

|Läs den här artikeln ...|Om du är ...|
|:-----|:-----|
|[Läs mer om skyddade meddelanden i Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|En slutanvändare som vill veta mer om hur krypterade meddelanden fungerar och vilka alternativ som är tillgängliga för dig.|
|[Hur öppnar jag ett skyddat meddelande?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|En slutanvändare som vill läsa ett skyddat meddelande som har skickats till dig. Den här artikeln innehåller information om hur du läser meddelanden i flera versioner av Outlook och från olika e-postkonton, inklusive konton utanför Microsoft 365 till exempel gmail och Yahoo! konton.|
|[Skicka, visa och svara på krypterade meddelanden i Outlook](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|En slutanvändare som vill skicka, visa eller svara på ett krypterat meddelande från Outlook. Även om du inte är medlem i en organisation får du fortfarande ett meddelande om krypterade meddelanden som skickas till dig i Outlook. Använd den här artikeln för anvisningar om hur du visar och svarar på krypterade meddelanden som skickas Office 365.|
|[Skicka ett digitalt signerat eller krypterat meddelande](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|En slutanvändare som vill skicka, visa eller svara på krypterade meddelanden med Outlook för Mac. I den här artikeln beskrivs också hur du använder andra krypteringsmetoder än OME, till exempel S/MIME.|
|[Visa krypterade meddelanden på en Android-enhet](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|En slutanvändare som har fått ett meddelande som krypterats med Meddelandekryptering i Office 365 på din Android-enhet kan du använda den kostnadsfria OME-visningsappen för att visa meddelandet och skicka ett krypterat svar. I den här artikeln förklaras hur.|
|[Visa krypterade meddelanden på din iPhone eller iPad](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|En slutanvändare som har fått ett meddelande som krypterats med Meddelandekryptering i Office 365 på din iPhone eller iPad kan du använda den kostnadsfria OME-visningsappen för att visa meddelandet och skicka ett krypterat svar. I den här artikeln förklaras hur.|
||