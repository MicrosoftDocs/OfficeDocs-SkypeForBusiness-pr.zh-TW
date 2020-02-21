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
ms.openlocfilehash: f620712404fffe8e46f8f2a6f066c6ffa7b77d74
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>使用最佳做法分析程式來掃描您的 Lync Server 2013 部署潛在的問題

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-21_

若要執行 Best Practices Analyzer 掃描，您必須指定下列各項：

  - **認證**   若要執行掃描，您必須登入所使用的帳戶是本機 Administrators 群組的成員，最佳做法分析程式會安裝所在的電腦。 此外，當您執行 Best Practices Analyzer 時，用來登入的使用者帳戶需要有執行適當掃描所需的使用者權限，否則，您必須指定具有適當使用者權限的憑證。 如需詳細資訊，請參閱[群組成員資格和 Lync Server 2013 中的最佳做法分析程式的使用者權限需求](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)。

  - **掃描的範圍**   掃描的範圍，請選取您想要掃描的伺服器與類別。 Lync Server 環境中，您可以選取所有類別，一或多個類別或特定類別中的一或多個伺服器。

  - **掃描類型**   目前健全狀況檢查] 掃描會掃描可用 （選取預設值） 的唯一類型。 狀況檢查掃描會產生報告，其中包含範圍中指定之所有伺服器的錯誤、警告和其他資訊。

  - **網路速度**   網路速度選項包括 Fast LAN （100 Mbps 以上），LAN (10 Mbps)，快速 WAN (1.5 Mbps)，或 WAN （64 kbps 為單位）。 完成掃描的估計時間取決於此設定。 此設定也會用來設定逾時期限。 在掃描期間，Best Practices Analyzer 會在指定的時間內等待伺服器回應。 如果在指定的逾時期限內未收到回應，就會移到掃描中的下一部伺服器。 在比較慢的網路上，這個指定的逾時期限會比較長，以處理較長的網路延遲。 建議您為此參數選取拓撲中最慢的連結，這樣該工具才不會太快逾時。

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>掃描 Lync Server 2013 部署

1.  使用具有本機系統管理員群組成員身分以及其他必要使用者權限的帳戶，登入已安裝 Best Practices Analyzer 的電腦。

2.  按一下 [**開始]**、 指向 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Best Practices Analyzer**。

3.  在 [歡迎]**** 畫面上，按一下 [選取相關選項以進行新的掃描]****。

4.  在「連線到 Active Directory」**** 頁面上，確認 **Active Directory 伺服器** 中指定的名稱，然後執行下列其中一項：
    
      - 若要使用您用來登入電腦的憑證執行掃描，請按一下 [連線到 Active Directory 伺服器]****。
    
      - 若要指定用於 Active Directory 網域服務、Edge Server 或 Exchange Server 的不同憑證，請按一下 [顯示進階登入選項]****，選取需要個別憑證的每個核取方塊，為所選取的每個核取方塊指定憑證，然後按一下 [連線到 Active Directory 伺服器]****。
    
    <div>
    

    > [!NOTE]
    > 在開始掃描之前，Best Practices Analyzer 會執行網路及權限檢查，以確保所指定的帳戶憑證有效，而且 Best Practices Analyzer 可以連線到 Active Directory 網域服務。如果該工具是在工作群組伺服器上執行，也會確認它可以連線到周邊網路中的 Edge Server (如果 Edge Server 包含在掃描中)。

    
    </div>

5.  在「啟動新的最佳作法掃描」**** 頁面上，選取您要包含在掃描中的選項，指定網路速度，然後按一下 [開始掃描]****。

6.  在「已完成掃描」**** 頁面上，按一下 [檢視此最佳作法掃描的報告]****。

7.  在「檢視最佳作法報告」**** 頁面上，執行下列其中一項：
    
      - 若要檢視伺服器元件所組織的報告，請按一下 **[清單報告]**，然後按 **[所有問題]** 索引標籤或 **[參考項目]** 索引標籤。
    
      - 若要檢視由結果類型所組織成的階層式清單，請按一下 **[樹狀報告]**，然後按 **[詳細檢視]** 索引標籤或 **[摘要檢視]** 索引標籤。
    
      - 若要檢視其他報告，請按一下 **[其他報告]**。
    
    <div>
    

    > [!NOTE]
    > 最佳做法分析程式報告和問題的詳細他們識別，請參閱<A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">檢視及 working with Lync Server 2013 中的最佳做法分析程式所建立的報告</A>和<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Lync Server 2013 中的最佳做法分析程式所識別的分析和解決問題</A>。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

