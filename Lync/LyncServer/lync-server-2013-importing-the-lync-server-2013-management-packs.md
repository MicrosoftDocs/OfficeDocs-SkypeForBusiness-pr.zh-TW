---
title: Lync Server 2013：匯入 Lync Server 2013 管理套件
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
ms.openlocfilehash: 4edc22c1cfc46b032e679a9dc0718113bc6967bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526650"
---
# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="6770a-102">匯入 Lync Server 2013 管理套件</span><span class="sxs-lookup"><span data-stu-id="6770a-102">Importing the Lync Server 2013 management packs</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6770a-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6770a-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6770a-104">您可以安裝管理套件（會決定 System Center Operations Manager 可監控哪些專案，以及應如何監視和報告警報）的軟體，以擴充 System Center Operations Manager 的功能。</span><span class="sxs-lookup"><span data-stu-id="6770a-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="6770a-105">Lync Server 2013 包括兩個 System Center Operations Manager 管理元件，可提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="6770a-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="6770a-106">Component 和 User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 追蹤事件記錄檔中記錄的 Lync Server 問題、由效能計數器所註冊，或是記錄在詳細通話記錄 (CDR) 或經驗品質 (QoE) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="6770a-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="6770a-107">針對嚴重問題，System Center Operations Manager 可以設定為透過電子郵件、立即訊息或短訊息服務立即通知系統管理員 (SMS) 訊息。</span><span class="sxs-lookup"><span data-stu-id="6770a-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="6770a-108">SMS 是用來將文字訊息從一部行動裝置傳送至另一部行動裝置的技術。 ) </span><span class="sxs-lookup"><span data-stu-id="6770a-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6770a-109">如需設定 Operations Manager 通知的詳細資訊，請參閱設定 TechNet 程式庫中的通知 <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A> 。</span><span class="sxs-lookup"><span data-stu-id="6770a-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="6770a-110">主動監控管理元件 (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主動測試重要的 Lync Server 元件，例如登入系統、交換立即訊息，或撥打位於公用交換電話網路 (PSTN) 的電話。</span><span class="sxs-lookup"><span data-stu-id="6770a-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="6770a-111">使用 Lync Server 綜合交易 Cmdlet 進行這些測試。</span><span class="sxs-lookup"><span data-stu-id="6770a-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="6770a-112">例如，您可以使用 **Test-CsIM** Cmdlet 來模擬一對測試使用者之間的立即訊息 (IM) 交談。</span><span class="sxs-lookup"><span data-stu-id="6770a-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="6770a-113">如果此模擬的郵件交談失敗，則會產生警示。</span><span class="sxs-lookup"><span data-stu-id="6770a-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="6770a-114">您必須匯入管理套件。</span><span class="sxs-lookup"><span data-stu-id="6770a-114">You need to import the management packs.</span></span> <span data-ttu-id="6770a-115">若不匯入管理套件，則無法使用 Operations Manager 來監視 Lync Server 事件或執行 Lync Server 綜合交易。</span><span class="sxs-lookup"><span data-stu-id="6770a-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="6770a-116">元件和使用者管理套件只會用來監視 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6770a-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="6770a-117">如果您處於共存案例中，且同時安裝了 Lync Server 2013 和 Lync Server 2010，則應該繼續使用 lync server 2010 管理套件進行 Lync Server 2010 電腦。</span><span class="sxs-lookup"><span data-stu-id="6770a-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6770a-118">Lync Server 2010 的管理元件包括 Lync Server 2010 Monitoring Management Pack 和 Lync Server 2010 Group Chat Monitoring Management Pack。</span><span class="sxs-lookup"><span data-stu-id="6770a-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="6770a-119">您可以使用下列其中一個工具匯入管理元件：</span><span class="sxs-lookup"><span data-stu-id="6770a-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="6770a-120">**System Center Operations Manager**    使用此方法，您可以使用 Operations Manager 來新增監控的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="6770a-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="6770a-121">**Operations Manager 命令**     介面您可以使用 Operations Manager 命令介面直接匯入，或疑難排解您使用 System Center Operations Manager 主控台匯入管理元件時所遇到的任何問題。</span><span class="sxs-lookup"><span data-stu-id="6770a-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="6770a-122">使用 System Center Operations Manager 匯入管理套件</span><span class="sxs-lookup"><span data-stu-id="6770a-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="6770a-123">下載檔案 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp。</span><span class="sxs-lookup"><span data-stu-id="6770a-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="6770a-124">在 System Center Operations Manager 中，按一下 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="6770a-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="6770a-125">在 [ **管理** ] 窗格中，以滑鼠右鍵按一下 [ **管理元件**]，然後按一下 [匯 **入管理元件**]。</span><span class="sxs-lookup"><span data-stu-id="6770a-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="6770a-126">在 [ **選取管理元件** ] 對話方塊中，按一下 [ **新增**]，然後按一下 [ **從磁片新增**]。</span><span class="sxs-lookup"><span data-stu-id="6770a-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="6770a-127">在 [ **線上目錄連線** ] 對話方塊中，按一下 [ **取消** ]，以防止 Operations Manager 進入線上狀態，以查看是否存在 Lync Server 管理套件的任何相依性。</span><span class="sxs-lookup"><span data-stu-id="6770a-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="6770a-128">如果您使用 System Center Operations Manager 2012，請按一下 [ **否**]。</span><span class="sxs-lookup"><span data-stu-id="6770a-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="6770a-129">在 [ **選取要匯入的管理元件** ] 對話方塊中，找出並選取 **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** 及 **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** 的檔案，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="6770a-129">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**.</span></span> <span data-ttu-id="6770a-130">若要在對話方塊中選取多個檔案，請按一下第一個檔案，按住 Ctrl 鍵，然後按一下第二個檔案。</span><span class="sxs-lookup"><span data-stu-id="6770a-130">To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="6770a-131">在 [ **選取管理元件** ] 對話方塊中，按一下 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="6770a-131">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="6770a-132">如果您收到錯誤訊息，且安裝失敗，這通常表示管理元件檔案位於由 Windows 使用者帳戶控制保護的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="6770a-132">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="6770a-133">如果發生這種情況，請將檔案複製到其他資料夾，然後重新開機匯入和安裝程式。</span><span class="sxs-lookup"><span data-stu-id="6770a-133">If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="6770a-134">在 [ **選取管理元件** ] 對話方塊中，按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6770a-134">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="6770a-135">請注意，匯入和安裝程式可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="6770a-135">Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="6770a-136">使用 Operations Manager 命令介面匯入管理元件</span><span class="sxs-lookup"><span data-stu-id="6770a-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="6770a-137">一般來說，使用 Operations Manager 匯入管理元件時，會比較容易。不過，如果發生錯誤，且匯入失敗，則主控台不一定會提供適當的錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="6770a-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="6770a-138">依比較，Operations Manager 命令介面會提供詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6770a-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="6770a-139">如果您使用的是 Operations Manager，而且在匯入管理元件時遇到問題，請使用 Operations Manager 命令介面匯入套裝軟體。</span><span class="sxs-lookup"><span data-stu-id="6770a-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="6770a-140">Operations Manager 命令介面提供更多資訊，可協助您判斷匯入失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="6770a-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="6770a-141">如果您使用的是 System Center Operations Manager 2007 R2，請完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="6770a-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="6770a-142">依序按一下 [ **開始**]、[ **所有程式**]、[ **System Center Operations Manager 2007 R2**]，然後按一下 [ **Operations Manager 命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6770a-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="6770a-143">在 Operations Manager 命令介面中，使用檔案 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 副本的實際路徑，在命令提示字元處輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="6770a-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="6770a-144">在匯入第一個管理套件之後，請使用檔案副本的路徑重複處理常式 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp：</span><span class="sxs-lookup"><span data-stu-id="6770a-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="6770a-145">關閉 Operations Manager 命令介面。</span><span class="sxs-lookup"><span data-stu-id="6770a-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="6770a-146">如果您使用 System Center Operations Manager 2012，請改為完成此程式：</span><span class="sxs-lookup"><span data-stu-id="6770a-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="6770a-147">依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft System Center 2012**] 及 [ **Operations Manager**]，然後按一下 [ **operations manager 命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6770a-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="6770a-148">在 Operations Manager 命令介面中，使用檔案 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 副本的實際路徑，在命令提示字元處輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="6770a-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="6770a-149">在匯入第一個管理套件之後，請使用檔案副本的路徑重複處理常式 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp：</span><span class="sxs-lookup"><span data-stu-id="6770a-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

