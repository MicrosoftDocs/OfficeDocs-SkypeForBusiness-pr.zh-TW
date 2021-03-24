---
title: 設定主要管理伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：設定您的主要管理伺服器、安裝 System Center Operations Manager，以及匯入商務用 Skype Server 2015 的管理套件。
ms.openlocfilehash: ace25e1b4971c561dc1544290b04f481f36c9676
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111639"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="acc79-103">設定主要管理伺服器</span><span class="sxs-lookup"><span data-stu-id="acc79-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="acc79-104">**摘要：** 設定您的主要管理伺服器、安裝 System Center Operations Manager，以及匯入商務用 Skype Server 2015 的管理套件。</span><span class="sxs-lookup"><span data-stu-id="acc79-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="acc79-105">若要充分利用商務用 Skype Server 2015 中包含的新狀況監視功能，您必須先指定一部電腦做為您的主要管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="acc79-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="acc79-106">接著，您必須在該電腦上安裝 System Center Operations Manager 2012 SP1 或 R2 或 System Center Operations Manager 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="acc79-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="acc79-107">此外，您必須先安裝支援版本的 SQL Server，才能充當 Operations Manager 後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="acc79-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="acc79-108">當您安裝 System Center Operations Manager 時，您將需要安裝該產品的所有元件，包括：</span><span class="sxs-lookup"><span data-stu-id="acc79-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="acc79-109">操作資料庫</span><span class="sxs-lookup"><span data-stu-id="acc79-109">Operational database</span></span>

- <span data-ttu-id="acc79-110">伺服器</span><span class="sxs-lookup"><span data-stu-id="acc79-110">Server</span></span>

- <span data-ttu-id="acc79-111">主控台</span><span class="sxs-lookup"><span data-stu-id="acc79-111">Console</span></span>

- <span data-ttu-id="acc79-112">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="acc79-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="acc79-113">Web 主控台</span><span class="sxs-lookup"><span data-stu-id="acc79-113">Web console</span></span>

- <span data-ttu-id="acc79-114">報告</span><span class="sxs-lookup"><span data-stu-id="acc79-114">Reporting</span></span>

- <span data-ttu-id="acc79-115">資料倉儲</span><span class="sxs-lookup"><span data-stu-id="acc79-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="acc79-116">安裝 System Center Operations Manager 2012 之前，必須先安裝「[Microsoft Report Viewer 2010 可轉散發元件套件](https://www.microsoft.com/download/details.aspx?id=6442)」。</span><span class="sxs-lookup"><span data-stu-id="acc79-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="acc79-117">如需這些產品及其安裝的詳細資訊，請參閱下列連結：</span><span class="sxs-lookup"><span data-stu-id="acc79-117">For details about these products and their installation, see the following links:</span></span>

- <span data-ttu-id="acc79-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span><span class="sxs-lookup"><span data-stu-id="acc79-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span></span>

- [<span data-ttu-id="acc79-119">System Center Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="acc79-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="acc79-120">請記住，每個商務用 Skype Server 部署只能有一個根管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="acc79-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="acc79-121">匯入商務用 Skype Server 2015 管理套件</span><span class="sxs-lookup"><span data-stu-id="acc79-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="acc79-122">您可以安裝管理套件（會決定 System Center operations Manager 可監控哪些專案、應如何監視這些專案，以及如何觸發及報告提醒）的軟體，以擴充 System Center Operations Manager 的功能。</span><span class="sxs-lookup"><span data-stu-id="acc79-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="acc79-123">商務用 Skype Server 2015 包括兩個 System Center Operations Manager 管理元件，可提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="acc79-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="acc79-124">**Component 和 User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) 會追蹤事件記錄檔中記錄的商務用 Skype Server 問題、由效能計數器所註冊，或是記錄在詳細通話記錄 (cdr) 或經驗品質 (QoE) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="acc79-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="acc79-125">針對嚴重問題，您可以設定 System Center Operations Manager 立即透過電子郵件、立即訊息或 SMS 訊息通知系統管理員。</span><span class="sxs-lookup"><span data-stu-id="acc79-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="acc79-126"> (短信或短訊息服務是用來將文字訊息從一部行動裝置傳送至另一部行動裝置的技術。 ) </span><span class="sxs-lookup"><span data-stu-id="acc79-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="acc79-127">如需設定 Operations Manager 通知的詳細資訊，請參閱設定 [通知](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="acc79-127">For details about configuring Operations Manager notification, see [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).</span></span>

- <span data-ttu-id="acc79-128">**使用中的 Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) 主動測試重要的商務用 Skype Server 元件，例如登入系統、交換立即訊息，或撥打位於公用交換電話網路 (PSTN) 的電話。</span><span class="sxs-lookup"><span data-stu-id="acc79-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="acc79-129">這些測試是透過商務用 Skype Server 綜合交易 Cmdlet 來執行。</span><span class="sxs-lookup"><span data-stu-id="acc79-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="acc79-130">例如， **Test-CsIM** Cmdlet 是用來模擬一對測試使用者之間的立即訊息交談。</span><span class="sxs-lookup"><span data-stu-id="acc79-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="acc79-131">如果此模擬交談失敗，就會產生警示。</span><span class="sxs-lookup"><span data-stu-id="acc79-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="acc79-132">匯入管理套件是一個重要的步驟。</span><span class="sxs-lookup"><span data-stu-id="acc79-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="acc79-133">若未匯入管理套件，您將無法使用 Operations Manager 來監視商務用 Skype 伺服器事件或執行商務用 Skype Server 綜合交易。</span><span class="sxs-lookup"><span data-stu-id="acc79-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="acc79-134">元件和使用者管理套件只會用來監視商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="acc79-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2015.</span></span> <span data-ttu-id="acc79-135">如果您處於同時安裝商務用 Skype Server 2015 和 Lync Server 2013 的共存案例中，您應該繼續使用 Lync server 2013 管理元件來進行 Lync Server 2013 電腦。</span><span class="sxs-lookup"><span data-stu-id="acc79-135">If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="acc79-136">商務用 Skype Server 2015 的管理元件包括商務用 Skype Server 2015 元件、使用者管理套件和商務用 Skype Server 2015 使用中監控管理元件。</span><span class="sxs-lookup"><span data-stu-id="acc79-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="acc79-137">您可以使用下列其中一個工具匯入管理元件：</span><span class="sxs-lookup"><span data-stu-id="acc79-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="acc79-138">**System Center Operations Manager** 使用此方法，您可以使用 Operations Manager 為商務用 Skype Server 新增監控。</span><span class="sxs-lookup"><span data-stu-id="acc79-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="acc79-139">**Operations Manager 命令** 介面您可以使用 Operations Manager 命令介面直接匯入，或疑難排解使用 System Center Operations Manager 主控台匯入管理元件時所遇到的任何問題。</span><span class="sxs-lookup"><span data-stu-id="acc79-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="acc79-140">使用 System Center Operations Manager 匯入管理套件</span><span class="sxs-lookup"><span data-stu-id="acc79-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="acc79-141">從 Microsoft Web 下載下載 SkypeForBusiness2015ManagementPacks.msi，然後安裝 msi。</span><span class="sxs-lookup"><span data-stu-id="acc79-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="acc79-142">在 System Center Operations Manager 中，按一下 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="acc79-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="acc79-143">在 [管理] 窗格中，以滑鼠右鍵按一下 [ **管理元件**]，然後按一下 [匯 **入管理元件**]。</span><span class="sxs-lookup"><span data-stu-id="acc79-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="acc79-144">在 [ **選取管理元件** ] 對話方塊中，按一下 [ **新增**]，然後按一下 [ **從磁片新增**]。</span><span class="sxs-lookup"><span data-stu-id="acc79-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="acc79-145">在 [ **線上目錄連線** ] 對話方塊中，按一下 [ **否**]。</span><span class="sxs-lookup"><span data-stu-id="acc79-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="acc79-146">在 [ **選取要匯入的管理元件** ] 對話方塊中，找出並選取 [檔案 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp] 和 [Microsoft.LS.2015.Monitoring.ComponentAndUser.mp]，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="acc79-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="acc79-147">若要在對話方塊中選取多個檔案，請按一下第一個檔案，然後按住 Ctrl 鍵並按一下後續的檔案。</span><span class="sxs-lookup"><span data-stu-id="acc79-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="acc79-148">在 [ **選取管理元件** ] 對話方塊中，按一下 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="acc79-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="acc79-149">如果您收到錯誤訊息，且安裝失敗，這通常表示管理元件檔案位於由 Windows 使用者帳戶控制保護的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="acc79-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="acc79-150">如果發生這種情況，請將檔案複製到其他資料夾，然後重新開機匯入和安裝程式。</span><span class="sxs-lookup"><span data-stu-id="acc79-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="acc79-151">在 [ **選取管理元件** ] 對話方塊中，按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="acc79-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="acc79-152">匯入和安裝程式可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="acc79-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="acc79-153">使用 Operations Manager 命令介面匯入管理套件</span><span class="sxs-lookup"><span data-stu-id="acc79-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="acc79-154">一般說來，使用 Operations Manager 主控台匯入管理元件會比較容易。</span><span class="sxs-lookup"><span data-stu-id="acc79-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="acc79-155">不過，如果發生錯誤，而且匯入失敗，則主控台不一定會提供適當的錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="acc79-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="acc79-156">依比較，Operations Manager 命令介面會提供詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="acc79-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="acc79-157">如果您使用的是 Operations Manager，而且在匯入管理元件時遇到問題，請使用 Operations Manager 命令介面匯入套裝軟體。</span><span class="sxs-lookup"><span data-stu-id="acc79-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="acc79-158">Operations Manager 命令介面提供的資訊可協助您決定匯入失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="acc79-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="acc79-159">依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft System Center 2012**] 及 [ **Operations Manager**]，然後按一下 [ **operations manager 命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="acc79-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="acc79-160">在 Operations Manager 命令介面中，使用您的檔案 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 副本的實際路徑，在命令提示字元處輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="acc79-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="acc79-161">在匯入第一個管理套件之後，請使用您的檔案 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp 副本的路徑重複此程式：</span><span class="sxs-lookup"><span data-stu-id="acc79-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```