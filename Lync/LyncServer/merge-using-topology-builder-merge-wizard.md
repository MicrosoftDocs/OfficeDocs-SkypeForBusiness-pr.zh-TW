---
title: 使用拓撲產生器合併嚮導進行合併
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a65dab8cb99b35821f12c5871ae52f608ae344
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>使用拓撲產生器合併嚮導進行合併

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

1.  使用拓撲建立器下載現有的部署。

2.  從 [**動作**] 功能表中，選取 [**合併 Office 通訊伺服器 2007 R2**]。

3.  按一下 **[下一步]**。

4.  在 [**指定邊緣設定**] 中，按一下 [**新增**]。
    
    [![合併拓撲嚮導]，指定 [邊緣設定] 頁面](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "合併拓撲嚮導，指定 [edge 設定] 頁面")  

5.  在 [**指定邊緣類型**] 中，輸入邊緣伺服器設定的類型，然後按 **[下一步]**。 這個範例使用 [**單一邊緣伺服器**] 選項。
    
    <div>
    

    > [!IMPORTANT]  
    > 已<STRONG>展開的邊緣部署</STRONG>不是受支援的配置。 <STRONG>展開的邊緣伺服器</STRONG>必須先轉換為<STRONG>單一邊緣伺服器</STRONG>或<STRONG>負載平衡的合併邊緣</STRONG>伺服器。

    
    </div>

6.  在 [**指定內部邊緣設定**] 中，視需要輸入邊緣池的內部 FQDN 和埠相關資訊，然後按 **[下一步]**。
    
    [![指定內部邊緣設定] 對話方塊]中的 [(images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "指定內部邊緣設定] 對話方塊")  

7.  在 [**指定外部邊緣**] 中，輸入 Edge 伺服器的網路會議 FQDN 資訊。
    
    <div>
    

    > [!IMPORTANT]  
    > 在您按一下<STRONG>[下一步]</STRONG>之前，請先執行此程式中的下一個步驟。 請務必不要錯過此步驟。

    
    </div>

8.  如果您打算將舊版 Office 通訊伺服器 2007 R2 Edge 伺服器用於同盟，請核取 [**此 Edge 池適用于同盟與公用 IM**連線] 核取方塊。 如果您部署了多個 Edge 伺服器，則只有其中一個是針對同盟啟用。 如果您不選取此方塊，且稍後決定要啟用同盟，您必須執行 [拓撲建立器合併] 嚮導並再次發佈拓撲。
    
    [![邊緣伺服器] 對話方塊中的 [指定外部邊緣頁面](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "邊緣伺服器] 對話方塊中的 [指定外部邊緣] 頁面")  

9.  在 **[指定下一個躍點]** 中，輸入您環境中下一個躍點位置的完整功能變數名稱（FQDN）。 按一下 **[完成]**。
    
    [![邊緣伺服器] 對話方塊中，指定 [下個躍點頁面](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "邊緣伺服器] 對話方塊")  

10. 在 [**指定邊緣設定**] 中，如果已新增所有 Office 通訊伺服器 2007 R2 Edge 伺服器，請按 **[下一步]**。 如果您要新增更多 Office 通訊伺服器 2007 R2 Edge 伺服器，請從步驟4開始重複此程式。

11. 在 [**指定內部 SIP 埠**] 中，選取預設設定（也就是如果您未修改預設的 SIP 埠）。 如果您不是使用預設埠5061，請視需要變更，然後按一下 **[下一步]**。

12. 在 [**摘要**] 中，按一下 **[下一步]** 以開始合併拓撲。

13. [嚮導] 頁面會確認拓撲的合併已成功完成。

14. 在 [**狀態**] 欄中，確認此值為 [**成功**]，然後按一下 **[完成]**。

15. 在 [拓撲建立器] 的左窗格中，您現在應該會看到 [ **BackCompatSite**]，表示您的 Office 通訊伺服器 2007 R2 環境已與 Lync Server 2013 合併。
    
    [拓撲建立器] 顯示已合併![的拓撲]拓撲建立器，(images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "其中顯示已合併的拓撲")  

16. 在 [**動作**] 功能表中，按一下 [**發佈拓撲**]，然後按一下 **[下一步]**。

17. **發佈嚮導**完成後，請按一下 **[完成]**。
    
    <div>
    

    > [!NOTE]  
    > 您必須完成下一個主題、匯<A href="import-policies-and-settings.md">入原則和設定</A>，以確保將舊版原則設定匯入 Lync Server 2013，這一點非常重要。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

