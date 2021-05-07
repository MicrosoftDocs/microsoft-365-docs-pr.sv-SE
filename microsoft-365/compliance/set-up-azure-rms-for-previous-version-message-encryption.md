---
title: Konfigurera Azure Rights Management för den tidigare versionen av meddelandekryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: Den tidigare versionen Meddelandekryptering i Office 365 på Microsoft Azure Rights Management (kallades tidigare för Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162046"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Konfigurera Azure Rights Management för den tidigare versionen av meddelandekryptering

I det här avsnittet beskrivs de steg du behöver följa för att aktivera och sedan konfigurera Azure Rights Management (RMS), en del av Azure Information Protection, för användning med den tidigare versionen av Meddelandekryptering i Office 365 (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Den här artikeln gäller endast den tidigare versionen av OME

Om du ännu inte har flyttat organisationen till de nya OME-funktionerna, men redan har distribuerat OME, gäller informationen i den här artikeln för din organisation. Microsoft rekommenderar att du gör en plan för att flytta över till de nya OME-funktionerna så snart det är lämpligt för din organisation. Instruktioner finns i [Konfigurera nya Meddelandekryptering i Office 365 funktioner.](set-up-new-message-encryption-capabilities.md) Om du vill veta mer om hur de nya funktionerna fungerar först kan du läsa mer [i Meddelandekryptering i Office 365](ome.md). Resten av den här artikeln refererar till OME-beteendet innan de nya OME-funktionerna släpps.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Krav för att använda den tidigare versionen av Meddelandekryptering i Office 365
<a name="warmprereqs"> </a>

Meddelandekryptering i Office 365 (OME), inklusive IRM, är beroende av Azure Rights Management (Azure RMS). Azure RMS är den skyddsteknik som används av Azure Information Protection. Om du vill använda OME måste organisationen ha en Exchange Online- Exchange Online Protection-prenumeration som i sin tur omfattar en Azure Rights Management-prenumeration.
  
- Om du inte är säker på vad prenumerationen innehåller kan du läsa mer Exchange Online tjänstbeskrivningar för [Meddelandeprincip, Återställning och Efterlevnad.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

- Om du har Azure Rights Management men det inte är inställt för Exchange Online eller Exchange Online Protection förklarar den här artikeln hur du aktiverar Azure Rights Management och beskriver sedan det bästa sättet att konfigurera OME så att det fungerar med Azure Rights Management.

- Om du redan har ställt in OME att fungera med Azure Rights Management för Exchange Online eller Exchange Online Protection, beroende på hur du har ställt in det, kanske du är redo att börja använda OME och de nya funktionerna direkt. I den här artikeln förklarar vi hur du tar reda på om du har ställt in OME korrekt, vad du kan göra om du behöver ändra inställningarna och vad som händer om du väljer att inte ändra inställningarna. Om du till exempel vill använda de nya funktionerna måste du använda Azure RMS med OME. Du kan inte använda de nya funktionerna med en lokal Active Directory RMS.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Aktivera Azure Rights Management för den tidigare versionen av OME i Office 365

Du måste aktivera Azure Rights Management så att användarna i organisationen kan tillämpa informationsskydd på meddelanden som de skickar och öppna meddelanden och filer som har skyddats av tjänsten Azure Rights Management. Anvisningar finns i [Aktivera Azure Rights Management.](/azure/information-protection/activate-service) När du har slutfört aktiveringen återgår du hit och fortsätter med uppgifterna i den här artikeln.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Konfigurera den tidigare versionen av OME att använda Azure RMS genom att importera betrodda publiceringsdomäner (TPDs)

En TPD är en XML-fil som innehåller information om organisationens rättighetshanteringsinställningar. Till exempel innehåller TPD information om serverlicensorcertifikatet (SLC) som används för att signera och kryptera certifikat och licenser, webbadresserna som används för licensiering och publicering och så vidare. Du importerar TPD till organisationen med hjälp av Windows PowerShell.
  
> [!IMPORTANT]
> Tidigare kunde du välja att importera TPD:er från AD RMS (Active Directory Rights Management service) till organisationen. Om du gör det kan du dock inte använda de nya OME-funktionerna, och det rekommenderas inte. Om organisationen är konfigurerad på det här sättet rekommenderar Microsoft att du skapar en plan för migrering från din lokala Active Directory RMS till molnbaserat Azure Information Protection. Mer information finns i [Migrera från AD RMS till Azure Information Protection.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Du kan inte använda de nya OME-funktionerna förrän du har slutfört migreringen till Azure Information Protection.
  
 **Importera TPD från Azure RMS**
  
1. [Anslut att Exchange Online använda Remote PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Välj den URL för nyckeldelning som motsvarar organisationens geografiska plats:

|**Plats**|**URL för nyckeldelningsplats**|
|:-----|:-----|
|Nordamerika  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|EU  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Asien  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Sydamerika  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 för myndigheter (Government Community Cloud)  <br/> Den här RMS-nyckeldelningsplatsen är reserverad för kunder som har köpt Office 365 för myndighets-SKU:er.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Konfigurera nyckeldelningsplatsen genom att köra [cmdleten Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) enligt följande: 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   Om du till exempel vill konfigurera nyckeldelningsplatsen om organisationen finns i Nordamerika:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Kör [cmdleten Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) med -RMSOnline-bytet för att importera TPD från Azure Rights Management: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Där  *TPDName*  är det namn du vill använda för TPD. Till exempel "Contoso north american TPD". 

5. Om du vill verifiera att organisationen har konfigurerats att använda Azure Rights Management-tjänsten kör du cmdlet:en [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) med -RMSOnline-bytet på följande sätt:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Den här cmdleten kontrollerar bland annat anslutningen till Azure Rights Management-tjänsten, laddar ned TPD och kontrollerar dess giltighet.

6. Kör [cmdleten Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) enligt följande för att inaktivera Azure Rights Management-mallar så att de inte blir tillgängliga i Outlook på webben och Outlook: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Kör [cmdleten Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) enligt följande för att aktivera Azure Rights Management för din molnbaserade e-postorganisation och konfigurera den för användning med Azure Rights Management för Meddelandekryptering i Office 365:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Verifiera att du har importerat TPD och aktiverat Azure Rights Management genom att använda cmdleten Test-IRMConfiguration för att testa funktionerna i Azure Rights Management. Mer information finns i "Exempel 1" i [Test-IRMConfiguration.](/powershell/module/exchange/test-irmconfiguration)

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Jag har den tidigare versionen av OME konfigurerad med Active Directory Rights Management och inte Azure Information Protection, vad ska jag göra?
<a name="importTPDs"> </a>

Du kan fortsätta att använda dina befintliga Meddelandekryptering i Office 365-postflödesregler med Active Directory Rights Management, men du kan inte konfigurera eller använda de nya OME-funktionerna. I stället måste du migrera till Azure Information Protection. Mer information om migrering och vad det innebär för organisationen finns i Migrera från [AD RMS till Azure Information Protection.](/information-protection/deploy-use/prepare-environment-adrms)
  
## <a name="next-steps"></a>Nästa steg
<a name="importTPDs"> </a>

När du har slutfört konfigurationen av Azure Rights Management och vill aktivera de nya OME-funktionerna kan du gå till Konfigurera nya Meddelandekryptering i Office 365-funktioner som bygger på [Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)
  
När du har ställt in din organisation på att använda de nya OME-funktionerna är du redo att Definiera e-postflödesregler för att skydda e-postmeddelanden [med nya OME-funktioner.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>Relaterade ämnen
<a name="importTPDs"> </a>

[Kryptering i Office 365](encryption.md)
  
[Teknisk referensinformation om kryptering i Office 365](technical-reference-details-about-encryption.md)
  
[Vad är Azure Rights Management?](/information-protection/understand-explore/what-is-azure-rms)