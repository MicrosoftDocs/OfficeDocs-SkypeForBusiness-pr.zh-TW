---
title: 使用最佳做法分析程式來掃描您的部署，以尋找可能的問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7d881ebc35a4f56207fedaa8533f0a3df3c7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>使用最佳做法分析程式來掃描您的 Lync Server 2013 部署，以尋找可能的問題

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

若要執行最佳做法分析程式掃描，您必須指定下列各項：

  - **認證**   ：若要執行掃描，您必須使用屬於本機管理員群組成員的帳戶登入已安裝最佳做法分析程式的電腦。 此外，您還需要使用具備執行適當的掃描所需之使用者權利和許可權的使用者帳戶登入，或者您在執行最佳做法分析程式時，您必須指定具備適當使用者權利和許可權的認證。 如需詳細資訊，請參閱[Lync Server 2013 中最佳做法分析程式的群組成員資格和使用者權利需求](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)。

  - **掃描範圍：**   若要指定掃描範圍，請選取您要掃描的類別和伺服器。 您可以在 Lync Server 環境的特定類別中，選取所有類別、一或多個類別，或是一或多個伺服器。

  - ****    目前的掃描類型： [健康情況檢查掃描] 是唯一可用的掃描類型（預設為已選取）。 [狀況檢查] 掃描會產生報告，其中包含範圍中指定的所有伺服器的錯誤、警告及其他資訊。

  - **網路速度**   的網路速度選項包括快速局域網（100 mbps 或更多）、局域網（10 Mbps）、快速 WAN （1.5 Mbps），或 WAN （64 kbps）。 完成掃描的估計時間是以這個設定為基礎。 此設定也可用來設定超時期限。 在掃描期間，最佳做法分析程式會等到伺服器回應指定時間為止。 如果它不會在指定的超時期間內接收回應，則會移至掃描中的下一個伺服器。 在較慢的網路上，此指定的超時期間會比對較長的網路延遲時間。 我們建議您選取此參數的拓撲中的最慢連結，以便讓工具不會超時太快。

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>若要掃描 Lync Server 2013 部署

1.  使用本機管理員群組成員的帳戶登入已安裝最佳做法分析程式的電腦，並具有其他必要的使用者權利和許可權。

2.  按一下 [**開始**]，指向 [**所有程式**]，按一下 [ **Microsoft Lync Server 2013**]，然後按一下 [**最佳做法分析工具**]。

3.  在 [**歡迎**] 畫面上，按一下 [**選取新掃描的選項**]。

4.  在 [連線**至 Active Directory]** 頁面上，確認 [ **Active directory Server**] 中指定的名稱，然後執行下列其中一項操作：
    
      - 若要使用您用來登入電腦的認證執行掃描，請按一下 [連線**至 Active Directory 伺服器]**。
    
      - 若要指定您想要用於 Active Directory 網域服務、Edge 伺服器或 Exchange Server 的不同認證，請按一下 [**顯示高級登入選項**]，選取每個需要個別認證的核取方塊，指定每個所選核取方塊的認證，然後按一下 **[連線至 Active Directory 伺服器]**。
    
    <div>
    

    > [!NOTE]
    > 在開始掃描之前，最佳做法分析程式會執行網路和許可權檢查，以確保指定的帳號認證有效，且最佳做法分析程式可以連線至 Active Directory 網域服務。 如果該工具是在工作組伺服器上執行，該工具也會確認它可以連線到周邊網路中的邊緣伺服器（亦即，如果它們包含在掃描中）。

    
    </div>

5.  在 [**開始新的最佳做法掃描**] 頁面上，選取您要包含在掃描中的選項，指定網路速度，然後按一下 [**開始掃描**]。

6.  在 [**掃描已完成**] 頁面上，按一下 [**查看此最佳做法掃描的報告**]。

7.  在 [**查看最佳做法報表**] 頁面上，執行下列其中一項操作：
    
      - 若要在依伺服器元件組織的清單中查看報表，請按一下 [**清單報表**]，然後按一下 [**所有問題**] 索引標籤或 [**資訊性專案**] 索引標籤。
    
      - 若要以依結果類型組織的階層式清單形式來查看報表，請按一下 [**樹狀報表**]，然後按一下 [**詳細視圖**] 索引標籤或 [**摘要視圖**] 索引標籤。
    
      - 若要查看其他報表，請按一下 [**其他報表**]。
    
    <div>
    

    > [!NOTE]
    > 如需最佳做法分析程式報告及其識別問題的詳細資料，請參閱<A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">在 Lync server 2013 中查看和使用最佳做法分析程式所建立的報表</A>，並<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">在 lync Server 2013 中分析及解決最佳做法分析程式所識別的問題</A>。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

