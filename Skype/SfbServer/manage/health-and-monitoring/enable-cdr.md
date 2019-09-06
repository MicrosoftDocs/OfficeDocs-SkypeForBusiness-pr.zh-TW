---
title: 在商務用 Skype Server 中啟用呼叫詳細資料錄製
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 摘要：瞭解如何在商務用 Skype Server 中啟用通話詳細資料錄製（CDR）記錄。
ms.openlocfilehash: 015ac3b57420401894e82c267e9737990ca7affb
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767055"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="755ca-103">在商務用 Skype Server 中啟用呼叫詳細資料錄製</span><span class="sxs-lookup"><span data-stu-id="755ca-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="755ca-104">**摘要：** 瞭解如何在商務用 Skype Server 中啟用通話詳細資料錄製（CDR）記錄。</span><span class="sxs-lookup"><span data-stu-id="755ca-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="755ca-105">通話詳細資料錄製（CDR）記錄對等活動的用法與診斷資訊，包括實例訊息、透過網際網路通訊協定（VoIP）通話、應用程式共用、檔案傳輸及會議。</span><span class="sxs-lookup"><span data-stu-id="755ca-105">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="755ca-106">使用資料可用來計算投資回報率（ROI），而診斷資料可用來針對對等活動和會議進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="755ca-106">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="755ca-107">使用下列程式可為您的整個組織或貴組織中的每個網站啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="755ca-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="755ca-108">若要啟用 CDR，您必須設定監視及監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="755ca-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="755ca-109">如需詳細資訊，請參閱[部署監視](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="755ca-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="755ca-110">使用商務用 Skype Server [控制台] 啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="755ca-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="755ca-111">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="755ca-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="755ca-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="755ca-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="755ca-113">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**呼叫詳細資料錄製**]。</span><span class="sxs-lookup"><span data-stu-id="755ca-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="755ca-114">在 [**通話詳細資料記錄**] 頁面上，從表格中按一下適當的網站，按一下 [**動作**]，然後按一下 [**啟用 CDR**]。</span><span class="sxs-lookup"><span data-stu-id="755ca-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="755ca-115">預設會啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="755ca-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="755ca-116">使用 Windows PowerShell Cmdlet 啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="755ca-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="755ca-117">您可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="755ca-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="755ca-118">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="755ca-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="755ca-119">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="755ca-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="755ca-120">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="755ca-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="755ca-121">若要針對單一位置啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="755ca-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="755ca-122">若要停用 CDR，請將 EnableCDR 參數設定為 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="755ca-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="755ca-123">若要針對單一位置停用 CDR</span><span class="sxs-lookup"><span data-stu-id="755ca-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="755ca-124">若要停用 CDR，請將 EnableCDR 參數設定為 False （$False）。</span><span class="sxs-lookup"><span data-stu-id="755ca-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="755ca-125">停用 CDR 不會卸載監視。</span><span class="sxs-lookup"><span data-stu-id="755ca-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="755ca-126">它會暫停 CDR 資料的收集和儲存。</span><span class="sxs-lookup"><span data-stu-id="755ca-126">It pauses the collection and storage of CDR data.</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="755ca-127">若要使用單一命令在多個位置啟用 CDR</span><span class="sxs-lookup"><span data-stu-id="755ca-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="755ca-128">這個命令會針對貴組織中目前使用的所有 CDR 配置設定啟用 CDR。</span><span class="sxs-lookup"><span data-stu-id="755ca-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="755ca-129">如需詳細資訊，請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="755ca-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="755ca-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="755ca-130">See also</span></span>

[<span data-ttu-id="755ca-131">規劃監視</span><span class="sxs-lookup"><span data-stu-id="755ca-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="755ca-132">部署監控</span><span class="sxs-lookup"><span data-stu-id="755ca-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
