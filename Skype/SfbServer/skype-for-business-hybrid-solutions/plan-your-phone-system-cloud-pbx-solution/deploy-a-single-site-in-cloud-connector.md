---
title: 在雲端連接器中部署單一網站
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: 瞭解如何在雲端連接器 Edition 中部署單一 PSTN 網站。
ms.openlocfilehash: cc508d21f9e39c215ce3c07403ab75e791e2414a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779349"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="bac76-103">在雲端連接器中部署單一網站</span><span class="sxs-lookup"><span data-stu-id="bac76-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="bac76-104">瞭解如何在雲端連接器 Edition 中部署單一 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="bac76-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="bac76-105">您可以部署具有或不具有高可用性（HA）支援的商務用 Skype 雲端連接器 Edition。</span><span class="sxs-lookup"><span data-stu-id="bac76-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="bac76-106">如果您想要啟用 HA，您必須在網站中部署兩部以上的裝置。</span><span class="sxs-lookup"><span data-stu-id="bac76-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="bac76-107">您也可以在部署現有裝置後，將其轉換為支援 HA。</span><span class="sxs-lookup"><span data-stu-id="bac76-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="bac76-108">部署第一個商務用 Skype 雲端連接器 Edition 裝置</span><span class="sxs-lookup"><span data-stu-id="bac76-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="bac76-109">若要部署網站中的第一個裝置，請以系統管理員身分開啟 PowerShell 主控台，然後執行下列 Cmdlet 來註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="bac76-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="bac76-110">依照指示提供租使用者管理員帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="bac76-110">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="bac76-111">使用您為雲端連接器線上管理所建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="bac76-111">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="bac76-112">此外，依照指示提供外部憑證密碼、安全模式系統管理密碼、網域管理員密碼和 VM 系統管理員密碼。</span><span class="sxs-lookup"><span data-stu-id="bac76-112">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="bac76-113">在版本1.4.2 及更早版本中，也依照指示提供外部憑證密碼、安全模式系統管理密碼、網域管理員密碼和 VM 系統管理員密碼。</span><span class="sxs-lookup"><span data-stu-id="bac76-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="bac76-114">在版本2.0 和更新版本中，也依照指示提供外部憑證密碼、CceService 密碼和 CABackupFile 密碼。</span><span class="sxs-lookup"><span data-stu-id="bac76-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="bac76-115">若要開始安裝，請以系統管理員身分開啟 PowerShell 主控台，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bac76-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="bac76-116">將裝置新增至現有的網站</span><span class="sxs-lookup"><span data-stu-id="bac76-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="bac76-117">您可以將其他裝置新增至網站，以擴充現有的雲端連接器網站以支援高可用性。</span><span class="sxs-lookup"><span data-stu-id="bac76-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="bac76-118">遵循[準備雲端連接器裝置](prepare-your-cloud-connector-appliance.md)中所述的步驟，以準備您的雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="bac76-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="bac76-119">請注意，只有部署中的第一個裝置需要一些步驟。</span><span class="sxs-lookup"><span data-stu-id="bac76-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="bac76-120">確認網站目錄存在，且已正確設定 HA 支援。</span><span class="sxs-lookup"><span data-stu-id="bac76-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="bac76-121">請僅在新加入的主伺服器上執行下列 Cmdlet，以更新 Office 365 組織設定中的拓撲資訊。</span><span class="sxs-lookup"><span data-stu-id="bac76-121">Run the following cmdlet only on the newly added host server to update topology information in your Office 365 organization configuration.</span></span> <span data-ttu-id="bac76-122">如果您想要同時新增多個裝置，請逐一在新加入的主機伺服器上執行 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bac76-122">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="bac76-123">在每一部主機伺服器上執行下列 Cmdlet，以更新現有裝置上的拓撲。</span><span class="sxs-lookup"><span data-stu-id="bac76-123">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="bac76-124">請只在現有的裝置上執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bac76-124">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="bac76-125">僅在新加入的主伺服器上執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bac76-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="bac76-126">請勿在現有裝置上執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bac76-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="bac76-127">如果您想要同時新增多個裝置，請逐一在新加入的主機伺服器上執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bac76-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="bac76-128">如果網站目錄已設定為本機資料夾路徑，您必須為此資料夾定義檔案共用，並在新裝置上使用網站目錄的 UNC 路徑。</span><span class="sxs-lookup"><span data-stu-id="bac76-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="bac76-129">您可以將第一個裝置網站目錄保留為本機路徑，或加以修改，以使用該共用的 UNC 路徑進行相同的資料夾。</span><span class="sxs-lookup"><span data-stu-id="bac76-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="bac76-130">若共用網站目錄的位置變更，則必須先卸載任何先前安裝的裝置，然後再重新安裝。</span><span class="sxs-lookup"><span data-stu-id="bac76-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="bac76-131">> 重要：在網站中部署的所有裝置上，CceService 帳戶和 CABackupFile 帳戶的密碼都必須相同，以便裝置可以在網站目錄中存取網站目錄共用和加密的 CA 備份檔案。</span><span class="sxs-lookup"><span data-stu-id="bac76-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="bac76-132">從現有的網站移除裝置</span><span class="sxs-lookup"><span data-stu-id="bac76-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="bac76-133">若要從現有的網站移除裝置：</span><span class="sxs-lookup"><span data-stu-id="bac76-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="bac76-134">請僅在您想要從網站移除的主伺服器上執行下列 Cmdlet，以更新 Office 365 組織設定中的拓撲資訊。</span><span class="sxs-lookup"><span data-stu-id="bac76-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="bac76-135">在您要移除裝置所有虛擬機器的主機伺服器上，只執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bac76-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


