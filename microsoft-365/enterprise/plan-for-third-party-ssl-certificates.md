---
title: Planera för tredje parts SSL-certifikat för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: 'Sammanfattning: Beskriver SSL-certifikaten som krävs för Exchange lokalt och hybrid, SSO med AD FS, Exchange Online och Exchange Web Services.'
ms.openlocfilehash: f2505a40e87ab36c96c0ed24514420b56d1479d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927494"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Planera för tredje parts SSL-certifikat för Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Om du vill kryptera kommunikationen mellan dina klienter och Microsoft 365-miljön måste SSL-certifikat (Secure Socket Layer) från tredje part vara installerade på dina infrastrukturservrar.

Den här artikeln är en [del av Nätverksplanering och prestandajustering för Microsoft 365](./network-planning-and-performance.md).
   
Certifikat krävs för följande Microsoft 365 komponenter:
  
- Exchange lokalt
    
- Enkel inloggning (SSO) (för både AD FS-federationsservrar (Active Directory Federation Services) och AD FS-federationsserverservrar)
    
- Exchange Online,t.ex. automatisk upptäckt, Outlook var som helst och Exchange webbtjänster
    
- Exchange-hybridserver
    
## <a name="certificates-for-exchange-on-premises"></a>Certifikat Exchange lokalt

En översikt över hur du använder digitala certifikat för att göra kommunikationen mellan den lokala Exchange-organisationen och Exchange Online säker finns i TechNet-artikeln [Förstå certifikatkrav.](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141))
  
## <a name="certificates-for-single-sign-on"></a>Certifikat för Sign-On

För att ge användarna en förenklad upplevelse med enkel inloggning som ger robust säkerhet krävs certifikaten i följande tabell på antingen federationsservrarna eller proxyservrarna för federationsservrarna. Tabellen nedan fokuserar på Active Directory Federation Services (AD FS), vi har också mer information om hur du använder [tredjepartsidentitetsproviders.](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)
  
| Certifikattyp | Beskrivning | Det här behöver du veta innan du distribuerar |
|:-----|:-----|:-----|
|**SSL-certifikat (kallas även serverautentiseringscertifikat)** <br/> |Det här är ett SSL-standardcertifikat som används för att göra kommunikationen säker mellan federationsservrar, klienter och proxydatorer för federationsservrar.  <br/> |AD FS kräver ett SSL-certifikat. Som standard använder AD FS det SSL-certifikat som är konfigurerat för standardwebbplatsen i Internet Information Services (IIS).  <br/> Ämnesnamnet för SSL-certifikatet används för att fastställa FS-namnet (Federation Service) för varje instans av AD FS som du distribuerar. Överväg att välja ett ämnesnamn för nya certifikat utfärdade av certifikatsutfärdare (CA) som på bästa sätt representerar namnet på ditt företag eller din organisation för att Microsoft 365. Namnet måste vara dirigerbart via Internet.  <br/>**Varning!** AD FS kräver att det här SSL-certifikatet inte har något ämnesnamn utan punkt (kort namn).          <br/> **Rekommendation:** Eftersom det här certifikatet måste vara betrott av klienter till AD FS rekommenderar vi att du använder ett SSL-certifikat utfärdat av en offentlig (tredje parts) certifikatutfärdare eller av en certifikatutfärdare som är underordnad en offentlig betrodd rot. Till exempel VeriSign eller Thawte.  <br/> |
|**Token-signeringscertifikat** <br/> |Det här är ett X.509-standardcertifikat som används för säker signering av alla tokens som federationsservern utfärdar och som Microsoft 365 accepterar och verifierar.  <br/> |Token-signeringscertifikatet måste innehålla en privat nyckel som länkar till en betrodd rot i FS. Som standard skapar AD FS ett själv signerat certifikat. Men beroende på organisationens behov kan du ändra det här certifikatet till ett certifikat utfärdat av en certifikatutfärdare med hjälp av snapin-modulen för AD FS-hantering.  <br/>**Varning!** Token-signeringscertifikatet är viktigt för stabiliteten i FS. Om certifikatet ändras måste Microsoft 365 meddelas om ändringen. Om något meddelande inte lämnas kan användarna inte logga in på Microsoft 365 tjänsterbjudanden.<br/>**Rekommendation:** Vi rekommenderar att du använder det självsignerade token-signeringscertifikatet som genereras av AD FS. Då hanteras det här certifikatet åt dig som standard. När det här certifikatet till exempel är på väg att löpa ut genererar AD FS ett nytt själv signerat certifikat.  <br/> |
   
För federationsservrars proxyservrar krävs det certifikat som beskrivs i följande tabell.
  
| Certifikattyp | Beskrivning | Det här behöver du veta innan du distribuerar |
|:-----|:-----|:-----|
|SSL-certifikat  <br/> |Det här är ett SSL-standardcertifikat som används för att skydda kommunikationen mellan en federationsserver, en federationsserverproxy och Internetklientdatorer.  <br/> |Ssl-certifikatet måste vara bundet till standardwebbplatsen i IIS innan du kan köra guiden Konfigurera AD FS-federationsserverproxy.  <br/> Certifikatet måste ha samma ämnesnamn som SSL-certifikatet som konfigurerades på federationsservern i företagsnätverket.  <br/> **Rekommendation:** Vi rekommenderar att du använder samma serverautentiseringscertifikat som är konfigurerat på den federationsserver som den här federationsserverproxyn ansluter till.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Certifikat för automatisk upptäckt, Outlook plats och Active Directory-synkronisering

Dina externa synkroniseringstjänster för Exchange 2013, Exchange 2010, Exchange 2007 och Exchange 2003-klientåtkomst (CAS) kräver ett SSL-certifikat från tredje part för säkra anslutningar för automatisk upptäckt, Outlook var som helst och active Directory-synkroniseringstjänster. Du kanske redan har certifikatet installerat i din lokala miljö.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Certifikat för en Exchange-hybridserver

Din externa externa Exchange-hybridserver eller -servrar kräver ett SSL-certifikat från tredje part för säker anslutning Exchange Online tjänsten. Du måste hämta certifikatet från din tredjeparts SSL-leverantör.
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365 Certifikatkedjor

I den här artikeln beskrivs de certifikat som du kan behöva installera på infrastrukturen. Mer information om certifikat som finns på våra Microsoft 365 finns i Microsoft 365 [certifikatkedjor.](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)
  
## <a name="see-also"></a>Se även

[Microsoft 365 Enterprise översikt](microsoft-365-overview.md)