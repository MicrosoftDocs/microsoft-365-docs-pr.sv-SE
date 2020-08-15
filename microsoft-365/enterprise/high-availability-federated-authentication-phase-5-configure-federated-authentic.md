---
title: Steg 5 Konfigurera federerad inloggningsautentisering för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: 'Sammanfattning: Konfigurera Azure AD Connect för din högprioriterade federerad verifikation för Microsoft 365 i Microsoft Azure.'
ms.openlocfilehash: f00763487261b62940ac5def38d35158db77a699
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694702"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a>Mellanliggande federerad autentiseringsläge med hög tillgänglighet: Konfigurera federerad auktorisering för Microsoft 365

I den här delen av distribuera federerad verifiering med hög tillgänglighet för Microsoft 365 i Azure Infrastructure Services får du och installerar ett certifikat som utfärdats av en offentlig certifikat utfärdare, verifierar din konfiguration och sedan installerar och kör Azure AD Connect på servern för katalogpartition. Azure AD Connect konfigurerar din Microsoft 365-prenumeration och AD FS (Active Directory Federation Services) och Webbprogramproxy-servrar för federerad-verifikation.
  
Se [distribuera federerad inloggningsautentisering med hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) för alla faser.
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a>Skaffa ett offentligt certifikat och kopiera det till katalogpartitionen för servrar

Skaffa ett digitalt certifikat från en offentlig certifikat utfärdare med följande egenskaper:
  
- Ett X. 509-certifikat som passar för att skapa SSL-anslutningar.
    
- Den utökade egenskapen för ämnets alternativa namn (SAN) är inställd på FQDN-namnet på Federations tjänsten (till exempel: fs.contoso.com).
    
- Certifikatet måste ha den privata och lagras i PFX-format.
    
Dessutom måste organisationens datorer och enheter lita på vilken offentlig certifikat utfärdare som utfärdar det digitala certifikatet. Detta förtroende upprättas genom att ha ett rot certifikat från den offentliga certifikat utfärdare som är installerat i arkivet Betrodda rot certifikat utfärdare på dina datorer och enheter. Datorer som kör Microsoft Windows har vanligt vis en uppsättning dessa typer av certifikat installerade från vanliga certifikat utfärdare. Om rot certifikatet från din offentliga certifikat utfärdare inte redan är installerat måste du distribuera detta till dator och enheter i organisationen.
  
För mer information om certifikat krav för federerad verifiering, se [förutsättningar för installation och konfiguration av Federation](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).
  
När du får ett certifikat kopierar du det till en mapp på C: s katalog-synkroniseringstjänst. Du kan till exempel ge filen namnet SSL. pfx och lagra den i mappen C: \\ certifikat på servern för katalogpartition.
  
## <a name="verify-your-configuration"></a>Verifiera din konfiguration

Du bör nu vara redo att konfigurera Azure AD Connect och federerad inloggningsautentisering för Microsoft 365. För att vara säker på att du är det här är en check lista:
  
- Din organisations offentliga domän läggs till i din Microsoft 365-prenumeration.
    
- Organisationens Microsoft 365-användarkonton är konfigurerade till organisationens offentliga domän namn och kan logga in.
    
- Du har fastställt ett FQDN-namn på Federations tjänsten baserat på det offentliga domän namnet.
    
- En offentlig DNS-post för Federations tjänstens FQDN pekar på den offentliga IP-adressen till Internet-Facing Azure Load Balance för webbprogramproxy.
    
- En privat DNS-post för Federations tjänstens FQDN pekar på den privata IP-adressen för den interna Azure-belastningsutjämnaren för AD FS-servrarna.
    
- En offentlig certifikat utfärdare-isssued digitala certifikat som är lämpligt för SSL-anslutningar med SAN-servern som är FQDN-namnet på din Federations tjänst är en PFX-fil som lagras på servern för din katalog.
    
- Rot certifikatet för den offentliga certifikat utfärdaren är installerat i arkivet Betrodda rot certifikat utfärdare på dina datorer och enheter.
    
Här är ett exempel för organisationen contoso:
  
**Exempel på konfiguration för en federerad infrastruktur med hög tillgänglighet i Azure**

![Exempel på en konfiguration av infrastrukturen för Microsoft 365 federerad-autentiseringsprocessen i Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a>Kör Azure AD Connect för att konfigurera federerad

Azure AD Connect-verktyget konfigurerar AD FS-servrarna, Webbprogramproxy och Microsoft 365 för federerad behörighet med följande steg:
  
1. Skapa en anslutning till fjärr skrivbord till din katalogpartition med ett domän konto med lokala administratörs behörigheter.
    
2. Öppna Internet Explorer och gå till på Skriv bordet för katalogpartitionen [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
3. Klicka på **Hämta**på sidan **Microsoft Azure Active Directory Connect** och sedan på **Kör**.
    
4. På sidan **Välkommen till Azure AD Connect** klickar du på **Jag accepterar**och klickar sedan på **Fortsätt.**
    
5. Klicka på **Anpassa**på sidan **Express inställningar** .
    
6. Klicka på **Installera**på sidan **installera nödvändiga komponenter** .
    
7. På sidan **Användarinloggning** klickar du på **Federation med AD FS** och sedan på **Nästa**.
    
8. På sidan **Anslut till Azure AD** skriver du in namnet och lösen ordet för ett globalt administratörs konto för Microsoft 365-prenumerationen och klickar sedan på **Nästa**.
    
9. På sidan **Anslut dina kataloger** ser du till att din lokala AD DS-skog (Active Directory Domain Services) är markerad i **skogen**, anger namn och lösen ord för ett domän administratörs konto, klickar på **Lägg till katalog**och sedan på **Nästa**.
    
10. Klicka på **Nästa**på sidan **konfiguration av inloggning med Azure AD** .
    
11. Klicka på **Nästa**på sidan **Domain and ou filter** .
    
12. På sidan **unik identifiering av användare** klickar du på **Nästa**.
    
13. Klicka på **Nästa**på sidan **filtrera användare och enheter** .
    
14. På sidan **valfria funktioner** klickar du på **Nästa**.
    
15. Klicka på **Konfigurera en ny AD FS-servergrupp**på sidan **AD FS-servergrupp** .
    
16. Klicka på **Bläddra** och ange plats och namn för SSL-certifikatet från den offentliga certifikat utfärdaren.
    
17. Ange lösen ordet för certifikatet när du uppmanas till det och klicka sedan på **OK**.
    
18. Kontrol lera att **subjekt namnet** och **namn på Federations tjänsten** är inställda på ditt FQDN för Federations tjänsten och klicka sedan på **Nästa**.
    
19. På sidan **AD FS-servrar** skriver du in namnet på den första AD FS-servern (tabell M-objekt 4-kolumnen virtuell dator) och klickar sedan på **Lägg till**.
    
20. Skriv in namnet på den andra AD FS-servern (tabell M-item 5-namn kolumnen virtuell dator), klicka på **Lägg till**och sedan på **Nästa**.
    
21. Skriv in namnet på den första Web Application-proxyservern (tabell M-item 6 – kolumnen Namn på virtuell dator) på sidan **Webbprogramproxy** och klicka sedan på **Lägg till**.
    
22. Skriv in namnet på den andra webb program servern (tabell M-item 7-namn kolumnen virtuell dator), klicka på **Lägg till**och sedan på **Nästa**.
    
23. Ange användar namn och lösen ord för ett domän administratörs konto på sidan **domän administratörs behörighet** och klicka sedan på **Nästa**.
    
24. På sidan **AD FS-** tjänstkonto anger du användar namn och lösen ord för ett företags administratörs konto och klickar sedan på **Nästa**.
    
25. På sidan **Azure AD-domän** i **Domain**väljer du organisationens DNS-domännamn och klickar sedan på **Nästa**.
    
26. På sidan **Klart att konfigurera** klickar du på **Installera**.
    
27. På sidan **Installationen är slutförd** klickar du på **Verifiera**. Två meddelanden visar att både intranät-och Internet konfigurationen verifierades.
    
  - Intranät meddelandet ska ange den privata IP-adressen för din Azure Internal-belastningsutjämnare för dina AD FS-servrar.
    
  - Internet meddelandet ska ange den offentliga IP-adressen för din Azure Internet-belastnings balansering för dina Web Application Proxy-servrar.
    
28. På sidan **Installationen är slutförd** klickar du på **Avsluta**.
    
Här är den sista konfigurationen med namn på plats hållare för servrarna.
  
**Fas 5: slutgiltig konfiguration av en federerad infrastruktur med hög tillgänglighet i Azure**

![Den sista konfigurationen av infrastrukturen för extern tillgänglighet i Microsoft 365 i Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Infrastrukturen för federerad infrastruktur med hög tillgänglighet för Microsoft 365 i Azure är klar.
  
## <a name="see-also"></a>Se även

[Distribuera federerad för hög tillgänglighet för Microsoft 365 i Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federerad identitet för din Microsoft 365-miljö](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365-center för lösningar och arkitektur](../solutions/solution-architecture-center.md)

[Federerad identitet för Microsoft 365](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)


