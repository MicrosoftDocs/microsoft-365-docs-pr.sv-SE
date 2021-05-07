---
title: Konfigurera IRM att använda en lokal AD RMS-server
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Läs om hur du konfigurerar IRM (Information Rights Management) i Exchange Online att använda en AD RMS-server (Active Directory Rights Management Service).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5e430f9c6ad5d377b568d22e9de53ab79d19165a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162743"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>Konfigurera IRM att använda en lokal AD RMS-server
  
För användning med lokala distributioner använder IRM (Information Rights Management) i Exchange Online Active Directory Rights Management Services (AD RMS), en teknik för informationsskydd i Windows Server 2008 och senare. IRM-skydd tillämpas på e-post genom att använda en principmall för AD RMS-rättigheter i ett e-postmeddelande. Rättigheter bifogas själva meddelandet så att skydd sker online och offline och inom och utanför organisationens brandvägg.
  
I det här avsnittet finns information om hur du konfigurerar IRM för användning av en AD RMS-server. Information om hur du använder de nya funktionerna för Meddelandekryptering i Office 365 med Azure Active Directory och Azure Rights Management finns i Vanliga [frågor Meddelandekryptering i Office 365 Azure Rights Management.](./ome-faq.yml)
  
Mer information om IRM i Exchange Online finns [i Information Rights Management i Exchange Online.](information-rights-management-in-exchange-online.md)
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Beräknad tid för att slutföra aktiviteten: 30 minuter

- Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna. Du kan se vilka behörigheter du behöver i "Information Rights Management" i avsnittet behörigheter för [meddelandepolicyer och efterlevnad (PÅ).](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) 

- AD RMS-servern måste köra Windows Server 2008 eller senare. Mer information om hur du distribuerar AD RMS finns i [Installera ett AD RMS-kluster.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11))

- Mer information om hur du installerar och konfigurerar Windows PowerShell och ansluter till tjänsten finns i konfigurera [Anslut att Exchange Online med Remote PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

- Mer information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i Kortkommandon för administrationscentret [Exchange i Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Har du problem? Be om hjälp i Exchange forum. Besök forumen på [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)eller [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="how-do-you-do-this"></a>Hur gör du det?
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>Steg 1: Använd AD RMS-konsolen för att exportera en betrodd publiceringsdomän (TPD) från en AD RMS-server

Det första steget är att exportera en betrodd publiceringsdomän (TPD) från den lokala AD RMS-servern till en XML-fil. TPD innehåller följande inställningar för att använda RMS-funktioner:
  
- Serverlicensorcertifikatet (SLC) som används för att signera och kryptera certifikat och licenser

- URL:er som används för licensiering och publicering

- Principmallarna för AD RMS-rättigheter som skapades med det specifika SLC för den TPD

När du importerar TPD lagras och skyddas den i Exchange Online.
  
1. Öppna Active Directory Rights Management Services och expandera AD RMS-klustret.

2. Expandera Förtroendeprinciper i **konsolträdet och** klicka sedan på **Betrodda publiceringsdomäner.**

3. I resultatfönstret väljer du certifikatet för den domän som du vill exportera.

4. Klicka på **Exportera** betrodd publiceringsdomän **i fönstret Åtgärder.**

5. Klicka på **Spara som i** rutan Publiceringsdomänfil för att spara filen på en viss plats på den lokala datorn.  Skriv ett filnamn, se till att ange  `.xml` filnamnstillägget och klicka sedan på **Spara**.

6. I **rutorna** Lösenord **och Bekräfta** lösenord anger du ett starkt lösenord som ska användas för att kryptera den betrodda publiceringsdomänfilen. Du måste ange det här lösenordet när du importerar TPD till din molnbaserade e-postorganisation. 

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>Steg 2: Använd Exchange Management Shell för att importera TPD-Exchange Online

När TPD har exporterats till en XML-fil måste du importera den till Exchange Online. När en TPD importeras importeras även organisationens AD RMS-mallar. När den första TPD har importerats blir den standard-TPD för den molnbaserade organisationen. Om du importerar en annan TPD kan du använda standardväxeln för att göra den till den standard-TPD som är tillgänglig för användare.  
  
Du importerar TPD genom att köra följande kommando i Windows PowerShell:
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

Du kan hämta värdena för parametrarna _ExtranetLicensingUrl_ och _IntranetLicensingUrl_ i Active Directory Rights Management Services konsolen. Välj AD RMS-klustret i konsolträdet. Url-adresser för licensiering visas i resultatfönstret. Dessa URL:er används av e-postklienter när innehållet måste dekrypteras och när Exchange Online behöver avgöra vilken TPD som ska användas.
  
När du kör det här kommandot uppmanas du att ange ett lösenord. Ange det lösenord som du angav när du exporterade TPD från AD RMS-servern.
  
Med följande kommando importeras till exempel TPD med namnet Exporterad TPD med den XML-fil du exporterade från AD RMS-servern och sparades på skrivbordet i administratörskontot. Parametern Name används för att ange ett namn på TPD.
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

Detaljerad information om syntax och parametrar finns i [Import-RMSTrustedPublishingDomain.](/powershell/module/exchange/import-rmstrustedpublishingdomain)
  
#### <a name="how-do-you-know-this-step-worked"></a>Hur vet du att det här steget fungerade?

Kontrollera att du har importerat TPD genom att köra cmdleten **Get-RMSTrustedPublishingDomain** för att hämta TPD:er i Exchange Online organisationen. Mer information finns i exemplen i [Get-RMSTrustedPublishingDomain.](/powershell/module/exchange/get-rmstrustedpublishingdomain)
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>Steg 3: Använda Exchange Management Shell för att distribuera en PRINCIPmall för AD RMS-rättigheter

När du har importerat TPD måste du se till att en principmall för AD RMS-rättigheter distribueras. En distribuerad mall visas för användare Outlook webben (kallades tidigare för Outlook Web App), som sedan kan använda mallarna i ett e-postmeddelande.
  
Om du vill returnera en lista över alla mallar som finns i standard-TPD kör du följande kommando:
  
```powershell
Get-RMSTemplate -Type All | fl
```

Om parameterns  _värde_ är  `Archived` , visas inte mallen för användarna. Endast distribuerade mallar i standard-TPD är tillgängliga i Outlook på webben.
  
Kör följande kommando för att distribuera en mall:
  
```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

Följande kommando importerar till exempel mallen Konfidentiellt.
  
```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

Detaljerad information om syntax och parametrar finns i [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) och [Set-RMSTemplate.](/powershell/module/exchange/set-rmstemplate)
  
**Mallen Vidarebefordra inte**
  
När du importerar standard-TPD från den lokala organisationen till Exchange Online importeras en AD RMS-rättighetsprincipmall med namnet Vidarebefordra **inte.** Som standard distribueras den här mallen när du importerar standard-TPD. Du kan inte använda **cmdleten Set-RMSTemplate** till att ändra mallen **Vidarebefordra inte.** 
  
När mallen **Vidarebefordra inte används** för ett meddelande kan bara meddelandets mottagare läsa det. Dessutom kan mottagarna inte göra följande:
  
- Vidarebefordra meddelandet till en annan person.

- Kopiera innehåll från meddelandet.

- Skriv ut meddelandet.

> [!IMPORTANT]
> Mallen **Vidarebefordra inte kan** inte förhindra att information i ett meddelande kopieras med skärmbilder från tredje part, kameror eller användare som manuellt transkriberar informationen 
  
Du kan skapa ytterligare principmallar för AD RMS-rättigheter på AD RMS-servern i den lokala organisationen för att uppfylla dina IRM-krav. Om du skapar ytterligare principmallar för AD RMS-rättigheter måste du exportera TPD från den lokala AD RMS-servern igen och uppdatera TPD:t i den molnbaserade e-postorganisationen.
  
#### <a name="how-do-you-know-this-step-worked"></a>Hur vet du att det här steget fungerade?

Kontrollera att du har distribuerat principen för och AD RMS-rättighetsprincipen genom att köra cmdlet:en **Get-RMSTemplate** för att kontrollera mallens egenskaper. Mer information finns i exemplen i [Get-RMSTemplate.](/powershell/module/exchange/get-rmstemplate)
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>Steg 4: Aktivera IRM med Exchange Management Shell

När du har importerat och distribuerat en principmall för AD RMS-rättigheter kör du följande kommando för att aktivera IRM för din molnbaserade e-postorganisation.
  
```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

Detaljerad information om syntax och parametrar finns i [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).
  
#### <a name="how-do-you-know-this-step-worked"></a>Hur vet du att det här steget fungerade?

Kontrollera att du har aktiverat IRM genom att köra cmdleten [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) för att kontrollera IRM-konfigurationen i Exchange Online organisation.
  
## <a name="how-do-you-know-this-task-worked"></a>Hur vet du att den här uppgiften fungerade?
<a name="sectionSection2"> </a>

Så här kontrollerar du att du har importerat TPD och aktiverat IRM:
  
- Använd **cmdleten Test-IRMConfiguration** för att testa IRM-funktioner. Mer information finns i "Exempel 1" i [Test-IRMConfiguration.](/powershell/module/exchange/test-irmconfiguration)

- Skriv ett nytt meddelande i Outlook och skydda det med IRM genom att välja alternativet Ange behörigheter i den utökade menyn  ![ (ikonen Fler ](../media/ITPro-EAC-MoreOptionsIcon.gif) alternativ).