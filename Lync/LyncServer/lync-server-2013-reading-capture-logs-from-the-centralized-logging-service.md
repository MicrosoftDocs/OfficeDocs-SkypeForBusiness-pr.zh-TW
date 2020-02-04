---
title: Lync Server 2013：從集中式記錄服務讀取捕獲記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2713c9a1209aad4a96fcb3a76afaf7c2bc61c0dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>從 Lync Server 2013 中的集中式記錄服務讀取捕獲記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-28_

您可以在執行搜尋之後，充分發揮集中式記錄服務的益處，而且您有一個檔案可用來追蹤已報告的問題。 您可以透過多種方式來讀取檔案。 輸出檔案是標準的文字格式，您可以使用 Notepad.exe 或任何其他能讓您開啟並讀取文字檔的程式。 針對較大的檔案和更複雜的問題，您可以使用類似 Snooper 的工具，該工具是專門用來從集中式記錄服務讀取及分析記錄輸出。 Snooper 隨附于 Lync Server 2013 調試工具中，可做為個別下載。 您可以在此處下載 Lync Server 2013 調試工具： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)。 當您安裝 Lync Server 2013 調試工具時，不會建立簡短的剪下和功能表項目。 安裝 Lync Server 2013 調試工具之後，請開啟 Windows 資源管理器、命令列視窗或 Lync Server 管理命令介面，然後移至目錄（預設位置） C：\\Program Files\\Microsoft Lync Server 2013\\調試工具。 按兩下 Snooper 或輸入 Snooper，然後在您使用命令列或 Lync Server 管理命令介面時，按下 ENTER。

<div>


> [!IMPORTANT]  
> 本主題的目的不是詳細說明並討論疑難排解技巧。 疑難排解及周圍的程式是一種複雜的主題。 如需疑難排解基本功能及特定工作負荷疑難排解的詳細資料，請參閱 Microsoft Lync Server 2010 <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>資源套件活頁簿。 程式和程式也適用于 Lync Server 2013。



</div>

Lync Server 2013 引進了一份更新版本的 Snooper，其中包含一些新功能。 下列螢幕擷取畫面顯示 Office 通訊伺服器2007的 Snooper 版本。

![Office Communications 2007 版 Snooper。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 版 Snooper。")

下列螢幕擷取畫面顯示 Lync Server 2013 調試工具中所包含的新 Snooper 版本。

![Lync Server 2013 版 Snooper。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 版 Snooper。")

下列螢幕擷取畫面顯示工具列，其中包含常用的函數。

![Snooper 2013 工具列。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 工具列。")

而且，新增值的最新功能就是流程圖（[通話流程]）圖表視圖。 您可以在 [**郵件**] 索引標籤中選取郵件流程，然後按一下 [**通話流程**] 按鈕。 當您在郵件中進行時，會使用新的資料來更新通話流程圖表。

![Snooper 2013 通話流程圖。](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 通話流程圖。")

您可以將游標暫留在圖表視圖上，並取得流程與訊息以及伺服器元素的訊息和內容的詳細資料。 按一下任何通話流程箭號，即可移至 [郵件] 視圖中的郵件。

![通話流程圖訊息詳細資料。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "通話流程圖訊息詳細資料。")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>若要在 Snooper 中開啟記錄檔

1.  若要使用 Snooper 及開啟記錄檔，您必須具備記錄檔案的讀取存取權。 若要使用 Snooper 及存取記錄檔，您必須是 CsAdministrator 的成員，或是 CsServerAdministrator 角色的存取控制（RBAC）安全性群組，或是包含這兩個群組中任一群組的自訂 RBAC 角色。

2.  安裝 Lync Server 調試工具（LyncDebugTools）之後，請使用 Windows 資源管理器或從命令列將目錄變更為 Snooper 的位置。 根據預設，調試工具位於 C：\\Program Files\\Microsoft Lync Server 2013\\調試工具中。 按兩下或執行 Snooper。

3.  開啟 Snooper 之後，以滑鼠**按右鍵 [檔案]，按一下**[ **OpenFile**]，尋找您的記錄檔，在 [**開啟**舊檔] 對話方塊中選取檔案，然後按一下 [**開啟**]。

4.  記錄檔的**追蹤**訊息會顯示在 [**追蹤**] 索引標籤上。按一下 [**郵件**] 索引標籤即可查看所收集追蹤的訊息內容。

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>顯示 [通話流程圖] 圖表

1.  若要使用 Snooper 及開啟記錄檔，您必須具備記錄檔案的讀取存取權。 若要使用 Snooper 及存取記錄檔，您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制（RBAC）安全性群組的成員，或是包含這兩個群組的自訂 RBAC 角色。

2.  開啟記錄檔，然後按一下 [**訊息**] 索引標籤，在 [訊息] 視圖中選取交談，或選取 [**追蹤**] 索引標籤上的追蹤元件。

3.  按一下 [**通話流程**]。
    
    <div>
    

    > [!NOTE]  
    > 如果您按一下不屬於通話流程的訊息或追蹤，圖表就不會出現，且 Snooper 底部會出現狀態訊息，指出「此訊息不符合資格，無法 callfow」。 如果郵件或追蹤是通話流程的一部分，請選擇 [其他訊息] 或 [追蹤]，就會顯示通話流程。

    
    </div>

4.  在訊息或追蹤線之間移動，並注意 [通話流程圖] 圖表是否會更新或變更以顯示新圖表。

5.  將游標暫留在元素上，以取得通話訊息、端點及其他元件的相關資訊。

</div>

</div>

<span> </span>

</div>

</div>

</div>

