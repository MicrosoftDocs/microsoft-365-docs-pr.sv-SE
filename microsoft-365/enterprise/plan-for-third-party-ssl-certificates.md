---
title: Planera för tredjeparts SSL-certifikat för Microsoft 365
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
description: 'Sammanfattning: beskriver de SSL-certifikat som behövs för Exchange lokalt och hybrid, SSO med AD FS, Exchange Online Services och Exchange Web Services.'
ms.openlocfilehash: 1738e4c316772d928138adc654372bd0b9efae65
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694568"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Planera för tredjeparts SSL-certifikat för Microsoft 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Om du vill kryptera kommunikation mellan klienter och Microsoft 365-miljön måste du installera SSL-certifikat från tredje part på infrastruktur servrarna.

Den här artikeln är en del av [nätverks planering och prestanda justering för Microsoft 365](https://aka.ms/tune).
   
Certifikat krävs för följande Microsoft 365-komponenter:
  
- Lokalt Exchange
    
- Enkel inloggning (SSO) (för både AD FS-federationtjänster (Active Directory Federation Services) och AD FS-federationsserverproxy)
    
- Exchange Online-tjänster, till exempel Autosök, Outlook överallt och Exchange-webbtjänster
    
- Exchange-hybrid server
    
## <a name="certificates-for-exchange-on-premises"></a>Certifikat för Exchange lokalt

En översikt över hur du använder digitala certifikat för att kommunicera kommunikationen mellan den lokala Exchange-organisationen och Exchange Online finns i artikeln om [certifikat krav](https://go.microsoft.com/fwlink/p/?LinkID=243657)för TechNet-artikel.
  
## <a name="certificates-for-single-sign-on"></a>Certifikat för enkel inloggning

För att användarna ska kunna använda en förenklad enkel inloggnings upplevelse med stabil säkerhet, måste de certifikat som visas i följande tabell vara antingen på Federations servrarna eller i federationsserverproxyn. Tabellen nedan fokuserar på AD FS (Active Directory Federation Services) och har också mer information om hur du [använder identitets leverantörer från tredje part](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).
  
| Certifikat typ | Beskrivning | Det här behöver du veta innan du distribuerar |
|:-----|:-----|:-----|
|**SSL-certifikat (kallas även för serverautentisering)** <br/> |Det här är ett standard-SSL-certifikat som används för att kommunicera mellan Federations servrar, klienter och federationsserverproxy.  <br/> |AD FS kräver ett SSL-certifikat. Som standard använder AD FS det SSL-certifikat som är konfigurerat för standard webbplatsen i Internet Information Services (IIS).  <br/> Ämnes namnet för SSL-certifikatet används för att fastställa namnet på Federations tjänsten (FS) för varje instans av AD FS som du distribuerar. Överväg att välja ett ämnes namn för nya certifikat utfärdare (CA)-certifikat som bäst motsvarar namnet på ditt företag eller din organisation till Microsoft 365. Det här namnet måste vara Internet-dirigerbart.  <br/>**Varning:** AD FS kräver att det här SSL-certifikatet inte har något namn utan punkter (kort namn).          <br/> **Rekommendation:** Eftersom det här certifikatet måste vara betrott av AD FS-klienter rekommenderar vi att du använder ett SSL-certifikat som utfärdas av en offentlig (tredjeparts) certifikat utfärdare eller av en certifikat utfärdare som är underordnad en offentlig betrodd rot. till exempel VeriSign eller Thawte.  <br/> |
|**Certifikat för tokensignering** <br/> |Det här är ett standard-X. 509-certifikat som används för att säkert Signera alla token som Federations servern utfärdar och att Microsoft 365 accepterar och validerar.  <br/> |Certifikatet för tokensignering måste innehålla en privat nyckel som är kedja till en betrodd rot i FS. Som standard skapar AD FS ett självsignerat certifikat. Beroende på behoven i din organisation kan du emellertid ändra det här certifikatet till ett certifikat som utfärdas av certifikat UTFÄRDAre genom att använda snapin-modulen AD FS-hantering.  <br/>**Varning:** Certifikat för tokensignering är avgörande för as-stabilitet. Om certifikatet ändras måste Microsoft 365 meddelas om ändringen. Om det inte finns något meddelande kan användarna inte logga in i Microsoft 365-tjänstens tjänster.<br/>**Rekommendation:** Vi rekommenderar att du använder ett självsignerat certifikat för tokensignering som genereras av AD FS. Om du gör det hanteras det här certifikatet för dig som standard. Till exempel när det här certifikatet upphör att gälla kommer AD FS att skapa ett nytt självsignerat certifikat.  <br/> |
   
För federationsserverproxy krävs det certifikat som beskrivs i följande tabell.
  
| Certifikat typ | Beskrivning | Det här behöver du veta innan du distribuerar |
|:-----|:-----|:-----|
|SSL-certifikat  <br/> |Det här är ett SSL-standardcertifikat som används för att skydda kommunikationen mellan en Federations Server, en federationsserverproxy och Internet klient datorer.  <br/> |Det här SSL-certifikatet måste bindas till standard webbplatsen i IIS innan du kan köra konfigurations guiden för AD FS-federationsserverproxyn.  <br/> Det här certifikatet måste ha samma ämnes namn som SSL-certifikatet som konfigurerades på Federations servern i företags nätverket.  <br/> **Rekommendation:** Vi rekommenderar att du använder samma server certifikat som är konfigurerat på den Federations server som federationsserverproxyn ansluter till.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Certifikat för automatisk upptäckt, Outlook överallt och Active Directory-synkronisering

Ditt externa Exchange-2013, Exchange 2010, Exchange 2007 och Exchange 2003-klient åtkomst servrar (CASs) kräver ett tredjeparts SSL-certifikat för säkra anslutningar för Autodiscover, Outlook överallt och Active Directory Synchronization Services. Du kanske redan har det här certifikatet installerat i din lokala miljö.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Certifikat för en Exchange-hybrid server

Din externa Exchange-hybrid server eller servrar kräver ett tredjeparts SSL-certifikat för säker anslutning till Exchange Online-tjänsten. Du måste skaffa detta intyg från din tredjeparts SSL-leverantör.
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365-certifikat kedjor

I den här artikeln beskrivs de certifikat som du kan behöva installera i infrastrukturen. Mer information om de certifikat som är installerade på våra Microsoft 365-servrar finns i [microsoft 365-certifikat kedjor](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb).
  
## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)
