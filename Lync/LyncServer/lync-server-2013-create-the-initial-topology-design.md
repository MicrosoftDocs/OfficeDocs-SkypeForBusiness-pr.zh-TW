---
title: Lync Server 2013：建立初始拓撲設計
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc8d3e731c2772b275dd861c41b8c10f2127a2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>建立 Lync Server 2013 的初始拓撲設計

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在您完成安裝 Lync Server 2013、計畫工具之後，您就可以開始規劃工具並開始設計建議的 Lync Server 2013 基礎結構。

<div>


> [!NOTE]  
> 規劃工具是一個由嚮導驅動的工具，其中包含詳細指南，可在您的網站和拓撲中通知決策過程。 本主題不是完整的指南，只是為了協助您在設計會話中開始使用規劃工具。



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>開始使用規劃工具並建立初始設計

1.  啟動 Lync Server 2013，規劃工具：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync Server 2013**]，然後按一下 [**規劃工具**]。

2.  開始規劃工具之後，就會出現 [**歡迎使用 Microsoft Lync Server 2013 規劃工具**] 頁面。 選擇下列其中一個選項開始進行設計：
    
      - **選項1：快速入門**   按一下 **[開始使用**] 提供特定系列的面試問題，以及相關選擇以定義準則。 完成初始 [**開始**進行訪談] 區段後，請繼續進行**設計網站**，以定義您的網站架構。 若要完成此選項，請繼續執行步驟3。
    
      - **選項2： [設計網站**   ] 按一下 [歡迎] 頁面上的 [**設計網站**]，即可避開 [**開始**使用] 區段中提供的訪談問題。 若要在 [**開始**使用] 區段中以回復面試問題所收集的資訊，請使用此選項設定為 [預設值]。 只要按一下 [**設計網站**]，經驗豐富的設計工具就能在 [**中央網站**開始] 頁面上略過初始面試，並視需要變更預設值。 若要完成此選項，請跳過步驟3-5，然後從步驟6開始。
    
      - **選項3：**   如果您已透過舊版規劃工具完成並儲存拓撲，就會顯示您已儲存的拓撲，您可以略過這些步驟，然後開啟並顯示拓撲。 您也可以對拓撲進行變更與更新、重新儲存，然後將其匯出至 Microsoft Excel 或 Microsoft Visio。 若要完成此選項，請跳過步驟3-12，然後從步驟13開始。

3.  按一下 [**開始**使用]，開始設計 Lync Server 2013 拓撲。

4.  針對您的設計選取適當的準則，然後按一下 **[下一步**] 以繼續進行下一個嚮導頁面，以回答每個區段。 按一下 [**返回**]，在前一頁上進行變更。
    
    <div>
    

    > [!TIP]  
    > 每個頁面都有選取準則的描述，以及根據最佳做法和容量規劃的建議。 如果您需要更多詳細資料，請按一下 [<STRONG>深入瞭解</STRONG>]，以閱讀 Microsoft TechNet 網站上的 Lync Server 2013 規劃檔中的詳細資訊。 您必須具備網際網路連線才能存取 Microsoft TechNet 網站。

    
    </div>

5.  針對您的設計選取適當的選項。 定義初始準則之後，頁面將會確認您的功能概述已完成。

6.  按一下 [**設計網站**] 來定義您的中心網站。
    
    <div>
    

    > [!NOTE]  
    > 每個 Lync Server 2013 拓撲都至少有一個中心網站。 您的設計可能有單一的中央網站、包含多個分支網站的中央網站、多個中央網站，或與每個中央網站相關聯之分支網站的多個中心網站。

    
    </div>

7.  在 [**網站名稱**] 中，輸入要用來識別此中心網站的名稱。

8.  在 [**網站穴使用者**] 中，輸入將駐留在這個中心網站的內部部署併發使用者數。

9.  在**雲端穴使用者**中，輸入將駐留在這個中央網站的預期線上併發使用者數目。

10. 視需要修改線上共同作業、使用者、語音、其他部署選項或伺服器應用程式的選項。
    
    <div>
    

    > [!IMPORTANT]  
    > 在設計中的這個階段，您只能選取或清除部署的選項。 不過，您可以在規劃工具的後續階段中設定更多選項。 還有無法使用且無法清除的選項。 此外，您可能必須清除其中一個選項，才能清除另一個選項。 例如，如果您清除 [語音] 底下的 [<STRONG>企業語音</STRONG>] 選項，則會同時清除 [伺服器應用程式] （所有都是企業語音功能）底下的 [<STRONG>回應] 群組</STRONG>、[<STRONG>宣告</STRONG>] 和 [<STRONG>通話駐留</STRONG>] 選項。

    
    </div>

11. 定義網站名稱和使用者數量之後，請按 **[下一步]**。

12. 下列頁面會詢問有關 SIP 網域、會議設定、語音設定和基礎結構、Exchange UM、外部使用者存取、持續聊天設定、客戶設定、collocation 選項和分支網站的相關資訊。 請視需要回答這些問題。

13. 最後一個問題會詢問您是否要建立另一個中心網站。 如果您選取 **[是]**，則規劃工具會回到 [中央網站] 頁面。 如果您選取 [**否**]，請按 **[下一步]**，然後按一下 [**繪圖**] 以顯示 [高層次] 全域拓撲圖視圖。

14. 若要查看現有的拓撲，請按一下 [**顯示**]。

15. 按一下代表先前儲存拓撲的 .xml 檔案，然後按一下 [**開啟**]。

16. 規劃工具會顯示 [全域拓撲] 頁面。 您現在可以使用規劃工具中提供的工具開始編輯、更新或變更拓撲。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中編輯設計](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

