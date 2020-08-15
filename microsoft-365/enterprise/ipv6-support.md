---
title: IPv6-stöd i Office 365-tjänster
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 'Sammanfattning: beskriver IPv6-stöd i Microsoft Office 365-komponenter och i Office 365 stats support.'
ms.openlocfilehash: c4ecd2ef26ecf660eb1d172b1951907724d2238a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694478"
---
# <a name="ipv6-support-in-office-365-services"></a>IPv6-stöd i Office 365-tjänster

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Office 365 stöder både IPv6 och IPv4; men inte alla Office 365-funktioner är helt aktiverade med IPv6. Det innebär att du måste använda både IPv4 och IPv6 för att ansluta till Office 365. Om du filtrerar utgående trafik till Office 365 finns den fullständiga listan över IPv6-adresser som stöds av Office 365 i artikeln [Office 365 URL: er och IP-adressintervall](urls-and-ip-address-ranges.md). När nätverket är konfigurerat och rätt IPv6-adresser tillåts kan du hämta [Office 365 IPv6 test plan](https://go.microsoft.com/fwlink/?LinkId=293447) från Microsoft Download Center.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>IPv6-stöd i prenumerations tjänsten för Office 365

### <a name="exchange-online-and-ipv6"></a>Exchange Online och IPv6

Om programmet som du använder för att ansluta till Exchange Online har stöd för IPv6 används IPv6 som standard i både kabelanslutna och trådlösa nätverk. Om du vill styra kommunikationen till Exchange Online kan du använda IP-adressintervall i [Office 365 URL: er och IP-adressintervall](urls-and-ip-address-ranges.md).
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online och IPv6

 **Office 365 myndigheter G1/G3/G4/K1** Om det program som du använder för att ansluta till SharePoint Online har stöd för IPv6 försöker det använda IPv6 som standard.
  
 **Offentliga moln för flera innehavare** Microsoft möjliggör SharePoint Online-IPv6 på din begäran. Du måste ange IP-adresserna för din organisations DNS-struktur för CIDR-uppskrivning. Kom ihåg att den här DNS-infrastrukturen inte kan delas av andra organisationer för IPv6 så att den kan aktive ras för din klient organisation. När IPv6 är aktiverat används IPv6 som standard om programmet som du använder för att ansluta till SharePoint Online har stöd för IPv6.
  
Om det program som du använder för att ansluta till SharePoint Online har stöd för IPv6 används IPv6 som standard i både kabelanslutna och trådlösa nätverk. Om du vill styra kommunikationen till SharePoint Online använder du IP-adressintervallet i [Office 365 URL: er och IP-adressintervall](urls-and-ip-address-ranges.md).
  
 **Office 365 myndigheter G1/G3/G4/K1** Om det program som du använder för att ansluta till SharePoint Online har stöd för IPv6 försöker det använda IPv6 som standard.
  
### <a name="skype-for-business-and-ipv6"></a>Skype för företag och IPv6

Observera att IPv6 inte stöds i Skype för företag och kan inte längre aktive ras.
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection och IPv6

Exchange Online Protection (EOP) stöder IPv6 om överföringen sker via säkerhets protokollet Transport Layer. Använd [Office 365 URL: er och IP-adressintervall](urls-and-ip-address-ranges.md)för det EOP intervallet.
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>IPv6-stöd för statligt utbud av Office 365

Stöd för Office 365 IPv6 för statliga offerter som följer organisationens förvaltnings-och budget avtal (OMB) för chefens myndigheters och byråers företags administratörer, samt statliga myndigheter för införande av en IPv6-memorandum (Internet Protocol version 6). [Microsoft Office 365 för myndigheter](https://go.microsoft.com/fwlink/p/?LinkId=325414) är en tjänst för flera innehavare som lagrar statliga uppgifter i ett avdelat gemenskaps moln. Precis som andra Office 365-erbjudanden tillhandahåller den funktioner för produktivitet och samarbete, inklusive Exchange Online, Skype för företag, SharePoint Online och Microsoft 365-appar för företag. 

Microsoft Office 365 myndighets bud gäller endast för 2013 och senare. Mer information om statligt utbud för Office 365 finns i artikeln [om att lansera office 365 för myndigheter: ett forum moln i USA](https://go.microsoft.com/fwlink/p/?LinkId=325414). Internationell trafik i stöd reglerna (ITAR) är en uppsättning amerikanska myndighets regler som styr export och import av skydd mot försvar i [Munitions lista (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415). 

Microsoft Office 365 för företag tillhandahåller dedikerade värd tjänster för Microsoft-lösningar som stöder säkerhets-, integritets-och myndighets krav för amerikanska myndigheter som kräver Federal Information Security Management (FISMA)-certifiering och kommersiella enheter, beroende på ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Saker att tänka på när du använder IPv6 och Office 365

Vi rekommenderar att du inte inaktiverar IPv6. Mer information finns i den här [artikeln](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). För att ta reda på vilka IP-versioner som används i nätverket bör du tänka på följande:
  
- Om visningen av kommandot **ipconfig** i kommando tolken innehåller rader med namnet "IPv6-adress" eller "tillfällig IPv6-adress" har du IPv6 i din miljö.

- Om alla IPv6-adresser börjar med "FE80" och motsvarar rader med namnet "länk lokal IPv6-adress" har du inte IPv6 i din miljö.

Dessa överväganden kanske gäller för ditt nätverk:
  
- Den offentliga abonnemangs tjänsten stöder inte inköp via kredit kort via IPv6. Detta gäller inte statliga community-molnet (GCC) eftersom regeringarna har en licens för Enterprise Agreement (EA).

- IPv6 stöder inte vissa RMS-scenarier (Rights Management Services).

- IPv6 stöder inte Black Berry® Enterprise Server (BES) eftersom Black Berry inte stöder IPv6.

- Om du använder AD FS (Active Directory Federation Services) med Office 365 stöds inte din AD FS-slutpunkt till Office 365 med IPv6. Du bör inte ta med AAAA-poster i AD FS DNS-posten när du använder Exchange Online. 

Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)
  
## <a name="see-also"></a>Se även

[Utbildnings översikt för IPv6](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Hjälp guide för IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
