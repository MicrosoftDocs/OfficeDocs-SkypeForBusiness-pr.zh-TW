---
title: 在商務用 Skype Server 中啟用體驗品質
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 摘要：瞭解如何在商務用 Skype Server 中啟用體驗品質（QoE）。
ms.openlocfilehash: 0a05266ed88b9d476ca787f1d32b91727e90475c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992933"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="79a49-103">在商務用 Skype Server 中啟用體驗品質</span><span class="sxs-lookup"><span data-stu-id="79a49-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="79a49-104">**摘要：** 瞭解如何在商務用 Skype Server 中啟用體驗品質（QoE）。</span><span class="sxs-lookup"><span data-stu-id="79a49-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="79a49-105">經驗品質（QoE）會記錄數位資料，指出媒體質量與參與者的相關資訊、裝置名稱、驅動程式、IP 位址，以及通話和會話中所涉及的端點類型。</span><span class="sxs-lookup"><span data-stu-id="79a49-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="79a49-106">如需詳細資訊，請參閱規劃檔中的[監控規劃](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="79a49-106">For details, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="79a49-107">使用下列程式為您的整個組織或貴組織中的每個網站啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="79a49-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="79a49-108">若要啟用 QoE，您必須先設定監視及監視後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="79a49-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="79a49-109">如需詳細資訊，請參閱[部署監視](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="79a49-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="79a49-110">使用商務用 Skype Server [控制台] 啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="79a49-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="79a49-111">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="79a49-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="79a49-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="79a49-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="79a49-113">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。</span><span class="sxs-lookup"><span data-stu-id="79a49-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="79a49-114">在 [**體驗品質資料**] 頁面上，按一下表格中的適當集合，按一下 [**動作**]，然後按一下 [**啟用 QoE**]。</span><span class="sxs-lookup"><span data-stu-id="79a49-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="79a49-115">使用 Windows PowerShell Cmdlet 啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="79a49-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="79a49-116">您可以使用 Windows PowerShell 和**CsQoEConfiguration** Cmdlet 來啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="79a49-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="79a49-117">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79a49-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="79a49-118">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="79a49-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="79a49-119">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="79a49-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="79a49-120">若要針對單一位置啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="79a49-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="79a49-121">若要啟用 QoE，請將 EnableQoE 參數設定為 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="79a49-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="79a49-122">針對單一位置停用 QoE</span><span class="sxs-lookup"><span data-stu-id="79a49-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="79a49-123">若要停用 QoE，請將 EnableQoE 參數設定為 False （$False）。</span><span class="sxs-lookup"><span data-stu-id="79a49-123">To disable QoE, set the EnableQoE parameter to False ($False).</span></span> <span data-ttu-id="79a49-124">這不會卸載監視。</span><span class="sxs-lookup"><span data-stu-id="79a49-124">This does not uninstall monitoring.</span></span> <span data-ttu-id="79a49-125">它會暫停 QoE 資料的收集和儲存。</span><span class="sxs-lookup"><span data-stu-id="79a49-125">It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="79a49-126">若要在多個位置使用單一命令來啟用 QoE</span><span class="sxs-lookup"><span data-stu-id="79a49-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="79a49-127">這個命令會針對貴組織中目前使用的所有 QoE 設定設定啟用 QoE。</span><span class="sxs-lookup"><span data-stu-id="79a49-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="79a49-128">如需詳細資訊，請參閱[設定 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="79a49-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="79a49-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="79a49-129">See also</span></span>

[<span data-ttu-id="79a49-130">規劃監視</span><span class="sxs-lookup"><span data-stu-id="79a49-130">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="79a49-131">部署監控</span><span class="sxs-lookup"><span data-stu-id="79a49-131">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

