---
title: Lync Server 2013：設定監視節點以使用憑證驗證
description: Lync Server 2013：設定監視節點以使用憑證驗證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b65d4e3f90b27aac69b8569472ac9896766e093e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576319"
---
# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="5c9ce-103">在 Lync Server 2013 中設定監視節點以使用憑證驗證</span><span class="sxs-lookup"><span data-stu-id="5c9ce-103">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c9ce-104">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="5c9ce-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="5c9ce-p101">如果您的監看員節點電腦位於周邊網路外部，則必須遵循稍微不同的程序，以設定監看員節點執行綜合交易。具體而言，您不應該建立信任的應用程式集區和信任的應用程式，且您必須安裝憑證，讓監看員節點能夠將通知傳送至周邊網路內的電腦。這表示您必須完成下列兩項工作：</span><span class="sxs-lookup"><span data-stu-id="5c9ce-p101">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions. Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network. This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="5c9ce-108">更新電腦之 RTC Local Read-only Administrators 群組中的成員資格</span><span class="sxs-lookup"><span data-stu-id="5c9ce-108">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="5c9ce-109">安裝監看員節點設定檔案</span><span class="sxs-lookup"><span data-stu-id="5c9ce-109">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="5c9ce-110">更新 RTC Local Read-Only Administrators 群組中的成員資格</span><span class="sxs-lookup"><span data-stu-id="5c9ce-110">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="5c9ce-p102">如果您的監看員節點電腦位於周邊網路外部，則必須將網路服務帳戶新增至監看員節點電腦上的 RTC Local Read-only Administrators 群組。若要執行這項操作，請在監看員節點上完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="5c9ce-p102">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer. To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="5c9ce-113">按一下 [開始]\*\*\*\*，然後以滑鼠右鍵按一下 [電腦]\*\*\*\*，再按一下 [管理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-113">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="5c9ce-114">在伺服器管理員中，依序展開 [設定]\*\*\*\* 及 [本機使用者和群組]\*\*\*\*，然後按一下 [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-114">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="5c9ce-115">在 [群組] 窗格中，按兩下 [RTC Local Read-only Administrators]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-115">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="5c9ce-116">在 [RTC Local Read-only Administrators 內容]\*\*\*\* 對話方塊中，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-116">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="5c9ce-117">在 [選取使用者、電腦、服務帳戶或群組]\*\*\*\* 對話方塊中，按一下 [位置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-117">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="5c9ce-118">在 [位置]\*\*\*\* 對話方塊中，選取監看員節點電腦的名稱，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-118">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="5c9ce-119">在 [輸入物件名稱來選取]\*\*\*\* 方塊中，輸入 [網路服務]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-119">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="5c9ce-120">在 [RTC Local Read-only Administrators 內容]\*\*\*\* 對話方塊中，按一下 [確定]\*\*\*\*，然後關閉 [伺服器管理員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-120">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="5c9ce-121">重新啟動監看員節點電腦。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-121">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="5c9ce-122">安裝監看員節點設定檔案</span><span class="sxs-lookup"><span data-stu-id="5c9ce-122">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="5c9ce-123">重新啟動監看員節點電腦之後，下一個步驟是執行 Watchernode.msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-123">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="5c9ce-124">若要執行這個檔案，請依序按一下 [ **開始**]、[ **所有程式**]、[ **lync server 2013**]，然後按一下 [ **lync server 管理命令**介面]，以開啟 lync server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-124">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="5c9ce-125">在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER (確定並指定您 Watchernode.msi) 副本的實際路徑：</span><span class="sxs-lookup"><span data-stu-id="5c9ce-125">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="5c9ce-p104">如前所述，Watchernode.msi 也可以透過命令視窗來執行。若要開啟命令視窗，請按一下 [開始]<STRONG></STRONG>，然後以滑鼠右鍵按一下 [命令提示字元]<STRONG></STRONG>，再按一下 [以系統管理員身分執行]<STRONG></STRONG>。開啟命令視窗時，輸入與稍早所示相同的命令。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-p104">As noted previously, Watchernode.msi can also be run from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="5c9ce-129">您可以在無法將監看員節點設為信任的應用程式集區時，使用交涉模式。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-129">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="5c9ce-130">在此模式中，系統管理員必須在監看員節點上管理測試使用者密碼。</span><span class="sxs-lookup"><span data-stu-id="5c9ce-130">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

