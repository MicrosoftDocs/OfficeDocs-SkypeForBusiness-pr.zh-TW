---
title: Lync Server 2013：從最佳做法分析器查看報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93ce3e013f5c0578c78db3ceee8ab1d65481efbb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>在 Lync Server 2013 中查看最佳做法分析器的報表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

在使用最佳做法分析程式掃描環境的時候，需指定掃描的名稱。一旦最佳做法分析程式完成掃描，就會將掃描結果儲存在報告中以及掃描名稱下方。掃描完成時，您可直接從 **[已完成掃描]** 頁面按一下 **[檢視此最佳作法掃描的報告]** 來檢視掃描所產生的報告，亦可稍後再從該掃描或先前的掃描檢視報告。您可於執行掃描的本機電腦上檢視報告、從其他電腦匯入掃描結果或匯出掃描結果以在已安裝最佳做法分析程式的其他電腦上檢視報告。

掃描結果會以下列報告類型顯示：

  - 清單報告

  - 樹狀報告

  - 其他報告

這些報告包括錯誤、警告及其他資訊。 如需每種報告及問題類型的詳細資訊，請參閱[瞭解 Lync Server 2013 中的最佳做法分析程式所建立的報告](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md)。

使用下列程序檢視最佳做法分析程式先前產生的掃描結果。

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>從先前的掃描檢視報告

1.  使用本機使用者帳戶之成員的帳戶登入已安裝最佳做法分析程式的電腦。
    
    > [!NOTE]  
    > 您可使用本機系統管理員群組成員的帳戶檢視掃描結果，但無法執行掃描，除非您具有適當的使用者權利與權限。 如需詳細資訊，請參閱<A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Lync Server 2013 中的最佳作法分析群組成員資格和使用者權限需求</A>。

2.  按一下 [**開始**]，依序指向 [**所有程式**]、[ **Microsoft Lync Server 2013**]，然後按一下 [**最佳做法分析**程式]。

3.  在 **[歡迎]** 畫面上按一下 **[選取要檢視的掃描結果]**。

4.  在 **[選取要檢視的最佳作法掃描]** 頁面上，執行下列其中一項作業：
    
      - 若要從本機儲存的掃描結果清單檢視報告，請按一下掃描名稱，然後按 **[檢視此掃描的報告]**。
        
        > [!NOTE]  
        > 最佳做法分析程式會從資料夾系統磁片的 [檔] &lt; 和 [ &gt; \\ 設定] \\ &lt; 使用者 &gt; \Application Data\Microsoft\RtcBPA. 中，建立本機檔案的清單
    
      - 若要檢視儲存於其他位置的掃描結果報告，請按一下 **[匯入掃描]**，尋找包含有掃描結果的檔案，然後按 **[開啟]**。
        
        > [!NOTE]  
        > 如果電腦上的最佳做法分析程式版本與已匯入檔案中用於收集資料的版本不相符，檔案匯入之後，電腦上的工具可能會再分析一次。

5.  在 **[檢視最佳作法報告]** 頁面上，執行下列其中一項作業：
    
      - 若要檢視伺服器元件所組織的報告，請按一下 **[清單報告]**，然後按 **[所有問題]** 索引標籤或 **[參考項目]** 索引標籤。
    
      - 若要檢視由結果類型所組織成的階層式清單，請按一下 **[樹狀報告]**，然後按 **[詳細檢視]** 索引標籤或 **[摘要檢視]** 索引標籤。
    
      - 若要檢視其他報告，請按一下 **[其他報告]**。
    
    > [!NOTE]  
    > 如需最佳作法分析報告及其所識別問題的詳細資訊，請參閱<A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">在 lync server 2013 中查看和使用最佳做法分析程式建立的報表</A>，以及<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">分析和解決 lync server 2013 中的最佳做法分析程式所識別的問題</A>。

</div>

</div>

</div>

</div>

</div>

