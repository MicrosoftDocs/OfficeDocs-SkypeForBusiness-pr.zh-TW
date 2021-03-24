---
title: 啟用商務用 Skype Server 中的詳細通話記錄
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 摘要：瞭解如何在商務用 Skype Server 中啟用 (CDR) 記錄的詳細通話記錄。
ms.openlocfilehash: e2f652eeef77c336fb34be07c123f1ef026d458c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095227"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="cc15d-103">啟用商務用 Skype Server 中的詳細通話記錄</span><span class="sxs-lookup"><span data-stu-id="cc15d-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="cc15d-104">**摘要：** 瞭解如何在商務用 Skype Server 中，啟用 (CDR) 記錄的詳細通話記錄。</span><span class="sxs-lookup"><span data-stu-id="cc15d-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="cc15d-p101">詳細通話記錄 (CDR) 會記錄對等活動 (包括立即訊息、VoIP 電話、應用程式共用、檔案傳輸和會議) 的使用方式與診斷資訊。使用方式資料可以用來計算投資報酬率 (ROI)，而診斷資料則可用來排解對等活動和會議的疑難問題。</span><span class="sxs-lookup"><span data-stu-id="cc15d-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="cc15d-107">使用下列程序來為整個組織或組織內的個別網站啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="cc15d-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="cc15d-108">如要啟用 CDR，您必須設定監控及監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="cc15d-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="cc15d-109">如需詳細資訊，請參閱＜[Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)＞。</span><span class="sxs-lookup"><span data-stu-id="cc15d-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="cc15d-110">啟用具有商務用 Skype Server 控制台的 CDR</span><span class="sxs-lookup"><span data-stu-id="cc15d-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="cc15d-111">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="cc15d-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="cc15d-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="cc15d-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="cc15d-113">在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。</span><span class="sxs-lookup"><span data-stu-id="cc15d-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="cc15d-114">在 **[詳細通話記錄]** 頁面上，依序按一下表格中的適當網站、**[動作]** 和 **[啟用 CDR]**。</span><span class="sxs-lookup"><span data-stu-id="cc15d-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc15d-115">預設會啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="cc15d-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cc15d-116">使用 Windows PowerShell Cmdlet 啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="cc15d-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="cc15d-117">您可以使用 Windows PowerShell 和 **Set-CsCdrConfiguration** Cmdlet 來啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="cc15d-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="cc15d-118">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cc15d-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cc15d-119">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="cc15d-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="cc15d-120">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="cc15d-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="cc15d-121">針對單一位置啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="cc15d-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="cc15d-122">如要停用 CDR，請將 EnableCDR 參數設為 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="cc15d-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="cc15d-123">針對單一位置停用 CDR</span><span class="sxs-lookup"><span data-stu-id="cc15d-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="cc15d-124">如要停用 CDR，請將 EnableCDR 參數設為 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="cc15d-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="cc15d-125">停用 CDR 不會卸載監控。</span><span class="sxs-lookup"><span data-stu-id="cc15d-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="cc15d-126">它會暫停 CDR 資料的收集和儲存。</span><span class="sxs-lookup"><span data-stu-id="cc15d-126">It pauses the collection and storage of CDR data.</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="cc15d-127">使用單一命令啟用多個位置的 CDR</span><span class="sxs-lookup"><span data-stu-id="cc15d-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="cc15d-128">以下命令會啟用組織中所有目前正在使用之 CDR 組態設定的 CDR。</span><span class="sxs-lookup"><span data-stu-id="cc15d-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="cc15d-129">如需詳細資訊，請參閱 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="cc15d-129">For more information, see the help topic for the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc15d-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cc15d-130">See also</span></span>

[<span data-ttu-id="cc15d-131">規劃監控</span><span class="sxs-lookup"><span data-stu-id="cc15d-131">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="cc15d-132">部署監控</span><span class="sxs-lookup"><span data-stu-id="cc15d-132">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)