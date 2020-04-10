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
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: Lär dig mer om domäner och deras associerade DNS-poster för att hantera dina Office 365-domäner.
ms.openlocfilehash: 4fd41102193a9e630ed04a9d1fb2e196dc94486b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210474"
---
# <a name="dns-basics"></a>Grundläggande om DNS

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
::: moniker range="o365-worldwide"

Domännamn, till exempel contoso.com, hanteras med ett världsomspännande system för domänregistratorer och databaser. DNS (Domain Name System) tillhandahåller en mappning mellan läsbara dator värdnamn och de IP-adresser som används av nätverksutrustning. En förståelse av grunderna i DNS och domän registrator kan hjälpa dig att hantera domäner i Office 365.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

Domännamn, till exempel contoso.com, hanteras med ett världsomspännande system för domänregistratorer och databaser. DNS (Domain Name System) tillhandahåller en mappning mellan läsbara dator värdnamn och de IP-adresser som används av nätverksutrustning. En förståelse av grunderna i DNS och domän registrator kan hjälpa dig att hantera domäner i Office 365.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

Domännamn, till exempel contoso.com, hanteras med ett världsomspännande system för domänregistratorer och databaser. DNS (Domain Name System) tillhandahåller en mappning mellan läsbara dator värdnamn och de IP-adresser som används av nätverksutrustning. En förståelse av grunderna i DNS och domänregistrator kan hjälpa dig att hantera domäner i Office 365 som drivs av 21Vianet.
  
::: moniker-end

## <a name="what-are-domain-names"></a>Vad är domännamn?

Domännamn används i URL:er och e-postadresser, och de har olika nivåer. Till exempel är mail.contoso.com ett domännamn med följande tre nivåer:
  
- **.com** är domänen på toppnivå 
    
- ** contoso** är domänen på andra nivån 
    
- **mail** är domänen på tredje nivån 
    
Varför ska du använda en domän på tredje nivån? Det kan vara en bra idé att ha olika domännamn för marknadsföring eller en blogg. Exempel: blog.contoso.com. Du lägger vanligtvis till en domän på andra nivån, t. ex. contoso.com, för att använda med Office 365 men du kan också använda domäner på tredje nivån om du vill.
  
Läs mer om vad du kan göra med domäner för respektive typ av erbjudande i [Tjänstbeskrivning för Office 365-domäner](https://go.microsoft.com/fwlink/?LinkId=402693).
  
## <a name="understand-dns-record-types"></a>Förstå DNS-posttyper

DNS-poster som lagras hos en DNS-värd för din domän används för att dirigera trafik för din domän. I följande tabell beskrivs vanliga DNS-poster och hur de används med Office 365.
  
|**NS-post (namnserver)**|** identifierar du de namnservrar som är de ”auktoritativa namnservrarna” för en domän. Om du ändrar namnservrarna för domänen ändrar du också var DNS-posterna hanteras och var DNS-systemet letar information om e-postservrar och annat. I Office 365 används en separat uppsättning namnservrar. Du kan dock välja att fortsätta använda de namnservrar som redan används för din egen domän.**|
|:-----|:-----|
|A-post (adresspost)  <br/> |Associerar ett domännamn med en IP-adress.  <br/> |
|CNAME-post (alias eller kanoniskt namn)  <br/> |Omdirigerar om en domän till en annan i DNS-systemet. När en namnserver letar upp en domän och den domänen har en CNAME-post ersätter servern det första domännamnet med CNAME-posten och sedan söker den efter det nya namnet.  <br/> |
|MX-post (e-postutbyte)  <br/> |Punkter dit e-postmeddelandet ska skickas. MX-posten har också ett prioritetsfält så att du kan skicka e-postmeddelanden till olika servrar i prioritetsordning.  <br/> |
|SPF-post (Sender Policy Framework)  <br/> |En TXT-post som förhindrar förfalskning och nätfiske.  <br/> |
|SRV-post (servicepost)  <br/> |Används av Skype för företag – Online och Exchange Online för att samordna informationsflödet mellan Office 365-tjänster. Till exempel krävs SRV-poster för att se närvaroinformation i Outlook för webben och för att använda Skype för företag Online, Skype eller andra verktyg för snabbmeddelanden med personer på andra företag.  <br/> |
|TTL (Time-To-Live)  <br/> |TLL står för hur länge en namnserver behåller en DNS-post innan servern blir låst för en uppdaterad version.  <br/> |
   
## <a name="how-does-dns-work"></a>Hur fungerar DNS?

En del av att konfigurera din domän med en molntjänst, till exempel Office 365 omfattar att ändra eller lägga till [DNS-poster](dns-basics.md) för domänen. Dessa ändringar är nödvändiga eftersom Internet använder DNS, Domain Name System, och domännamn för att ta reda på vart något ska skickas eller var något finns, till exempel e-post och webbplatser. 
  
Tack vare DNS (Domain Name System) kan vi använda vanliga namn som contoso.com för att hitta specifika webbplatser istället för de mer komplicerade IP-adresserna (Internet Protocol) som används under ytan. IP-adresser ser ut ungefär som 70.42.241.42, så att du kan se det är mycket enklare att använda ett domännamn för att identifiera platser som e-postvärdar och webbplatser.
  
Det är alltså ett kort svar: DNS-posterna talar om för Internet var du ska skicka e-post (t. ex. joe@contoso.com) eller hitta webbplatser (som www.contoso.com) som använder ditt domännamn. När du placerar rätt information till rätt DNS-poster för din domän, dirigerar DNS-systemet allt som finns på rätt sätt så att din e-post till exempel anländer till Office 365 i stället för någon annanstans.
  
En domäns DNS-poster kan vara till hjälp på andra sätt. En domäns DNS-poster kan vara användbart på andra sätt också. Till exempel Exchange kontrollerar en DNS-post som kan Outlook automatiskt konfigurera en anslutning till höger Exchange-server.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>DNS-poster hjälper Internet skicka e-post till rätt plats

Som du läser ovan, DNS i princip omdirigerar trafik kring Internet, mappa eget domännamn i de svårt att komma ihåg IP-adresser. En DNS-post, en så kallad MX-post används specifikt för att skicka e-post till rätt värd.
  
DNS-poster är som en databas med information om din domän. Posterna och deras värden behålls i något som kallas en zonfil som innehåller en lista över alla poster för din domän och dess värde. Domänregistratorer och andra DNS-värdar tillhandahåller användargränssnitt för webbplatser så att du kan redigera posterna i domänens zonfil. Och det är där du uppdaterar MX-posten för din domän, så att du kan skicka e-postmeddelanden till Office 365.
  
 *När du ändrar e-posten till Office 365, genom att uppdaterar din domäns MX-post i nästa steg, börjar ALL e-post som skickas till den domänen att komma till Office 365.*  Om andra personer använder din domän för e-post måste du konfigurera Office 365-postlådor för var och en av dem. 
  
Låter komplicerat? Ja, det kan vara, men vi hjälper dig steg för steg i konfigurationen av Office 365-domänen.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>DNS-talar om för Internet var du ska leta för webbplatser

När du skriver på en webbplatsadress, till exempel www.contoso.com, kontrollerar Internet först med en av DNS-servrarna efter något som kallas namnserver-post (i det här fallet) contoso.com. NS-posten talar om för Internet var den ska leta efter zonfilen som innehåller alla andra DNS-värden för domänen. Det finns många DNS-servrar som är anslutna till varandra. Servrarna arbetar tillsammans för att hålla reda på alla registrerade domännamn som måste vara unika och var domänens zonfiler finns.
  
::: moniker range="o365-worldwide"

Anta att NS-posten för contoso.com säger "godaddy.com". Nu vet Internet att GoDaddy.com är platsen den ska leta efter zonfilen som innehåller alla andra DNS-poster för contoso.com. De här DNS-posterna innehåller MX-posten som anger var e-post ska skickas till contoso.com och andra poster. Om MX-posten har ett värde som säger (men i tekniska termer) "skicka e-post till Office 365", kommer alla e-postmeddelanden som skickas till en contoso.com-e-postadress (till exempel joe@contoso.com) att skickas. Så länge det finns en postlåda som heter ”joe”, kommer e-postmeddelandet att levereras.

::: moniker-end

::: moniker range="o365-germany"

Anta att NS-posten för contoso.com säger "godaddy.com". Nu vet Internet att GoDaddy.com är platsen den ska leta efter zonfilen som innehåller alla andra DNS-poster för contoso.com. De här DNS-posterna innehåller MX-posten som anger var e-post ska skickas till contoso.com och andra poster. Om MX-posten har ett värde som säger (men i tekniska termer) "skicka e-post till Office 365", kommer alla e-postmeddelanden som skickas till en contoso.com-e-postadress (till exempel joe@contoso.com) att skickas. Så länge det finns en postlåda som heter ”joe”, kommer e-postmeddelandet att levereras.

::: moniker-end

::: moniker range="o365-21vianet"

Anta att NS-posten för contoso.com säger "hichina.com". Nu vet Internet att hichina’.com är platsen den ska leta efter zonfilen som innehåller alla andra DNS-poster för contoso.com. De här DNS-posterna innehåller MX-posten som anger var e-post ska skickas till contoso.com och andra poster. Om MX-posten har ett värde som säger (men i tekniska termer) "skicka e-post till Office 365", kommer alla e-postmeddelanden som skickas till en contoso.com-e-postadress (till exempel joe@contoso.com) att skickas. Så länge det finns en postlåda som heter ”joe”, kommer e-postmeddelandet att levereras.

::: moniker-end

De faktiska värdena som du måste ange för att alla ska fungera med Office 365 visas i anvisningarna när du konfigurerar din domän. Om du konfigurerar manuellt kan du kopiera och klistra in värdena i rätt DNS-poster (MX-post, CNAME-poster och så vidare) på din DNS-värd som kan vara din domänregistrator men behöver inte vara det.
  
::: moniker range="o365-worldwide"

Varför kan domänens zonfil finnas på en annan plats än hos din domänregistrator? Du kan också registrera domännamnet hos en domänregistrator, t. ex. GoDaddy, men dina DNS-poster kanske hanteras någon annanstans, på ett separat värdföretag för DNS eller ett webbhotell. NS-posterna för din domän lagrar information så att alla DNS-servrar vet var de ska leta.

::: moniker-end

::: moniker range="o365-germany"

Varför kan domänens zonfil finnas på en annan plats än hos din domänregistrator? Du kan också registrera domännamnet hos en domänregistrator, t. ex. GoDaddy, men dina DNS-poster kanske hanteras någon annanstans, på ett separat värdföretag för DNS eller ett webbhotell. NS-posterna för din domän lagrar information så att alla DNS-servrar vet var de ska leta.

::: moniker-end

::: moniker range="o365-21vianet"

Varför kan domänens zonfil finnas på en annan plats än hos din domänregistrator? Du kan också registrera domännamnet hos en domänregistrator, t. ex. HiChina, men dina DNS-poster kanske hanteras någon annanstans, på ett separat värdföretag för DNS eller ett webbhotell. NS-posterna för din domän lagrar information så att alla DNS-servrar vet var de ska leta.

::: moniker-end

> [!NOTE]
> Om du har konfigurerat en domän i Office 365 så att [Office 365 ställer in och hanterar DNS-posterna](../setup/domains-faq.md#how-does-office-365-manage-my-dns-records) åt dig kommer du som ett led i konfigurationen att [Ändra DNS-hanteringen till Office 365](../setup/domains-faq.md#change-dns-management-to-office-365). 
 

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-office-365"></a>Varför ska jag lägga till en domän i Office 365?


Genom att lägga till en egen domän, t. ex. fourthcoffee.com i Office 365 kan du använda en kortare, välbekant e-postadress och userID med tjänsten. Du [tilldelas en domän att använda](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) när du registrerar dig för ett Office 365-konto, men det innehåller "onmicrosoft.com". Många föredrar att lägga till sin organisation eller affärsdomän om de planerar att använda Office 365 för e-post. 
  
> [!NOTE]
> Om du bara vill ladda ned och använda Office 365-program, som Outlook och Word, behöver du inte lägga till en domän: [Installera Office på din PC eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx). 
  
Du kan använda ditt domännamn i Office 365 med din e-post, offentliga webbplats och din adress för snabbmeddelanden.
  
- **E-post:** ditt domännamn kan du anpassa din e-post så att du kan använda en kortare och enklare adress än [den första onmicrosoft.com e-postadress](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) som medföljer ditt konto. I stället för joe@contoso.onmicrosoft.com kan e-postadressen (som också är det arbetskonto som du använder för att logga in på Office 365) vara joe@contoso.com. 
    
- **Webbplats:** Om du har en Office 365-prenumeration med en offentlig SharePoint Online-webbplats (går inte längre att köpa) har den offentliga webbplatsen från början en adress enligt följande: contoso-public.sharepoint.com. Om du konfigurerar en webbplats för företaget kan du använda en egen domän för att byta namn på webbplatsens adress till något i stil med www.contoso.com. 
    
- **Snabbmeddelanden:** Adressen för ditt Skype för företag Online kan också anpassas med domännamnet så att personer i organisationen kan kommunicera via Skype för företag Online med en kortare, mer minnesvänlig adress (t.ex. joe@contoso.com). 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-office-365"></a>Varför ska jag lägga till en domän i Office 365?


Genom att lägga till en egen domän, t. ex. fourthcoffee.com i Office 365 kan du använda en kortare, välbekant e-postadress och userID med tjänsten. Du [tilldelas en domän att använda](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) när du registrerar dig för ett Office 365-konto, men det innehåller "onmicrosoft.com". Många föredrar att lägga till sin organisation eller affärsdomän om de planerar att använda Office 365 för e-post. 
  
> [!NOTE]
> Om du bara vill ladda ned och använda Office 365-program, som Outlook och Word, behöver du inte lägga till en domän: [Installera Office på din PC eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx). 
  
Du kan använda ditt domännamn i Office 365 med din e-post, offentliga webbplats och din adress för snabbmeddelanden.
  
- **E-post:** ditt domännamn kan du anpassa din e-post så att du kan använda en kortare och enklare adress än [den första onmicrosoft.com e-postadress](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) som medföljer ditt konto. I stället för joe@contoso.onmicrosoft.com kan e-postadressen (som också är det arbetskonto som du använder för att logga in på Office 365) vara joe@contoso.com. 
    
- **Webbplats:** Om du har en Office 365-prenumeration med en offentlig SharePoint Online-webbplats (går inte längre att köpa) har den offentliga webbplatsen från början en adress enligt följande: contoso-public.sharepoint.com. Om du konfigurerar en webbplats för företaget kan du använda en egen domän för att byta namn på webbplatsens adress till något i stil med www.contoso.com. 
    
- **Snabbmeddelanden:** Adressen för ditt Skype för företag Online kan också anpassas med domännamnet så att personer i organisationen kan kommunicera via Skype för företag Online med en kortare, mer minnesvänlig adress (t.ex. joe@contoso.com). 
    
::: moniker-end

## <a name="the-dns-records-required-for-office-365"></a>DNS-poster som krävs för Office 365

Det finns ett antal DNS-poster som krävs för att Office 365 ska fungera tillsammans med din domän. Förutom att ställa in domänens MX-post så att e-post skickas till Office 365 finns det också poster som hjälper till med åtgärder som att automatiskt ansluta Outlook till rätt Exchange-server, konfigurera snabbmeddelanden och förhindra skräppost.
  
Du kan [hitta en lista med värden](information-for-dns-records.md) att konfigurera din domän. De är inkluderade direkt i Office 365-portalen. 
  
Om du planerar en distribution kanske du vill granska en lista över alla de DNS-poster som behövs för Office 365, vad deras funktion är och exempelvärden. Ta en titt på [Externa DNS-poster för Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).
  
## <a name="how-can-i-learn-more"></a>Var hittar jag mer information?

Läs något av följande avsnitt: 
  
- Vet du inte var din domän är registrerad? [Få hjälp att hitta din domänregistrator](find-your-domain-registrar.md)
    
- Läs om [varför du måste slutföra stegen i guiden](../setup/add-domain.md) innan du kan använda domänen med Office 365. 
    

