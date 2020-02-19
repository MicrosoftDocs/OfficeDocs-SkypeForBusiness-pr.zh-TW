---
title: 使用最佳做法分析程式來掃描您的部署有潛在的問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6c3c2c5b49ae59c93ac6f78a2ae354061d7bf0d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="20355-102">使用最佳做法分析程式來掃描您的 Lync Server 2013 部署潛在的問題</span><span class="sxs-lookup"><span data-stu-id="20355-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20355-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="20355-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="20355-104">若要執行 Best Practices Analyzer 掃描，您必須指定下列各項：</span><span class="sxs-lookup"><span data-stu-id="20355-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="20355-105">**認證**   若要執行掃描，您必須登入所使用的帳戶是本機 Administrators 群組的成員，最佳做法分析程式會安裝所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="20355-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="20355-106">此外，當您執行 Best Practices Analyzer 時，用來登入的使用者帳戶需要有執行適當掃描所需的使用者權限，否則，您必須指定具有適當使用者權限的憑證。</span><span class="sxs-lookup"><span data-stu-id="20355-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="20355-107">如需詳細資訊，請參閱[群組成員資格和 Lync Server 2013 中的最佳做法分析程式的使用者權限需求](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)。</span><span class="sxs-lookup"><span data-stu-id="20355-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="20355-108">**掃描的範圍**   掃描的範圍，請選取您想要掃描的伺服器與類別。</span><span class="sxs-lookup"><span data-stu-id="20355-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="20355-109">Lync Server 環境中，您可以選取所有類別，一或多個類別或特定類別中的一或多個伺服器。</span><span class="sxs-lookup"><span data-stu-id="20355-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="20355-110">**掃描類型**   目前健全狀況檢查] 掃描會掃描可用 （選取預設值） 的唯一類型。</span><span class="sxs-lookup"><span data-stu-id="20355-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="20355-111">狀況檢查掃描會產生報告，其中包含範圍中指定之所有伺服器的錯誤、警告和其他資訊。</span><span class="sxs-lookup"><span data-stu-id="20355-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="20355-112">**網路速度**   網路速度選項包括 Fast LAN （100 Mbps 以上），LAN (10 Mbps)，快速 WAN (1.5 Mbps)，或 WAN （64 kbps 為單位）。</span><span class="sxs-lookup"><span data-stu-id="20355-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="20355-113">完成掃描的估計時間取決於此設定。</span><span class="sxs-lookup"><span data-stu-id="20355-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="20355-114">此設定也會用來設定逾時期限。</span><span class="sxs-lookup"><span data-stu-id="20355-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="20355-115">在掃描期間，Best Practices Analyzer 會在指定的時間內等待伺服器回應。</span><span class="sxs-lookup"><span data-stu-id="20355-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="20355-116">如果在指定的逾時期限內未收到回應，就會移到掃描中的下一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="20355-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="20355-117">在比較慢的網路上，這個指定的逾時期限會比較長，以處理較長的網路延遲。</span><span class="sxs-lookup"><span data-stu-id="20355-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="20355-118">建議您為此參數選取拓撲中最慢的連結，這樣該工具才不會太快逾時。</span><span class="sxs-lookup"><span data-stu-id="20355-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="20355-119">掃描 Lync Server 2013 部署</span><span class="sxs-lookup"><span data-stu-id="20355-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="20355-120">使用具有本機系統管理員群組成員身分以及其他必要使用者權限的帳戶，登入已安裝 Best Practices Analyzer 的電腦。</span><span class="sxs-lookup"><span data-stu-id="20355-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="20355-121">按一下 [**開始]**、 指向 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Best Practices Analyzer**。</span><span class="sxs-lookup"><span data-stu-id="20355-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="20355-122">在 [歡迎]\*\*\*\* 畫面上，按一下 [選取相關選項以進行新的掃描]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20355-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="20355-123">在「連線到 Active Directory」\*\*\*\* 頁面上，確認 **Active Directory 伺服器** 中指定的名稱，然後執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="20355-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="20355-124">若要使用您用來登入電腦的憑證執行掃描，請按一下 [連線到 Active Directory 伺服器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20355-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="20355-125">若要指定用於 Active Directory 網域服務、Edge Server 或 Exchange Server 的不同憑證，請按一下 [顯示進階登入選項]\*\*\*\*，選取需要個別憑證的每個核取方塊，為所選取的每個核取方塊指定憑證，然後按一下 [連線到 Active Directory 伺服器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20355-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="20355-p105">在開始掃描之前，Best Practices Analyzer 會執行網路及權限檢查，以確保所指定的帳戶憑證有效，而且 Best Practices Analyzer 可以連線到 Active Directory 網域服務。如果該工具是在工作群組伺服器上執行，也會確認它可以連線到周邊網路中的 Edge Server (如果 Edge Server 包含在掃描中)。</span><span class="sxs-lookup"><span data-stu-id="20355-p105">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services. If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="20355-128">在「啟動新的最佳作法掃描」\*\*\*\* 頁面上，選取您要包含在掃描中的選項，指定網路速度，然後按一下 [開始掃描]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20355-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="20355-129">在「已完成掃描」\*\*\*\* 頁面上，按一下 [檢視此最佳作法掃描的報告]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20355-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="20355-130">在「檢視最佳作法報告」\*\*\*\* 頁面上，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="20355-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="20355-131">若要檢視伺服器元件所組織的報告，請按一下 **[清單報告]**，然後按 **[所有問題]** 索引標籤或 **[參考項目]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="20355-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="20355-132">若要檢視由結果類型所組織成的階層式清單，請按一下 **[樹狀報告]**，然後按 **[詳細檢視]** 索引標籤或 **[摘要檢視]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="20355-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="20355-133">若要檢視其他報告，請按一下 **[其他報告]**。</span><span class="sxs-lookup"><span data-stu-id="20355-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="20355-134">最佳做法分析程式報告和問題的詳細他們識別，請參閱<A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">檢視及 working with Lync Server 2013 中的最佳做法分析程式所建立的報告</A>和<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Lync Server 2013 中的最佳做法分析程式所識別的分析和解決問題</A>。</span><span class="sxs-lookup"><span data-stu-id="20355-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

