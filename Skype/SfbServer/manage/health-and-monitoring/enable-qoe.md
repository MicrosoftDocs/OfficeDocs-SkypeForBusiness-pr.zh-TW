---
title: 在商務用 Skype Server 中啟用經驗品質
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 摘要：瞭解如何在商務用 Skype Server 中啟用 (QoE) 的經驗品質。
ms.openlocfilehash: 67b752df3791d3ba0493a7e3575f25c58231ad26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816853"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="c7bb7-103">在商務用 Skype Server 中啟用經驗品質</span><span class="sxs-lookup"><span data-stu-id="c7bb7-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="c7bb7-104">**摘要：** 瞭解如何在商務用 Skype Server 中啟用 (QoE) 的經驗品質。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="c7bb7-105">經驗品質 (QoE) 會記錄數字資料，指出有關通話與工作階段中所包含參與者、裝置名稱、驅動程式、IP 位址和端點類型的媒體品質和資訊。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="c7bb7-106">如需詳細資訊，請參閱規劃檔中的 [規劃監控](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-106">For details, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="c7bb7-107">請使用下列程式，為您的整個組織或組織中的每個網站啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="c7bb7-108">若要啟用 QoE，您必須先設定監控和監控後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="c7bb7-109">如需詳細資訊，請參閱＜[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c7bb7-110">使用商務用 Skype Server 控制台啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="c7bb7-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c7bb7-111">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="c7bb7-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="c7bb7-113">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="c7bb7-114">在 [ **經驗品質資料** ] 頁面上，按一下表格中的適當集合，按一下 [ **動作**]，然後按一下 [ **啟用 QoE**]。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c7bb7-115">使用 Windows PowerShell Cmdlet 啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="c7bb7-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c7bb7-116">您可以使用 Windows PowerShell 及 **Set CsQoEConfiguration** Cmdlet 來啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="c7bb7-117">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c7bb7-118">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c7bb7-119">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="c7bb7-120">針對單一位置啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="c7bb7-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="c7bb7-121">若要啟用 QoE，請將 EnableQoE 參數設定為 True ($True) 。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="c7bb7-122">停用單一位置的 QoE</span><span class="sxs-lookup"><span data-stu-id="c7bb7-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="c7bb7-123">若要停用 QoE，請將 EnableQoE 參數設定為 False ($False) 。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-123">To disable QoE, set the EnableQoE parameter to False ($False).</span></span> <span data-ttu-id="c7bb7-124">這不會卸載監控。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-124">This does not uninstall monitoring.</span></span> <span data-ttu-id="c7bb7-125">它會暫停 QoE 資料的收集和儲存。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-125">It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="c7bb7-126">使用單一命令啟用多個位置的 QoE</span><span class="sxs-lookup"><span data-stu-id="c7bb7-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="c7bb7-127">此命令會為組織中目前使用的所有 QoE 設定設定啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="c7bb7-128">如需詳細資訊，請參閱 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c7bb7-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7bb7-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c7bb7-129">See also</span></span>

[<span data-ttu-id="c7bb7-130">規劃監控</span><span class="sxs-lookup"><span data-stu-id="c7bb7-130">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="c7bb7-131">部署監控</span><span class="sxs-lookup"><span data-stu-id="c7bb7-131">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

