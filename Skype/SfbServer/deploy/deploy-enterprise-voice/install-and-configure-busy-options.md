---
title: 安裝及設定商務用 Skype Server 的 Busy 選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 瞭解如何在商務用 Skype Server 中安裝及設定 Busy 選項。
ms.openlocfilehash: 13f529ddd7bd3b83f9d065599d3a213662da31a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189331"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="a7b09-103">安裝及設定商務用 Skype Server 的 Busy 選項</span><span class="sxs-lookup"><span data-stu-id="a7b09-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="a7b09-104">瞭解如何在商務用 Skype Server 中安裝及設定 Busy 選項。</span><span class="sxs-lookup"><span data-stu-id="a7b09-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="a7b09-105">[忙碌選項] 是一種新的語音策略, 在2016年7月累計更新中引進, 可讓您設定當使用者已在通話或會議中, 或有來電處於保留狀態時, 處理來電的方式。</span><span class="sxs-lookup"><span data-stu-id="a7b09-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="a7b09-106">您可以使用占線信號或轉接至語音信箱來拒絕新的或來電的通話。</span><span class="sxs-lookup"><span data-stu-id="a7b09-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="a7b09-107">如果組織已啟用 [忙碌] 選項, 企業中的所有使用者 (企業語音和非企業語音使用者) 都可以使用下列設定選項:</span><span class="sxs-lookup"><span data-stu-id="a7b09-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="a7b09-108">繁忙-在此情況下, 如果使用者太忙, 就會拒絕新的傳入通話。</span><span class="sxs-lookup"><span data-stu-id="a7b09-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="a7b09-109">占線時的語音信箱-當使用者忙碌時, 會將新的撥入電話轉寄到語音信箱。</span><span class="sxs-lookup"><span data-stu-id="a7b09-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="a7b09-110">不論其忙碌選項的設定方式為何, 通話或會議中的使用者, 或通話保持通話的使用者, 都不會被禁止開始新的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="a7b09-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="a7b09-111">如需繁忙選項功能的詳細資訊, 請參閱[規劃商務用 Skype Server 的繁忙選項](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="a7b09-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="a7b09-112">安裝</span><span class="sxs-lookup"><span data-stu-id="a7b09-112">Install</span></span>

<span data-ttu-id="a7b09-113">確定您已安裝最新版本的商務用 Skype Server, 且您已安裝最新的修補程式。</span><span class="sxs-lookup"><span data-stu-id="a7b09-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="a7b09-114">若要這樣做, 請先停止所有服務, 然後執行商務用 Skype Server 更新安裝程式, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="a7b09-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="a7b09-115">執行 [停止 CsWindowsService] 命令。</span><span class="sxs-lookup"><span data-stu-id="a7b09-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="a7b09-116">在池中的每個前端伺服器上執行 SkypeServerUpdateInstaller 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="a7b09-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="a7b09-117">如果您想要確保在 SBS 上的容錯移轉支援, 請在每個 Survivable 分支伺服器 (SBS) 上執行 SkypeServerUpdateInstaller 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="a7b09-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="a7b09-118">安裝程式將會部署最新版本的 [Busy 選項] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7b09-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="a7b09-119">不過, 預設不會啟用應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7b09-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="a7b09-120">若要啟用應用程式, 請執行下列步驟:</span><span class="sxs-lookup"><span data-stu-id="a7b09-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="a7b09-121">執行[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) Cmdlet 來全域啟用 Busy 選項, 如下列範例所示:</span><span class="sxs-lookup"><span data-stu-id="a7b09-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="a7b09-122">接著, 如果網站有語音原則, 您必須為語音原則啟用 Busy 選項, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="a7b09-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="a7b09-123">首先, 請執行[CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)以取得網站名稱:</span><span class="sxs-lookup"><span data-stu-id="a7b09-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```
   Get-CsSite
   ```

    <span data-ttu-id="a7b09-124">使用身分識別值 (例如: Site: Redmond1) 從 CsSite 中檢索, 以取得網站的語音原則, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="a7b09-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="a7b09-125">如果網站有語音原則, 請執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="a7b09-125">If a voice policy exists for the site, run the following command:</span></span>

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="a7b09-126">接著, 執行[新的 CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) Cmdlet, 在伺服器應用程式清單中新增 Busy 選項, 如下列範例所示:</span><span class="sxs-lookup"><span data-stu-id="a7b09-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="a7b09-127">您必須以特定池的完整功能變數名稱取代% FQDN%。</span><span class="sxs-lookup"><span data-stu-id="a7b09-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="a7b09-128">接著, 執行[CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) Cmdlet 來更新適用于 Busy 選項 Cmdlet 的角色式存取控制 (RBAC) 角色, 如下列範例所示:</span><span class="sxs-lookup"><span data-stu-id="a7b09-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```
   Update-CsAdminRole
   ```

5. <span data-ttu-id="a7b09-129">最後, 執行 [[開始-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) ] 命令, 在已安裝及啟用 [忙碌] 選項的所有池中, 啟動所有前端伺服器上的商務用 Skype Server Windows 服務:</span><span class="sxs-lookup"><span data-stu-id="a7b09-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="a7b09-130">設定</span><span class="sxs-lookup"><span data-stu-id="a7b09-130">Configure</span></span>

<span data-ttu-id="a7b09-131">若要設定 Busy 選項, 請使用[CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a7b09-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="a7b09-132">例如, 下列命令會設定使用者「Ken Myer」的 busy 選項。</span><span class="sxs-lookup"><span data-stu-id="a7b09-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="a7b09-133">在這個設定中, 任何對 "Ken Myer" 的呼叫都會在他已在通話中時傳回占線信號:</span><span class="sxs-lookup"><span data-stu-id="a7b09-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="a7b09-134">在下一個範例中, 命令會為使用者 [Chrystal Velasquez] 設定 busy 選項。</span><span class="sxs-lookup"><span data-stu-id="a7b09-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="a7b09-135">在此設定中, 當她已在通話中時, 會將來電轉接至 [Chrystal Velasquez] 的新來電:</span><span class="sxs-lookup"><span data-stu-id="a7b09-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="a7b09-136">您可以使用[CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) Cmdlet 來取得有關 Busy 選項的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="a7b09-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="a7b09-137">下列範例會傳回 "KenMyer@Contoso.com" 的 Busy 選項設定:</span><span class="sxs-lookup"><span data-stu-id="a7b09-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="a7b09-138">您可以使用[CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) Cmdlet 來移除 Busy 選項。</span><span class="sxs-lookup"><span data-stu-id="a7b09-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="a7b09-139">下列命令會移除「Ken Myer」的 Busy 選項:</span><span class="sxs-lookup"><span data-stu-id="a7b09-139">The following command removes Busy Options for "Ken Myer":</span></span>

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="a7b09-140">如需用來設定 Busy 選項之 Cmdlet 的詳細資訊, 請參閱[設定 CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)、 [CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)及[移除 CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)的技術參考內容。</span><span class="sxs-lookup"><span data-stu-id="a7b09-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="a7b09-141">啟用記錄功能</span><span class="sxs-lookup"><span data-stu-id="a7b09-141">Enable logging</span></span>

<span data-ttu-id="a7b09-142">若要使用集中式記錄服務啟用 [忙碌] 選項的記錄, 請指定下列專案:</span><span class="sxs-lookup"><span data-stu-id="a7b09-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="a7b09-143">驗證及疑難排解</span><span class="sxs-lookup"><span data-stu-id="a7b09-143">Verify and troubleshoot</span></span>

<span data-ttu-id="a7b09-144">安裝 Busy 選項之後, 您可以使用[CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) Cmdlet 來取得伺服器應用程式的清單, 以驗證安裝成功。</span><span class="sxs-lookup"><span data-stu-id="a7b09-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="a7b09-145">如果 [忙碌] 選項已正確安裝, 則 Cmdlet 的輸出應該會顯示 [忙碌選項] 設定, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="a7b09-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="a7b09-146">您也可以使用 Windows 事件檢視器, 確認 [忙碌] 選項安裝已成功, 且商務用 Skype 伺服器已順利載入 Busy 選項。</span><span class="sxs-lookup"><span data-stu-id="a7b09-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="a7b09-147">若要驗證 Busy 選項, 請開啟**事件\>檢視器-應用程式\>和服務記錄-Skype (或 Lync) 伺服器**, 並搜尋事件 ID = 30253。</span><span class="sxs-lookup"><span data-stu-id="a7b09-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
