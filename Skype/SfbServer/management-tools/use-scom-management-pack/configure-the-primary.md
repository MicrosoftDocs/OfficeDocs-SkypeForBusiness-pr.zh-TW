---
title: 設定主要管理伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 摘要：設定您的主要管理伺服器、安裝 System Center Operations Manager，並匯入商務用 Skype Server 2015 的管理套件。
ms.openlocfilehash: 0492a86062577d5118860faae8beca50f9f7bed2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816122"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="38d8c-103">設定主要管理伺服器</span><span class="sxs-lookup"><span data-stu-id="38d8c-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="38d8c-104">**摘要：** 設定您的主要管理伺服器、安裝 System Center Operations Manager，並匯入商務用 Skype Server 2015 的管理套件。</span><span class="sxs-lookup"><span data-stu-id="38d8c-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="38d8c-105">若要充分利用商務用 Skype Server 2015 中包含的新健康情況監視功能，您必須先指定電腦作為您的主要管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="38d8c-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="38d8c-106">接著，您必須在該電腦上安裝 System Center Operations Manager 2012 SP1 或 R2 或 System Center Operations Manager 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="38d8c-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="38d8c-107">此外，您必須先安裝支援的 SQL Server 版本，才能充當 Operations Manager 後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="38d8c-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="38d8c-108">當您安裝 System Center Operations Manager 時，您必須安裝該產品的所有元件，包括：</span><span class="sxs-lookup"><span data-stu-id="38d8c-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="38d8c-109">運算元據庫</span><span class="sxs-lookup"><span data-stu-id="38d8c-109">Operational database</span></span>

- <span data-ttu-id="38d8c-110">伺服器</span><span class="sxs-lookup"><span data-stu-id="38d8c-110">Server</span></span>

- <span data-ttu-id="38d8c-111">控制</span><span class="sxs-lookup"><span data-stu-id="38d8c-111">Console</span></span>

- <span data-ttu-id="38d8c-112">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="38d8c-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="38d8c-113">網頁主控台</span><span class="sxs-lookup"><span data-stu-id="38d8c-113">Web console</span></span>

- <span data-ttu-id="38d8c-114">報告</span><span class="sxs-lookup"><span data-stu-id="38d8c-114">Reporting</span></span>

- <span data-ttu-id="38d8c-115">資料倉儲</span><span class="sxs-lookup"><span data-stu-id="38d8c-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38d8c-116">您必須先安裝 [[Microsoft 報表檢視器2010可轉散發元件套件](https://www.microsoft.com/en-us/download/details.aspx?id=6442)]，才能安裝 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="38d8c-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="38d8c-117">如需這些產品及其安裝的詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="38d8c-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="38d8c-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="38d8c-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="38d8c-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="38d8c-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/en-us/library/bb735860.aspx)

<span data-ttu-id="38d8c-120">請記住，每個商務用 Skype Server 部署只能有一個根管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="38d8c-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="38d8c-121">匯入商務用 Skype Server 2015 管理套件</span><span class="sxs-lookup"><span data-stu-id="38d8c-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="38d8c-122">您可以透過安裝管理套件來延伸 System Center Operations Manager 的功能，此軟體會指示 System Center Operations Manager 可以監視哪些專案、應如何監視這些專案，以及應如何觸發預警，以及曾.</span><span class="sxs-lookup"><span data-stu-id="38d8c-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="38d8c-123">商務用 Skype Server 2015 包含兩個系統中心作業管理員管理套件，可提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="38d8c-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="38d8c-124">**元件與使用者管理套件**（Microsoft.LS.2015.Monitoring.ComponentAndUser.mp）會追蹤事件日誌中記錄的商務用 Skype 伺服器問題、由效能計數器註冊，或記錄在通話詳細資料記錄（CDRs）或體驗品質（QoE）資料庫中。</span><span class="sxs-lookup"><span data-stu-id="38d8c-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="38d8c-125">針對重要問題，系統中心作業管理員可以設定為透過電子郵件、立即訊息或 SMS 訊息立即通知管理員。</span><span class="sxs-lookup"><span data-stu-id="38d8c-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="38d8c-126">（SMS 或短訊息服務）是用來將文字訊息從一部行動裝置傳送至另一部的技術。</span><span class="sxs-lookup"><span data-stu-id="38d8c-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="38d8c-127">如需有關設定 Operations Manager 通知的詳細資訊，請參閱設定[通知](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="38d8c-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="38d8c-128">**主動監視管理套件**（Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp）會主動測試重要的商務用 Skype Server 元件，例如登入系統、交換立即訊息，或撥打電話至位於公用交換電話網絡（PSTN）的電話。</span><span class="sxs-lookup"><span data-stu-id="38d8c-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="38d8c-129">這些測試是使用商務用 Skype Server 綜合交易 Cmdlet 進行。</span><span class="sxs-lookup"><span data-stu-id="38d8c-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="38d8c-130">例如， **CsIM** Cmdlet 是用來模擬一對測試使用者之間的立即訊息交談。</span><span class="sxs-lookup"><span data-stu-id="38d8c-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="38d8c-131">如果這個模擬交談失敗，就會產生警示。</span><span class="sxs-lookup"><span data-stu-id="38d8c-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="38d8c-132">匯入管理套件是一個重要的步驟。</span><span class="sxs-lookup"><span data-stu-id="38d8c-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="38d8c-133">如果不是匯入管理套件，您將無法使用 Operations Manager 來監控商務用 Skype 伺服器事件，或執行商務用 Skype Server 綜合交易。</span><span class="sxs-lookup"><span data-stu-id="38d8c-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="38d8c-134">元件與使用者管理套件只用來監控商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="38d8c-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2015.</span></span> <span data-ttu-id="38d8c-135">如果您在已安裝商務用 Skype Server 2015 和 Lync Server 2013 的共存案例中，您應該繼續針對 Lync Server 2013 電腦使用 Lync Server 2013 管理套件。</span><span class="sxs-lookup"><span data-stu-id="38d8c-135">If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="38d8c-136">商務用 Skype Server 2015 的管理套件包括商務用 Skype Server 2015 元件與使用者管理套件，以及商務用 Skype Server 2015 活動的監視管理套件。</span><span class="sxs-lookup"><span data-stu-id="38d8c-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="38d8c-137">您可以使用下列其中一個工具匯入管理套件：</span><span class="sxs-lookup"><span data-stu-id="38d8c-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="38d8c-138">**System Center Operations Manager**使用這個方法，您可以使用 Operations Manager 來新增商務用 Skype Server 的監視。</span><span class="sxs-lookup"><span data-stu-id="38d8c-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="38d8c-139">**Operations Manager 命令**介面您可以使用 Operations Manager Shell 直接匯入，或針對您使用 System Center Operations Manager 主控台匯入管理套件時所遇到的任何問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="38d8c-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="38d8c-140">使用 System Center Operations Manager 匯入管理套件</span><span class="sxs-lookup"><span data-stu-id="38d8c-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="38d8c-141">從 Microsoft Web 下載下載 SkypeForBusiness2015ManagementPacks，然後安裝 msi。</span><span class="sxs-lookup"><span data-stu-id="38d8c-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="38d8c-142">在系統中心作業管理員中，按一下 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="38d8c-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="38d8c-143">在 [管理] 窗格中，以滑鼠右鍵按一下 [**管理套件**]，然後按一下 [匯**入管理套件**]。</span><span class="sxs-lookup"><span data-stu-id="38d8c-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="38d8c-144">在 [**選取管理套件**] 對話方塊中，按一下 [**新增**]，然後按一下 [**從磁片新增**]。</span><span class="sxs-lookup"><span data-stu-id="38d8c-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="38d8c-145">在 [**線上目錄連線**] 對話方塊中，按一下 [**否**]。</span><span class="sxs-lookup"><span data-stu-id="38d8c-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="38d8c-146">在 [**選取要匯入的管理套件**] 對話方塊中，找出並選取 [檔案] Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="38d8c-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="38d8c-147">若要在對話方塊中選取多個檔案，請按一下第一個檔案，然後按住 Ctrl 鍵並按一下後續的檔案。</span><span class="sxs-lookup"><span data-stu-id="38d8c-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="38d8c-148">在 [**選取管理套件**] 對話方塊中，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="38d8c-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="38d8c-149">如果您收到錯誤訊息，且安裝失敗，通常表示管理套件檔案位於受 Windows 使用者帳戶控制保護的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="38d8c-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="38d8c-150">如果發生這種情況，請將檔案複製到不同的資料夾，然後重新開機匯入和安裝程式。</span><span class="sxs-lookup"><span data-stu-id="38d8c-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="38d8c-151">在 [**選取管理套件**] 對話方塊中，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="38d8c-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="38d8c-152">匯入及安裝程式可能需要幾分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="38d8c-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="38d8c-153">使用 Operations Manager 命令介面匯入管理套件</span><span class="sxs-lookup"><span data-stu-id="38d8c-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="38d8c-154">一般來說，您可以使用 Operations Manager 主控台來輕鬆匯入管理套件。</span><span class="sxs-lookup"><span data-stu-id="38d8c-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="38d8c-155">不過，如果發生錯誤，並匯入失敗，則主機不一定會提供足夠的錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="38d8c-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="38d8c-156">根據比較，Operations Manager 命令介面會提供詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="38d8c-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="38d8c-157">如果您使用的是 Operations Manager，且在您匯入管理套件時遇到問題，請使用 Operations Manager 命令介面匯入套件。</span><span class="sxs-lookup"><span data-stu-id="38d8c-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="38d8c-158">Operations Manager 命令介面提供的資訊可協助您判斷匯入失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="38d8c-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="38d8c-159">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft System Center 2012**]，再按一下 [ **Operations Manager**]，然後按一下 [ **operations manager 命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="38d8c-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="38d8c-160">在 Operations Manager Shell 中，在命令提示字元中輸入下列命令，並使用您的檔案 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 複本的實際路徑，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="38d8c-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="38d8c-161">匯入第一個管理套件之後，請使用您的 [檔案 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp] 複本路徑來重複此程式：</span><span class="sxs-lookup"><span data-stu-id="38d8c-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
