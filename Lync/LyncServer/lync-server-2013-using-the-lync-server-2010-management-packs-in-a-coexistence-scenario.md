---
title: 在共存案例中使用 Lync Server 2010 管理套件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb614726458f2cf9c77bdfe740ddb13d99d54f2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529920"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>在共存案例中使用 Lync Server 2010 管理套件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

許多客戶在其企業中採用推廣計畫，讓使用者從 Microsoft Lync Server 2010 逐步遷移至 Lync Server 2013。 這些公司的系統管理員會關心監控這兩種版本的 Lync Server，以協助確保他們的所有使用者都能取得最佳的通訊體驗。 在此案例中，Lync Server 2013 管理元件支援使用 Lync Server 2010 管理元件的並列遷移路徑。

在 Lync Server 2010 中，透過隨中央管理存放區儲存的拓撲檔來探索 Lync Server 電腦。 在此設定中，一部電腦會報告所有其他 Lync Server 電腦是否存在。

Lync Server 2013 的管理元件現在使用電腦層級探索，而不是 Lync Server 2010 中所用的中央探索機制。 這表示每個 System Center agent 實質上會自行探索，並向 System Center Operations Manager 報告其存在性。 使用電腦層級探索可簡化系統中心基礎結構的管理，也會啟用不同版本的 Lync Server 管理套件 (例如，lync Server 2010 的管理套件和 Lync Server 2013 的管理元件) ，都能更輕鬆地相互共存。

若要支援此遷移，您必須先升級現有的 Lync Server 2010 監控，以避免覆蓋範圍的缺口。 若要這麼做，請選擇現有的 Lync Server 2010 電腦，以在將中央管理存放區升級至 Lync Server 2013 之前，先為 Lync Server 2010 服務中央探索腳本。 這是四個步驟的處理常式：

1.  將 Lync Server 2010 管理元件升級為累計更新7。

2.  指示 Lync Server 2010 電腦執行中央探索腳本。

3.  覆寫 Microsoft Lync Server 2010 管理元件中的「集中探索候選人」。

4.  確認已探索到新的集中探索候選項目。

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>指示 Lync Server 2010 電腦執行中央探索腳本

若要提名非中央管理存放區電腦 (例如，Lync Server 前端) 伺服器處理中央探索，您必須在非中央管理存放區伺服器上建立下列登錄機碼：

HKLM \\ 軟體 \\ Microsoft \\ 即時通訊 \\ 健康情況 \\ CentralDiscoveryCandidate

您可以完成下列程式來建立此登錄機碼：

1.  按一下 [開始]****，然後按一下 [執行]****。

2.  在 [執行]**** 對話方塊中，輸入 **regedit**，然後按 ENTER。

3.  在 [登錄編輯程式] 中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **軟體**]，展開 [ **Microsoft**]，然後展開 [ **即時通訊**]。

4.  以滑鼠右鍵按一下 [ **健全**]，按一下 [ **新增**]，然後按一下 [機 **碼**]。 如果 **狀況** 機碼不存在，請以滑鼠右鍵按一下 [ **即時通訊**]，指向 [ **新增**]，然後按一下 [機 **碼**]。 建立新金鑰時，輸入 Health，然後按 ENTER 鍵。
    
    建立新機碼之後，輸入 **CentralDiscoveryCandidate** ，然後按 enter 重新命名機碼。

這可能需要數小時的時間來挑選此項變更。 若要讓變更立即生效，請停止狀況代理程式服務，然後再重新開機。 若要重新開機狀況代理程式服務，請在 Lync Server 2010 電腦上完成下列程式：

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **附屬設施**]、[ **命令提示**字元] 及 [以 **系統管理員身分執行**]。

2.  在主控台視窗中輸入下列命令，然後按 ENTER 鍵：
    
        Net stop HealthService

3.  您會看到一則訊息，指出「System Center Management service 即將停止」，接著還有第二封訊息，告知您已停止服務。 服務停止後，您可以輸入下列命令，然後按 ENTER，以重新開機它：
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>覆寫 Lync Server 2010 管理元件中的集中探索候選人

在指示 Lync Server 2010 電腦在 Lync Server 2010 電腦上報告之後，您也需要通知 Lync Server 2010 管理元件有關此變更的相關資訊。 若要這麼做，您將需要在管理元件中建立覆寫。 若要完成，請完成下列程式：

1.  在 Operations Manager 主控台中，按一下 [ **製作**]。

2.  在 [製作] 索引標籤上，展開 [ **管理元件物件**]，按一下 [ **物件發現**]，然後按一下 [ **範圍**]。

3.  在 [ **範圍管理元件物件** ] 對話方塊中，選取具有目標 **LS 探索候選** 專案的專案，然後按一下 **[確定]**。 請注意，只有在您已安裝 Lync Server 2010 管理元件時，才會顯示 LS 探索候選人。

4.  在 Operations Manager 主控台中，以滑鼠右鍵按一下 [ **LS 探索候選人**]，指向 [ **覆寫**]，指向 **[覆寫物件探索**]，然後按一下 [ **類別的所有物件： LS 探索候選**專案]。

5.  在 [覆**寫屬性**] 對話方塊中，選取 [參數**中央探索 WatcherNode Fqdn**] 旁邊的 [覆**寫**] 核取方塊。 在 [覆 **寫值** ] 和 [ **有效值** ] 方塊中，輸入 Lync Server 2010 電腦的完整功能變數名稱。 選取 [ **強制執行** ] 核取方塊，然後按一下 **[確定]**。

建立覆寫後，您必須重新開機根管理伺服器上的健康情況服務。 若要重新開機狀況服務，請在根管理伺服器上完成下列程式：

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **附屬設施**]、[ **命令提示**字元] 及 [以 **系統管理員身分執行**]。

2.  在主控台視窗中，輸入下列命令，然後按 ENTER：
    
        Net stop HealthService

3.  您會看到一則訊息，說明「System Center Management service 即將停止」，接著還有第二封訊息，告知您已停止服務。 服務停止後，您可以輸入下列命令並按 ENTER 鍵，以重新開機它：
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>確認已發現新的集中探索候選項目

升級中央管理存放區的最後一個步驟是，確定 Lync Server 2010 管理元件已探索到新的集中探索候選項目。 若要這麼做，請開啟 Operations Manager 主控台，然後按一下 [監視]。 在 [監視] 索引標籤上，展開 [ **Microsoft Lync Server 2010 Health**]，展開 [ **拓撲探索**]，然後按一下 [ **探索狀態視圖**]。 驗證顯示中的列是否有列出集中式探索候選人之完整功能變數名稱的 **路徑** 。 您也應該確認電腦狀態已報告為 **狀況良好**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

