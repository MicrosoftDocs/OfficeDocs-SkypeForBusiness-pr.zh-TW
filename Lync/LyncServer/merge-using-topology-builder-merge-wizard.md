---
title: 使用拓撲產生器合併嚮導進行合併
description: 使用拓撲產生器合併嚮導進行合併。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d71a63eef95e3e36802dedfa9fbc1a173d283b65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544559"
---
# <a name="merge-using-topology-builder-merge-wizard"></a>使用拓撲產生器合併嚮導進行合併

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

1.  使用拓撲產生器下載現有的部署。

2.  從 [ **動作** ] 功能表中，選取 [ **合併 Office 通訊伺服器 2007 R2**]。

3.  按 [下一步]****。

4.  在 [指定 Edge 安裝]**** 中，按一下 [新增]****。
    
    ![合併拓撲嚮導的 [指定 Edge 安裝] 頁面](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "合併拓撲嚮導的 [指定 Edge 安裝] 頁面")  

5.  在 [指定 Edge 類型]**** 中，輸入 Edge Server 設定類型，然後按 [下一步]****。 此範例使用 [單一 Edge Server]**** 選項。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>擴充的 Edge 部署</STRONG> 不是支援的設定。 <STRONG>擴充的 Edge server</STRONG>必須先轉換成<STRONG>單一 Edge server</STRONG>或<STRONG>負載平衡的合併 Edge</STRONG> server。

    
    </div>

6.  在 [ **指定內部 Edge 設定** ] 中，視需要輸入您 Edge 集區的內部 FQDN 與埠相關資訊，然後按 **[下一步]**。
    
    ![[指定內部 Edge 設定] 對話方塊](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "[指定內部 Edge 設定] 對話方塊")  

7.  在 [指定外部 Edge]**** 中，為您的 Edge Server 輸入 Web 會議 FQDN 資訊。
    
    <div>
    

    > [!IMPORTANT]  
    > 在您按 [下一步]<STRONG></STRONG> 之前，請先執行本程序的下一個步驟。 請勿錯過此步驟是非常重要的。

    
    </div>

8.  如果您打算使用舊版 Office 通訊伺服器 2007 R2 Edge Server 進行同盟，請選取 [ **此 Edge 集區用於同盟與公用 IM** 連線] 核取方塊。 如果您已部署多部 Edge Server，當中只有一部會啟用同盟功能。 如果您未勾選此方塊，且您稍後決定要啟用同盟，您必須執行拓撲產生器合併嚮導，並再次發佈拓撲。
    
    ![[Edge Server] 對話方塊中的 [指定外部 Edge] 頁面](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "[Edge Server] 對話方塊中的 [指定外部 Edge] 頁面")  

9.  在 [指定下一個躍點]**** 中，輸入您環境中下一個躍點位置的完整網域名稱 (FQDN)。 按一下 **[完成]**。
    
    ![Edge Server 對話方塊，指定下一個躍點頁面](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server 對話方塊，指定下一個躍點頁面")  

10. 在 [ **指定 Edge 設定**] 中，如果已新增所有 Office 通訊伺服器 2007 R2 Edge server，請按 **[下一步]**。 若要新增更多 Office 通訊伺服器 2007 R2 Edge Server，請從步驟4開始，重複此程式。

11. 在 [ **指定內部 SIP 埠** ] 中，選取預設設定 (也就是說，如果您未修改預設 SIP 埠) 。 若您不使用預設連接埠 5061，請視需要變更，然後按 [下一步]****。

12. 在 [摘要]**** 中按 [下一步]****，以開始合併拓撲。

13. 精靈頁面會驗證拓撲的合併是否成功。

14. 在 [狀態]**** 欄位中，檢查其值是否為 [成功]****，然後按一下 [完成]****。

15. 在 [拓撲產生器] 的左窗格中，您現在應該會看到 **BackCompatSite**，這表示您的 Office 通訊伺服器 2007 R2 環境已與 Lync Server 2013 合併。
    
    ![顯示合併拓撲的拓撲產生器](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "顯示合併拓撲的拓撲產生器")  

16. 從 [ **動作** ] 功能表中，按一下 [ **發行拓撲**]，然後按 **[下一步]**。

17. 當 [發行精靈]**** 完成之後，按一下 [完成]****。
    
    <div>
    

    > [!NOTE]  
    > 請務必完成下一個主題：匯 <A href="import-policies-and-settings.md">入原則及設定</A>，以確保將舊版原則設定匯入 Lync Server 2013。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

