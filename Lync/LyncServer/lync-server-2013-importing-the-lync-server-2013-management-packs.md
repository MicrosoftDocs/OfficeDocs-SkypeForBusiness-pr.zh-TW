---
title: Lync Server 2013： 匯入 Lync Server 2013 管理組件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2c6dd42056fe665c0d4ec53d28103745ace2c84
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="9cd8e-102">匯入 Lync Server 2013 管理組件</span><span class="sxs-lookup"><span data-stu-id="9cd8e-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cd8e-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="9cd8e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="9cd8e-104">您可以藉由安裝管理組件擴充功能的 System Center Operations Manager — 軟體，即表示這項目 System Center Operations Manager 可監視、 如何應監視這些項目並觸發提醒的方式和報告。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="9cd8e-105">Lync Server 2013 包含兩個 System Center Operations Manager 管理組件提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="9cd8e-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="9cd8e-106">元件及使用者管理組件 (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 追蹤記錄在事件記錄檔、 登錄的效能計數器，或登入詳細通話記錄 (CDR) 或經驗品質 (QoE) 的 Lync Server 問題資料庫。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="9cd8e-107">針對重大問題，可以設定 System Center Operations Manager 立即通知系統管理員透過電子郵件、 立即訊息，或短訊息服務 (SMS) 通訊。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="9cd8e-108">SMS 是用來將文字訊息從一種行動裝置傳送到另一個技術）。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9cd8e-109">如需設定 Operations Manager 通知的詳細資訊，請參閱 TechNet Library 「 設定通知<A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="9cd8e-110">作用中監控管理組件 (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主動測試重要的 Lync Server 元件，例如登入系統、 交換立即訊息，或撥打電話到位於公用交換電話電話網路 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="9cd8e-111">使用 Lync Server 綜合交易 cmdlet 進行這些測試。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="9cd8e-112">例如，您可以使用**Test-csim**指令程式以模擬立即訊息 (IM) 交談的測試使用者對之間。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="9cd8e-113">如果此模擬的訊息對話失敗警示產生。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="9cd8e-114">您必須匯入管理組件。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-114">You need to import the management packs.</span></span> <span data-ttu-id="9cd8e-115">如果您不要匯入管理組件，您無法使用 Operations Manager 監視 Lync Server 的事件，或執行 Lync Server 綜合交易。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="9cd8e-116">使用者管理組件與元件只用來監視 Lync Server 2013 中。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="9cd8e-117">如果您是在共存案例中，其中有 Lync Server 2013 和 Lync Server 2010 安裝，您應繼續使用 Lync Server 2010 管理組件的 Lync Server 2010 電腦。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9cd8e-118">適用於 Lync Server 2010 管理組件包含 Lync Server 2010 Monitoring Management Pack 及 Lync Server 2010 群組聊天監控管理組件。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="9cd8e-119">您可以使用下列其中一個下列工具匯入管理組件：</span><span class="sxs-lookup"><span data-stu-id="9cd8e-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="9cd8e-120">**System Center Operations Manager**   使用此方法之後，您可以使用 Operations Manager 新增 Lync Server 的監視。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="9cd8e-121">**Operations Manager 殼層**   直接匯入或您使用 System Center Operations Manager 主控台匯入管理組件時，發生任何問題進行疑難排解，您可以使用 Operations Manager 殼層。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="9cd8e-122">使用 System Center Operations Manager 匯入管理組件</span><span class="sxs-lookup"><span data-stu-id="9cd8e-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="9cd8e-123">下載 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 及 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="9cd8e-124">在 System Center Operations Manager，按一下 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="9cd8e-125">在 [**管理**] 窗格中，以滑鼠右鍵按一下 [**管理組件**，，，然後按一下 [**匯入管理組件**。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="9cd8e-126">在 [**選取管理組件**] 對話方塊中，按一下 [**新增**]，然後按一下 [**從磁碟新增]**。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="9cd8e-127">在 [**線上目錄連線**] 對話方塊中，按一下 [**取消**] 以防止 Operations Manager 移 online，請參閱針對 Lync Server 管理組件若存在任何相依性。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="9cd8e-128">如果您使用 System Center Operations Manager 2012，按一下 [**否]**。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="9cd8e-129">在 [**選取要匯入管理組件**] 對話方塊中，尋找和選取**Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp**及**Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**兩個檔案，然後按一下**開啟**。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-129">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**.</span></span> <span data-ttu-id="9cd8e-130">若要選取多個檔案] 對話方塊中，按一下 [第一個檔案，按住 Ctrl 鍵，然後按一下第二個檔案。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-130">To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="9cd8e-131">在 [**選取管理組件**] 對話方塊中，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-131">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="9cd8e-132">如果您收到錯誤訊息，安裝就會失敗，，通常表示管理組件檔案在受保護的 Windows 使用者帳戶控制] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-132">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="9cd8e-133">如果發生這種情況，將檔案複製到不同的資料夾，然後重新啟動匯入並安裝程序。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-133">If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="9cd8e-134">在 [**選取管理組件**] 對話方塊中，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-134">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="9cd8e-135">請注意的匯入和安裝程序可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-135">Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="9cd8e-136">使用 Operations Manager 殼層匯入管理組件</span><span class="sxs-lookup"><span data-stu-id="9cd8e-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="9cd8e-137">一般會比較容易使用作業 Manager.However 中，如果發生錯誤，而且匯入失敗時，主控台一律也不會提供足夠的錯誤報告匯入管理組件。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="9cd8e-138">相較之下，Operations Manager 命令介面中，提供詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="9cd8e-139">如果您使用 Operations Manager，而且您遇到匯入管理組件，匯入組件，以使用 Operations Manager 命令介面。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="9cd8e-140">Operations Manager 殼層提供可協助您判斷匯入失敗的原因的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="9cd8e-141">如果您使用 System Center Operations Manager 2007 R2，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="9cd8e-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="9cd8e-142">按一下 [**開始]**、 [**所有程式]**、 [ **System Center Operations Manager 2007 R2**，，然後按一下**Operations Manager 殼層**。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="9cd8e-143">在 Operations Manager 命令介面中，在命令提示字元處使用 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp，檔案副本的實際路徑輸入下列命令，然後按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="9cd8e-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="9cd8e-144">匯入第一個管理組件後，重複進行這個程序，使用 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 檔案的路徑：</span><span class="sxs-lookup"><span data-stu-id="9cd8e-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="9cd8e-145">關閉 Operations Manager 殼層。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="9cd8e-146">如果您使用 System Center Operations Manager 2012，請改為完成此程序：</span><span class="sxs-lookup"><span data-stu-id="9cd8e-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="9cd8e-147">按一下 [**開始]**、 [**所有程式]**、 按一下 [ **Microsoft System Center 2012**，按一下**Operations Manager**]，然後按一下**Operations Manager 殼層**。</span><span class="sxs-lookup"><span data-stu-id="9cd8e-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="9cd8e-148">在 Operations Manager 命令介面中，在命令提示字元處使用 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp，檔案副本的實際路徑輸入下列命令，然後按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="9cd8e-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="9cd8e-149">您已匯入第一個管理組件後，重複使用 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 檔案的路徑的程序：</span><span class="sxs-lookup"><span data-stu-id="9cd8e-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

