---
title: Lync Server 2013：查看最佳做法分析工具的報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2c229d683ecd0dcf4fee94b456514527226152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>在 Lync Server 2013 中查看最佳做法分析程式的報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

當您使用最佳做法分析程式來掃描您的環境時，請指定掃描的名稱。 在最佳做法分析程式完成掃描之後，它會將掃描結果儲存在報告中，並將其儲存在掃描的名稱底下。 完成掃描之後，您可以按一下 [直接從 [**掃描已完成**] 頁面上的 [**查看此最佳做法的報告**] 來查看為該掃描產生的報告。 您也可以稍後從該掃描或前一次掃描中查看報告。 您可以在執行掃描的本機電腦上，查看報告、匯入另一部電腦的掃描結果，或匯出掃描結果，以在安裝了最佳做法分析程式的另一部電腦上查看報告。

掃描結果會顯示在下列類型的報告中：

  - 清單報表

  - 樹狀報表

  - 其他報表

這些報表包括錯誤、警告及其他資訊。 如需這些報表與問題的詳細資料，請參閱[瞭解 Lync Server 2013 中由最佳做法分析工具所建立的報表](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md)。

使用下列程式來查看先前由最佳做法分析工具產生的掃描結果。

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>若要從先前的掃描中查看報表

1.  使用本機使用者帳戶成員的帳戶登入已安裝最佳做法分析程式的電腦。
    
    > [!NOTE]  
    > 您可以使用本機管理員群組成員的帳戶來查看掃描結果，但除非您有適當的使用者權利和許可權，否則您無法執行掃描。 如需詳細資訊，請參閱<A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Lync Server 2013 中最佳做法分析程式的群組成員資格和使用者權利需求</A>。

2.  按一下 [**開始**]，指向 [**所有程式**]，按一下 [ **Microsoft Lync Server 2013**]，然後按一下 [**最佳做法分析工具**]。

3.  在 [**歡迎**] 畫面上，按一下 **[選取要查看的掃描結果**]。

4.  在 [**選取最佳做法掃描至視圖**] 頁面上，執行下列其中一項操作：
    
      - 若要從本機儲存的掃描結果清單中查看報告，請按一下掃描的名稱，然後按一下 [**查看此掃描的報告**]。
        
        > [!NOTE]  
        > 最佳做法分析&lt;工具會從資料夾 systemDrive&gt;\\檔和設定\\&lt;使用者&gt;\Application Data\Microsoft\RtcBPA. 建立本機檔案清單
    
      - 若要查看儲存在其他位置之掃描結果的報告，請按一下 [匯**入掃描**]，找出包含掃描結果的檔案，然後按一下 [**開啟**]。
        
        > [!NOTE]  
        > 如果這台電腦上的最佳做法分析程式版本不符合收集檔案資料所用的版本，則在匯入後，電腦上的工具可能會再次分析檔案。

5.  在 [**查看最佳做法報表**] 頁面上，執行下列其中一項操作：
    
      - 若要在依伺服器元件組織的清單中查看報表，請按一下 [**清單報表**]，然後按一下 [**所有問題**] 索引標籤或 [**資訊性專案**] 索引標籤。
    
      - 若要以依結果類型組織的階層式清單形式來查看報表，請按一下 [**樹狀報表**]，然後按一下 [**詳細視圖**] 索引標籤或 [**摘要視圖**] 索引標籤。
    
      - 若要查看其他報表，請按一下 [**其他報表**]。
    
    > [!NOTE]  
    > 如需最佳做法分析程式報告以及其所識別問題的詳細資料，請參閱<A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">在 Lync server 2013 中查看和使用最佳做法分析程式所建立的報表</A>，並<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">在 lync Server 2013 中分析及解決最佳做法分析工具所識別的問題</A>。

</div>

</div>

</div>

</div>

</div>

