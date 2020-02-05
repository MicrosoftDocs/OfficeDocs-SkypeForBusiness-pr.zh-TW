---
title: 在商務用 Skype 中部署 SEFAUtil 工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 在商務用 Skype Server 中部署 SEFAUtil 工具。
ms.openlocfilehash: ab0d41990e0c4bf9d4d2abb635ce447180899de8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767496"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="db303-103">在商務用 Skype 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="db303-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="db303-104">在商務用 Skype Server 中部署 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="db303-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="db303-105">若要部署及管理群組呼叫，您必須使用商務用 Skype Server 版本的 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="db303-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="db303-106">Microsoft 整合通訊管理 API （UCMA）：必須在您打算執行 SEFAUtil 工具的任何電腦上安裝5個執行時間。</span><span class="sxs-lookup"><span data-stu-id="db303-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="db303-107">請在這裡下載：[整合通訊管理 API 5.0 運行](https://www.microsoft.com/en-us/download/details.aspx?id=47344)時間。</span><span class="sxs-lookup"><span data-stu-id="db303-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="db303-108">您也可以下載 UCMA 5 SDK （包括執行時間），如下所示： [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345)。</span><span class="sxs-lookup"><span data-stu-id="db303-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="db303-109">您可以在部署的任何前端池中執行 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="db303-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="db303-110">若要執行 SEFAUtil 工具，您必須在受信任的應用程式電腦上，從商務用 Skype 部署嚮導執行步驟1、2和3。</span><span class="sxs-lookup"><span data-stu-id="db303-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="db303-111">SEFAUtil 需要有本機配置存放區，以及認證。</span><span class="sxs-lookup"><span data-stu-id="db303-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="db303-112">如需執行 SEFAUtil 的詳細資訊，請參閱博客文章：「[如何取得 SEFAUtil 執行？](https://go.microsoft.com/fwlink/?LinkId=278940)」。</span><span class="sxs-lookup"><span data-stu-id="db303-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="db303-113">若要部署 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="db303-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="db303-114">登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝，如**委派設定許可權**中所述。</span><span class="sxs-lookup"><span data-stu-id="db303-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="db303-115">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="db303-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="db303-116">SEFAUtil 工具只能在屬於受信任的應用程式池的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="db303-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="db303-117">如有需要，請為您打算執行 SEFAUtil 的前端池定義受信任的應用程式池。</span><span class="sxs-lookup"><span data-stu-id="db303-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="db303-118">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="db303-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="db303-119">[池 FQDN]：將裝載 SEFAUtil 應用程式的伺服器或池的 FQDN （通常是商務用 Skype 前端伺服器或池）。</span><span class="sxs-lookup"><span data-stu-id="db303-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="db303-120">Pool 註冊機構 FQDN：與此應用程式池關聯的商務用 Skype 前端伺服器或池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="db303-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="db303-121">[文件庫網站]：此池所駐留的網站的 [網站識別碼]。</span><span class="sxs-lookup"><span data-stu-id="db303-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="db303-122">將 SEFAUtil 工具定義為受信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="db303-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="db303-123">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="db303-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="db303-124">如有需要，您可以使用不同的埠。</span><span class="sxs-lookup"><span data-stu-id="db303-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="db303-125">使用您的變更啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="db303-125">Enable the topology with your changes.</span></span> <span data-ttu-id="db303-126">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="db303-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="db303-127">如果您還沒有從[這個位置](https://www.microsoft.com/en-us/download/details.aspx?id=52631)下載 SEFAUtil 工具的商務用 Skype Server 版本，請將它安裝在您在步驟3所建立的信任應用程式池中。</span><span class="sxs-lookup"><span data-stu-id="db303-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="db303-128">確認 SEFAUtil 工具正常運作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="db303-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="db303-129">是.</span><span class="sxs-lookup"><span data-stu-id="db303-129">a.</span></span> <span data-ttu-id="db303-130">從具有系統管理員許可權的 Windows 命令提示字元執行該工具，以在您的部署中顯示使用者的來電轉接設定。</span><span class="sxs-lookup"><span data-stu-id="db303-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="db303-131">乙.</span><span class="sxs-lookup"><span data-stu-id="db303-131">b.</span></span> <span data-ttu-id="db303-132">顯示使用者的 [來電轉接] 設定。</span><span class="sxs-lookup"><span data-stu-id="db303-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="db303-133">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="db303-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="db303-134">隨即會顯示使用者的 [來電轉接] 設定。</span><span class="sxs-lookup"><span data-stu-id="db303-134">The call forwarding settings for the user will be displayed.</span></span>
    

