---
title: Lync Server 2013：從集中式記錄服務讀取捕獲記錄檔
description: Lync Server 2013：從集中式記錄服務讀取捕獲記錄檔。
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
ms.openlocfilehash: fcdd70c924b49098814e80a375ae34d2bf48dc41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559159"
---
# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中讀取集中式記錄服務的捕獲記錄檔

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-28_

在您執行搜尋後，您就可以充分利用集中式記錄服務，您可以用來追蹤已報告問題的檔案。 您可以使用許多方式來讀取檔案。 輸出檔是標準的文字格式，您可以使用 Notepad.exe 或任何其他可讓您開啟及讀取文字檔的程式。 針對較大的檔案和更複雜的問題，您可以使用類似 Snooper.exe 的工具，以用於讀取及分析集中式記錄服務的記錄輸出。 Snooper 隨附的 Lync Server 2013 調試工具，可做為個別下載。 您可以在以下位置下載 Lync Server 2013 調試工具： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) 。 當您安裝 Lync Server 2013 調試工具時，不會建立簡短的剪下及功能表項目目。 安裝 Lync Server 2013 調試工具後，請開啟 Windows Explorer、命令列視窗或 Lync Server 管理命令介面，然後移至目錄 (預設位置) C： \\ Program Files \\ Microsoft Lync Server 2013 \\ 調試工具。 在 [Snooper.exe] 或 [輸入 Snooper.exe] 中按兩下，如果使用命令列或 Lync Server 管理命令介面，請按 ENTER 鍵。

<div>


> [!IMPORTANT]  
> 本主題的目的不是詳細討論和討論疑難排解技術。 疑難排解及其周圍的程式是複雜的主體。 如需疑難排解基本及疑難排解特定工作負載的詳細資訊，請參閱《 Microsoft Lync Server 2010 Resource 工具組手冊》 <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A> 。 處理常式和程式仍適用于 Lync Server 2013。



</div>

Lync Server 2013 引進 Snooper 的更新版本，包含一些新功能。 下列螢幕擷取畫面顯示 Office 通訊伺服器2007的 Snooper 版本。

![Office 通訊2007版本的 Snooper。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office 通訊2007版本的 Snooper。")

下列螢幕擷取畫面顯示 Lync Server 2013 調試工具中所包含的新 Snooper 版本。

![Lync Server 2013 版本的 Snooper。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 版本的 Snooper。")

下列螢幕擷取畫面顯示工具列使用常用的功能。

![Snooper 2013 工具列。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 工具列。")

而且，新增值的最新功能是流程圖表 (的通話流程) 圖表] 視圖。 您可以選取 [ **郵件** ] 索引標籤中的郵件流程，然後按一下 [ **通話流程** ] 按鈕。 當您繼續進行郵件時，通話流程圖表會以新的資料進行更新。

![Snooper 2013 通話流程圖表。](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 通話流程圖表。")

您可以將游標移到圖表視圖上方，並取得流程和郵件以及伺服器元素的訊息和內容的詳細資料。 按一下任何呼叫流程箭號，以移至郵件視圖中的郵件。

![通話流程圖表郵件詳細資料。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "通話流程圖表郵件詳細資料。")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>若要在 Snooper 中開啟記錄檔

1.  若要使用 Snooper 及開啟記錄檔，您需要有記錄檔的讀取權。 若要使用 Snooper 和存取記錄檔，您必須是 CsAdministrator 的成員或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組，或是包含這兩個群組的自訂 RBAC 角色。

2.  安裝 Lync Server 調試工具 ( # A0) 後，請使用 Windows Explorer 或命令列變更目錄至 Snooper.exe 的位置。 根據預設，調試工具位於 C： \\ Program Files \\ Microsoft Lync Server 2013 \\ 調試工具中。 按兩下或執行 Snooper.exe。

3.  開啟 Snooper 後，以滑鼠 **按右鍵 [檔案]，按一下**[ **OpenFile**]，尋找您的記錄檔，選取 [ **開啟** ] 對話方塊中的檔案，然後按一下 [ **開啟**]。

4.  記錄檔的 **追蹤** 訊息會顯示在 [ **追蹤** ] 索引標籤上。按一下 [ **訊息** ] 索引標籤，以查看收集之追蹤的郵件內容。

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>顯示通話流程圖表

1.  若要使用 Snooper 及開啟記錄檔，您需要有記錄檔的讀取權。 若要使用 Snooper 並存取記錄檔，您必須是 CsAdministrator 的成員或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組，或是包含這兩個群組的自訂 RBAC 角色。

2.  開啟記錄檔，然後按一下 [ **訊息** ] 索引標籤，在 [ **追蹤** ] 索引標籤上選取 [交談]，或選取一個追蹤元件。

3.  按一下 [ **通話流程**]。
    
    <div>
    

    > [!NOTE]  
    > 如果您按一下的訊息或追蹤不是通話流程的一部分，將不會顯示圖表，而且會在 Snooper 的底部顯示狀態訊息，指出「這封郵件不符合 callfow」。 選擇 [另一封郵件] 或 [追蹤]，如果郵件或追蹤屬於通話流程的一部分，就會顯示通話流程。

    
    </div>

4.  在訊息或追蹤列間移動，並附注通話流程圖表是否更新或變更，以顯示新的圖表。

5.  將游標移到元素上，以取得通話訊息、端點及其他元件的相關資訊。

</div>

</div>

<span> </span>

</div>

</div>

</div>

