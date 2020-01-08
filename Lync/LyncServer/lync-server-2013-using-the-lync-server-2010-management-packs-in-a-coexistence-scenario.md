---
title: 在共存案例中使用 Lync Server 2010 管理套件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>在共存案例中使用 Lync Server 2010 管理套件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

許多客戶在其企業中採用推出方案，這些使用者會從 Microsoft Lync Server 2010 逐步遷移至 Lync Server 2013。 這些公司的系統管理員會關心監視兩個版本的 Lync Server，以協助確保他們的所有使用者都能獲得最佳的通訊體驗。 在這種情況下，Lync Server 2013 管理套件支援與 Lync Server 2010 管理套件進行並排遷移路徑。

在 Lync Server 2010 中，Lync Server 電腦是透過中央管理存放區所儲存的拓撲檔來探索。 在這個設定中，單一電腦會報告所有其他 Lync Server 電腦是否存在。

Lync Server 2013 的管理套件現在使用電腦層級探索，而不是在 Lync Server 2010 中使用的中央探索機制。 這表示每個系統中心代理程式都本質上探索自己，並將它的存在性報告給 System Center 運營系統管理員。 使用電腦層級探索可簡化系統中心基礎結構的管理，同時也會啟用不同版本的 Lync Server 管理套件（例如，Lync Server 2010 的管理套件和 Lync Server 2013 的管理套件）更容易地共存。

若要支援這項遷移，您必須先升級現有的 Lync Server 2010 監視，以避免覆蓋範圍中的差距。 若要這樣做，請選擇現有的 Lync Server 2010 電腦，在將您的中央管理儲存在 Lync Server 2013 升級前，為 Lync Server 2010 提供中央探索腳本服務。 這是四個步驟的程式：

1.  將 Lync Server 2010 管理套件升級為累積更新7。

2.  指示 Lync Server 2010 電腦執行中央探索腳本。

3.  覆寫 Microsoft Lync Server 2010 管理套件中的 [集中搜尋候選]。

4.  確認已探索新的中央探索候選方案。

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>指示 Lync Server 2010 電腦執行中央探索腳本

若要提名非集中式管理商店電腦（例如，Lync Server 前端伺服器）來處理中央探索，您必須在非中央管理儲存伺服器上建立下列登錄機碼：

HKLM\\\軟體\\Microsoft\\即時通訊\\健康情況\\CentralDiscoveryCandidate

您可以透過完成下列程式來建立此登錄機碼：

1.  按一下 [**開始**]，然後按一下 [**執行**]。

2.  在 [**執行**] 對話方塊中，輸入**regedit** ，然後按 enter。

3.  在 [登錄編輯程式] 中，展開 [ ** \_HKEY 本機\_電腦**]、展開 [**軟體**]、[ **Microsoft**]，然後展開 [**即時通訊**]。

4.  以滑鼠右鍵按一下 [**健康情況**]，按一下 [**新增**]，然後按一下 [**金鑰**]。 如果**健康**時間金鑰不存在，請以滑鼠右鍵按一下 [**即時通訊**]，指向 [**新增**]，然後按一下 [**金鑰**]。 建立新的金鑰後，請輸入 Health，然後按 ENTER。
    
    建立新的金鑰之後，請輸入**CentralDiscoveryCandidate** ，然後按 enter 鍵來重新命名金鑰。

可能需要幾個小時的時間，才能取得這項變更。 若要讓變更立即生效，請停止並重新啟動 Health 代理服務。 若要重新開機 Health 代理程式服務，請在 Lync Server 2010 電腦上完成下列程式：

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]

2.  在主控台視窗中，輸入下列命令，然後按 ENTER：
    
        Net stop HealthService

3.  您會看到一則訊息，指出「System Center 管理服務即將停止」，後面接著第二個訊息，告訴您該服務已停止。 停止服務之後，您可以輸入下列命令，然後按 ENTER 來重新開機它：
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>覆寫 Lync Server 2010 管理套件中的中央探索候選人

指示 Lync Server 2010 電腦在 Lync Server 2010 電腦上報告之後，您必須通知 Lync Server 2010 管理套件與此變更。 若要這樣做，您將需要在管理套件中建立覆寫。 完成下列程式，即可完成作業：

1.  在 Operations Manager 主控台中，按一下 [**撰寫**]。

2.  在 [撰寫] 索引標籤上，展開 [**管理套件物件**]，按一下 [**物件發現**]，然後按一下 [**範圍**]。

3.  在 [**範圍管理套件物件**] 對話方塊中，選取具有目標 LS [**探索候選**] 的專案，然後按一下 **[確定]**。 請注意，只有當您已安裝 Lync Server 2010 管理套件時，才會出現 LS 搜尋候選版本。

4.  在 Operations Manager 主控台中，以滑鼠右鍵按一下**LS [探索候選人**]，指向 [**覆寫**]，指向 [覆**寫物件探索**]，然後按一下 [**所有類別的物件： LS 探索候選**專案]。

5.  在 [ **Override 屬性**] 對話方塊中，選取參數 [**中央探索 WatcherNode Fqdn**] 旁的 [**覆蓋**] 核取方塊。 在 [**取代值**] 和 [**生效值**] 方塊中，輸入 Lync Server 2010 電腦的完整功能變數名稱。 選取 [**強制**] 核取方塊，然後按一下 **[確定]**。

在您建立覆蓋之後，您必須重新開機根管理伺服器上的健康情況服務。 若要重新開機健康情況服務，請在根管理伺服器上完成下列程式：

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]

2.  在主控台視窗中，輸入下列命令，然後按 ENTER：
    
        Net stop HealthService

3.  您會看到一則訊息，指出「系統中心管理服務即將停止」，後面接著第二個訊息，告訴您該服務已停止。 停止服務之後，您可以輸入下列命令，然後按 ENTER 來重新開機它：
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>確認已發現新的中央探索候選人

升級「中央管理儲存區」前的最後一個步驟是，確定 Lync Server 2010 管理套件發現了新的中央探索候選版本。 若要這樣做，請開啟 Operations Manager 主控台，然後按一下 [監視]。 在 [監視] 索引標籤上，展開 [ **Microsoft Lync Server 2010 健康情況**]，展開 [**拓撲探索**]，然後按一下 [**探索狀態視圖**]。 確認顯示中的列有一個**路徑**，其中列出「集中搜尋候選字」的完整功能變數名稱。 您也應該確認電腦狀態報表為**健康情況**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

