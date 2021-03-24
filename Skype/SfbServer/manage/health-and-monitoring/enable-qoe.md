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
ms.openlocfilehash: 9f3e032506641cd22fbaa78054fcf6e40a72665e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095207"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="1a667-103">在商務用 Skype Server 中啟用經驗品質</span><span class="sxs-lookup"><span data-stu-id="1a667-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="1a667-104">**摘要：** 瞭解如何在商務用 Skype Server 中啟用 (QoE) 的經驗品質。</span><span class="sxs-lookup"><span data-stu-id="1a667-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="1a667-105">經驗品質 (QoE) 會記錄數字資料，指出有關通話與工作階段中所包含參與者、裝置名稱、驅動程式、IP 位址和端點類型的媒體品質和資訊。</span><span class="sxs-lookup"><span data-stu-id="1a667-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="1a667-106">如需詳細資訊，請參閱規劃檔中的 [規劃監控](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) 。</span><span class="sxs-lookup"><span data-stu-id="1a667-106">For details, see [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation.</span></span>

<span data-ttu-id="1a667-107">請使用下列程式，為您的整個組織或組織中的每個網站啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="1a667-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="1a667-108">若要啟用 QoE，您必須先設定監控和監控後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="1a667-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="1a667-109">如需詳細資訊，請參閱＜[Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)＞。</span><span class="sxs-lookup"><span data-stu-id="1a667-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1a667-110">使用商務用 Skype Server 控制台啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="1a667-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1a667-111">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1a667-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="1a667-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="1a667-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1a667-113">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。</span><span class="sxs-lookup"><span data-stu-id="1a667-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="1a667-114">在 [ **經驗品質資料** ] 頁面上，按一下表格中的適當集合，按一下 [ **動作**]，然後按一下 [ **啟用 QoE**]。</span><span class="sxs-lookup"><span data-stu-id="1a667-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1a667-115">使用 Windows PowerShell Cmdlet 啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="1a667-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1a667-116">您可以使用 Windows PowerShell 及 **Set CsQoEConfiguration** Cmdlet 來啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="1a667-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="1a667-117">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a667-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1a667-118">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="1a667-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="1a667-119">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="1a667-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="1a667-120">針對單一位置啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="1a667-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="1a667-121">若要啟用 QoE，請將 EnableQoE 參數設定為 True ($True) 。</span><span class="sxs-lookup"><span data-stu-id="1a667-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="1a667-122">停用單一位置的 QoE</span><span class="sxs-lookup"><span data-stu-id="1a667-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="1a667-123">若要停用 QoE，請將 EnableQoE 參數設定為 False ($False) 。</span><span class="sxs-lookup"><span data-stu-id="1a667-123">To disable QoE, set the EnableQoE parameter to False ($False).</span></span> <span data-ttu-id="1a667-124">這不會卸載監控。</span><span class="sxs-lookup"><span data-stu-id="1a667-124">This does not uninstall monitoring.</span></span> <span data-ttu-id="1a667-125">它會暫停 QoE 資料的收集和儲存。</span><span class="sxs-lookup"><span data-stu-id="1a667-125">It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="1a667-126">使用單一命令啟用多個位置的 QoE</span><span class="sxs-lookup"><span data-stu-id="1a667-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="1a667-127">此命令會為組織中目前使用的所有 QoE 設定設定啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="1a667-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="1a667-128">如需詳細資訊，請參閱 [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1a667-128">For details, see [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="1a667-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1a667-129">See also</span></span>

[<span data-ttu-id="1a667-130">規劃監控</span><span class="sxs-lookup"><span data-stu-id="1a667-130">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="1a667-131">部署監控</span><span class="sxs-lookup"><span data-stu-id="1a667-131">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)