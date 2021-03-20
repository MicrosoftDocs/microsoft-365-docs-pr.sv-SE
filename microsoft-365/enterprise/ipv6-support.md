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
description: 'Sammanfattning: Beskriver stöd för IPv6 i Microsoft Office 365-komponenter och i Office 365-myndighetserbjudanden.'
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909688"
---
# <a name="ipv6-support-in-office-365-services"></a>IPv6-stöd i Office 365-tjänster

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Office 365 stöder både IPv6 och IPv4. Men alla Office 365-funktioner är inte helt aktiverade med IPv6. Det innebär att du måste använda både IPv4 och IPv6 för att ansluta till Office 365. Om du filtrerar din utgående trafik till Office 365 finns den fullständiga listan med IPv6-adresser som stöds av Office 365 i artikeln [Office 365 URL:er och IP-adressintervall.](urls-and-ip-address-ranges.md) När nätverket är konfigurerat och lämpliga IPv6-adresser är tillåtna kan du ladda ned [Office 365 IPv6-testplanen](https://go.microsoft.com/fwlink/?LinkId=293447) från Microsoft Download Center.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>IPv6-stöd i Office 365-prenumerationstjänsten

### <a name="exchange-online-and-ipv6"></a>Exchange Online och IPv6

Om programmet som du använder för att ansluta till Exchange Online stöder IPv6 används IPv6 som standard i både kabelanslutna och trådlösa nätverk. Om du vill kontrollera kommunikationen till Exchange Online använder du IP-adressintervallen i [Office 365-URL:er och IP-adressintervall.](urls-and-ip-address-ranges.md)
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online och IPv6

 **Office 365 Government G1/G3/G4/K1** Om programmet som du använder för att ansluta till SharePoint Online stöder IPv6 försöker det använda IPv6 som standard.
  
 **Offentligt moln för flera klientorganisationen** Microsoft aktiverar IPv6 för SharePoint Online på din begäran. Du måste ange DE CIDR-noterade IP-adresserna för organisationens DNS-infrastruktur. Kom ihåg att den här DNS-infrastrukturen inte kan delas av andra organisationer för att IPv6 ska vara aktiverat för din klientorganisation. Om programmet som du använder för att ansluta till SharePoint Online stöder IPv6 används IPv6 som standard när IPv6 är aktiverat.
  
Om programmet som du använder för att ansluta till SharePoint Online stöder IPv6 används IPv6 som standard i både kabelanslutna och trådlösa nätverk. Om du vill kontrollera kommunikationen till SharePoint Online använder du IP-adressintervallen i [Office 365-URL:er och IP-adressintervall.](urls-and-ip-address-ranges.md)
  
 **Office 365 Government G1/G3/G4/K1** Om programmet som du använder för att ansluta till SharePoint Online stöder IPv6 försöker det använda IPv6 som standard.
  
### <a name="skype-for-business-and-ipv6"></a>Skype för företag och IPv6

Tänk på att IPv6 inte stöds i Skype för företag och att det inte längre går att aktivera.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams och IPV6

Microsoft Teams direktdirigering stöder endast IPv4. Microsoft Teams-tjänsten och -klienten har stöd för både IPv4 och IPv6. Om du vill kontrollera kommunikationen till Microsoft Teams använder du IP-adressintervallen i [Office 365-URL:er och IP-adressintervall.](urls-and-ip-address-ranges.md)
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection och IPv6

Exchange Online Protection (EOP) stöder IPv6 om överföringen sker via Transport Layer Security Protocol. För EOP-intervallet använder du [OFFICE 365 URL:er och IP-adressintervall.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>IPv6-stöd för Office 365-myndighetserbjudanden

Office 365 IPv6-stöd för myndighetserbjudanden överensstämmer med Office of Management and Budget (OMB) Chief for Chief Information Officers of Executive Departments and Agencies, liksom Federal Government Adoption of Internet Protocol Version 6 (IPv6) -protokoll. [Microsoft Office 365 för myndigheter](https://go.microsoft.com/fwlink/p/?LinkId=325414) är en tjänst för flera innehavare som lagrar data för amerikanska myndigheter i ett avskiljt communitymoln. Precis som andra Office 365-erbjudanden erbjuder det produktivitets- och samarbetstjänster, inklusive Exchange Online, Skype för företag, SharePoint Online och Microsoft 365-appar för företag. 

Microsoft Office 365-myndighetserbjudanden gäller endast för 2013 och senare. Mer information om Office 365-myndighetserbjudanden finns i Vi presenterar [Office 365 för myndigheter: Ett amerikanska Government Community Cloud.](https://go.microsoft.com/fwlink/p/?LinkId=325414) International Traffic in Arms Regulations (ITAR) är en uppsättning bestämmelser för myndigheter i USA som styr export och import av försvarrelaterade artiklar och tjänster för [United States Munitions List (USML).](https://go.microsoft.com/fwlink/p/?LinkId=325415) 

Microsoft Office 365 för företag tillhandahåller dedikerade värdtjänster för Microsofts produktivitetslösningar som uppfyller kraven för säkerhet, sekretess och regelefterlevnad för amerikanska federala myndigheter som kräver Federal Information Security Management-certifiering (FISMA) och kommersiella enheter som omfattas av ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Saker att tänka på när du använder IPv6 och Office 365

Vi rekommenderar att du inte inaktiverar IPv6. Mer information finns i den här [vägledningsartikeln.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users) Ta hänsyn till följande för att fastställa vilka IP-versioner som används i nätverket:
  
- Om visningen av **IPConfig-kommandot** i kommandotolken innehåller rader med namnet "IPv6-adress" eller "Tillfällig IPv6-adress" har du IPv6 i din miljö.

- Om alla IPv6-adresser börjar med "fe80" och motsvarar rader med namnet "Länk lokal IPv6-adress" har du inte IPv6 i din miljö.

Det här kan gälla för ditt nätverk:
  
- I den offentliga prenumerationstjänsten går det inte att göra köp med kreditkort via IPv6. Detta gäller inte GCC (Government Community Cloud) eftersom myndigheter har EA-licensiering (Enterprise Agreement).

- IPv6 stöder inte vissa RMS-scenarier (Rights Management Services).

- IPv6 stöder inte BES (BlackBerry® Enterprise Server) eftersom BlackBerry inte stöder IPv6.

- Om du använder AD FS (Active Directory Federation Services) med Office 365 stöds inte reklam din AD FS-nätverksslutpunkt till Office 365 med hjälp av IPv6. Du ska inte inkludera AAAA-poster i AD FS DNS-posten när du använder Exchange Online. 

Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>Se även

[IPv6 Learning-översikt](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6- informationsguide](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)