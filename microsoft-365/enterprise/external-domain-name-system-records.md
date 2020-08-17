---
title: Externa DNS-poster för Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/21/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0
description: En referenslista över externa DNS-poster att använda när du planerar en distribution av Office 365.
ms.openlocfilehash: da5a9a1095e50de779ee2fc148803e31583426a2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694862"
---
# <a name="external-domain-name-system-records-for-office-365"></a>Externa DNS-poster för Office 365

|||
|:-----|:-----|
|![Domän](../media/e05b1c78-1df0-4200-ba40-6e26b7ead68f.png)|**Vill du se en anpassad lista över DNS-posterna för din Office 365-organisation?** Du [hittar den information du behöver för att skapa Office 365 DNS-poster ](https://support.office.microsoft.com/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67) för din domän i Office 365.  <br/> **Vill du ha steg för steg instruktioner för hur du lägger till dessa poster hos domänens DNS-värd, t. ex. GoDaddy eller eNom?** [Hitta länkar till steg för steg instruktioner för många vanliga DNS-värdar](https://go.microsoft.com/fwlink/?LinkId=286745). <br/>  **Hänger du kvar för att använda referenslistan för en egen anpassad distribution?** Nedanstående lista bör användas som referens för en anpassad Office 365-distribution. Du måste välj vilka poster som gäller för din organisation och fylla i lämpliga värden. <br/> **Gå tillbaka till **[Nätverksplanering och prestandajustering för Office 365](https://aka.ms/tune)..  <br/> |

Ofta är SPF-och MX-posterna svårast att reda ut. Vi har uppdaterat vår vägledning för SPF-poster i slutet av den här artikeln. Det viktiga att komma ihåg är att _du bara kan ha en enda SPF-post för domänen_. Du kan ha flera MX-poster men det kan orsaka problem med e-postleveranser. Om du har en enda MX-post som dirigerar e-post till ett e-postsystem undviker du många möjliga problem.
  
Avsnitten nedan är ordnade per tjänst i Office 365. För att se en anpassad lista över Office 365 DNS-posterna för din domän, loggar du in på Office 365 och [ du hittar här den information du behöver för att skapa Office 365 DNS-postes](https://support.office.com/article/77f90d4a-dc7f-4f09-8972-c1b03ea85a67).
  
## <a name="external-dns-records-required-for-office-365-core-services"></a>Externa DNS-poster som krävs för Office 365 (kärntjänster)
<a name="BKMK_ReqdCore"> </a>

Alla Office 365-kunder måste lägga till två poster i sin externa DNS. Den första CNAME-posten ser till att Office 365 kan dirigera arbetsstationer att autentisera med lämplig identitetsplattform. Den andra obligatoriska posten är till för att bevisa att du äger domännamnet.
  
||||
|:-----|:-----|:-----|
|**DNS-post** <br/> |**Syfte** <br/> |**Värde som ska användas** <br/> |
|**CNAME** <br/> **(Serie)** <br/> |Används av Office 365 för att dirigera autentiseringen till rätt identitetsplattform. [Mer information](https://go.microsoft.com/fwlink/p/?LinkId=322005) <br/> **Obs1:** Detta CNAME gäller bara för Office 365 som drivs av 21Vianet. [Mer information](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-operated-by-21vianet)  |**Alias:** msoid  <br/> **Target:** clientconfig.partner.microsoftonline-p.net.cn  <br/> |
|**TXT** <br/> **(Domänverifiering)** <br/> |Används av Office 365 för att verifiera att du äger domänen. Det påverkar inte något annat.  <br/> |**Värd:** @ (eller, för vissa DNS-värdtjänster, ditt domännamn)  <br/> **TXT-värde:** _en textsträng som tillhandahålls av_ Office 365  <br/> Office 365 guiden för **domänkonfiguration ** anger värdena du använder för att skapa den här posten.  <br/> |


## <a name="external-dns-records-required-for-email-in-office-365-exchange-online"></a>Externa DNS-poster som krävs för e-post i Office 365 (Exchange Online)
<a name="BKMK_ReqdCore"> </a>

E.post i Office 365 kräver flera olika poster. De tre primära posterna som alla kunder ska använda är Autodiscover, MX och SPF.
  
- Med **Autodiscover-posten** kan klientdatorer automatiskt hitta Exchange och konfigurera klienten på rätt sätt.

- **MX-posten** berättar för andra e-postsystem vart e-posten ska skickas för din domän. **Obs!:** När du ändrar e-posten till Office 365, genom att uppdatera domänens MX-post, levereras ALL e-post som skickas till den domänen till Office 365.  
Vill du bara att några e-postadresser går över till Office 365? Du kan [ pilottesta Office 365 med några e-postadresser på din anpassade domän.](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7).

- **TXT-posten för SPF** används av mottagar-e-postsystem för att verifiera att den server som skickar din e-post är den du godkänner. Det hjälper till att förhindra problem som förfalskning och nätfiske. Se [Externa DNS-poster som krävs för SPF](external-domain-name-system-records.md#BKMK_SPFrecords)i den här artikeln för att få hjälp att förstå vad du ska inkludera i posten.

E-postkunder som använder Exchange-federation behöver även CNAME- och TXT-posten som visas längst ned i tabellen.
  
||||
|:-----|:-----|:-----|
|**DNS-post** <br/> |**Syfte** <br/> |**Värde som ska användas** <br/> |
|**CNAME** <br/> **(Exchange Online)** <br/> |Hjälper Outlook-klienter att enkelt ansluta till Exchange Online-tjänsten genom att använda tjänsten Automatisk upptäckt. Automatisk upptäckt hittar automatiskt rätt Exchange Server-värd och konfigurerar Outlook för användarna.  <br/> |**Alias:** Autodiscover  <br/> **Target:** autodiscover.outlook.com  <br/> |
|**MX** <br/> **(Exchange Online)** <br/> |Skickar ingående e-post för domänen till Exchange Online-tjänsten i Office 365.  <br/> [!NOTE] När e-posten flödar till Exchange Online tar du bort MX-posterna som pekar på ditt gamla system.   |**Domän:** till exempel contoso.com  <br/> **E-postmålserver:**\<MX token\>.mail.protection.outlook.com  <br/> **Inställning/prioritet:** lägre än andra MX-poster (det ser till att e-posten levereras till Exchange Online) – t.ex. 1 eller ”låg”  <br/>  Hitta din \<MX token\>genom att följa dessa anvisningar:  <br/>  Logga in på Office 365, gå till Office 365 administratörsdomäner \>.  <br/>  Välj Åtgärda problem i kolumnen Åtgärd för domänen.  <br/>  Välj Vad behöver jag åtgärda i avsnittet MX-poster.  <br/>  Följ anvisningarna på sidan för att uppdatera MX-posten.  <br/> [Vad är MX-prioritet?](https://go.microsoft.com/fwlink/p/?LinkId=396471) <br/> |
|**SPF (TXT)** <br/> **(Exchange Online)**  <br/> |Förhindrar att andra personer använder din domän till att skicka skräppost eller annan skadlig e-post. SPF-poster (Sender Policy Framework) fungerar genom att identifiera servrarna som har godkänts för att skicka e-post från domänen.  <br/> |[Externa DNS-poster som krävs för SPF](external-domain-name-system-records.md#BKMK_SPFrecords) <br/> |
|**TXT** <br/> **(Exchange federation)** <br/> |Används för Exchange-federation för hybriddistribution.  <br/> |**TXT-post 1:** Till exempel contoso.com och tillhörande särskilt genererad hash-text som domänbevis (t.ex. Y96nu89138789315669824)  <br/> **TXT-post 2:** till exempel exchangedelegation.contoso.com och tillhörande särskilt genererad hash-text som domänbevis (t.ex.Y3259071352452626169)  <br/> |
|**CNAME** <br/> **(Exchange federation)** <br/> |Hjälper Outlook-klienter att enkelt ansluta till Exchange Online-tjänsten genom att använda tjänsten Automatisk upptäckt när företaget använder Exchange-federation. Automatisk upptäckt hittar automatiskt rätt Exchange Server-värd och konfigurerar Outlook för dina användare.  <br/> |**Alias:** till exempel Autodiscover.service.contoso.com  <br/> **Target:** autodiscover.outlook.com  <br/> |


## <a name="external-dns-records-required-for-skype-for-business-online"></a>Externa DNS-poster som krävs för Skype för företag Online
<a name="BKMK_ReqdCore"> </a>

Det finns olika åtgärder att vidta när du använder [Office 365 URL: er och IP-adressintervall ](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) för att kontrollera att nätverket är konfigurerat på rätt sätt.

> [!NOTE]
> De här DNS-posterna gäller även för Teams, särskilt i ett hybrid Teams och Skype för företag-scenario, där vissa Federations problem kan uppstå.
  
||||
|:-----|:-----|:-----|
|**DNS-post** <br/> |**Syfte** <br/> |**Värde som ska användas** <br/> |
|**SRV** <br/> **(Skype for företag online)** <br/> |Gör så att Office 365-domänen kan dela funktioner för snabbmeddelanden med externa klienter genom att aktivera SIP-federation. Mer information finns i [URL-adresser och IP-adressintervall för Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO).  <br/> |**Tjänst**: sipfederationtls  <br/> **Protokoll:** TCP  <br/> **Prioritet:** 100  <br/> **Vikt:** 1  <br/> **Port:** 5061  <br/> **Target:** sipfed.online.lync.com  <br/> **Obs!:** Om brandväggen eller proxyservern blockerar SRV-sökningar på en extern DNS bör du lägga till den här posten i den interna DNS-posten.   |
|**SRV** <br/> **(Skype for företag online)** <br/> |Används av Skype för företag för att koordinera flödet av information mellan Lync-klienter.  <br/> |**Tjänst**: sip  <br/> **Protokoll**: TLS  <br/> **Prioritet:** 100  <br/> **Vikt:** 1  <br/> **Port:** 443  <br/> **Target**: sipdir.online.lync.com  <br/> |
|**CNAME** <br/> **(Skype for företag online)** <br/> |Används av Lync-klienten för att hjälpa till att hitta Skype för företag online-tjänsten och logga in.  <br/> |**Alias:** sip  <br/> **Target**: sipdir.online.lync.com  <br/> Mer information finns i [URL-adresser och IP-adressintervall för Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO).  <br/> |
|**CNAME** <br/> **(Skype for företag online)** <br/> |Används av Lync-mobilklienten för att hjälpa till att hitta Skype för företag online-tjänsten och logga in.  <br/> |**Alias:** lyncdiscover  <br/> **Target:** webdir.online.lync.com  <br/> |

## <a name="external-dns-records-required-for-office-365-single-sign-on"></a>Externa DNS-poster krävs för enkel inloggning för Office 365
<a name="BKMK_ReqdCore"> </a>

||||
|:-----|:-----|:-----|
|**DNS-post** <br/> |**Syfte** <br/> |**Värde som ska användas** <br/> |
|**Värd (A)** <br/> |Används för enkel inloggning (SSO). Det anger slutpunkten för externa användare (och lokala användare om du vill) för att ansluta till serverproxy för din Active Directory Federation Services (AD FS) eller belastningsutjämnad virtuell IP (VIP).  <br/> |**Mål:** till exempel sts.contoso.com  <br/> |

## <a name="external-dns-records-required-for-spf"></a>Externa DNS-poster som krävs för SPF
<a name="BKMK_SPFrecords"> </a>

> [!IMPORTANT]
> SPF har utformats för att hjälpa till att förhindra förfalskning men det finns förfalskningsmetoder som SPF inte skyddar mot. För att kunna skydda mot dessa ska du, efter att ha konfigurerat SPF, även konfigurera DKIM och DMARC för Office 365. Information om hur du kommer igång finns i [Använda DKIM för att validera utgående e-post som skickas från din domän i Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Därefter läser du [Använd DMARC för att validera e-post i Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
  
SPF-poster är TXT-poster som hjälper till att hindra andra personer från att använda domänen till att skicka skräppost eller annan skadlig e-post. SPF-poster (Sender Policy Framework) fungerar genom att identifiera servrarna som har godkänts för att skicka e-post från domänen.
  
Du kan bara ha en SPF-post (dvs. en TXT-post som definierar SPF) för domänen. Den enda posten kan ha några olika inkluderingar men det totala antalet DNS-sökningar som görs får inte vara mer än 10 (det hjälper till att förhindra överbelastningsattacker, DoS). Se tabellen och andra exempel nedan som hjälp för hur du skapar eller uppdaterar rätt SPF-postvärden för din miljö.
  
### <a name="structure-of-an-spf-record"></a>Strukturen för en SPF-post

Alla SPF-poster består av tre delar: deklarationen att det är en SPF-post, domänerna och IP-adresserna som ska skicka e-post och en regel för verkställande. Du behöver alla tre i en giltig SPF-post. Här är ett exempel på en gemensam SPF-post för Office 365 när du bara använder Exchange Online-e-post:
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com -all
```

Ett e-postsystem som tar emot e-post från din domän ser på SPF-posten, och om e-postservern som har skickat meddelandet är en Office 365-server accepteras meddelandet. Om servern som har skickat meddelandet är ditt gamla e-postsystem eller ett skadligt system på Internet, t. ex, kan det hända att SPF-kontrollen inte fungerar och meddelandet inte kunde levereras. Det här hjälper dig att förhindra förfalsknings-och nätfiskemeddelanden.
  
### <a name="choose-the-spf-record-structure-you-need"></a>Välj den SPF-poststruktur du behöver

För scenarier där du inte bara använder Exchange Online-e-post för Office 365 (till exempel när du även använder e-post som kommer från SharePoint Online) kan du använda följande tabell för att avgöra vad som ska ingå i värdet för posten.
  
> [!NOTE]
> Om du har ett komplicerat scenario som till exempel omfattar Edge-e-postservrar för att hantera e-posttrafik via brandväggen, behöver du konfigurera en mer detaljerad SPF-post. Lära dig hur du kan[ konfigurera SPF-poster i Office 365 för att förhindra förfalskning](https://go.microsoft.com/fwlink/?LinkId=787656). Du kan också lära dig mer om hur SPF fungerar med Office 365 genom att läsa [Hur Office 365 använder Sender Policy Framework (SPF) för att förhindra förfalskning](https://go.microsoft.com/fwlink/?LinkId=787065).
  
| Tal|Om du använder...  <br/> |Syfte  <br/> |Lägg till följande  <br/> |
|:-----|:-----|:-----|:-----|
|1  <br/> |Alla e-postsystem (obligatoriskt)  <br/> |Alla SPF-poster startar med det här värdet  <br/> |v=spf1  <br/> |
|2  <br/> |Exchange Online (vanlig)  <br/> |Använd med bara Exchange Online  <br/> |include:spf.protection.outlook.com  <br/> |
|3  <br/> |E-postsystem från tredje part (mindre vanligt)  <br/> ||inkluderar:\<email system like mail.contoso.com\>  <br/> |
|4  <br/> |Lokalt e-postsystem (mindre vanligt)  <br/> |Använd om du använder Exchange Online Protection eller Exchange Online plus ett annat e-postsystem  <br/> |ip4:\<0.0.0.0\>  <br/> ip6:\< : : \>  <br/> include:\<mail.contoso.com\>  <br/> Värdet inom parenteser (\<\>) ska vara andra e-postsystem som skickar e-post för din domän.  <br/> |
|5  <br/> |Alla e-postsystem (obligatoriskt)  <br/> ||-all  <br/> |

### <a name="example-adding-to-an-existing-spf-record"></a>Exempel: Lägga till i en befintlig SPF-post
<a name="bkmk_addtospf"> </a>

Om du redan har en SPF-post måste du lägga till eller uppdatera värden för Office 365. Anta att din befintliga SPF-post för contoso.com är följande:
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
```

Nu uppdaterar du SPF-posten för Office 365. Du redigerar den aktuella posten så att du har en SPF-post med de värden du behöver. For Office 365, "spf.protection.outlook.com".
  
Rätt:
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:spf.protection.outlook.com include:smtp.adatum.com -all
```

Fel:
  
``` dns
Record 1:
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
Record 2:
Values: v=spf1 include:spf.protection.outlook.com -all
```

### <a name="more-examples-of-common-spf-values"></a>Fler exempel på vanliga SPF-värden
<a name="bkmk_addtospf"> </a>

Om du använder den fullständiga Office 365-sviten och använder MailChimp för att skicka marknadsföringsmeddelanden med e-post kan SPF-posten på contoso.com se ut enligt följande, med raderna 1, 3 och 5 från tabellen ovan. Kom ihåg att raderna 1 och 5 är obligatoriska.
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:servers.mcsv.net -all
```

Alternativt: om du har en Exchange-hybridkonfiguration där e-posten skickas från både Office 365 och lokala e-postsystem kan SPF-posten på contoso.com se ut så här:
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:mail.contoso.com -all
```

Det här är några vanliga exempel som kan hjälpa dig att anpassa den befintliga SPF-posten när du lägger till din domän i Office 365 för e-post. Om du har ett komplicerat scenario som till exempel omfattar Edge-e-postservrar för att hantera e-posttrafik via brandväggen, behöver du konfigurera en mer detaljerad SPF-post. Lära dig hur du kan[ konfigurera SPF-poster i Office 365 för att förhindra förfalskning](https://go.microsoft.com/fwlink/?LinkId=787656).
  
Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/o365edns](https://aka.ms/o365edns)
