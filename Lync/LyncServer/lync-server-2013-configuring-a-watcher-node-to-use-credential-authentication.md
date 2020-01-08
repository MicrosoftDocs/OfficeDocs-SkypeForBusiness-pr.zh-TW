---
title: Lync Server 2013：將觀察程式節點設定為使用認證驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3746042e0fbf6c7342dd19085f563440b26bb0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="35f44-102">在 Lync Server 2013 中將 [觀察程式] 節點設定為使用認證驗證</span><span class="sxs-lookup"><span data-stu-id="35f44-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35f44-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="35f44-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="35f44-104">如果您的觀察程式節點電腦位於周邊網路之外，您必須遵循稍有不同的程式，才能設定該觀察程式節點執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="35f44-104">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions.</span></span> <span data-ttu-id="35f44-105">具體來說，您不應該建立信任的應用程式池和受信任的應用程式，而且您必須安裝可讓觀察程式節點傳送通知到周邊網路內電腦的憑證。</span><span class="sxs-lookup"><span data-stu-id="35f44-105">Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network.</span></span> <span data-ttu-id="35f44-106">這表示您需要完成兩個不同的工作：</span><span class="sxs-lookup"><span data-stu-id="35f44-106">This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="35f44-107">更新電腦 RTC 本機唯讀系統管理員群組中的成員資格</span><span class="sxs-lookup"><span data-stu-id="35f44-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="35f44-108">安裝觀察程式節點設定檔</span><span class="sxs-lookup"><span data-stu-id="35f44-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="35f44-109">更新 RTC 本機唯讀系統管理員群組中的成員資格</span><span class="sxs-lookup"><span data-stu-id="35f44-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="35f44-110">如果您的觀察程式節點位於周邊網路之外，您必須將網路服務帳戶新增到 [程式] 節點電腦上的 RTC 本機唯讀系統管理員群組。</span><span class="sxs-lookup"><span data-stu-id="35f44-110">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer.</span></span> <span data-ttu-id="35f44-111">若要這樣做，請在 [觀察程式] 節點上完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="35f44-111">To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="35f44-112">按一下 [**開始**]，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="35f44-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="35f44-113">在 [伺服器管理員] 中，展開 [設定] **，展開 [\*\*\*\*本機使用者和群組**]，然後按一下 [**群組**]。</span><span class="sxs-lookup"><span data-stu-id="35f44-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="35f44-114">在 [群組] 窗格中，按兩下 [ **RTC 局部唯讀管理員**]。</span><span class="sxs-lookup"><span data-stu-id="35f44-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="35f44-115">在 [ **RTC 本機唯讀系統管理員屬性**] 對話方塊中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="35f44-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="35f44-116">在 [**選取使用者、電腦、服務帳戶或群組**] 對話方塊中，按一下 [**位置**]。</span><span class="sxs-lookup"><span data-stu-id="35f44-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="35f44-117">在 [**位置**] 對話方塊中，選取 [觀察程式] 節點電腦的名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="35f44-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="35f44-118">在 [**輸入要選取的物件名稱**] 方塊中，輸入 [**網路服務**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="35f44-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="35f44-119">在 [ **RTC 本機唯讀系統管理員屬性**] 對話方塊中，按一下 **[確定**]，然後關閉 [**伺服器管理員**]。</span><span class="sxs-lookup"><span data-stu-id="35f44-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="35f44-120">重新開機觀察程式節點電腦。</span><span class="sxs-lookup"><span data-stu-id="35f44-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="35f44-121">安裝觀察程式節點設定檔</span><span class="sxs-lookup"><span data-stu-id="35f44-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="35f44-122">在觀察程式節點電腦重新開機後，下一步就是執行檔案 Watchernode。</span><span class="sxs-lookup"><span data-stu-id="35f44-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="35f44-123">若要執行此檔案，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **lync server 2013**]，然後按一下 [ **lync Server Management shell**]，以開啟 Lync server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="35f44-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="35f44-124">在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER （請確定並指定您 Watchernode 複本的實際路徑）：</span><span class="sxs-lookup"><span data-stu-id="35f44-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="35f44-125">如先前所述，Watchernode 也可以從命令視窗執行。</span><span class="sxs-lookup"><span data-stu-id="35f44-125">As noted previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="35f44-126">若要開啟命令視窗，請按一下 [<STRONG>開始</STRONG>]，以滑鼠右鍵按一下 [<STRONG>命令提示</STRONG>字元]，然後按一下 [<STRONG>以系統管理員身分執行</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="35f44-126">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="35f44-127">當命令視窗開啟時，請輸入相同的命令，如先前所示。</span><span class="sxs-lookup"><span data-stu-id="35f44-127">When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="35f44-128">當無法將觀察程式節點設定為受信任的應用程式池時，就會使用 [協商] 模式。</span><span class="sxs-lookup"><span data-stu-id="35f44-128">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="35f44-129">在此模式中，系統管理員必須在 [觀察程式] 節點上管理測試使用者密碼。</span><span class="sxs-lookup"><span data-stu-id="35f44-129">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

