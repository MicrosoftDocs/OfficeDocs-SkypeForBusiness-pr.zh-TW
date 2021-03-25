---
title: 在商務用 Skype 中部署 SEFAUtil 工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 013890e3b65dfd3a8360da859a1c9179fa9b5a13
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105799"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="8ec05-103">在商務用 Skype 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="8ec05-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="8ec05-104">在商務用 Skype Server 中部署 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="8ec05-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="8ec05-105">若要部署和管理群組呼叫收取，您必須使用 SEFAUtil 工具的商務用 Skype Server 版本。</span><span class="sxs-lookup"><span data-stu-id="8ec05-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8ec05-106">Microsoft 整合通訊 Managed API (UCMA) 5 執行時間必須安裝在您計畫執行 SEFAUtil 工具的任何電腦上。</span><span class="sxs-lookup"><span data-stu-id="8ec05-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="8ec05-107">請在這裡下載： [整合通訊 MANAGED API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344)。</span><span class="sxs-lookup"><span data-stu-id="8ec05-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="8ec05-108">您也可以下載 UCMA 5 SDK，其中包含執行時間，如下所示： [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345)。</span><span class="sxs-lookup"><span data-stu-id="8ec05-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="8ec05-109">您可以在部署中的任何前端集區中執行 SEFAUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="8ec05-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="8ec05-110">若要執行 SEFAUtil 工具，您必須在受信任的應用程式電腦上，從商務用 Skype 部署嚮導執行步驟1、2和3。</span><span class="sxs-lookup"><span data-stu-id="8ec05-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="8ec05-111">SEFAUtil 需要有本機設定存放區，以及憑證。</span><span class="sxs-lookup"><span data-stu-id="8ec05-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ec05-112">如需有關執行 SEFAUtil 的詳細資訊，請參閱博客文章：「[如何取得 SEFAUtil 執行？](/archive/blogs/jenstr/how-to-get-sefautil-running)」。</span><span class="sxs-lookup"><span data-stu-id="8ec05-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](/archive/blogs/jenstr/how-to-get-sefautil-running)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="8ec05-113">若要部署 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="8ec05-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="8ec05-114">登入安裝商務用 Skype Server 管理命令介面的電腦，並將其安裝為 RTCUniversalServerAdmins 群組的成員，或使用 **委派安裝許可權** 中所述的必要使用者權限。</span><span class="sxs-lookup"><span data-stu-id="8ec05-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="8ec05-115">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="8ec05-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8ec05-116">SEFAUtil 工具只能在屬於受信任應用程式集區一部分的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="8ec05-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="8ec05-117">如有需要，針對您計畫執行 SEFAUtil 的前端集區定義信任的應用程式集區。</span><span class="sxs-lookup"><span data-stu-id="8ec05-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="8ec05-118">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="8ec05-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="8ec05-119">集區 FQDN：將主控 SEFAUtil 應用程式之伺服器或集區的 FQDN (通常是商務用 Skype 前端伺服器或集區) 。</span><span class="sxs-lookup"><span data-stu-id="8ec05-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="8ec05-120">集區註冊機 FQDN：與此應用程式集區相關聯之商務用 Skype 前端伺服器或集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8ec05-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="8ec05-121">集區網站：此集區所在之網站的網站識別碼。</span><span class="sxs-lookup"><span data-stu-id="8ec05-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="8ec05-122">將 SEFAUtil 工具定義為信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8ec05-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="8ec05-123">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="8ec05-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="8ec05-124">如有需要，您可以使用不同的埠。</span><span class="sxs-lookup"><span data-stu-id="8ec05-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="8ec05-125">使用您的變更來啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="8ec05-125">Enable the topology with your changes.</span></span> <span data-ttu-id="8ec05-126">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="8ec05-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="8ec05-127">如果您尚未從 [這個位置](https://www.microsoft.com/download/details.aspx?id=52631)下載 SEFAUtil 工具的商務用 Skype Server 版本，請將其安裝在您在步驟3中建立的信任應用程式集區。</span><span class="sxs-lookup"><span data-stu-id="8ec05-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="8ec05-128">請確認 SEFAUtil 工具是否運作正常，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8ec05-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="8ec05-129">a.</span><span class="sxs-lookup"><span data-stu-id="8ec05-129">a.</span></span> <span data-ttu-id="8ec05-130">從具有管理員許可權的 Windows 命令提示字元執行工具，以顯示部署中使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="8ec05-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="8ec05-131">b.</span><span class="sxs-lookup"><span data-stu-id="8ec05-131">b.</span></span> <span data-ttu-id="8ec05-132">顯示使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="8ec05-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="8ec05-133">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="8ec05-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="8ec05-134">將會顯示使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="8ec05-134">The call forwarding settings for the user will be displayed.</span></span>
