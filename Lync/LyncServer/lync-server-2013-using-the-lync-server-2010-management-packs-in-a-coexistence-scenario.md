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
ms.openlocfilehash: ffc2aed62b9ad26fd1498787ecd3d58144a005b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>在共存案例中使用 Lync Server 2010 管理套件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

許多客戶採用導入程式順序會逐漸遷移使用者從 Microsoft Lync Server 2010 to Lync Server 2013 企業內的內容。 在這些公司系統管理員將在意監視兩個版本的 Lync Server，以協助確保所有使用者可獲得最可能的通訊體驗。 此案例中，為 Lync Server 2013 管理組件支援與 Lync Server 2010 管理組件的並排顯示移轉路徑。

在 [Lync Server 2010，Lync Server 電腦發現整個拓撲文件儲存與中央管理存放區。 在此組態中，在單一電腦會報告其他所有 Lync Server 電腦的存在。

針對 Lync Server 2013 管理組件現在會使用機器層級探索而不是使用 Lync Server 2010 中的集中探索機制。 這表示每個 System Center 代理程式基本上探索本身，並報告至 System Center Operations Manager 其存在。 使用電腦層級探索簡化管理 System Center 基礎結構和也可讓不同版本的 Lync Server 管理組件 （例如，管理組件的 Lync Server 2010） 和 Lync Server 2013 管理組件若要更輕鬆地共存。

若要支援此移轉，您必須升級監視以避免涵蓋範圍間斷的傷害您現有 Lync Server 2010。 若要這麼做，請選擇現有的 Lync Server 2010 電腦來升級您的中央管理存放區至 Lync Server 2013 之前服務 [Lync Server 2010 的集中探索指令碼。 這是四個步驟的程序：

1.  將 Lync Server 2010 管理組件升級至累計更新 7。

2.  指示 Lync Server 2010 的電腦執行集中探索指令碼。

3.  覆寫的 Microsoft Lync Server 2010 管理組件中的集中探索候選項目。

4.  請確認已探索到新的集中探索候選。

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>指示 Lync Server 2010 電腦執行集中探索指令碼

若要指定非中央管理存放區電腦 （例如，Lync Server 前端） 伺服器來處理集中探索，您必須在非中央管理存放區伺服器上建立下列登錄機碼：

HKLM\\軟體\\Microsoft\\即時通訊\\狀況\\CentralDiscoveryCandidate

您可以建立此登錄機碼，請完成下列程序：

1.  按一下 [開始]****，然後按一下 [執行]****。

2.  在 [執行]**** 對話方塊中，輸入 **regedit**，然後按 ENTER。

3.  在 「 登錄編輯程式中，依序展開 [ **HKEY\_本機\_機器**、 展開**軟體**，依序展開 [ **Microsoft**，，然後展開 [**即時通訊**。

4.  以滑鼠右鍵按一下 [**健康情況**，按一下 [**新增**]，然後按一下 [**機碼**。 如果**健康情況**機碼不存在，然後在**即時通訊**上按一下滑鼠右鍵，指向 [**新增**]，，然後按一下 [**機碼**。 建立新的索引鍵時，輸入健康情況，並按 ENTER。
    
    在建立新的金鑰之後，輸入**CentralDiscoveryCandidate** ，然後按 ENTER 以重新命名機碼。

它可能需要的電腦數小時，要揀選這項變更。 若要變更立即生效，停止，並再重新啟動 Health 代理程式服務。 若要重新啟動 Health 代理程式服務，請完成下列程序在 Lync Server 2010 的電腦上：

1.  按一下 [**開始]**、 [**所有程式]**、 [**附屬應用程式**，以滑鼠右鍵按一下 [**命令提示字元處**，，然後按一下**以管理員身分執行**。

2.  在主控台視窗中輸入下列命令，然後按 ENTER 鍵：
    
        Net stop HealthService

3.  您會看到訊息指出 「 System Center Management] 服務會停止 」 後面接著第二個的訊息，告知您的服務已停止。 服務停止之後，您可以重新啟動它中輸入下列命令並按 ENTER 鍵：
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>覆寫 Lync Server 2010 管理組件中的集中探索候選項目

之後指示 Lync Server 2010 的電腦回報 Lync Server 2010 的電腦上，您必須通知這項變更以及 Lync Server 2010 管理組件。 若要這麼做，您必須在管理組件中建立覆寫。 可以藉由完成下列程序：

1.  在 Operations Manager 主控台中，按一下 [**撰寫**]。

2.  製作索引標籤上，依序展開 [**管理組件物件**，請按一下 [**物件探索**]，和 [**範圍**。

3.  在 [**範圍管理組件物件**] 對話方塊中，選取的項目與目標**LS 探索候選項目**，然後按一下 [**確定]**。 請注意，只有當您已安裝 Lync Server 2010 管理組件，會出現 LS 探索候選項目。

4.  在 Operations Manager 主控台中，以滑鼠右鍵按一下**LS 探索候選項目**，指向 [**覆寫**，並指向 [**覆寫物件探索**，然後按一下 [**類別的所有物件： LS 探索候選項目**。

5.  在 [**覆寫內容**] 對話方塊中，選取參數**集中探索 WatcherNode Fqdn**旁的 [**覆寫**] 核取方塊。 在 [**覆寫值**和**有效的值**] 方塊中輸入的 Lync Server 2010 電腦的完整的網域名稱。 選取 [**強制**] 核取方塊，然後按一下 [**確定]**。

您已建立覆寫之後，您需要重新啟動 Root Management Server 上的健全狀況服務。 若要重新啟動的健全狀況服務，請完成下列程序 Root Management Server 上：

1.  按一下 [**開始]**、 [**所有程式]**、 [**附屬應用程式**，以滑鼠右鍵按一下 [**命令提示字元處**，，然後按一下**以管理員身分執行**。

2.  在主控台視窗中，輸入下列命令，並按 ENTER:
    
        Net stop HealthService

3.  您會看到訊息，表示，「 System Center Management] 服務已停止 」，後面加上第二個的訊息，告知您的服務已停止。 服務停止之後，您可以再重新啟動它中輸入下列命令並按 ENTER 鍵：
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>確認已探索到新的集中探索候選項目

再升級中央管理存放區的最後一個步驟是確認 Lync Server 2010 管理組件已探索到新的集中探索候選項目。 若要這麼做，開啟 Operations Manager 主控台中，然後按一下 [監視]。 在 [監視] 索引標籤上依序展開 [ **Microsoft Lync Server 2010 狀況**、 展開**拓撲搜索**，，然後按一下**探索狀態檢視**。 確認中顯示的資料列有列出集中探索候選項目的完整的網域名稱的**路徑**。 您也應確認電腦狀態被回報為**狀況良好**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

