---
title: 為商務用 Skype Server 安裝及設定忙碌選項
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 閱讀如何在商務用 Skype Server 中安裝及設定忙碌選項。
ms.openlocfilehash: 04690e9f2c7fbf16b67432526fe5c8fd6e5b95af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106309"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="cac5c-103">為商務用 Skype Server 安裝及設定忙碌選項</span><span class="sxs-lookup"><span data-stu-id="cac5c-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="cac5c-104">閱讀如何在商務用 Skype Server 中安裝及設定忙碌選項。</span><span class="sxs-lookup"><span data-stu-id="cac5c-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="cac5c-105">「忙碌選項」是在2016累積更新中引進的新語音原則，可讓您設定使用者已在通話或會議中，或有來電暫止的情況下，如何處理來電。</span><span class="sxs-lookup"><span data-stu-id="cac5c-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="cac5c-106">您可以使用繁忙的信號或轉接至語音信箱來拒絕新的或來電的來電。</span><span class="sxs-lookup"><span data-stu-id="cac5c-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="cac5c-107">如果為組織啟用忙碌選項，企業中的所有使用者（Enterprise Voice 和非企業語音使用者）都可以使用下列設定選項：</span><span class="sxs-lookup"><span data-stu-id="cac5c-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="cac5c-108">忙於忙碌-當使用者忙碌時，將會以忙碌信號拒絕新的來電。</span><span class="sxs-lookup"><span data-stu-id="cac5c-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="cac5c-109">在忙碌中的語音信箱，當使用者忙碌時，會將新的來電轉送到語音信箱。</span><span class="sxs-lookup"><span data-stu-id="cac5c-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="cac5c-110">不論其忙碌選項的設定方式為何，通話或會議中的使用者或是具有保留狀態的使用者，都不會被禁止撥打新的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="cac5c-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="cac5c-111">如需「忙碌選項」功能的相關資訊，請參閱 [Plan For 商務用 Skype Server 的繁忙選項](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="cac5c-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="cac5c-112">安裝</span><span class="sxs-lookup"><span data-stu-id="cac5c-112">Install</span></span>

<span data-ttu-id="cac5c-113">請確定您已安裝最新版的商務用 Skype Server，且已安裝最新版的修補程式。</span><span class="sxs-lookup"><span data-stu-id="cac5c-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="cac5c-114">若要執行此動作，請先停止所有服務，然後執行商務用 Skype Server 更新安裝程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cac5c-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="cac5c-115">執行 Stop-CsWindowsService 命令。</span><span class="sxs-lookup"><span data-stu-id="cac5c-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="cac5c-116">在集區中的每一部前端伺服器上執行 SkypeServerUpdateInstaller.exe 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="cac5c-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="cac5c-117">如果您想要確保 SBS 上的容錯移轉支援，請在每個 Survivable 分支伺服器 (SBS) 上執行 SkypeServerUpdateInstaller.exe 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="cac5c-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="cac5c-118">安裝程式將會部署最新版本的「忙碌選項」應用程式。</span><span class="sxs-lookup"><span data-stu-id="cac5c-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="cac5c-119">不過，預設不會啟用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="cac5c-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="cac5c-120">若要啟用此應用程式，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cac5c-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="cac5c-121">執行 [Set-CsVoicePolicy](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) Cmdlet 以全域啟用忙碌選項，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="cac5c-121">Run the [Set-CsVoicePolicy](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="cac5c-122">接下來，如果網站有語音原則，您必須啟用語音原則的「忙碌」選項，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cac5c-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="cac5c-123">首先，執行 [Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps) 以取得網站的名稱：</span><span class="sxs-lookup"><span data-stu-id="cac5c-123">First, run [Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="cac5c-124">使用身分識別值 (例如：從 Get-CsSite 取得的 Site： Redmond1) ，以取得網站的語音原則，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cac5c-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="cac5c-125">如果網站有語音原則，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cac5c-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="cac5c-126">接下來，執行 [New-CsServerApplication](/powershell/module/skype/new-csserverapplication?view=skype-ps) Cmdlet 以將忙碌選項新增至伺服器應用程式清單，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="cac5c-126">Next, run the [New-CsServerApplication](/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="cac5c-127">您必須以特定集區的完整功能變數名稱取代% FQDN%。</span><span class="sxs-lookup"><span data-stu-id="cac5c-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="cac5c-128">接下來，執行 [Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) Cmdlet 以更新「忙碌」選項 CMDLET (RBAC) 角色的角色型存取控制，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="cac5c-128">Next, run the [Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="cac5c-129">最後，使用執行 [Start-CsWindowsService](/powershell/module/skype/start-cswindowsservice?view=skype-ps) 命令，在已安裝及啟用 [忙碌] 選項的所有集區中，啟動所有前端伺服器上的商務用 Skype Server Windows 服務：</span><span class="sxs-lookup"><span data-stu-id="cac5c-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="cac5c-130">設定</span><span class="sxs-lookup"><span data-stu-id="cac5c-130">Configure</span></span>

<span data-ttu-id="cac5c-131">若要設定忙碌選項，請使用 [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cac5c-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="cac5c-132">例如，下列命令會設定使用者「Ken Myer」的繁忙選項。</span><span class="sxs-lookup"><span data-stu-id="cac5c-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="cac5c-133">在此設定中，任何對「Ken Myer」的呼叫都會在來電已通話時傳回占線信號：</span><span class="sxs-lookup"><span data-stu-id="cac5c-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="cac5c-134">在下一個範例中，此命令會為使用者 "Chrystal Velasquez" 設定繁忙選項。</span><span class="sxs-lookup"><span data-stu-id="cac5c-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="cac5c-135">在此設定中，當她已經在通話中時，會將「Chrystal Velasquez」的新來電轉寄到語音信箱：</span><span class="sxs-lookup"><span data-stu-id="cac5c-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="cac5c-136">您可以使用 [CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) 指令程式，來取得忙碌選項的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="cac5c-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="cac5c-137">下列範例會傳回 "KenMyer@Contoso.com" 的 [忙碌選項] 設定：</span><span class="sxs-lookup"><span data-stu-id="cac5c-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="cac5c-138">您可以使用 [CsBusyOptions 指令程式](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) 移除忙碌選項。</span><span class="sxs-lookup"><span data-stu-id="cac5c-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="cac5c-139">下列命令會移除 "Ken Myer" 的繁忙選項：</span><span class="sxs-lookup"><span data-stu-id="cac5c-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="cac5c-140">如需您用來設定忙碌選項之 Cmdlet 的詳細資訊，請參閱 [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)、 [CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)和 [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)的技術參考內容。</span><span class="sxs-lookup"><span data-stu-id="cac5c-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="cac5c-141">啟用記錄</span><span class="sxs-lookup"><span data-stu-id="cac5c-141">Enable logging</span></span>

<span data-ttu-id="cac5c-142">若要使用集中式記錄服務來啟用忙碌選項的記錄，請指定下列各項：</span><span class="sxs-lookup"><span data-stu-id="cac5c-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="cac5c-143">驗證及疑難排解</span><span class="sxs-lookup"><span data-stu-id="cac5c-143">Verify and troubleshoot</span></span>

<span data-ttu-id="cac5c-144">安裝忙碌選項之後，您可以使用 [Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) Cmdlet 來取得伺服器應用程式的清單，以確認安裝成功。</span><span class="sxs-lookup"><span data-stu-id="cac5c-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="cac5c-145">如果已正確安裝忙碌選項，指令指令的輸出應會顯示「忙碌選項」設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cac5c-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="cac5c-146">您也可以使用 Windows 事件檢視器，確認「忙碌選項」安裝順利完成，且商務用 Skype Server 成功載入繁忙選項。</span><span class="sxs-lookup"><span data-stu-id="cac5c-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="cac5c-147">若要驗證忙碌選項，請開啟 [ **事件檢視器- \> 應用程式及服務記錄檔- \> Skype (] 或 [Lync) Server** ]，然後搜尋事件 ID= 30253。</span><span class="sxs-lookup"><span data-stu-id="cac5c-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>