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
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a><span data-ttu-id="c999f-104">Distribuera Defender för slutpunkt på Linux med Chef</span><span class="sxs-lookup"><span data-stu-id="c999f-104">Deploy Defender for Endpoint on Linux with Chef</span></span>

<span data-ttu-id="c999f-105">Innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="c999f-105">Before you begin:</span></span>

- <span data-ttu-id="c999f-106">Installera packa upp om det inte redan är installerat.</span><span class="sxs-lookup"><span data-stu-id="c999f-106">Install unzip if it’s not already installed.</span></span> <span data-ttu-id="c999f-107">Chefkomponenterna är redan installerade och det finns en chefsplats (chef som genererar lagringsplatsen) för att lagra kokboken som ska användas för att distribuera till Defender för Endpoint på Linux-servrar hanterad <reponame> av Chef.</span><span class="sxs-lookup"><span data-stu-id="c999f-107">The Chef components are already installed and a Chef repository exists (chef generate repo <reponame>) to store the cookbook that will be used to deploy to Defender for Endpoint on Chef managed Linux servers.</span></span>

<span data-ttu-id="c999f-108">Du kan skapa en ny kokbok på din befintliga lagringsplats genom att köra följande kommando från kokboksmappen på din chefsplats:</span><span class="sxs-lookup"><span data-stu-id="c999f-108">You can create a new cookbook in your existing repository by running the following command from inside the cookbooks folder that is in your chef repository:</span></span></br>
`chef generate cookbook mdatp`

<span data-ttu-id="c999f-109">Det här kommandot skapar en ny mappstruktur för den nya kokboken som heter mdatp.</span><span class="sxs-lookup"><span data-stu-id="c999f-109">This command will create a new folder structure for the new cookbook called mdatp.</span></span>  <span data-ttu-id="c999f-110">Du kan också använda en befintlig kokbok om du redan har en som du vill använda för att lägga till MDE-distributionen i.</span><span class="sxs-lookup"><span data-stu-id="c999f-110">You can also use an existing cookbook if you already have one you’d like to use to add the MDE deployment into.</span></span>
<span data-ttu-id="c999f-111">När kokboken har skapats skapar du en mapp med filer i kokboksmappen som precis har skapats:</span><span class="sxs-lookup"><span data-stu-id="c999f-111">After the cookbook is created, create a files folder inside the cookbook folder that just got created:</span></span>

`mkdir mdatp/files`

<span data-ttu-id="c999f-112">Överför ZIP-filen för Linux Server Onboarding som kan laddas ned från Microsoft Defender Säkerhetscenter-portalen till den här nya filmappen.</span><span class="sxs-lookup"><span data-stu-id="c999f-112">Transfer the Linux Server Onboarding zip file that can be downloaded from the Microsoft Defender Security Center portal to this new files folder.</span></span>

<span data-ttu-id="c999f-113">Gå till mappen mdatp/recipes på arbetsstationen chef.</span><span class="sxs-lookup"><span data-stu-id="c999f-113">On the Chef Workstation, navigate to the mdatp/recipes folder.</span></span> <span data-ttu-id="c999f-114">Den här mappen skapas när kokboken skapades.</span><span class="sxs-lookup"><span data-stu-id="c999f-114">This folder is created when the cookbook was generated.</span></span> <span data-ttu-id="c999f-115">Använd den önskade textredigeraren (t.ex. vi eller nano) för att lägga till följande instruktioner i slutet av filen default.rb:</span><span class="sxs-lookup"><span data-stu-id="c999f-115">Use your preferred text editor (like vi or nano) to add the following instructions to the end of the default.rb file:</span></span>
-   <span data-ttu-id="c999f-116">include_recipe ::onboard_mdatp</span><span class="sxs-lookup"><span data-stu-id="c999f-116">include_recipe '::onboard_mdatp'</span></span>
- <span data-ttu-id="c999f-117">include_recipe ::install_mdatp</span><span class="sxs-lookup"><span data-stu-id="c999f-117">include_recipe '::install_mdatp'</span></span>

<span data-ttu-id="c999f-118">Spara och stäng sedan filen default.rb.</span><span class="sxs-lookup"><span data-stu-id="c999f-118">Then save and close the default.rb file.</span></span>
<span data-ttu-id="c999f-119">Skapa sedan en ny receptfil med namnet install_mdatp.rb i receptmappen och lägg till den här texten i filen:</span><span class="sxs-lookup"><span data-stu-id="c999f-119">Next create a new recipe file named install_mdatp.rb in the recipes folder and add this text to the file:</span></span>

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

<span data-ttu-id="c999f-120">Du behöver ändra versionsnumret, distributionen och lagringsplatsens namn så att det överensstämmer med den version du distribuerar till och den kanal som du vill distribuera.</span><span class="sxs-lookup"><span data-stu-id="c999f-120">You’ll need to modify the version number, distribution, and repo name to match the version you’re deploying to and the channel you’d like to deploy.</span></span>
<span data-ttu-id="c999f-121">Därefter ska du skapa en onboard_mdatp.rb-fil i mappen mdatp/recipies.</span><span class="sxs-lookup"><span data-stu-id="c999f-121">Next you should create an onboard_mdatp.rb file in the mdatp/recipies folder.</span></span>  <span data-ttu-id="c999f-122">Lägg till följande text i filen:</span><span class="sxs-lookup"><span data-stu-id="c999f-122">Add the following text to that file:</span></span>

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

<span data-ttu-id="c999f-123">Uppdatera sökvägen till introduktionsfilens plats.</span><span class="sxs-lookup"><span data-stu-id="c999f-123">Make sure to update the path name to the location of the onboarding file.</span></span>
<span data-ttu-id="c999f-124">Testa att distribuera den på arbetsstationen Chef genom att bara köra ``sudo chef-client -z -o mdatp`` .</span><span class="sxs-lookup"><span data-stu-id="c999f-124">To test deploy it on the Chef workstation, just run ``sudo chef-client -z -o mdatp``.</span></span>
<span data-ttu-id="c999f-125">Efter distributionen bör du överväga att skapa och distribuera en konfigurationsfil till servrarna baserat på Ange inställningar för Microsoft Defender ATP för [Linux – Windows | Microsoft Docs.](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences)</span><span class="sxs-lookup"><span data-stu-id="c999f-125">After your deployment you should consider creating and deploying a configuration file to the servers based on  [Set preferences for Microsoft Defender ATP for Linux - Windows security | Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).</span></span>  
<span data-ttu-id="c999f-126">När du har skapat och testat konfigurationsfilen kan du placera den i cookboken/mdatp/files-mappen där du också placerade onboarding-paketet.</span><span class="sxs-lookup"><span data-stu-id="c999f-126">After you've created and tested your configuration file, you can place it into the cookbook/mdatp/files folder where you also placed the onboarding package.</span></span>  <span data-ttu-id="c999f-127">Sedan kan du skapa en settings_mdatp.rb-fil i mappen mdatp/recipies och lägga till den här texten:</span><span class="sxs-lookup"><span data-stu-id="c999f-127">Then you can create a settings_mdatp.rb file in the mdatp/recipies folder and add this text:</span></span>

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

<span data-ttu-id="c999f-128">Om du vill ta med det här steget som en del av receptet lägger du include_recipe till ":: settings_mdatp" till filen default.rb i receptmappen.</span><span class="sxs-lookup"><span data-stu-id="c999f-128">To include this step as part of the recipe just add include_recipe ':: settings_mdatp' to your default.rb file within the recipe folder.</span></span>
<span data-ttu-id="c999f-129">Du kan också använda fliken för att schemalägga automatiska uppdateringar [Schemalägga en uppdatering av Microsoft Defender för Endpoint (Linux)](linux-update-MDE-Linux.md).</span><span class="sxs-lookup"><span data-stu-id="c999f-129">You can also use crontab to schedule automatic updates [Schedule an update of the Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span></span>

<span data-ttu-id="c999f-130">Avinstallera MDATP-kokboken:</span><span class="sxs-lookup"><span data-stu-id="c999f-130">Uninstall MDATP cookbook:</span></span>

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

