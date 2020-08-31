---
title: Grundläggande om DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: Lär dig mer om domäner och deras associerade DNS-poster för att hantera dina domäner.
ms.openlocfilehash: 9819ec858eecb659f8576d9fa3c1ef426d500e80
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306569"
---
# <a name="dns-basics"></a>Grundläggande om DNS

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
::: moniker range="o365-worldwide"

Domännamn, till exempel contoso.com, hanteras med ett världsomspännande system för domänregistratorer och databaser. DNS (Domain Name System) tillhandahåller en mappning mellan läsbara dator värdnamn och de IP-adresser som används av nätverksutrustning. En förståelse av grunderna i DNS och domänregistratorer kan hjälpa dig att hantera domäner.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

Domännamn, till exempel contoso.com, hanteras med ett världsomspännande system för domänregistratorer och databaser. DNS (Domain Name System) tillhandahåller en mappning mellan läsbara dator värdnamn och de IP-adresser som används av nätverksutrustning. En förståelse av grunderna i DNS och domänregistratorer kan hjälpa dig att hantera domäner.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

Domännamn, till exempel contoso.com, hanteras med ett världsomspännande system för domänregistratorer och databaser. DNS (Domain Name System) tillhandahåller en mappning mellan läsbara dator värdnamn och de IP-adresser som används av nätverksutrustning. Administratörer som förstår grunderna i DNS- och domänregistratorer kommer att hantera domäner bättre.
  
::: moniker-end

## <a name="what-are-domain-names"></a>Vad är domännamn?

Domännamn används i URL:er och e-postadresser, och de har olika nivåer. Till exempel är mail.contoso.com ett domännamn med följande tre nivåer:
  
- **.com** är domänen på toppnivå 
    
- ** contoso** är domänen på andra nivån 
    
- **mail** är domänen på tredje nivån 
    
Varför ska du använda en domän på tredje nivån? Det kan vara en bra idé att ha olika domännamn för marknadsföring eller en blogg. Exempel: blog.contoso.com. Du lägger normalt till en domän på andra nivå som du kan använda med Microsoft, till exempel contoso.com, men om du föredrar kan du också använda domäner på tredje nivå.
  
Läs mer om vad du kan göra med domäner för varje typ av tjänst i beskrivningarna av [Microsoft 365 och Office 365-plattformen](https://go.microsoft.com/fwlink/?LinkId=402693).
  
## <a name="understand-dns-record-types"></a>Förstå DNS-posttyper

DNS-poster som lagras hos en DNS-värd för din domän används för att dirigera trafik för din domän. Följande tabell beskriver vanliga DNS-poster och hur de används.
  
|**NS-post (namnserver)**|**Identifierar namnservrar som är "auktoritära namnservrar" för en domän. När du ändrar domännamnservrar ändras det också var dina DNS-poster hanteras, där DNS-systemet letar efter information om e-postservrar och så vidare. Microsoft har sina egna namnservrar, eller så kan du välja att fortsätta använda namnservrar som redan är konfigurerade med din domän.**|
|:-----|:-----|
|A-post (adresspost)  <br/> |Associerar ett domännamn med en IP-adress.  <br/> |
|CNAME-post (alias eller kanoniskt namn)  <br/> |Omdirigerar om en domän till en annan i DNS-systemet. När en namnserver letar upp en domän och den domänen har en CNAME-post ersätter servern det första domännamnet med CNAME-posten och sedan söker den efter det nya namnet.  <br/> |
|MX-post (e-postutbyte)  <br/> |Punkter dit e-postmeddelandet ska skickas. MX-posten har också ett prioritetsfält så att du kan skicka e-postmeddelanden till olika servrar i prioritetsordning.  <br/> |
|SPF-post (Sender Policy Framework)  <br/> |En TXT-post som förhindrar förfalskning och nätfiske.  <br/> |
|SRV-post (servicepost)  <br/> |Används av Skype för företag Online och Exchange Online för att samordna dataflödet mellan Microsoft-tjänster. Till exempel krävs SRV-poster för att se närvaroinformation i Outlook för webben och för att använda Skype för företag Online, Skype eller andra verktyg för snabbmeddelanden med personer på andra företag.  <br/> |
|TTL (Time-To-Live)  <br/> |TLL står för hur länge en namnserver behåller en DNS-post innan servern blir låst för en uppdaterad version.  <br/> |
   
## <a name="how-does-dns-work"></a>Hur fungerar DNS?

En del av att ställa in din domän för en molntjänst som Microsoft 365 innebär att du ändrar eller lägger till [DNS-poster ](dns-basics.md)för domänen. Dessa ändringar är nödvändiga eftersom Internet använder DNS, Domain Name System, och domännamn för att ta reda på vart något ska skickas eller var något finns, till exempel e-post och webbplatser. 
  
Tack vare DNS (Domain Name System) kan vi använda vanliga namn som contoso.com för att hitta specifika webbplatser istället för de mer komplicerade IP-adresserna (Internet Protocol) som används under ytan. IP-adresser ser ut ungefär som 70.42.241.42, så att du kan se det är mycket enklare att använda ett domännamn för att identifiera platser som e-postvärdar och webbplatser.
  
Det är alltså ett kort svar: DNS-posterna talar om för Internet var du ska skicka e-post (t. ex. joe@contoso.com) eller hitta webbplatser (som www.contoso.com) som använder ditt domännamn. När du inkluderar rätt information i rätt DNS-poster för din domän dirigeras allt korrekt av DNS-systemet, så att din e-post kommer till exempel till Microsoft 365 och inte på en annan plats.
  
En domäns DNS-poster kan vara till hjälp på andra sätt. En domäns DNS-poster kan vara användbart på andra sätt också. Till exempel Exchange kontrollerar en DNS-post som kan Outlook automatiskt konfigurera en anslutning till höger Exchange-server.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS-poster hjälper Internet skicka e-post till rätt plats

Som du läser ovan, DNS i princip omdirigerar trafik kring Internet, mappa eget domännamn i de svårt att komma ihåg IP-adresser. En DNS-post, en så kallad MX-post används specifikt för att skicka e-post till rätt värd.
  
DNS-poster är som en databas med information om din domän. Posterna och deras värden behålls i något som kallas en zonfil som innehåller en lista över alla poster för din domän och dess värde. Domänregistratorer och andra DNS-värdar tillhandahåller användargränssnitt för webbplatser så att du kan redigera posterna i domänens zonfil. Och det här är platsen där du uppdaterar MX-posten för din domän för att skicka e-postmeddelanden till Microsoft 365.
  
 *När du överför din e-postadress till Microsoft 365 genom att uppdatera domänens MX-post i nästa steg, kommer alla e-postmeddelanden som skickas till den domänen till Microsoft 365.*  Om andra använder din domän för e-post måste du ställa in Microsoft 365-postlådor för varje person. 
  
Låter komplicerat? Det kan hända att vi guidar dig genom varje steg i Microsoft-domäninställningen.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>DNS-talar om för Internet var du ska leta för webbplatser

När du skriver på en webbplatsadress, till exempel www.contoso.com, kontrollerar Internet först med en av DNS-servrarna efter något som kallas namnserver-post (i det här fallet) contoso.com. NS-posten talar om för Internet var den ska leta efter zonfilen som innehåller alla andra DNS-värden för domänen. Det finns många DNS-servrar som är anslutna till varandra. Servrarna arbetar tillsammans för att hålla reda på alla registrerade domännamn som måste vara unika och var domänens zonfiler finns.
  
::: moniker range="o365-worldwide"

Anta att NS-posten för contoso.com säger "godaddy.com". Nu vet Internet att GoDaddy.com är platsen den ska leta efter zonfilen som innehåller alla andra DNS-poster för contoso.com. De här DNS-posterna innehåller MX-posten som anger var e-post ska skickas till contoso.com och andra poster. Om MX-posten har ett värde som säger (i tekniska termer) 'Skicka e-post till Microsoft 365' kommer alla e-postmeddelanden att adresseras där till en contoso.com-e-postadress (till exempel jan@contoso.com) skickas dit. Så länge det finns en postlåda som heter ”joe”, kommer e-postmeddelandet att levereras.

::: moniker-end

::: moniker range="o365-germany"

Anta att NS-posten för contoso.com säger "godaddy.com". Nu vet Internet att GoDaddy.com är platsen den ska leta efter zonfilen som innehåller alla andra DNS-poster för contoso.com. De här DNS-posterna innehåller MX-posten som anger var e-post ska skickas till contoso.com och andra poster. Om MX-posten har ett värde som säger (i tekniska termer) 'Skicka e-post till Microsoft 365' kommer alla e-postmeddelanden att adresseras där till en contoso.com-e-postadress (till exempel jan@contoso.com) skickas dit. Så länge det finns en postlåda som heter ”joe”, kommer e-postmeddelandet att levereras.

::: moniker-end

::: moniker range="o365-21vianet"

Anta att NS-posten för contoso.com säger "hichina.com". Nu vet Internet att hichina’.com är platsen den ska leta efter zonfilen som innehåller alla andra DNS-poster för contoso.com. De här DNS-posterna innehåller MX-posten som anger var e-post ska skickas till contoso.com och andra poster. Om MX-posten har ett värde som säger (i tekniska termer) 'Skicka e-post till Microsoft 365' kommer alla e-postmeddelanden att adresseras där till en contoso.com-e-postadress (till exempel jan@contoso.com) skickas dit. Så länge det finns en postlåda som heter ”joe”, kommer e-postmeddelandet att levereras.

::: moniker-end

De faktiska värdena som du måste ange för Microsoft 365 visas i stegen att följa när du konfigurerar din domän. Om du konfigurerar manuellt kan du kopiera och klistra in värdena i rätt DNS-poster (MX-post, CNAME-poster och så vidare) på din DNS-värd som kan vara din domänregistrator men behöver inte vara det.
  
::: moniker range="o365-worldwide"

Varför kan domänens zonfil finnas på en annan plats än hos din domänregistrator? Du kan också registrera domännamnet hos en domänregistrator, t. ex. GoDaddy, men dina DNS-poster kanske hanteras någon annanstans, på ett separat värdföretag för DNS eller ett webbhotell. NS-posterna för din domän lagrar information så att alla DNS-servrar vet var de ska leta.

::: moniker-end

::: moniker range="o365-germany"

Varför kan domänens zonfil finnas på en annan plats än hos din domänregistrator? Du kan också registrera domännamnet hos en domänregistrator, t. ex. GoDaddy, men dina DNS-poster kanske hanteras någon annanstans, på ett separat värdföretag för DNS eller ett webbhotell. NS-posterna för din domän lagrar information så att alla DNS-servrar vet var de ska leta.

::: moniker-end

::: moniker range="o365-21vianet"

Varför kan domänens zonfil finnas på en annan plats än hos din domänregistrator? Du kan också registrera domännamnet hos en domänregistrator, t. ex. HiChina, men dina DNS-poster kanske hanteras någon annanstans, på ett separat värdföretag för DNS eller ett webbhotell. NS-posterna för din domän lagrar information så att alla DNS-servrar vet var de ska leta.

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>Varför ska jag lägga till en domän i Microsoft 365?


Om du lägger till en anpassad domän, till exempel fourthcoffee.com, till Microsoft 365, kan du använda kortare, mer betrodda e-postadresser och använder-ID med tjänsten. Du[kommer att tilldelas en domän ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) när du registrerar dig för ett Microsoft 365-konto, men detta inkluderar onmicrosoft.com. Många föredrar att lägga till domänen för sin organisation eller företag om de vill använda Microsoft 365 för e-post. 
  
> [!NOTE]
> Om du bara vill ladda ned och använda Microsoft-program, som Outlook och Word, behöver du inte lägga till en domän: [Installera Office på din PC eller Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Du kan använda ditt domännamn i Microsoft 365 för din e-postadress, din offentliga webbplatsadress och din chattadress.
  
- **E-post:** ditt domännamn kan du anpassa din e-post så att du kan använda en kortare och enklare adress än [den första onmicrosoft.com e-postadress](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) som medföljer ditt konto. I stället för jan@contoso.onmicrosoft.com, kan e-postadressen (som också är det arbetskonto som du använder för att logga in på Microsoft 365) vara jan@contoso.com. 
    
- **Webbplats:** Om du har en Microsoft 365-prenumeration med en offentlig SharePoint Online-webbplats (går inte längre att köpa) har den offentliga webbplatsen från början en adress som följande: contoso-public.sharepoint.com. Om du konfigurerar en webbplats för företaget kan du använda en egen domän för att byta namn på webbplatsens adress till något i stil med www.contoso.com. 
    
- **Snabbmeddelanden:** Adressen för ditt Skype för företag Online kan också anpassas med domännamnet så att personer i organisationen kan kommunicera via Skype för företag Online med en kortare, mer minnesvänlig adress (t.ex. joe@contoso.com). 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a>Varför ska jag lägga till en domän i Microsoft 365?


Om du lägger till en anpassad domän, till exempel fourthcoffee.com, till Microsoft 365, kan du använda kortare, mer betrodda e-postadresser och använder-ID med tjänsten. Du[kommer att tilldelas en domän ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) när du registrerar dig för ett Microsoft 365-konto, men detta inkluderar onmicrosoft.com. Många föredrar att lägga till domänen för sin organisation eller företag om de vill använda Microsoft 365 för e-post. 
  
> [!NOTE]
> Om du bara vill ladda ned och använda Microsoft 365-appar, som Outlook och Word, behöver du inte lägga till en domän: [Installera Office på din PC eller Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Du kan använda ditt domännamn i Microsoft 365 för din e-postadress, din offentliga webbplatsadress och din chattadress.
  
- **E-post:** ditt domännamn kan du anpassa din e-post så att du kan använda en kortare och enklare adress än [den första onmicrosoft.com e-postadress](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) som medföljer ditt konto. I stället för jan@contoso.onmicrosoft.com, kan e-postadressen (som också är det arbetskonto som du använder för att logga in på Microsoft 365) vara jan@contoso.com. 
    
- **Webbplats:** Om du har en prenumeration med en offentlig SharePoint Online-webbplats (går inte längre att köpa) har den offentliga webbplatsen från början en adress som följande: contoso-public.sharepoint.com. Om du konfigurerar en webbplats för företaget kan du använda en egen domän för att byta namn på webbplatsens adress till något i stil med www.contoso.com. 
    
- **Snabbmeddelanden:** Adressen för ditt Skype för företag Online kan också anpassas med domännamnet så att personer i organisationen kan kommunicera via Skype för företag Online med en kortare, mer minnesvänlig adress (t.ex. joe@contoso.com). 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>DNS-poster som krävs för Microsoft 365

Det finns ett antal DNS-poster som krävs för att Microsoft 365 ska fungera tillsammans med din domän. Förutom att ställa in domänens MX-post så att e-post skickas till Microsoft 365 finns det också poster som hjälper till med åtgärder som att automatiskt ansluta Outlook till rätt Exchange-server, konfigurera snabbmeddelanden och förhindra skräppost.
  
Du kan [hitta en lista med värden](information-for-dns-records.md) att konfigurera din domän. De finns i Administrationscenter för Microsoft 365. 
  
Om du planerar en distribution kanske du vill granska en lista över alla de DNS-poster som behövs för Microsoft 365, vad deras funktion är och exempelvärden. Ta en titt på [Externa DNS-poster för Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).
  
## <a name="how-can-i-learn-more"></a>Var hittar jag mer information?

Läs något av följande avsnitt: 
  
- Vet du inte var din domän är registrerad? [Få hjälp att hitta din domänregistrator](find-your-domain-registrar.md)
- Läs om [varför du måste slutföra stegen i guiden](../setup/add-domain.md) innan du kan använda domänen med Microsoft 365.
