---
title: Så här distribuerar du Defender för Slutpunkt i Linux med Chef
description: Lär dig hur du distribuerar Defender för Slutpunkt på Linux med Chef
keywords: microsoft, defender, atp, linux, genomsökningar, antivirus, microsoft defender för slutpunkt (linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 362222e4737b1a8dd6b8a0a284bf3bfb1903c288
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861456"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Distribuera Defender för slutpunkt på Linux med Chef

Innan du börjar:

- Installera packa upp om det inte redan är installerat. Chefkomponenterna är redan installerade och det finns en chefsplats (chef som genererar lagringsplatsen) för att lagra kokboken som ska användas för att distribuera till Defender för Endpoint på Linux-servrar hanterad <reponame> av Chef.

Du kan skapa en ny kokbok på din befintliga lagringsplats genom att köra följande kommando från kokboksmappen på din chefsplats:</br>
`chef generate cookbook mdatp`

Det här kommandot skapar en ny mappstruktur för den nya kokboken som heter mdatp.  Du kan också använda en befintlig kokbok om du redan har en som du vill använda för att lägga till MDE-distributionen i.
När kokboken har skapats skapar du en mapp med filer i kokboksmappen som precis har skapats:

`mkdir mdatp/files`

Överför ZIP-filen för Linux Server Onboarding som kan laddas ned från Microsoft Defender Säkerhetscenter-portalen till den här nya filmappen.

Gå till mappen mdatp/recipes på arbetsstationen chef. Den här mappen skapas när kokboken skapades. Använd den önskade textredigeraren (t.ex. vi eller nano) för att lägga till följande instruktioner i slutet av filen default.rb:
-   include_recipe ::onboard_mdatp
- include_recipe ::install_mdatp

Spara och stäng sedan filen default.rb.
Skapa sedan en ny receptfil med namnet install_mdatp.rb i receptmappen och lägg till den här texten i filen:

```powershell

#Add Microsoft Defender   
Repo  
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

Du behöver ändra versionsnumret, distributionen och lagringsplatsens namn så att det överensstämmer med den version du distribuerar till och den kanal som du vill distribuera.
Därefter ska du skapa en onboard_mdatp.rb-fil i mappen mdatp/recipies.  Lägg till följande text i filen:

```powershell

#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

Uppdatera sökvägen till introduktionsfilens plats.
Testa att distribuera den på arbetsstationen Chef genom att bara köra ``sudo chef-client -z -o mdatp`` .
Efter distributionen bör du överväga att skapa och distribuera en konfigurationsfil till servrarna baserat på Ange inställningar för Microsoft Defender ATP för [Linux – Windows | Microsoft Docs.](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences)  
När du har skapat och testat konfigurationsfilen kan du placera den i cookboken/mdatp/files-mappen där du också placerade onboarding-paketet.  Sedan kan du skapa en settings_mdatp.rb-fil i mappen mdatp/recipies och lägga till den här texten:

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

Om du vill ta med det här steget som en del av receptet lägger du include_recipe till ":: settings_mdatp" till filen default.rb i receptmappen.
Du kan också använda fliken för att schemalägga automatiska uppdateringar [Schemalägga en uppdatering av Microsoft Defender för Endpoint (Linux)](linux-update-MDE-Linux.md).

Avinstallera MDATP-kokboken:

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8 
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```

